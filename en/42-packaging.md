# Packaging your AI services into three clear offers

**Time:** about 30 min reading + 30 min practice

The dollar amounts in the examples below are made up. They show how packages are structured, not market prices or an income forecast. Work out your own price in the next lesson, [Value-based pricing](39-monetization-pricing.md).

---

## The gist

Without a menu, a client doesn't know what to order or what it costs. They ask, "So what can you do?", you launch into a long explanation, and the conversation goes nowhere. Packages are your menu: three clear options, each with a clear list of what's inside and a price. The client picks one on their own, and you don't have to haggle at every step.

---

## Key concepts

- **Service vs. product**: a service is different every time, a product is repeatable. Packages make a service work more like a product
- **3 packages**: the psychology of choice. Three options are usually easier to choose from than one, or five or more (a working hypothesis, not a law)
- **Scope**: a clear list of what's included and what's NOT. Without it, scope creep (the project quietly growing past what you agreed to) is inevitable
- **SLA**: a Service Level Agreement. Response time, uptime (how reliably the system keeps running), how support works
- **Handoff documentation**: what the client gets besides the system itself: instructions, training, logins and access
- **Pricing tiers**: price levels that reflect the amount of work, the speed and the level of support

---

## Theory

### Service vs. product: what's the difference

**A service** (the way freelancers usually sell):
- Every project is negotiated from scratch
- The price is unknown until you've estimated the job
- The client doesn't know what they'll get
- Hard to scale, because every job is new

**A productized service** (packages):
- The client sees the options in advance
- The price is known before the first call
- A clear scope of what's included
- Easier to deliver, because you reuse templates and what you learned on past projects

🎨 **Picture this:** a restaurant menu. The chef can cook hundreds of dishes, but the menu lists 30, each with a price. The customer picks one. They don't wonder "what's even possible here?" and they don't haggle over the price of every ingredient.

---

### The psychology of three packages

🎨 **Picture this:** three cup sizes at a coffee shop: small, medium, large. The small looks tiny next to the large. Plenty of people order the medium, because it feels like "the sensible choice." You design that perception on purpose.

