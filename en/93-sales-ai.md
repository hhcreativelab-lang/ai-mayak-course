# AI for sales: qualifying leads, follow-ups, closing

**Time:** about 25 min reading + 35 min practice

---

## The gist

Sales is filtering. Out of a hundred leads (people or companies who have shown some interest), only a small share will buy. A salesperson's job is to find the ones who will buy, fast, and spend time on them instead of on everyone else.

Claude makes that filtering systematic: it qualifies leads with BANT, gives each one a readiness score, writes personalized emails and prepares answers to objections. The rep walks into the conversation already knowing who's on the other end and what they care about.

This lesson has a lot of Python code. If you don't program, take the prompt texts from it: they work in a regular Claude chat too, once you paste in your own notes about the client.

🎨 **Picture this:** an experienced salesperson who gets a quick briefing from a colleague before every call: "This is Kevin from Northfield Supply. They're looking at competitors, the budget is there, but the CEO hasn't made the call yet, and the main objection is integration with QuickBooks." That's what Claude does for every lead, automatically.

---

## Key concepts

- **BANT qualification**: Budget, Authority, Need, Timeline, worked out with AI
- **Lead scoring 0-100**: who's ready to buy right now
- **Personalized follow-ups**: every email written for one specific person
- **An objection library**: Claude drafts an answer to any objection
- **Sales playbook → AI assistant**: a document turns into a working advisor
- **Apollo.io + Claude**: outreach with deep personalization

---

## Theory

### BANT qualification: four questions that decide everything

BANT is a long-standing sales framework, and it still works:

- **B**udget: is there money? How much are they willing to spend?
- **A**uthority: is this the person who makes the decision, or someone just gathering information?
- **N**eed: is there a real need, or are they "just looking"?
- **T**imeline: when do they plan to buy? This quarter, or "someday"?

Claude pulls BANT out of your conversations: emails, chats, notes from calls and meetings.

```python
import anthropic
import json

client = anthropic.Anthropic()


def text_of(response) -> str:
    """Collects the text of a reply: newer models may put "thinking" blocks before the text."""
    return "".join(block.text for block in response.content if block.type == "text")

def qualify_lead_bant(
    company_name: str,
    contact_name: str,
    contact_position: str,
    interaction_history: str
) -> dict:
    """Qualifies a lead with BANT based on the interaction history"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=8000,
        messages=[{
            "role": "user",
            "content": f"""Run a BANT qualification of this lead based on the information available.

Company: {company_name}
Contact: {contact_name}, {contact_position}

Interaction history:
{interaction_history}

Score each BANT criterion on a 0-3 scale:
0 = no information
1 = weak or doubtful signal
2 = some signs
3 = clear confirmation

Return only JSON, with no explanations and no triple backticks around it:
{{
    "bant": {{
        "budget": {{
            "score": a number 0-3,
            "evidence": "a quote or a fact from the conversation",
            "concern": "what looks worrying",
            "recommendation": "what else to find out"
        }},
        "authority": {{
            "score": a number 0-3,
            "evidence": "...",
            "concern": "...",
            "recommendation": "..."
        }},
        "need": {{
            "score": a number 0-3,
            "evidence": "...",
            "concern": "...",
            "recommendation": "..."
        }},
        "timeline": {{
            "score": a number 0-3,
            "evidence": "...",
            "concern": "...",
            "recommendation": "..."
        }}
    }},
    "total_score": a number 0-12,
    "qualification_verdict": "hot/warm/cold/disqualify",
    "recommended_next_step": "a specific next action",
    "key_questions_to_ask": ["a list of 3 questions for the next contact"]
}}"""
        }]
    )

    result = json.loads(text_of(response))

    # Add a percentage score
    result["qualification_percent"] = round(result["total_score"] / 12 * 100)

    return result


# A test with made-up data
history = """
April 15, first call:
Kevin asked about our product and said they're "looking at options to
automate the department." He's a business development manager. The CEO
"isn't involved yet." Budget didn't come up. "We'd like to sort this out
by the end of the year."

April 22, second call:
Kevin came back with a detailed list of requirements. Said the CEO approved
looking into it. Mentioned that a competitor's similar product costs $10,000 a year,
and that feels expensive to them. They want to start "no later than Q3, it's tied
to our budget cycle."

April 28, email:
"We watched the demo. We like it, but we need to understand how it integrates
with our QuickBooks. Also, our CEO would like to meet in person. Are you free
next week?"
"""

result = qualify_lead_bant(
    company_name="Northfield Supply Co.",
    contact_name="Kevin Walsh",
    contact_position="Business Development Manager",
    interaction_history=history
)

print(f"BANT Score: {result['total_score']}/12 ({result['qualification_percent']}%)")
print(f"Status: {result['qualification_verdict'].upper()}")
print(f"\nNext step: {result['recommended_next_step']}")
print(f"\nQuestions for the meeting:")
for q in result['key_questions_to_ask']:
    print(f"  • {q}")
```

