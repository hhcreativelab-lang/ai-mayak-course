# AI for email: a smarter inbox, drafts and replies

**Time:** about 20 min reading + 30 min practice

---

## The gist

Professionals spend a noticeable chunk of the workday on email (check your own time tracker if you use one). It isn't because there are so many emails. It's because every email makes you think: what to reply, how to phrase it, how not to forget it. Claude takes over that thinking. You stay the one making the decisions.

This isn't "AI instead of you." It's AI as a filter and a first draft. You still click "Send." You just spend a fraction of the time getting there.

🎨 **Picture this:** an AI email assistant is like the White House press secretary. The President doesn't write every answer personally. The press secretary knows the President's positions and style, knows what the President would never say, and prepares the text. The President reads it, changes a couple of words and signs off. The power and the decisions stay with the President; what gets freed up is time.

---

## Key concepts

- **Gmail MCP**: Claude reads your inbox, sorts your emails and writes draft replies right inside Claude Code. (MCP is a standard way to plug outside apps and services into Claude.)
- **Auto-drafts**: a draft reply written in your style; you approve it instead of writing it
- **Inbox Zero workflow**: in the morning Claude goes through everything, and you get a prioritized list
- **Apollo / Hunter.io**: tools for finding the right email addresses and doing cold outreach
- **Lemlist**: automatic follow-up sequences
- **Email sequence**: a chain of emails that takes someone from sign-up to a deal, written once

---

## Theory

### Why use AI for email: the time math (a made-up example)

A typical day:

- 80 incoming emails
- 20 of them need a reply
- Each reply: 5-7 minutes to think it through and write it
- Total: 100-140 minutes, or roughly 2 hours

With AI:

- Claude reads everything and sorts it: urgent / waiting on your reply / just information / spam
- For the 20 emails that need a reply, it writes drafts
- You read the drafts, edit about 20% of them and approve the rest
- Total: 25-30 minutes

In this made-up example, you save roughly 70 to 115 minutes a day. Plug in your own numbers.

---

### Gmail MCP: Claude reads your inbox

There are several ways to connect Gmail to Claude. Once it's connected, Claude can read your emails, search them by criteria and write draft replies. You talk to Claude the way you'd talk to an assistant.

**Ways to connect (as of October 2026):**

- **The Gmail / Google Workspace connector in Claude's settings** (on paid plans): the simplest route. Check Claude's help center to see which actions it supports.
- **Google's official Gmail MCP server** (Google Workspace Developer Preview). According to Google's documentation, it searches emails and threads, reads messages, creates drafts and applies labels; sending email is not on its list of capabilities. You'll need a Google Cloud project, an OAuth client and a Claude plan that supports custom connectors.
- **Third-party MCP servers and hubs** (for example, Composio): convenient, but a third party gets access to your email. Check the permissions, the company's reputation and its data retention policy.

**Access rule:** give the minimum permissions (read and draft), and keep sending for yourself. If it's a work account, check your employer's AI policy before you connect anything.

```
# Google's official Gmail server connects to Claude as a custom connector:
# Settings → Connectors → Add custom connector
# Remote MCP server URL: https://gmailmcp.googleapis.com/mcp/v1
# The OAuth Client ID and Secret are created in Google Cloud Console
# (instructions: developers.google.com/workspace/gmail/api/guides/configure-mcp-server)
```

Once it's connected, here's what you type in Claude:

```
Check my inbox. Find every email from the last 3 days
that needs a reply from me. Sort them into:
- Urgent (needs a reply today)
- Normal (reply within 3 days)
- FYI (information only, no reply needed)

For each urgent one, write a draft reply in my style:
short, specific, no filler.
```

Claude reads the emails and gives you a table with the categories plus ready-made drafts for the urgent ones. You look through the drafts, edit where needed, copy them into Gmail and send.

---

### Auto-drafts: a CLAUDE.md for your email style

To make the drafts sound like you and not like boilerplate corporate text, describe your style in the project's CLAUDE.md file (Claude Code reads it as standing instructions) or in a system prompt.

**Sample CLAUDE.md for an email assistant:**

```markdown
# My email style

## General rules
- 150 words max per reply (unless it's a contract or a detailed scope of work)
- Get straight to the point; no "I hope this email finds you well"
- End every email with a specific call to action: what I need from the person and by when
- Lists instead of long paragraphs

## Never use
- "Per my last email..." (it reads as passive-aggressive)
- "Basically," "generally speaking," "at the end of the day" (vague filler)
- More than one question per email (one question only)

## Example of a good reply
Someone asks what a consultation costs:
"An initial consultation is $200/hour.
Next openings: tomorrow at 3 p.m. or Friday at 11 a.m.
Let me know which works and I'll send you a Zoom link."

## Example of a bad reply (don't write like this)
"Good afternoon! Thank you so much for your question! I'm delighted to let you
know that our consultations are available under a variety of pricing plans..."
```