Behavioral economics describes several effects that tiered pricing is built on (the decoy effect is covered in Dan Ariely's book *Predictably Irrational*). Here's a working hypothesis worth testing with your own clients:

- With **one option**, the client thinks "should I buy this or not?"
- With **three options**, the client thinks "which of the three should I buy?"
- With **five or more options**, choice paralysis can set in, and the client puts off the decision

People often pick the middle option (this is called the compromise effect). The top package makes the middle one look "reasonable," and the bottom one highlights the value of the middle one. How well this works in your market is something your own sales will show you.

**Your goals when you design packages:**
- Bottom package (Basic): genuinely useful, but with obvious limits
- Middle package (Pro): the one you want to sell most often
- Top package (Enterprise): makes Pro look reasonable, and also genuinely fits larger clients

---

### Sample structure for three packages: newsletter automation

| | Basic | Pro | Enterprise |
|---|---|---|---|
| **Price** | \$800 | \$2,200 | \$5,000 |
| **What we build** | Basic newsletter | Newsletter + CRM (a customer database) | Newsletter + CRM + analytics + A/B testing (comparing two versions of an email) |
| **News sources** | 1 (Perplexity) | 3 (Perplexity + RSS + custom) | Unlimited |
| **Recipients** | Up to 500 | Up to 5,000 | Unlimited |
| **Infographics** | ❌ | ✅ (basic) | ✅ (custom) |
| **Branding** | Template | Matched to your brand | Fully custom |
| **Documentation** | README | Video walkthrough | SOP + team training |
| **Support** | 2 weeks by email | 1 month in Slack | 3 months + 4-hour SLA |
| **Timeline** | 5 days | 10 days | 3-4 weeks |

---

### What's in scope: be specific

🎨 **Picture this:** a scope document is like a menu with a price next to every dish. "Everything included" with no list means the client orders dessert, then another dessert, then says, "But you said everything was included." With a clear menu, they know what comes with the combo and what costs extra.

Scope creep is a common reason projects end up losing money. Along the way, the client asks for "small changes" that together double the amount of work.

**Rule:** if the agreement doesn't explicitly list something as included, it isn't included.

**Scope document template** (this is a structure, not a legal document; have a lawyer look over your client contract):

```markdown
## Project: Newsletter Automation, Pro Package

### Included:
- Setup and launch of the main workflow
- Integration with Perplexity, RSS news feeds (up to 3 sources) and your domain
- HTML email template matched to your brand guidelines
- Slack bot to approve each issue before it goes out
- Google Sheets log of every send
- Integration with your CRM (Notion, HubSpot or Airtable, your choice of one)
- Video walkthrough (Loom, ~20 min): how to use the system
- 30 days of support in Slack (reply within one business day)

### NOT included in Pro (available as a separate upgrade):
- More than three news sources
- A/B testing of subject lines
- Analytics dashboard
- Integration with email marketing platforms (Mailchimp, SendGrid); Pro sends through Gmail only
- Translating emails into multiple languages
- Custom infographics (basic AI-generated ones are included)

### Terms:
- Payment: 50% upfront / 50% after the demo and sign-off
- Timeline: 10 business days from receipt of the deposit and access
- Revisions: up to 2 rounds included
```

---

### SLA: keep it simple

🎨 **Picture this:** an SLA is like your deal with a plumber. "If a pipe bursts at night, I'll be there within 4 hours. Routine maintenance happens during business hours." The client knows what to expect. You know what you've committed to. No unpleasant surprises.

An SLA doesn't have to be a legal document. For a small business, three parameters are enough:

**1. Response time to questions:**
- Basic: reply within 2 business days by email
- Pro: reply within one business day in Slack
- Enterprise: reply within 4 hours, weekends included

**2. Uptime (for systems that keep running on their own):**
- If the system stops working, I let you know within 2 hours (during business hours)
- Fix: within one business day for critical problems

**3. What's not covered:**
- Outages on third-party services (Anthropic API, Gmail API and so on)
- Changes to third-party APIs that break the integration (that's a separate job)

---

### Handoff documentation: what the client gets

🎨 **Picture this:** documentation is like the manual for a washing machine. The owner has no idea what's inside the motor. But if the manual says "press button 2 when you see error E3," they can handle it themselves. Your goal: the client should be able to run the system without calling you.

A good handoff is what sets a professional apart from the average freelancer. There are three levels:

**Basic: README.md (written instructions)**

```markdown
# Newsletter Automation: Instructions

## How to send the newsletter
1. Open Slack and message the bot: "Start newsletter"
2. Enter this week's topic
3. Wait for the preview (usually 2-3 minutes)
4. Review the email and click "Send" or "Edit"

## Where to see the stats
Open Google Sheets: [link]
Columns: Date, Topic, Recipients, Status

## What to do if something isn't working
1. Check that the API keys in Cloudflare haven't expired (every 90 days)
2. Message me: [contact]. I'll reply within one business day
```

**Pro: video walkthrough (Loom, 15-20 minutes; Loom's free plan limits video length, so check the terms)**

A screen recording where you show:
- How to run the workflow
- How to add a new recipient
- Where to find the logs and stats
- How to update the brand guidelines
- What to do if something breaks

**Enterprise: SOP (Standard Operating Procedure)**

A complete operations document for the client's team. It includes instructions for each role, escalation procedures, a runbook (a step-by-step playbook) for unusual situations, and support contacts.

---

### Upselling through packages: the natural path

🎨 **Picture this:** upselling (selling more to a client you already have) through packages works like an auto shop. You came in for an oil change, and the mechanic shows you that your brake pads will need replacing soon too. You're already there and you already trust them, so it makes sense. A client's backlog (their wish list for later) is your list of "almost worn-out brake pads" you noticed while doing the work.

Packages create natural points for growth:

```
Basic client, 2 months later:
"The system works great. Can we add A/B testing for subject lines?"
→ Upgrade to Pro, or a separate add-on at its own price

Pro client, 3 months later:
"We need a dashboard for our marketing director"
→ Upgrade to Enterprise, or a separate analytics project
```

For each client, keep a backlog of everything they mentioned as "it would be nice to have." That's your list of upsell opportunities.

---

## Practice

**Exercise: create packages for your own service**

Take a service you want to offer clients (for example, the idea you picked in the niche lessons) or a project you've already built.

1. Fill in the three-package table:

| Parameter | Basic (\$___) | Pro (\$___) | Enterprise (\$___) |
|---|---|---|---|
| Core features | | | |
| Limits | | | |
| Documentation | | | |
| Support | | | |
| Timeline | | | |

2. Write a scope document for the Pro package:
   - An "included" list (at least 5 items)
   - A "NOT included" list (at least 3 items)
   - Payment and revision terms

3. Create an SLA for Pro (3 parameters: response time, uptime, what's not covered)

4. Write a README template for the Basic package: how the client will use the system without you

**Goal:** a ready-made menu of three packages you can send to a potential client before the first call.

---

## Quick reference: package matrix (a universal template, made-up amounts)

| Parameter | Basic (\$500-\$1,500) | Pro (\$1,500-\$5,000) | Enterprise (\$5,000-\$15,000) |
|---|---|---|---|
| **Features** | Basic workflow, 1 integration | Full workflow, 2-3 integrations | Everything + custom modules |
| **Customization** | Template design | Matched to the client's brand | Fully custom |
| **Data sources** | 1 | 2-3 | Unlimited |
| **Documentation** | Written README | Loom video + README | SOP + team training |
| **Support** | 2 weeks by email | 1 month in Slack (reply within a business day) | 3 months + 4-hour SLA |
| **Revisions** | 1 round | 2 rounds | 3 rounds + review |
| **Timeline** | 3-5 days | 7-10 days | 2-4 weeks |
| **Payment** | 100% upfront | 50/50 | 30/40/30 |

Copy this table and adapt it to your own service. The middle package (Pro) is the one you want to sell most often.

---

## Common mistakes

- **The same features in Basic and Pro.** If the only difference is "support," the client will take Basic. Basic should WORK, but with obvious limits (1 source, template design, minimal support).
- **Not listing what's "NOT included."** The "NOT included" list protects you from scope creep. Without it, the client assumes "everything is included."
- **Price gaps that are too big.** Basic \$500 → Enterprise \$15,000, and the client can't see the logic. Basic \$800 → Pro \$2,200 → Enterprise \$5,000 is a progression that makes sense.

---

## Related lessons

- **→ [Value-based pricing](39-monetization-pricing.md)**: the next lesson, on working out the base for your package prices from the value to the client
- **→ [The factory model](48-factory-model.md)**: templates speed up delivering packages and raise your margin (what's left for you after costs); a later lesson
- **→ [Delivery and retention](46-delivery-retention.md)**: how to hand a package over to the client professionally; a later lesson

---

## Tools and resources

- **Notion**: [notion.com/templates](https://www.notion.com/templates). For a public page with your packages (you can embed it in your portfolio)
- **Google Docs**: for scope documents (easy to share with the client for review)
- **Loom**: [loom.com](https://www.loom.com/). For recording the video walkthrough for the Pro package (the free plan has limits; see the website)
- **PandaDoc / Docusign**: for e-signing the scope document (once your volume grows)
- **Stripe**: [stripe.com](https://stripe.com/). Takes payments; you can create a Payment Link for each package. Stripe isn't available in every country; check the list on its site
- **Tally**: [tally.so](https://tally.so/). Intake forms, with a free plan (the client fills out a questionnaire before the project starts)
- **Calendly**: [calendly.com](https://calendly.com/). A link to book a call, right on your packages page

---

## Key takeaways

> Three packages aren't arbitrary. People often find it easier to choose from three options than from one or five. Many will take the middle one.

> A scope document protects both sides. The client knows what they'll get. You know what to build. No disappointments.

> An SLA doesn't have to be a legal document. Three simple parameters (response time, uptime, what's not covered) are enough for a small business.

> Keep an upsell backlog. Every "it would be nice to have" from a client could be your next contract. Write it down.

---

## Next lesson

→ [How to price AI services: value-based pricing](39-monetization-pricing.md)