### Lead scoring: who's hot right now

BANT is the foundation, but dozens of other signals show whether someone is ready to buy. Claude looks at all of them at once and gives a score from 0 to 100.

```python
def score_lead_readiness(
    contact_info: dict,
    interaction_history: str,
    product_type: str,
    avg_deal_cycle_days: int
) -> dict:
    """Overall assessment of how ready a lead is to buy"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=8000,
        messages=[{
            "role": "user",
            "content": f"""Rate how ready this lead is to buy.

Contact information:
{json.dumps(contact_info, ensure_ascii=False)}

Product type: {product_type}
Average deal cycle: {avg_deal_cycle_days} days

History:
{interaction_history}

Analyze the signals:
POSITIVE: specific questions about details, asks about integration or rollout,
mentions deadlines, names a budget, asks for a meeting with the CEO, compares you with competitors,
asks for a proposal or a contract

NEGATIVE: vague answers, "we'll see", long silences with no reply,
says it's "not my decision", keeps changing requirements, wants everything cheaper

Return only JSON, with no explanations and no triple backticks around it:
{{
    "score": a number 0-100,
    "stage": "awareness/consideration/decision/ready_to_buy",
    "hot_signals": ["a list of positive signals found in the history"],
    "cold_signals": ["a list of warning signals"],
    "estimated_close_days": a number (forecast of how many days until the deal closes),
    "confidence": "low/medium/high",
    "action": {{
        "immediate": "what to do right now",
        "this_week": "what to do this week",
        "if_no_response": "what to do if there's no reply for 3 days"
    }}
}}"""
        }]
    )

    return json.loads(text_of(response))
```

🎨 **Picture this:** a doctor looks at the symptoms and makes a diagnosis. A salesperson looks at the signals and gives a score. Claude is a diagnostic assistant that checks every symptom on the list and doesn't get tired after the 50th lead.

### Personalized follow-up emails

Template emails rarely work. "Hello! We'd like to remind you about our offer..." usually gets deleted unread.

Personalization works. But personalizing 50 follow-ups by hand isn't realistic.

```python
def generate_followup_email(
    contact: dict,
    last_interaction_summary: str,
    days_since_last_contact: int,
    followup_number: int,  # First, second or third follow-up
    product_name: str,
    your_name: str
) -> dict:
    """Generates a personalized follow-up email"""

    followup_tone = {
        1: "friendly and light, add value (an article or a case study)",
        2: "a little more direct, ask whether they have questions or anything has changed",
        3: "the last one, make it clear this is the final follow-up, but without pressure"
    }

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=8000,
        messages=[{
            "role": "user",
            "content": f"""Write a personalized follow-up email.

CONTACT DETAILS:
Name: {contact.get('name')}
Company: {contact.get('company')}
Title: {contact.get('position')}
Interest: {contact.get('main_interest')}

CONTEXT:
Last contact: {last_interaction_summary}
Days without a reply: {days_since_last_contact}
This is follow-up number: {followup_number} of 3
Tone: {followup_tone.get(followup_number, followup_tone[1])}

Product: {product_name}
From: {your_name}

REQUIREMENTS:
- 3-5 sentences max
- The first sentence refers specifically to the last conversation (not a template line)
- Add something useful (a helpful observation, a real statistic with a source, a short real case study); don't invent facts
- One clear call to action
- No pressure, no pushiness
- Natural language, not corporate-speak

Return only JSON, with no explanations and no triple backticks around it:
{{
    "subject": "email subject line",
    "body": "email text",
    "ps": "a P.S. (optional, only if it makes the email stronger)",
    "value_add": "what useful thing the email adds"
}}"""
        }]
    )

    return json.loads(text_of(response))


# Example (made-up data)
email = generate_followup_email(
    contact={
        "name": "Kevin",
        "company": "Northfield Supply Co.",
        "position": "Business Development Manager",
        "main_interest": "Sales team automation, QuickBooks integration"
    },
    last_interaction_summary="We did a demo. Kevin was impressed but asked about the QuickBooks integration. We agreed they'd discuss it with their team.",
    days_since_last_contact=4,
    followup_number=1,
    product_name="SalesBot Pro",
    your_name="Daniel"
)

print(f"Subject: {email['subject']}")
print(f"\n{email['body']}")
if email.get('ps'):
    print(f"\nP.S. {email['ps']}")
```