---

### Python script: auto-drafting a reply

If you want to build this into your own system without MCP, call the API directly:

```python
import anthropic
import os

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

def draft_reply(incoming_email: str, context: str = "") -> str:
    """
    Generates a draft reply to an incoming email.
    Returns the draft. It does NOT send anything automatically.
    You review it and send it yourself.
    """
    response = client.messages.create(
        model="claude-sonnet-5-5",  # current model IDs: see Anthropic's documentation
        max_tokens=500,
        system="""You are a personal email assistant. You write replies in this style:
        
        - Short and to the point: no more than 100-150 words
        - Start with the substance, no small-talk greetings
        - Always end with a specific call to action: what you need from the person and by when
        - Use a list if there are 3 or more points
        - Tone: professional, not stiff
        
        IMPORTANT: you are proposing a draft, not the final text.
        Never add a signature; I add my own.""",
        messages=[{
            "role": "user",
            "content": f"""Incoming email:
---
{incoming_email}
---

Extra context for the reply: {context if context else 'none'}

Write a draft reply."""
        }]
    )
    return response.content[0].text


def classify_email(email_text: str) -> dict:
    """
    Classifies an email: does it need a reply, how urgent is it, what type is it.
    Returns a dict with the classification.
    """
    response = client.messages.create(
        model="claude-haiku-4-5",  # Haiku is fast and cheap for classification; Haiku 4.5 may be retired from the API no earlier than October 15, 2026, so check the model ID in the docs
        max_tokens=150,
        messages=[{
            "role": "user",
            "content": f"""Classify this email. Return JSON only:
{{
  "needs_reply": true/false,
  "urgency": "high"/"medium"/"low",
  "type": "client_inquiry"/"follow_up"/"newsletter"/"spam"/"internal"/"other",
  "summary": "one sentence on what the email is about"
}}

Email:
{email_text}"""
        }]
    )
    import json
    return json.loads(response.content[0].text)


# Example usage
if __name__ == "__main__":
    incoming = """
    Hi! I'd like to book a consultation about buying a home in San Antonio.
    My wife and I are thinking about moving there from Chicago next year, and we
    want to understand what homes really cost and how buying from out of state works.
    How much is a consultation, and when are you available?
    """
    
    # Step 1: classify
    classification = classify_email(incoming)
    print(f"Type: {classification['type']}")
    print(f"Urgency: {classification['urgency']}")
    print(f"Summary: {classification['summary']}")
    print(f"Needs reply: {classification['needs_reply']}")
    
    # Step 2: if it needs a reply, generate a draft
    if classification["needs_reply"]:
        context = "A consultation is $200/hour. Next openings: tomorrow at 3 p.m. or Friday at 11 a.m."
        draft = draft_reply(incoming, context)
        print(f"\nDraft reply:\n{'-'*40}\n{draft}")
```

---

### Apollo + Hunter.io: AI for cold email

Apollo and Hunter.io solve the "find this person's email address" problem. Claude turns the contacts you find into personalized emails.

🎨 **Picture this:** Apollo plus Claude is like a fishing net with smart bait. The net (Apollo) finds the right people. The bait (Claude) is made for each one personally, not stamped out from a template. The fish (a potential client) is more likely to bite.

```
# How you connect depends on the hub or service you choose:
# see the Apollo, Hunter or MCP hub documentation for the command format and how to sign in.
# Don't put API keys in the request URL: keep them in environment variables.
```

**A word on cold email:** emailing people you don't know is regulated by anti-spam and privacy laws (what gives you grounds to email someone, an easy way to unsubscribe, how you store contacts). In the US, commercial email falls under the federal CAN-SPAM Act; other countries have their own rules. Check the rules where you are and where your recipient is. Claude writes the text; responsibility for sending it stays with you.

Once it's connected, here's the task for Claude Code:

```
Use Apollo. Find 20 owners of real estate brokerages
in San Antonio, Texas. For each one:
1. Find their email with Hunter.io
2. Look at their LinkedIn profile (if Apollo has it)
3. Write a personalized cold email in English:
   - Mention something specific from their profile or business
   - Explain in 2 sentences how I can be useful to them
   - One specific question at the end
   - No more than 120 words

Save the results to a CSV: name, email, email text.
```

The manual version without MCP, with a direct API call:

