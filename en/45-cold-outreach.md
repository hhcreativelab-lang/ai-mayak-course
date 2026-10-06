# Cold email and LinkedIn outreach with Claude

**Time:** about 25 min reading + 40 min practice

The percentages and numbers in this lesson are rough guides, not statistics and not a promise of results. Measure your own baseline in your CRM spreadsheet. Rules for commercial email depend on the country: see the section on the legal side in the next lesson, [Cold outreach in 2026](39c-cold-outreach-deep.md).

---

## The gist

Warm contacts (see the [First clients](38-monetization-clients.md) lesson) are like fishing at a pond you know. You know where the fish are and what they bite on. Cold outreach (writing to people who don't know you yet) is casting a line in a new lake. You need to figure out where the fish are, what bait to use, and how not to pollute the lake with spam. Many people do outreach the wrong way and get almost no replies. A personalized approach usually gets noticeably more.

---

## Key concepts

- **The cold email formula**: a personalized first line, a specific pain point, one question
- **Reply rate**: the share of people who write back. It's low for mass email blasts and noticeably higher for personalized emails (exact numbers depend on the niche, so measure your own)
- **A follow-up sequence**: 3 to 5 touches, each from a different angle. Don't repeat the same thing
- **A/B testing**: two versions of a subject line or a first line; you compare which one gets more replies
- **CRM tracking**: a simple record (CRM stands for customer relationship management) of where each person is in your pipeline and when you last contacted them
- **NEVER spam**: the course's working rule is up to 20 personalized emails a day, sent by hand

---

## Theory

### Why cold outreach fails for most people

Most cold emails look like this:

```
Subject: An amazing offer for your business!

Hi there!

I'm [Name] from [Company]. We offer cutting-edge AI solutions
that transform business processes.

Want to learn more? Just reply to this email!

Best regards,
[Signature]
```

Almost everyone ignores a template like this. Here's why:
- No personalization: it's obviously a template
- No specific pain point: "cutting-edge solutions" means nothing
- No value: it doesn't explain why I should spend my time on it
- It sells from the very first contact, which breaks trust

🎨 **Picture this:** a stranger walks up to you on the street and immediately says, "Buy my stuff." You turn away. But if the same stranger says, "Those bags look heavy. There's an elevator right around the corner," you stop.

---

### The cold email formula: what actually works

🎨 **Picture this:** a good cold email is like a good resume. Not "I can do a lot of things," but "here's a specific problem I solved for a similar company, and here's the result in numbers." The first line works like the opening of a cover letter that names the company and the job: right away the reader can tell a real person wrote it for them, not for 500 people at once.

**The structure of the email (5 parts):**

```
1. A personalized first line (one short sentence about them)
2. A specific pain point you noticed (1-2 sentences)
3. One concrete result you delivered for a similar client (1 sentence)
4. A soft question: not "buy this" but "is this relevant for you?"
5. Signature (your name + a link to a case study or your LinkedIn)
```

**An example of a good email:**

```
Subject: Handling email requests at [Company]: worth automating?

[Name],

I saw on LinkedIn that you recently grew your support team to 4 people,
which tells me request volume has gone up.

When that happens, a good share of incoming messages are usually routine
questions about shipping, order status and returns. That's time
you could hand off to AI.

For an agency with a similar workload, we cut response time
from 4 hours to 8 minutes and freed up 22 hours a week for the team.
[The numbers in this example are made up. In your own email, include only real results from your own projects.]

Is this relevant for your situation?

[Name]
[Link to case study]
```

**Length:** 5 to 7 sentences. No more. It takes about 20 seconds to read.

---

### Personalizing the first line with Claude

🎨 **Picture this:** a personalized first line is like a coffee cup with your name written on the side. Same cup, but with your name on it, and you look at it a little more closely. Only instead of their name, you use a detail from their life. It takes a few minutes of reading their profile and noticeably raises your reply rate.

Personalization isn't "Hi, [Name]!". It's proof that you read about them.

**Where to find personalization details:**
- LinkedIn: their latest post, recent changes to the team, a new product
- Their website: the About page, the blog, recent news
- Job listings: if they're hiring someone to manage email, the volume is high
- Reviews on Google, Yelp or Trustpilot: what customers praise and what they complain about

**How to use Claude for personalization:**

A prompt for Claude:
```
I looked at the LinkedIn profile of [Name] from [Company].
Recently they: [copy 2-3 facts from the profile].
I automate [type of task].

Write a personalized first line for an email (one sentence, up to 15 words)
that shows I've read about them and connects to what I offer.

Give me three versions, each from a different angle.
```

Claude will give you options like these:
- "Saw traffic jumped after your new product launch, which usually means more requests too"
- "Congrats on growing the team. How are you keeping up with the volume of requests?"
- "Three support manager openings at once: has the workload grown that much?"

Pick the best one, tweak it a little, and use it. Check that every fact in the line is true: Claude can fill in details that weren't in your notes.

---

### LinkedIn outreach: when you don't need email

When you sell to other businesses (B2B), a LinkedIn message sometimes works better than email. On a free account you can only message people you're already connected with, so you start with a connection request. InMail, a message to someone outside your connections, comes only with paid plans.

**Rules for LinkedIn outreach:**

1. Start with a connection request that includes a personalized note. On a free account the note can be up to 200 characters and is available for only a few invitations a month; on a paid account it's up to 300 characters (as of October 2026; check LinkedIn for the current terms):
```
Hi [Name], I see you're growing [business/product]. I work on
AI automation for [your industry] and would enjoy comparing notes.
Would be glad to connect.
```

2. Once they accept, send your first message 1-2 days later:
```
Thanks for connecting! I noticed [personalized detail from their profile].
For similar companies, I've automated [specific task],
with this result: [your golden number].
Is this relevant for you? I can show you how it works in 15 minutes.
```

A "golden number" is the one figure that shows your result at a glance, like hours saved per week or a faster response time. The Portfolio and case studies lesson covers it in detail.

3. It's better not to send voice messages or video in the very first cold contact on LinkedIn. A video (for example, recorded with Loom; see the [Cold outreach in 2026](39c-cold-outreach-deep.md) lesson) fits better after the first reply, or for a small number of your most valuable contacts.

---

### A/B testing: how to improve your results

An A/B test for email is simple: one variable, two versions, a similar group of recipients for each.

**What to test first:**

1. **The subject line** affects the open rate (whether they open it at all):
   - A: "[Company]: automating request handling"
   - B: "A question about the [Company] support team"

2. **The first line** affects whether they keep reading:
   - A: "I see you've grown your team..."
   - B: "I looked at your website and noticed that..."

3. **The call to action** affects whether they reply:
   - A: "Is this relevant for your situation?"
   - B: "When would be a good time for a 15-minute call?"

**Minimum sample size for an A/B test:** the more emails per version, the more reliable the conclusion. With a few dozen emails, the result is more of a hint than proof.

---

### A follow-up sequence: 3 to 5 touches

🎨 **Picture this:** follow-ups are like drops of water on a stone. One drop does nothing. Three drops at the right rhythm start to wear a small dip. The point isn't to be pushy; it's to show up regularly and bring a new angle each time.

Most people don't answer the first email not because they aren't interested, but because they saw it at a bad moment and forgot. Follow-ups (reminders) are normal practice.

**Follow-up rules:**
- Each new email brings a new angle, not just "checking in"
- Between emails: 3 to 5 business days
- 3 to 5 touches at most, then let it go
- No pressure: no fake deadlines or "last chance" offers, and no guilt trips about an unanswered email

**An example sequence:**

```
Day 0: The main email (personalization + pain point + result + question)

Day 4: Follow-up 1, a different case or a different pain point
"[Name], one more thing to add to my last note: here's another situation
where this helped: [another case]. Maybe it's closer to what you're dealing with?"

Day 9: Follow-up 2, a resource or a useful idea (give value)
"[Name], not a sales pitch: I came across an article about [their industry]
that you might find interesting: [link]. It has a good example
related to the automation I wrote about."

Day 15: Follow-up 3, the breakup email (the last one)
"[Name], this is my last email on this; I don't want to clutter your inbox.
If it becomes relevant down the road, I'd be glad to talk.
Good luck with [their project/product you saw]."
```

The breakup email sometimes gets a reply from people who had been silent: many people appreciate that you respect their time.

---

### Reply rate: what counts as normal

| Type of outreach | Open rate | Reply rate | Conversion to a call |
|---|---|---|---|
| Mass (template) | low | low | very low |
| Personalized (partly unique) | higher | noticeably higher | higher |
| Hyper-personalized (fully unique) | highest | highest | highest |

We don't have exact numbers: they depend on the niche, the contact list and the quality of the email. Your own numbers from your CRM spreadsheet matter more than anyone else's.

**Bottom line:** 20 personalized emails usually work better than 200 template emails.

---

### CRM tracking: a simple way not to lose contacts

🎨 **Picture this:** a CRM spreadsheet is like the dispatch board at a cab company: where every car is, who's riding in it, where it's headed. Without the board, it's chaos: calls get mixed up and customers are left waiting. Even a Google Sheet with six columns beats keeping 50 contacts in your head.

You don't need a complicated CRM at the start. A Google Sheet with six columns will do:

```
| Name | Company | Channel | Status | Last contact | Notes |
|---|---|---|---|---|---|
| Sarah K. | RealtyCo | LinkedIn | Awaiting reply | 2026-10-05 | Growing the team |
| Mike R. | AgencyX | Email | Follow-up 1 | 2026-10-08 | Saw the case study |
| Maria T. | StartupZ | LinkedIn | Call on Oct 12 | 2026-10-07 | Interested |
```

Statuses: "Contacted" → "Awaiting reply" → "Follow-up 1/2/3" → "Call scheduled" → "Case study sent" → "Closed (yes/no)"

Every morning, open the sheet and see who's due for a follow-up.

---

### NEVER spam: why it matters

🎨 **Picture this:** your domain's reputation is like your credit score. It takes years to build and a month to wreck. Blasting mass email from Gmail is like taking out a loan you can't pay back. The bank (Google) puts you on a blacklist, and even your normal emails stop getting through.

The working rule for personalized outreach: **up to 20 emails a day**.

Why:
- Google and Microsoft (Outlook) send email to spam or reject it when a sender gets a lot of spam complaints and bounces (emails that can't be delivered)
- Your domain's reputation suffers, and even normal emails start landing in spam
- Personalized means time-consuming: 20 emails a day with real personalization is 2 to 3 hours of work

If you need to scale, use professional platforms (Lemlist, Instantly) with domain warm-up (slowly raising your sending volume so email providers learn to trust a new domain), not Gmail for mass sending. Email laws depend on the country (CAN-SPAM, GDPR, CASL and others): check the rules in your country and in your recipient's. In the US, commercial email falls under the federal CAN-SPAM Act. In general terms, it comes down to honesty and an easy way out: don't mislead people about who you are or what the email is about, include your mailing address, give them a simple way to opt out, and respect it when they do. This isn't legal advice; for the specifics, read the official guidance (the links are in the next lesson) or ask a lawyer.

---

## Practice

**Exercise: Write and send 5 personalized emails**

1. Pick a niche from your Trust Map (your list of warm contacts from the First clients lesson) or outside it: 5 companies of the same type, for example real estate brokerages or digital marketing agencies

2. For each company, find:
   - The name and title of the decision-maker (LinkedIn)
   - One specific fact about the company (a post, a news item, a job opening)

3. Use Claude for personalization (the prompt from this lesson): three versions of the first line for each company

4. Write 5 emails using the formula: personalization → pain point → result → question

5. Set up a CRM spreadsheet in Google Sheets (the six columns from this lesson)

6. (If you're ready to send) Send 2-3 messages through LinkedIn and 2-3 by email. Before you send, check the email rules in your country and in your recipient's

7. Four days later, write a follow-up to everyone who didn't reply

**Goal:** 5 personalized emails ready to send, a CRM spreadsheet set up, and, after 2 weeks, a count of how many people replied. That's your first reference point; 5 emails are too few to draw conclusions.

---

## A cold email template (ready to copy)

```
Subject: [Name], [a specific observation about their business]

Hi [Name],

I noticed [a specific observation from LinkedIn/their website/job listings].
We automated [a similar process] for [type of company],
with this result: [a specific metric, your golden number].

Could I show you how it works in 15 minutes?

[Your name]
[Link to a case study or your Calendly]
[Your mailing address]
Not relevant? Just reply "no thanks" and I won't follow up.
```

**A filled-in example:**
```
Subject: Sarah, RealtyCo's growing support team

Hi Sarah,

I noticed RealtyCo grew its support team to 4 people,
which tells me request volume has gone up.
We automated routine questions for a real estate agency,
with this result: [a real metric from your own case study; for example: 22 hours a week freed up, response time down from 4 hours to 8 minutes].

Could I show you how it works in 15 minutes?

James Miller
https://calendly.com/[your-name]/15min
[mailing address]
Not relevant? Just reply "no thanks" and I won't follow up.
```

---

## Quick reference: cold outreach metrics

| Metric | What it shows | If it's low |
|---|---|---|
| Open rate (email) | whether your subject line and domain reputation are working | change the subject line; check your domain and warm-up |
| Reply rate | whether your text and personalization are working | strengthen the first line and the pain point |
| Positive reply rate | whether you reached the right audience | rethink your contact list |
| Conversion to a call | whether your call to action works | make the question simpler; suggest a specific time |
| Emails before a reply | how many touches it takes | rethink your follow-up sequence |

Take your benchmarks from your own CRM spreadsheet: your baseline from the first 2 weeks matters more than anyone else's numbers. Only outreach platforms show an open rate; if you send by hand from your regular email, watch your replies instead. If the open rate is low, the problem is the subject line. If the open rate is fine but replies are few, the problem is the text.

---

## Common mistakes

- **Sending a template without a personalized first line.** "Hi! We offer AI solutions" gets almost no replies. "I see you grew your team to 4 people" gets noticeably more. One line changes a lot.
- **Selling in the first email.** The first email isn't a sale; it's a question. "Is this relevant for your situation?" works better than "Buy our automation."
- **Skipping follow-ups.** A good share of replies come after the 2nd or 3rd email. One follow-up a few days later usually brings in more replies.
- **Sending mass email from Gmail.** High volume from a Gmail account can easily get you flagged as spam and blocked. To scale, use specialized platforms (Instantly, Lemlist).
- **No CRM.** Even a simple Google Sheet with a few columns is better than nothing. Without tracking, you don't know whom you wrote to, when, or who replied.

---

## Related lessons

- **→ [Cold outreach in 2026](39c-cold-outreach-deep.md)**: the next lesson: channels, sequences, the legal side
- **→ [First clients](38-monetization-clients.md)**: already covered: start with warm contacts, then add cold ones
- **→ [Portfolio and case studies](41-portfolio-case-studies.md)**: already covered: a link to a case study in your signature helps more people say yes
- **→ [Lead generation system](39-lead-generation.md)**: an optional library lesson on building a contact list automatically

---

## Tools and resources

- **LinkedIn Sales Navigator**: [business.linkedin.com/sales-solutions](https://business.linkedin.com/sales-solutions). For finding decision-makers (check the website for free trial terms)
- **Hunter.io**: [hunter.io](https://hunter.io/). Finds email addresses by company domain (the free plan includes 50 credits a month, as of October 2026)
- **Apollo.io**: [apollo.io](https://www.apollo.io/). A database of B2B contacts with email verification and enrichment (filling in missing details about a contact)
- **Instantly.ai**: [instantly.ai](https://instantly.ai/). Cold email automation with domain warm-up
- **Lemlist**: [lemlist.com](https://www.lemlist.com/). Personalized sequences and A/B tests
- **Google Sheets**: a simple CRM for your first 50 contacts
- **Calendly**: [calendly.com](https://calendly.com/). A booking link for your email signature (it ends the "when works for you?" back-and-forth)

---

## Key takeaways

> Personalization isn't "Hi, [Name]!". It's proof that you read about them. One specific detail from their profile noticeably raises your reply rate.

> 20 personalized emails usually work better than 200 template emails. Don't chase volume; chase relevance.

> Following up is normal, not pushy. A good share of replies come after the 2nd or 3rd email.

> Claude writes personalized first lines in seconds. You give it the facts; it gives you options. That noticeably cuts the time each email takes.

---

## Next lesson

→ [Cold outreach that gets replies: channels, sequences and the legal side](39c-cold-outreach-deep.md)

After that: [How to handle objections and close the deal](45b-closing-objections.md).