### An objection library: an answer for everything

Every product runs into 10-15 typical objections. An experienced salesperson knows the answer to each one. A new one gets flustered.

Claude helps you keep your footing:

```python
def handle_objection(
    objection: str,
    product_name: str,
    product_key_benefits: list[str],
    contact_context: str = ""
) -> str:
    """Drafts responses to an objection using several approaches"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=8000,
        messages=[{
            "role": "user",
            "content": f"""A customer raised an objection. Help me respond.

PRODUCT: {product_name}
BENEFITS: {', '.join(product_key_benefits)}
OBJECTION: "{objection}"
CUSTOMER CONTEXT: {contact_context or "No additional context"}

Give 3 response options:

1. **Direct**: agree with the part of the objection that's true, then turn it around
2. **With a question**: ask a question that helps the customer reach the answer on their own
3. **With a case**: the story of a real customer who had a similar objection (if there's no real case, say so instead of making one up)

For each one:
- The response (2-4 sentences)
- When to use it

Also give:
- The hidden reason: what's really behind this objection
- Red flag: is this a genuine objection, or a sign the deal won't happen?"""
        }]
    )

    return text_of(response)


# Common objections and responses
objections = [
    "This is too expensive for us",
    "We need to discuss it with management",
    "We already use another solution",
    "Let's come back to this next quarter",
    "We need to think about it"
]

print("=== OBJECTION RESPONSE LIBRARY ===\n")
for obj in objections[:2]:  # Show the first two as an example
    print(f"OBJECTION: {obj}")
    print("-" * 50)
    response = handle_objection(
        objection=obj,
        product_name="SalesBot Pro",
        product_key_benefits=["Saves 5 hours a week", "QuickBooks integration", "Up and running in 2 days"],
        contact_context="B2B client, mid-size company, 10-person sales team"
    )
    print(response)
    print("\n")
```

### Sales playbook → a working AI advisor

If you already have a sales playbook (a written guide to how your company sells: who to target, what to say, how to handle objections), Claude turns it into an interactive advisor for your reps.

```python
def create_sales_advisor(playbook_content: str):
    """Creates a sales advisor based on a playbook"""

    def ask_advisor(question: str, deal_context: str) -> str:
        response = client.messages.create(
            model="claude-sonnet-5-5",
            max_tokens=8000,
            system=f"""You're an experienced sales coach. You have the company's playbook:

{playbook_content}

Base your answers strictly on the playbook. If a question goes beyond the playbook,
say so. Give specific phrases a rep can use right now.""",
            messages=[{
                "role": "user",
                "content": f"Customer situation: {deal_context}\n\nQuestion: {question}"
            }]
        )
        return text_of(response)

    return ask_advisor

# Usage example (the company and its rules are made up)
playbook = """
# Sales Playbook: Techservice Inc.

## Qualification
- Minimum budget we work with: $5,000
- Target title: CEO / VP of Sales / IT director
- Red flag: if they can't name their pain specifically, they're not our customer

## Handling the "too expensive" objection
1. Ask: "Expensive compared to what?"
2. Turn it into ROI: "How many hours a week do your people spend on X right now?"
3. Show a case study from a company of a similar size

## Closing
- Never give a discount without a reason
- Either-or questions: "Would it work better to start on the 1st or the 15th?"
"""

advisor = create_sales_advisor(playbook)

# A rep asks for advice right before a call
advice = advisor(
    question="The customer says it's too expensive but is clearly interested. What should I do?",
    deal_context="50-person company, IT director, they've been evaluating for 3 months, budget is 'under discussion'"
)
print(advice)
```

### Apollo.io + Claude: personalized outreach

Apollo.io is a service with a database of business contacts and tools for cold email. Claude adds the kind of personalization a template can't.

⚠️ Cold emails and collecting contact data are regulated by anti-spam and personal data laws, and every country has its own: check the rules of your country and of your recipient's (in the US, the FTC's CAN-SPAM guide). Collect details from LinkedIn by hand: LinkedIn prohibits automated collection (bots, browser extensions). Before you launch, reread the lesson [Cold outreach that gets replies](39c-cold-outreach-deep.md); for more on the laws, see the library lesson [AI regulation and compliance](61c-ai-regulation-compliance.md).

