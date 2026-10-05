# Making money with AI: 5 client cases, by the numbers

**Time:** about 30 min reading + 20 min practice

---

## The gist

Five X-rays. Each case is an X-ray of a client's business: you can see the problem, what's broken inside, the fix and the result in numbers. These are teaching examples: they show how a project like this is put together and how the math works, with the numbers, the tools, the mistakes and what worked.

If you've been searching for AI side hustles, this is what that kind of work can look like up close: a business with a problem, a build, and the math behind the price.

⚠️ **Important:** the numbers in these cases are illustrative. They're template calculations meant to teach you how to work out payback. They are not a report on real clients, not a typical result and not a promise of income. Your rates, project prices and timelines will be different. Plug your own numbers into the formula in the "ROI calculator" section.

You don't need to memorize the tool names in the "Stack" lines. What matters for now is three things: what the problem was, what was built, and how the payoff was calculated.

---

## Key concepts

- **ROI calculation**: how to work out what a project pays back to the client (ROI, return on investment: what the client gets back for the money spent)
- **Time-to-value**: how many days it takes before the client starts getting results
- **Client testimonial**: what a testimonial that helps you sell looks like (there's a sample in Case 1)
- **Recurring vs one-time**: a one-off project vs monthly support
- **A stack for each type of task**: what to use and why

---

## 5 cases with numbers

🎨 **Picture this:** the five cases are five routes through the same city. One city (AI automation), different routes (newsletters, leads, an assistant, content, a CRM). Each route shows where the traffic jams are, where the detours are and how long the trip really takes.

---

### Case 1: Newsletter automation for a digital agency

**Client:** a digital marketing agency with 12 clients and a team of 6

**Problem:**
Every Monday, a marketer spent 3 hours putting together weekly reports for 12 clients. The data was pulled by hand from Google Analytics, Meta Ads and Google Ads. They copied the numbers into a template, wrote comments and sent the reports out. Monotonous, tedious work, and mistakes happened.

**Cost of the problem:**
```
3 hours × 52 weeks = 156 hours a year
Marketer's rate: $45/hour
Annual loss: $7,020
Plus the risk of errors (it happened: a report went out with another client's data)
```

**Solution:**
A newsletter automation pipeline on Cloudflare Workers + Trigger.dev:
- Every Sunday at 11 p.m., Workers pull metrics from three services through their APIs (an API is a way for one program to request data from another)
- Claude Haiku writes the narrative part (trends, anomalies, recommendations)
- The system builds a PDF with Puppeteer
- A Slack bot sends the agency director a preview with two buttons: "Send to all" / "Edit"
- Google Sheets keeps a log of every send

**Stack:** Cloudflare Workers, Trigger.dev, Claude Haiku API, Google Analytics API, Meta Marketing API, Google Ads API, Puppeteer (PDF), Slack API, Google Sheets API

**Result:**

| Metric | Before | After |
|---|---|---|
| Time spent on reports | 3 hours/week | 10 min/week (review) |
| Annual cost | $7,020 | ~$600 (API costs) |
| Errors | 2-3 a month | 0 |
| When the client gets the first report | Mon 11 a.m. | Mon 7 a.m. (earlier) |

**Project finances:**
```
Development cost: $2,800 (Pro package)
API costs per month: ~$50 (Claude Haiku + services)
Payback: about 5 months: $2,800 / ($7,020 / 12 - $50)
First-year ROI: ($7,020 - $3,400) / $3,400 = 106%
  where $3,400 = $2,800 project + $600 API for the year
```

(The "Pro package" is the middle tier of a Basic/Pro/Enterprise lineup. A later lesson covers how to package your services this way.)

**Build time:** 9 business days

**Mistake along the way:** the Meta Marketing API required special permissions to read ad account data, and a full day went into setting up the OAuth flow (the sign-in-and-permission handshake between apps). The template now sets aside 2 days for API authentication.

**Testimonial (a typical one, written for illustration, not a real client quote):**
"The first time I saw the system send all 12 reports on its own on a Sunday night, I didn't believe it. I checked in the morning, and everything was right. Now our marketer spends Monday on real work."

---

### Case 2: A lead generation system for a B2B SaaS company

**Client:** a B2B SaaS company (it sells subscription software to other businesses, in this case project management software), 8 people, selling to small businesses in Latin America

**Problem:**
An SDR (sales development rep) searched LinkedIn for potential customers by hand, wrote personalized emails, sent them and kept the CRM (the software that tracks customers and deals) up to date. Each lead took 25-30 minutes. That's 8-10 leads a day at most. Conversion to a call: 8%.

**Cost of the problem:**
```
SDR salary: $3,000/month = $18.75/hour
8 leads × 30 min = 4 hours a day ≈ $75/day ≈ $1,500/month (half of the SDR's paid time)
Result: 160-200 leads a month, 13-16 calls
```

**Solution:**
A lead gen pipeline with Claude:
- It's started by hand with a command like "find 20 leads in [niche]"
- A subagent (a separate helper inside Claude Code with its own task) finds companies and contacts through Apollo.io, a paid database of business contacts with an official API
- A second subagent gathers details for personalization from public sources: the company's website, news, job openings. The program doesn't collect LinkedIn profiles: LinkedIn's rules prohibit that
- Claude Sonnet writes a personalized first email for each lead
- The system loads everything into HubSpot CRM
- The SDR sees 20 ready-to-go leads with personalized emails, reviews each one (2-3 minutes) and clicks "Send" personally

**Stack:** Claude Code (runs the subagents), Claude Sonnet API, Apollo.io API, HubSpot CRM API, Slack bot (notifications)

**Result:**

| Metric | Before | After |
|---|---|---|
| Leads per day | 8-10 | 40-50 (with 2 hours of SDR work) |
| Time per lead | 25-30 min | 2-3 min (review and send) |
| Conversion to a call | 8% | 14% (better personalization) |
| Calls per month | 13-16 | 112-140 (40-50 leads × 20 working days × 14%) |

**Project finances:**
```
Development: $3,200 (one-time project)
Monthly support: $400/month (monitoring + API updates)
API costs: ~$150/month (Claude Sonnet + Apollo)
Extra revenue from the new calls: the client ran those numbers themselves
```

**Build time:** 14 business days

**Mistake along the way:** the first version collected profile data from LinkedIn on its own, and the account was quickly restricted. LinkedIn's User Agreement explicitly prohibits collecting data with software and bots. The fix: automated collection from LinkedIn was dropped completely. Contacts come from Apollo.io through its official API, and the SDR opens a LinkedIn profile by hand when needed. That's now a rule of the template: before you launch, read the terms of every platform you take data from.

**Time-to-value:** the SDR got the first 20 ready-to-go leads on day 3 of development (an early look at the work in progress). This matters: the client sees progress early.

---

### Case 3: An executive assistant for a small-business CEO

🎨 **Picture this:** an AI executive assistant is a personal assistant who never gets sick and never takes vacation. It reads the email, prepares a briefing before every meeting and writes the reports. The CEO works on strategy; the assistant handles day-to-day operations. A person still reviews and approves the work.

**Client:** the CEO of a property management company: 15 properties, a team of 4

**Problem:**
The CEO spent 15-20 hours a week on operational routine: answering routine tenant questions by email, putting together weekly investor reports, scheduling meetings, preparing materials for negotiations. Strategic work got pushed to the weekends.

**Cost of the problem:**
```
CEO's rate: $150/hour (their own estimate)
15 hours of routine × $150 = $2,250/week ≈ $9,750/month ($117,000 a year)
Or put another way: 15 hours of routine = 15 hours not spent on strategy
```

**Solution:**
An executive assistant built on Claude, with three modules:

**Module 1: Email triage**
It checks incoming email every 30 minutes. Routine questions (payment status, a repair request, a question about lease terms) get an automatic answer from a knowledge base. Everything else gets sorted by priority and forwarded to the CEO in Slack with a short summary.

**Module 2: Weekly investor report**
Every Friday at 5 p.m., it pulls data from the bookkeeping spreadsheets and generates a structured investor report with the key metrics, anomalies and recommendations. The CEO reviews it and sends it.

**Module 3: Meeting prep**
One hour before a meeting (based on Google Calendar), it gathers the latest emails with that person, any deal history in the CRM, and relevant news if it's an outside partner. It packs all of that into a short briefing in Slack.

**Stack:** Cloudflare Workers (cron, meaning scheduled jobs), Claude Sonnet API, Gmail API, Google Calendar API, Slack bot, Airtable (property database), Google Sheets (financial data)

**Result:**

| Metric | Before | After |
|---|---|---|
| Hours of routine per week | 15-20 | 3-4 (review and approval) |
| Routine emails: response time | 4-24 hours | 15 minutes (automatic) |
| Investor report | 2-3 hours/week | 20 minutes of review |
| Meeting prep | 30-45 min | 5 min (the briefing is ready) |

**Project finances:**
```
Development: $5,500 (3 modules)
Monthly support: $750/month
API costs: ~$80/month
Savings for the client: ~$9,750/month (by the client's own estimate of an hour's worth)
Payback: less than 1 month
```

**Build time:** 18 business days (three modules, one after another)

**Key insight:** the CEO wanted to automate meeting scheduling, with AI suggesting time slots. After looking into it, they decided not to build it: it created a risk of conflicts for important meetings. Focusing on meeting prep turned out to be more valuable.

---

### Case 4: A content pipeline for a YouTube channel

🎨 **Picture this:** a content pipeline is a newspaper's assembly line. The newsroom puts out an issue every day: reporters gather the facts, a writer drafts the story, a layout editor puts the page together. The creator is now the editor-in-chief: they approve the topic and edit the final text. The pipeline handles the routine.

**Client:** an independent YouTube creator in personal finance, 180K subscribers

**Problem:**
Most of the creator's time went into pre-production: finding topics (5-6 hours), writing the script (4-6 hours), preparing the YouTube description and tags (1 hour), writing a thumbnail brief for the designer (30 min). Total: 11-14 hours before filming even started.

**Solution:**
A content pipeline in three stages:

**Stage 1: Topic research**
Once a week, a subagent analyzes YouTube trends in the niche through the YouTube Data API, Reddit (r/personalfinance) and Google Trends. Claude picks out 10 promising topics and explains each choice (search volume, competition, fit with the audience). The creator chooses 1-2 of them in 10 minutes.

**Stage 2: Script generation**
For the chosen topic, Claude Opus (a stronger, more expensive model, picked for quality) writes a full script in the channel's style, using 5 of the best past scripts as examples. Structure: hook → problem → main content (3-5 sections) → CTA (call to action). The creator spends 30-60 minutes editing instead of 4-6 hours writing.

**Stage 3: Distribution pack**
From the finished script, automatically: a YouTube description (SEO-optimized), 15 tags, a thumbnail brief for the designer, a thread for Twitter/X, and a short-form version for Shorts. All in 5 minutes.

**Stack:** Trigger.dev (weekly schedule), Claude Opus API (scripts), Claude Haiku API (distribution), YouTube Data API, Reddit Data API (access only after Reddit approves it), Google Trends (the official API is still in alpha, by application; without it the data is exported by hand), Slack (delivery)

**Result:**

| Metric | Before | After |
|---|---|---|
| Pre-production time | 11-14 hours | 2-3 hours |
| Videos per month | 4 | 6-7 |
| SEO quality | Subjectively "fine" | Structured around data |

**Project finances:**
```
Development: $2,400 (Pro package)
Monthly support: $350/month (updates as the platforms change)
API costs: ~$120/month (Claude Opus for scripts costs more)
Payment model: one-time development + monthly support = more predictable revenue
```

**Build time:** 11 business days

**Mistake along the way:** the first scripts from Claude were too "polished" and didn't sound like this particular creator. The fix: add 3-5 transcripts of the channel's best videos to the context. After that, the style matched about 80%.

---

### Case 5: A CRM integration for a real estate agency

**Client:** a real estate brokerage with 8 agents and 40-60 active deals at any given time; many of its clients message their agent on WhatsApp

**Problem:**
Agents moved client data by hand between WhatsApp, email, the CRM (HubSpot) and the Google Sheets reports. Every client interaction meant updating three places. Some data got lost. The managing broker couldn't see an up-to-date, real-time picture of the deals.

**Solution:**
An integration hub on Cloudflare Workers:

**Webhook listener:** the WhatsApp Business API sends every message to a Workers endpoint (a webhook is an automatic notice one app sends another when something happens). Claude classifies it: is this a new lead or an existing client? A price question? A request for a showing? A meeting confirmation?

**CRM auto-update:** based on that classification, the record in HubSpot updates automatically: deal stage, date of last contact, a summary of the conversation (Claude writes 2-3 sentences).

**Manager dashboard:** a Google Sheet with formulas shows in real time: deals by stage, agents by activity, the most-requested properties, and deals that have "stalled" (no contact for more than 7 days).

**Alert system:** a Slack bot alerts the managing broker: a new hot lead, a deal with no movement, an agent with no activity for more than 24 hours.

**Stack:** Cloudflare Workers, Claude Haiku API (classification; it's cheaper), WhatsApp Business API, HubSpot API, Google Sheets API, Slack API

**Result:**

| Metric | Before | After |
|---|---|---|
| Time spent updating the CRM | 15-20 min/agent/day | ~0 (automatic) |
| How up to date the CRM data is | 60-70% (agents forgot) | 95%+ |
| Managing broker's time on status checks | 1-2 hours/day | 15 min/day |
| "Lost" leads | 5-8% (never entered) | ~0% |

**Project finances:**
```
Development: $4,200 (a complex integration, 4 APIs)
Monthly support: $600/month (the WhatsApp API needs monitoring)
API costs: ~$90/month
Savings: 8 agents × 20 min/day × 22 days × $25/hour = $1,467/month
Payback: about 3 months on the time saved alone ($4,200 / $1,467);
         about 5-6 months once support and API costs are subtracted:
         $4,200 / ($1,467 - $600 - $90)
```

**Build time:** 17 business days (4 of them went to Meta's business verification for the WhatsApp Business API)

**The main lesson:** you can start using the WhatsApp Business API right away, but with a starting cap on how many people you can message. To raise it, the agency went through Meta's business verification. Build a buffer of several business days for it into the timeline (in this case it took 4 days), and warn the client up front. One more thing: a system like this handles clients' personal data. The agency has to tell its clients about it and follow the privacy laws that apply to it.

---

## Patterns across all 5 cases

🎨 **Picture this:** the patterns from these cases are like traffic rules written after thousands of accidents. API authentication causing delays isn't bad luck; it's how this particular road works. Know the rule, and you steer around the pothole instead of hitting it.

| Pattern | What it means for you |
|---|---|
| Recurring revenue in 4 of 5 | Offer support: that's your stability |
| API authentication is the main delay | Add 3-5 days for integrations |
| Claude Haiku for classification | Saves money where deep understanding isn't needed |
| A chat app (Slack) as the delivery channel | Easiest for the client; no separate interface to build |
| "Show progress early" | Show an interim result on day 3-5 |

---

## Practice

**Exercise: an ROI calculation for your own potential project**

1. Pick one business owner or professional you know whose work problem you understand. (Later, in the lesson on first clients, you'll gather people like this into a list.)

2. Fill in the case template. For now, rough guesses are fine in the "Stack" and "Project price" lines: you'll come back to them in the modules on your offer and your price.
   ```
   Client (type): ____________
   Problem: ____________
   Hours per week spent on it: ___
   Hourly rate: $___
   Annual loss: $___
   
   Proposed solution: ____________
   Stack: ____________
   Expected reduction: ___%
   
   Project price: $___
   Monthly support: $___
   Payback: ___ months
   ```

3. Write a headline for the case with a golden number (the one number that shows the result at a glance)

4. Figure out which API could cause trouble (it requires verification, or has a complicated OAuth setup) and add days to the timeline

**Goal:** a finished ROI calculation for your first real conversation with a potential client.

---

## ROI calculator: a universal formula

🎨 **Picture this:** an ROI calculator works like a mortgage calculator on a bank's website. The client looks at the monthly payment and thinks, "I can afford that." You show them: invest $3,500 → save $23,000 a year → pay it back in 2 months. The calculator turns an abstract price into a concrete decision.

```
### ROI calculator for any project

Current cost of the process:
  [hours/week] × [rate $/hour] × 52 weeks = [annual cost of the problem]

Savings per year:
  [annual cost of the problem] × [expected reduction, %]

Cost of the automation:
  [one-time development] + [monthly support × 12] + [API costs × 12] = [annual cost of the solution]

ROI = (Savings - Cost of the solution) / Cost of the solution × 100%

Payback = Development cost / (Monthly savings - support - API) = [X months]
```

**Example (from Case 1):**
```
Annual cost of the problem: 3 h/week × $45/hour × 52 = $7,020
Annual cost of the solution: $2,800 + $0 support + $600 API = $3,400
ROI = ($7,020 - $3,400) / $3,400 = 106%
Payback = $2,800 / ($7,020/12 - $50 API) = 5.2 months
```

**Example (from Case 3, the executive assistant):**
```
Annual cost of the problem: 15 h/week × $150/hour × 52 = $117,000
Annual cost of the solution: $5,500 + $9,000 support + $960 API = $15,460
ROI = ($117,000 - $15,460) / $15,460 = 657%
Payback = $5,500 / ($9,750 - $750 support - $80 API) = 0.6 months
```

To keep things simple, both examples assume the automation removes all of the routine (a 100% reduction). In real life some time is still spent on review: in Case 1 it's 10 minutes a week. So in your own calculation, use the honest percentage from the template, or your ROI will come out inflated.

Build this calculation once in Google Sheets and use it in every sales conversation.

---

## Common mistakes

- **ROI in words, not on paper.** "You'll save a lot of time" doesn't convince anyone. "$23,040 a year in savings on a $3,500 investment, paid back in 2 months" does. Show an Excel or Google Sheets file with the formulas.
- **Inflating the ROI.** If the automation really covers 70% of the work, don't say 100%. An honest ROI builds trust. And if the client sees the real result beat what you promised, they'll tell their friends.
- **Leaving API costs out of the math.** Claude API, data-collection services like Apify, paid contact databases like Apollo: all of it costs money. $50-150/month for APIs: always include it in the cost of the solution you show the client.
- **Ignoring opportunity cost.** A CEO spending 15 hours on routine = 15 hours NOT spent on strategy. The cost isn't only $150/hour × 15; it's also the deals and decisions that never happened.

---

## How this connects to other lessons

- **→ [Pricing](39-monetization-pricing.md)**: the ROI formula from this lesson is the foundation for value-based pricing
- **→ [Portfolio and case studies](41-portfolio-case-studies.md)**: these 5 cases are templates for your own case studies
- **→ [Factory Model](48-factory-model.md)**: the patterns from these cases are the foundation for the Factory templates

---

## Tools and resources

- **Trigger.dev**: [trigger.dev](https://trigger.dev/): runs tasks on a schedule; has a free plan (the terms are on the service's pricing page)
- **Apollo.io**: [apollo.io](https://www.apollo.io/): a database of business contacts with an official API, for lead gen projects
- **HubSpot**: a CRM with a free tier and an API
- **WhatsApp Business API**: through [Meta for Developers](https://developers.facebook.com/); you can start without business verification, but with a starting cap on how many people you can message. Business verification is one of the ways to raise the cap; Meta sets the timeline, so build in a buffer
- **Claude API pricing**: [platform.claude.com/docs/en/about-claude/pricing](https://platform.claude.com/docs/en/about-claude/pricing): for accurate API costs in your ROI math; a summary is on the [What's current](https://aimayak.com/en/now/) page
- **Google Sheets**: for building your ROI calculator (build it once, use it for every client)

---

## Key takeaways

> Recurring revenue is what makes the business stable. Only one of the 5 cases is a one-off. Always offer monthly support.

> API authentication is the main source of delays. Build in a buffer, and warn your clients.

> Show results early. Give an interim demo on day 3-5. The client sees progress, and trust grows.

> An ROI calculation is more convincing than general promises. Numbers remove doubt, as long as they're honest.

---

## Next lesson

→ [100+ AI business ideas](100-ai-business-ideas-smb.md): a reference of ideas; pick the niche you'll start with