```python
import anthropic
import requests
import os
import csv

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])
HUNTER_API_KEY = os.environ["HUNTER_API_KEY"]

def find_email(domain: str, first_name: str, last_name: str) -> str:
    """Finds an email address with Hunter.io from a domain and a name"""
    response = requests.get(
        "https://api.hunter.io/v2/email-finder",
        params={
            "domain": domain,
            "first_name": first_name,
            "last_name": last_name,
            "api_key": HUNTER_API_KEY,
        }
    )
    data = response.json()
    if data.get("data", {}).get("email"):
        return data["data"]["email"]
    return None


def write_cold_email(
    recipient_name: str,
    company: str,
    context_about_them: str,
    language: str = "English"
) -> str:
    """Generates a personalized cold email"""
    
    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=300,
        system=f"""You write personalized cold emails in this language: {language}.
        
        Rules:
        - 120 words max
        - Mention one specific detail about the person or the company
        - The value in 1-2 sentences: exactly what you can offer
        - One question at the end (not several)
        - No boilerplate like "I hope this email finds you well..."
        - Professional tone, not salesy""",
        messages=[{
            "role": "user",
            "content": f"""Recipient: {recipient_name}
Company: {company}
What I know about them: {context_about_them}

Me: an agent at Acme Realty. I help families relocating to San Antonio buy or rent a home.
I'm open to referral partnerships and co-op deals with other real estate agencies.

Write a cold email."""
        }]
    )
    return response.content[0].text


# Contact list for outreach
contacts = [
    {
        "name": "Carlos Rodríguez",
        "company": "Example Realty Group",
        "domain": "example.com",
        "first_name": "Carlos",
        "last_name": "Rodriguez",
        "context": "Specializes in historic homes near downtown"
    },
    # ... the rest of your contacts
]

# Generate the emails and save them to a CSV
with open("cold_outreach.csv", "w", newline="", encoding="utf-8") as f:
    writer = csv.writer(f)
    writer.writerow(["Name", "Company", "Email", "Message"])
    
    for contact in contacts:
        email = find_email(
            contact["domain"],
            contact["first_name"],
            contact["last_name"]
        )
        
        if email:
            letter = write_cold_email(
                contact["name"],
                contact["company"],
                contact["context"],
                language="English"  # or "Spanish" for Spanish-speaking contacts
            )
            writer.writerow([contact["name"], contact["company"], email, letter])
            print(f"Done: {contact['name']} <{email}>")
        else:
            print(f"Email not found: {contact['name']}")

print("Saved to cold_outreach.csv")
```

---

### Email sequence: from sign-up to a deal

An email sequence is a chain of emails that goes out automatically after someone signs up or takes an action. Claude writes all the emails once; you set them up in Lemlist (or another email service) or in your own script.

```
Someone fills out a form on your website
          |
          v
Right away: Welcome email
            (Claude personalizes it from the form data: name, where they're moving from, what they're interested in)
          |
          v
Day 3:   Value email
         (AI picks content from your library: if they're interested in renting → an article about renting)
          |
          v
Day 7:   Case study email
         (the story of a real client similar to this person)
          |
          v
Day 14:  Offer email
         (a specific offer with a call to action to book a consultation)
```

```python
import anthropic
import os
from datetime import datetime

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

def generate_welcome_email(
    name: str,
    interest: str,  # "renting" / "buying" / "investing"
    city_of_origin: str
) -> str:
    """Personalized welcome email"""
    
    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=400,
        system="""You write a welcome email to someone who is interested
        in buying or renting a home in San Antonio.
        
        Style: warm, not formal. It should sound like a real person wrote it.
        Length: 100-120 words.
        Structure: greeting → what they'll get next → one question so you can help them better.""",
        messages=[{
            "role": "user",
            "content": f"""Name: {name}
Interest: {interest}
Moving from: {city_of_origin}

Write a welcome email."""
        }]
    )
    return response.content[0].text


def select_value_content(interest: str, knowledge_base: dict) -> str:
    """
    Picks the relevant content from the knowledge base for the Value email.
    knowledge_base: a dict of topics → article or tip texts
    """
    response = client.messages.create(
        model="claude-haiku-4-5",
        max_tokens=600,
        messages=[{
            "role": "user",
            "content": f"""This person is interested in: {interest}

Available content:
{chr(10).join([f"- {topic}: {text[:100]}..." for topic, text in knowledge_base.items()])}

Pick the most relevant content and write a 120-150 word email.
Use specific facts from the content you picked."""
        }]
    )
    return response.content[0].text


# Knowledge base (in real life it's read from files or a database; the data below is made up, for illustration only)
KNOWLEDGE_BASE = {
    "renting": "Sample rents in our area: 1-bedroom $1,100-1,400/month, 2-bedroom $1,400-1,900/month. Neighborhoods clients ask about most: Downtown, the North Side...",
    "buying": "Typical steps for a buyer: mortgage pre-approval → offer → inspection → appraisal → closing. Often 30-60 days from accepted offer to closing...",
    "investing": "Rental returns depend on the neighborhood and the property; in a real knowledge base, this is where your own verified numbers and caveats go (not investment advice)...",
}

# Example: generate a welcome email
email = generate_welcome_email(
    name="Mike",
    interest="buying",
    city_of_origin="Chicago"
)
print("Welcome email:")
print(email)
print()

# Value email
value_email = select_value_content("buying", KNOWLEDGE_BASE)
print("Value email (day 3):")
print(value_email)
```