```python
def personalize_cold_outreach(
    prospect_data: dict,  # About the person: company, title, what they've posted (from Apollo and LinkedIn)
    your_product: str,
    your_value_prop: str
) -> dict:
    """Personalizes a cold email for a specific person"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=8000,
        messages=[{
            "role": "user",
            "content": f"""Write a personalized cold email.

PROSPECT INFORMATION (from Apollo/LinkedIn):
{json.dumps(prospect_data, ensure_ascii=False, indent=2)}

OUR PRODUCT: {your_product}
VALUE PROPOSITION: {your_value_prop}

RULES:
- The first sentence MUST be about them (not about us)
- Connect their real context (title, company, activity) to our product
- One clear question at the end (not a "buy now" pitch)
- Under 100 words

Return only JSON, with no explanations and no triple backticks around it:
{{
    "subject": "subject line (up to 50 characters)",
    "opening": "the personalized first sentence",
    "value": "how our product solves their specific problem",
    "question": "a question for them to answer",
    "personalization_source": "what the personalization is based on"
}}"""
        }]
    )

    return json.loads(text_of(response))
```

---

## Practice

### Exercise: build a lead qualification system with Claude scoring

**What we're building:** a script that takes a lead's details and returns a full qualification plus a plan for working that lead.

**Without programming.** Paste your notes about a lead and the prompt text from the `full_lead_analysis()` function below into a Claude chat. You get the same qualification and plan, just without a file.

**With code.** You need Python, the `anthropic` library (`pip install anthropic`) and an Anthropic API key in the `ANTHROPIC_API_KEY` environment variable. You create the key in the Claude Console (platform.claude.com); it's billed by tokens, separately from a subscription.

The request to Claude includes the name, company, title and notes, but not the email or phone number: don't send more personal data than you need. If you work with real clients' data, check that your privacy policy and the laws where you work allow it.