---

### Inbox Zero workflow: a 20-minute morning routine

A practical routine for every day:

```
7:00 a.m.  Claude (via Gmail MCP or a script) reads every new email from overnight
           Sorts them: urgent / normal / FYI / spam
           Writes drafts for everything that needs a reply

7:10 a.m.  You open the brief (a file, or a message to yourself in Slack or email)
           You see: 3 urgent, 8 normal, 12 FYI

7:10-7:30  You go through the drafts for the urgent emails
           Edit if needed (usually 20-30% need changes)
           Send
           Normal ones: schedule for this evening or tomorrow
           FYI: archive with one click

7:30 a.m.  Inbox Zero. Your day has started.
```

```python
import anthropic
import os
from typing import List

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

def process_inbox(emails: List[dict], your_context: str) -> dict:
    """
    Processes a list of emails: classifies them and writes drafts.
    
    emails: a list of dicts with the fields subject, sender, body, date
    your_context: a description of your work so Claude can write in your style
    """
    
    results = {
        "urgent": [],
        "normal": [],
        "fyi": [],
        "spam": [],
    }
    
    for email in emails:
        # Classification
        classification_response = client.messages.create(
            model="claude-haiku-4-5",
            max_tokens=200,
            messages=[{
                "role": "user",
                "content": f"""Classify this email. Return JSON:
{{
  "category": "urgent"/"normal"/"fyi"/"spam",
  "needs_reply": true/false,
  "summary": "one sentence"
}}

From: {email['sender']}
Subject: {email['subject']}
Body: {email['body'][:500]}"""
            }]
        )
        
        import json
        classification = json.loads(classification_response.content[0].text)
        category = classification["category"]
        
        email_data = {
            **email,
            "summary": classification["summary"],
            "draft": None
        }
        
        # Draft only if a reply is needed
        if classification["needs_reply"] and category in ["urgent", "normal"]:
            draft_response = client.messages.create(
                model="claude-sonnet-5-5",
                max_tokens=300,
                system=f"""You are an email assistant. About the person you write for:
{your_context}

Reply style: short, to the point, a specific call to action at the end.""",
                messages=[{
                    "role": "user",
                    "content": f"""Write a draft reply to this email:

From: {email['sender']}
Subject: {email['subject']}
Body: {email['body']}"""
                }]
            )
            email_data["draft"] = draft_response.content[0].text
        
        results[category].append(email_data)
    
    return results


def format_daily_brief(processed: dict) -> str:
    """Formats the brief for your morning read"""
    
    lines = [
        f"Inbox brief for {__import__('datetime').date.today()}",
        f"Urgent: {len(processed['urgent'])} | "
        f"Normal: {len(processed['normal'])} | "
        f"FYI: {len(processed['fyi'])} | "
        f"Spam: {len(processed['spam'])}",
        "",
    ]
    
    if processed["urgent"]:
        lines.append("URGENT (reply today):")
        for email in processed["urgent"]:
            lines.append(f"  From: {email['sender']}")
            lines.append(f"  Summary: {email['summary']}")
            if email["draft"]:
                lines.append(f"  Draft:\n  {email['draft'][:200]}...")
            lines.append("")
    
    if processed["normal"]:
        lines.append("NORMAL:")
        for email in processed["normal"]:
            lines.append(f"  - {email['sender']}: {email['summary']}")
    
    return "\n".join(lines)


# Example usage (in real life the emails come in through the Gmail API)
sample_emails = [
    {
        "sender": "carlos@example.com",
        "subject": "Working together on a buyer?",
        "body": "Hi! I have a client relocating from Chicago who's looking for a condo around $150K. Could we work on this one together?",
        "date": "2026-10-05"
    },
    {
        "sender": "newsletter@realestate-news.com",
        "subject": "Weekly market digest",
        "body": "Last week's San Antonio housing market report...",
        "date": "2026-10-05"
    },
]

YOUR_CONTEXT = """
Acme Realty helps families relocating to San Antonio buy or rent a home.
I work with clients directly and through local partner agencies.
Communication style: friendly, specific, no filler.
"""

processed = process_inbox(sample_emails, YOUR_CONTEXT)
brief = format_daily_brief(processed)
print(brief)
```

---

### Multilingual email: one system, two languages

If some of your clients write in English and others write in Spanish, Claude can figure out the language and reply in it automatically. You still read every draft before it goes out; if you don't read Spanish yourself, the English summary tells you what the email is about, and it's worth having a fluent speaker look over anything important.

```python
def multilingual_reply(incoming_email: str, your_context: str) -> dict:
    """
    Detects the email's language and writes a reply in the same language.
    Returns: {detected_language, draft, summary_in_english}
    """
    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=500,
        system=f"""You are a bilingual email assistant (English + Spanish).

About the person you write for:
{your_context}

Rules:
1. Detect the language of the incoming email
2. Reply in the SAME language (don't switch without a reason)
3. If it's Spanish, keep a professional tone that fits Latin American business email
4. If it's English, use a short, businesslike style

Return JSON:
{{
  "detected_language": "English"/"Spanish"/"Other",
  "draft": "the draft reply, in the email's language",
  "summary_in_english": "one sentence on what the email is about, always in English"
}}""",
        messages=[{
            "role": "user",
            "content": f"Email:\n{incoming_email}"
        }]
    )
    import json
    return json.loads(response.content[0].text)


# Test
spanish_email = """
¡Buenos días! Soy agente inmobiliario en Monterrey y tengo clientes
que se mudan a San Antonio y buscan casa. ¿Podríamos colaborar?
"""

result = multilingual_reply(spanish_email, YOUR_CONTEXT)
print(f"Language: {result['detected_language']}")
print(f"Summary (in English): {result['summary_in_english']}")
print(f"\nDraft reply:\n{result['draft']}")
```

---

## Practice

1. Connect Gmail to Claude: use the Gmail / Google Workspace connector in Claude's settings or Google's official Gmail MCP server (see above). Give it the minimum permissions: read and draft, no sending.

2. Write an `email_classifier.py` script with the `classify_email` and `draft_reply` functions from this lesson. Test it on 5 emails from your inbox (strip out client details first: don't send other people's personal information to services you don't have permission to share it with).

3. Create a CLAUDE.md for your email assistant: describe your style, list 3-5 banned phrases, and add an example of a good reply and an example of a bad one.

4. Set up `process_inbox` + `format_daily_brief`, run them on your own email and see how good the drafts are.

5. Pick one cold outreach task (5-10 contacts) and try `write_cold_email` on real data.

---

## Tools and resources

- **[Composio](https://composio.dev)**: an MCP hub for connecting Gmail, Apollo, Hunter and other services to Claude (a third party gets access to your email, so check the permissions)
- **[Gmail API](https://developers.google.com/gmail/api)**: the official documentation, if you connect directly
- **[Google's Gmail MCP server](https://developers.google.com/workspace/gmail/api/guides/configure-mcp-server)**: developer preview; search, read, drafts, labels
- **[Apollo.io](https://apollo.io)**: contact database + email finder (has a free plan; terms and prices on the site)
- **[Hunter.io](https://hunter.io)**: finds email addresses by domain (has a free plan; terms on the site)
- **[Lemlist](https://lemlist.com)**: cold email with automatic follow-ups (terms on the site)
- **[Instantly.ai](https://instantly.ai)**: an alternative to Lemlist for sending at volume (terms on the site)
- **[anthropic Python SDK](https://github.com/anthropics/anthropic-sdk-python)**: for the scripts in this lesson
- **Prices and versions:** [What's current](https://aimayak.com/now/)

---

## Key takeaways

> Email isn't really about writing text. It's about making decisions: who to answer, what to say and when. Claude takes the mechanical part (writing the text in your style). The decisions stay with you.

> Auto-drafts only work if Claude knows your style. Spend 30 minutes on a CLAUDE.md with good and bad examples; it pays off every day.

> Inbox Zero is doable. Sorting plus drafts for incoming mail noticeably cuts the time you spend on email. The key: don't fully automate sending; keep the final review for yourself.

> Cold outreach with AI means personalization without the manual work. Apollo finds the people, Hunter.io finds the email addresses, and Claude writes each email as if you'd spent 20 minutes researching the person. In reality, it's about five seconds of an API call, so check the details it used before you hit Send.

---

## Next lesson

→ [AI for meetings: transcripts and automatic notes](74-ai-meetings.md): record your meetings and turn them into tasks