```python
# lead_qualification_system.py

import anthropic
import json
from dataclasses import dataclass
from typing import Optional

client = anthropic.Anthropic()


def text_of(response) -> str:
    """Collects the text of a reply: newer models may put "thinking" blocks before the text."""
    return "".join(block.text for block in response.content if block.type == "text")

@dataclass
class Lead:
    name: str
    company: str
    position: str
    email: str
    phone: Optional[str] = None
    source: str = "inbound"
    notes: str = ""
    interaction_log: str = ""

def full_lead_analysis(lead: Lead) -> dict:
    """
    Full lead analysis: BANT + scoring + action plan
    """

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=8000,
        messages=[{
            "role": "user",
            "content": f"""Run a full lead analysis for the sales team.

LEAD:
Name: {lead.name}
Company: {lead.company}
Title: {lead.position}
Source: {lead.source}
Rep's notes: {lead.notes}

INTERACTION HISTORY:
{lead.interaction_log or "First contact, no history yet"}

Return only JSON, with no explanations and no triple backticks around it:
{{
    "qualification": {{
        "bant_score": a number 0-12,
        "readiness_score": a number 0-100,
        "verdict": "hot/warm/cold/disqualify",
        "verdict_reason": "why this verdict"
    }},
    "bant_details": {{
        "budget": {{"score": 0-3, "evidence": "...", "gap": "what's still unknown"}},
        "authority": {{"score": 0-3, "evidence": "...", "gap": "..."}},
        "need": {{"score": 0-3, "evidence": "...", "gap": "..."}},
        "timeline": {{"score": 0-3, "evidence": "...", "gap": "..."}}
    }},
    "persona_analysis": {{
        "decision_role": "champion/decision_maker/influencer/blocker/user",
        "communication_style": "analytical/relationship/speed/stability",
        "main_motivation": "what drives this person"
    }},
    "action_plan": {{
        "next_24h": "a specific action",
        "next_week": "the plan for the week",
        "key_questions": ["3 questions for the next meeting"],
        "risks": ["what could go wrong"],
        "win_conditions": ["what it takes to close this deal"]
    }},
    "suggested_followup_timing": {{
        "if_interested": "how many days until you write again",
        "if_silent": "how many days until you send a reminder",
        "max_attempts": a number
    }}
}}"""
        }]
    )

    return json.loads(text_of(response))


def format_lead_report(lead: Lead, analysis: dict) -> str:
    """Formats a clean report for the rep"""

    q = analysis["qualification"]
    bant = analysis["bant_details"]
    action = analysis["action_plan"]

    verdict_emoji = {
        "hot": "🔥", "warm": "☀️", "cold": "❄️", "disqualify": "🚫"
    }.get(q["verdict"], "❓")

    report = f"""
╔══════════════════════════════════════════════╗
║  LEAD REPORT: {lead.name[:30]:<30} ║
╚══════════════════════════════════════════════╝

{verdict_emoji} STATUS: {q['verdict'].upper()} ({q['readiness_score']}/100)
📊 BANT Score: {q['bant_score']}/12
💡 Reason: {q['verdict_reason']}

BANT DETAILS:
  💰 Budget:    {'█' * bant['budget']['score']}{'░' * (3-bant['budget']['score'])} ({bant['budget']['score']}/3) — {bant['budget']['evidence'][:60]}
  👔 Authority: {'█' * bant['authority']['score']}{'░' * (3-bant['authority']['score'])} ({bant['authority']['score']}/3) — {bant['authority']['evidence'][:60]}
  🎯 Need:      {'█' * bant['need']['score']}{'░' * (3-bant['need']['score'])} ({bant['need']['score']}/3) — {bant['need']['evidence'][:60]}
  ⏰ Timeline:  {'█' * bant['timeline']['score']}{'░' * (3-bant['timeline']['score'])} ({bant['timeline']['score']}/3) — {bant['timeline']['evidence'][:60]}

ACTION PLAN:
  ⚡ Today: {action['next_24h']}
  📅 This week: {action['next_week']}

QUESTIONS FOR THE NEXT MEETING:
"""
    for q_text in action['key_questions']:
        report += f"  • {q_text}\n"

    report += f"""
RISKS:
"""
    for risk in action['risks']:
        report += f"  ⚠️ {risk}\n"

    return report


# ===== TEST (the person and the company are made up) =====
test_lead = Lead(
    name="Mike Thompson",
    company="Diamond Group Holdings",
    position="Director of Operations",
    email="[lead email]",
    source="inbound call",
    notes="Called us on his own, said he saw us at a conference. Asked about integrations.",
    interaction_log="""
    May 14 (call, 25 min):
    Mike is director of operations; he oversees 3 departments, including sales (12 people).
    Problem: reps don't keep the CRM up to date, and leads get lost.
    They're looking at a solution "by the end of Q2"; that's their internal deadline.
    Budget: "within reason, the details are with our CFO." The IT director is already in the loop.
    Asked us to send a proposal and case studies from similar companies.
    Competitor: they looked at Pipedrive, "didn't love the interface."
    Next step: a meeting with the CFO in a week if they like the materials.
    """
)

print("Analyzing the lead...")
analysis = full_lead_analysis(test_lead)
report = format_lead_report(test_lead, analysis)
print(report)

# Save to JSON for the CRM
with open(f"lead_{test_lead.name.replace(' ', '_')}.json", "w", encoding="utf-8") as f:
    json.dump({
        "lead": {
            "name": test_lead.name,
            "company": test_lead.company,
            "position": test_lead.position
        },
        "analysis": analysis
    }, f, ensure_ascii=False, indent=2)

print("\n✅ Analysis saved to JSON")
```

**Run it:**
```bash
python lead_qualification_system.py
```

---

## Tools and resources

- **Apollo.io**: a contact database and cold email (check the site for plans and limits)
- **HubSpot CRM**: a CRM for storing customer data, with a free plan (check the site for paid plans; see also the library lesson [CRM on autopilot](90-crm-autopilot.md))
- **Lemlist / Instantly**: services for sending cold email campaigns
- **Notion**: a place to keep your sales playbook
- **Claude API**: the model names in the code are as of October 2026; current prices and versions are on the [What's current](https://aimayak.com/en/now/) page

---

## Key takeaways

> BANT isn't bureaucracy, it's speed. Figuring out quickly whether someone is your customer respects both your time and theirs.
>
> Personalization isn't a luxury anymore; it's a must. People get lots of template emails, and one personalized email stands out right away.
>
> The most valuable part of sales AI isn't how fast it writes. It's consistency. Claude gives the hundredth lead the same level of analysis as the first. People get tired. AI doesn't.

---

## Next lesson

→ [Build-Along: start an AI consulting business](113-build-along-ai-consulting.md)
