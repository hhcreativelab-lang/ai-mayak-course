# Zapier AI: thousands of apps and smart Zaps with AI

**Time:** about 20 min reading + 30 min practice

---

## The gist

Imagine you have a universal interpreter who speaks the languages of thousands of different programs at once. Gmail speaks its own language, Notion speaks another, Stripe yet another. Zapier is that interpreter: it picks up a signal from one app and passes it to another, switching "languages" along the way. The AI steps in Zapier are the interpreter's brain. Instead of mechanically forwarding data, it decides what to say and how: it analyzes, sorts, writes a reply, makes a decision.

🎨 **Picture this:** Zapier without AI is a mail carrier. It picks up an envelope here and drops it off there. Zapier with AI is a sharp office assistant. It takes the letter, reads it, gets the point, writes a reply in the right tone and sends it to the right person. That's the difference between mechanics and intelligence.

In this lesson you'll learn Zapier AI, one of the best-known no-code tools. You'll learn to build Zaps with AI steps, see when Zapier beats its competitors, and create your first smart automated workflow without a single line of code.

---

## Key concepts

- **Zap**: an automation with 2 or more steps: a trigger (an event) + an action (what to do)
- **AI by Zapier**: a built-in step that calls Claude or ChatGPT right inside a Zap
- **Zapier Agents**: autonomous agents in Zapier that work without a manual trigger
- **Zapier Tables**: Zapier's built-in database, which can also run AI analysis
- **Webhook**: a universal way to receive data from any source (even one with no official integration)
- **Task**: the billing unit. A Zap's actions use up tasks every time it runs (see Zapier's help center for exactly how they're counted)
- **Multi-step Zap**: a Zap with 3 or more steps (paid plans only), and where the real work happens

---

## Theory

### Zapier vs Make vs n8n: which to choose when

There are three main players in no-code automation. Each one has its own niche.

| Criterion | Zapier | Make | n8n |
|---|---|---|---|
| Integrations | Thousands of apps (see Zapier's site) | Thousands of apps (see Make's site) | hundreds of ready-made nodes + HTTP |
| Learning curve | Minimal | Medium | Steep |
| Free plan | 100 tasks/month, two-step Zaps only | 1,000 credits/month | Community Edition on your own server |
| Paid plans start at (as of October 2026) | $19.99/month billed yearly (750 tasks) | Core from $9/month billed monthly (10,000 credits) | Cloud Starter €20/month billed yearly (2,500 executions) |
| AI steps | Built in (AI by Zapier, Agents, Copilot) | Make AI Agents | AI Agent and LLM nodes, MCP |
| Who it's for | Non-technical people, small businesses | Technical users, complex scenarios | Developers, privacy-first teams |
| Where it runs | Cloud | Cloud | Self-hosted or cloud |

Current prices and versions: [What's current](https://aimayak.com/now/).

🎨 **Picture this:** Zapier is like an iPhone. It costs more, but it works right out of the box, it looks good, and there's an app for everything. Make is like Android: cheaper, more flexible, and it takes a bit of figuring out. n8n is like Linux: full control, but you'll have to roll up your sleeves.

**When Zapier wins:**

- The client wants "set it up and go, I'll take it from here": Zapier is the most intuitive
- You need an unusual integration (a custom CRM, a local service): thousands of ready-made integrations have you covered
- Support and uptime guarantees matter: check the terms of the plan
- A team with no technical background will be adjusting the Zaps themselves

**When Make or n8n wins:**

- You need complex branching with hundreds of thousands of operations a month: Make is cheaper
- The data can't pass through outside servers: self-hosted n8n
- The budget is tiny and there aren't many tasks: Make's entry-level paid plan covers a lot of needs

---

### AI by Zapier: the brain inside a Zap

"AI by Zapier" is the official step in the Zap editor that calls a language model (one of those available in Zapier, such as Claude or ChatGPT) with your prompt and the data from earlier steps.

**What AI by Zapier can do:**

- Analyze text (an email, an inquiry, a review)
- Classify data (hot lead or cold lead, positive review or negative)
- Generate text (a draft reply to an email, a product description)
- Extract structured data (pull a name, a company and a budget out of messy text)
- Translate and adapt content

**What it looks like in the editor:**

The "AI by Zapier" step has two fields:

- **Prompt**: your request to the AI (you can insert data from earlier steps with `{{variable}}`)
- **Response**: the AI's answer, which flows into the next steps

An example prompt for classifying a lead:
```
Analyze this inquiry from our website:
Name: {{Name}}
Company: {{Company}}
Message: {{Message}}

Determine:
1. Lead temperature: hot / warm / cold
2. Budget: stated / not stated / large (>$10k)
3. Next step: call today / send an email / mark as spam

Reply with JSON only:
{"temperature": "...", "budget": "...", "next_step": "..."}
```

The AI processes the inquiry and returns JSON, which the next step parses to send a notification to the right sales rep.

🎨 **Picture this:** a new inquiry from your website used to land in the CRM and sit there until a sales rep found time for it. Now AI reads it in seconds, tags it "hot" and sends the rep a push notification that says "call right now." The sooner someone calls a hot lead, the better the odds of closing the deal.

---

### Zapier Agents: autonomous work without triggers

Zapier Agents is a feature that goes beyond classic Zaps. An agent is an AI that:

- Runs continuously, without anyone starting it by hand
- Can decide on its own which tools to use (read Gmail, post in Slack, add a contact to a CRM)
- Remembers its past actions
- Takes instructions in plain language

**A real agent example:**
"You're my sales assistant. Every time an email labeled 'from a lead' arrives in Gmail, read it, write a short summary, look up information about the company, add the contact to HubSpot and send me a Slack notification with a short plan for the call."

That's one agent replacing 4-5 manual Zaps, and it works more intelligently: it understands context instead of just shuffling data from place to place.

**Limitations of Agents:**

- They're billed separately from regular Zap tasks (check Zapier's pricing page for how)
- They're less predictable (the AI makes its own decisions)
- They're a worse fit for tightly defined processes

For most business tasks, classic Zaps with AI steps are the best choice: they're predictable, transparent and cheap.

---

### Zapier Tables + AI: a database with brains

Zapier Tables is a built-in, spreadsheet-style database that connects natively to Zaps. Add a record → a Zap starts automatically. The Zap processes the data → the result goes back into the table.

**Case: a customer database with AI enrichment:**

1. A customer fills out a form → a new record in Zapier Tables
2. Trigger: new record → the Zap starts
3. AI step: from the name and company, generate a hypothesis about what the customer needs
4. Enrichment step: a data-enrichment service adds information about the company
5. The result is written back to the table in an "AI analysis" field
6. A sales rep opens the table, and every lead already has context

No outside database, no code. Everything lives in one tool.

---

### Key use cases

**1. CRM enrichment and lead routing**

A lead comes in through a website form → AI classifies it by temperature, budget and industry → hot leads go to the top sales rep in Slack, cold ones go into an email drip sequence in Mailchimp, and spam gets deleted.

**2. Content distribution**

A new post in Notion (a draft) → AI by Zapier adapts it for a Facebook page (short, with emoji) → another AI step adapts it for LinkedIn (a professional tone) → it's published to both channels automatically.

**3. Email triage**

A new email in Gmail → AI reads it and classifies it: client / partner / spam / urgent → urgent client emails trigger a text message (SMS) to your phone, and a draft reply written by the AI is already waiting, so all that's left is to hit "Send."

**4. Reviews and reputation**

A new review on Google Maps → AI analyzes the tone → negative: a notification to the manager + a draft reply → positive: published on your website automatically through the CMS.

**5. Financial monitoring**

A new transaction in Stripe → AI checks it for anomalies (an unusual amount, a new region, a first purchase) → if something's off → a Slack notification with a risk analysis.

---

### What it really costs

**Zapier Free:** 100 tasks/month, two-step Zaps only. Good for learning.

**Zapier Professional:** as of October 2026, from $19.99/month billed yearly ($29.99 billed monthly), 750 tasks, multi-step Zaps, AI by Zapier. This is the minimum for real-world scenarios.

**Zapier Team:** as of October 2026, from $69/month billed yearly ($103.50 billed monthly), more tasks, multiple users (up to 25).

Current prices and versions: [What's current](https://aimayak.com/now/).

**Billing pitfalls:**

- A Zap's actions use up tasks on every run. Simple math: a 5-step Zap that runs 100 times a day = 500 tasks a day = 15,000 tasks a month. The starting allowance on paid plans won't cover that.
- AI steps are billed separately: per step and per tool call (terms on the pricing page)
- Keep an eye on your usage in the Zapier dashboard, and set limits on your Zaps

**A realistic estimate for a small business:**

- 5-10 Zaps
- Each one runs 20-50 times a day
- Average Zap length: 3-4 steps
- Total: about 3,000-6,000 tasks/month. That's more than the starting allowance on paid plans, so you'll need to choose a larger task volume and check its price on the pricing page

---

### "Zapier as a service": selling automation

Not every client needs code. Many of them just need automations that work.

**What to sell:**

*Package 1: "Starter" (one-time):*

- An audit of the client's current manual processes
- 3-5 basic Zaps (no AI)
- Setup and handing over access
- 30 days of support

*Package 2: "AI automation" (one-time):*

- The same, but with AI by Zapier on the key steps
- CRM enrichment or email triage
- Documentation and team training

*Package 3: "Retainer" (monthly):*

- 2-3 hours a month refining Zaps
- Error monitoring
- Adding new automations as the client grows

**Where to find clients:**

- Small businesses with a team of 3-15 people: they're often buried in manual tasks
- E-commerce stores on Shopify or WooCommerce: lead generation, abandoned carts, reviews
- Agencies and firms (marketing, real estate, law): lots of repetitive work with documents

**The key sales argument:**
"I'll save your office manager N hours a week. Multiply N by what an hour of their time costs and by four weeks: that's your monthly savings. Compare it with my price and the cost of the Zapier plan." Run the numbers honestly with the client's own data, and don't promise savings you can't back up. To work out your price, see the lessons [Packaging your AI services](42-packaging.md) and [How to price AI services](39-monetization-pricing.md).

---

### Webhooks: receiving data from any source

A webhook in Zapier is a unique URL that any program can send any data to. If your app doesn't have an official Zapier integration, that's not a problem.

**How it works:**

1. You create a Zap with the "Webhooks by Zapier" trigger
2. Zapier gives you a unique URL like `https://hooks.zapier.com/hooks/catch/1234567/abc123`
3. Any app that can make an HTTP POST request can send data to that URL
4. The data arrives in the Zap and moves on through the next steps

**A practical example:**
A client has a custom CRM built on WordPress, with no Zapier integration. A developer adds one line of PHP: when a new lead comes in, send an HTTP POST with the contact's details to the Zapier webhook. From there, Zapier runs the data through AI and sends notifications to Slack or by text message. Thirty minutes of work for the developer. A working automation for the client.

---

### Zapier vs Claude Code: when to use which

This isn't a competition. They're two tools for different jobs.

| Scenario | Tool |
|---|---|
| Connecting 2 popular SaaS apps with no custom logic | Zapier |
| The client's budget is tight and it has to be fast | Zapier |
| The client wants to edit the automations themselves | Zapier |
| Complex custom logic, unusual data | Claude Code |
| You need full control and your own server | Claude Code |
| The job needs a complex UI or a dashboard | Claude Code |
| A very high volume of operations (expensive on Zapier) | Claude Code |
| You need an integration with an unusual API | Claude Code + Webhook |

**The golden rule:** start with Zapier. If you run into the limits or the complexity gets out of hand, move to code. As long as the scenario is simple, paying for a Zapier plan is usually cheaper for the client than custom development from scratch.

---

### A real Zap: Email → CRM → Slack

**The task:** new emails from potential clients automatically land in the CRM with an AI analysis, and the sales rep gets a notification.

**Setup:**

```
TRIGGER: Gmail → New Email (Matching Search: "label:potential-client")
↓
STEP 2: Formatter by Zapier → Extract from Text
  → Extract: Name, Company, Phone
↓
STEP 3: AI by Zapier → "Analyze this email and rate lead quality"
  Prompt:
  """
  Email from: {{Sender}}
  Subject: {{Subject}}
  Body: {{Body}}
  
  Rate this lead on a scale of 1-10 and explain why.
  Return JSON: {"score": N, "reason": "...", "next_action": "call/email/ignore"}
  """
↓
STEP 4: HubSpot → Create/Update Contact
  → Name: {{Step 2 - Name}}
  → Company: {{Step 2 - Company}}
  → Note: {{Step 3 - AI Response}}
  → Tag: "AI score: {{score}}"
↓
STEP 5 (condition): Filter by Zapier → Only if score >= 7
↓
STEP 6: Slack → Send Message to #sales
  → "Hot lead: {{Name}} from {{Company}}
     Score: {{score}}/10
     Reason: {{reason}}
     Action: {{next_action}}
     Email: {{Gmail Link}}"
```

Setup time: about an hour the first time. How much time it saves your sales rep depends on how many emails come in, so work it out from your own numbers.

---

## Practice

### Step 1: Create an account and your first Zap

1. Go to [zapier.com](https://zapier.com) → Sign up (a free account)
2. On the dashboard, click **"+ Create"** → **"Zap"**
3. You're now in the Zap editor. The steps are on the left, the settings on the right

### Step 2: Set up the trigger

1. Click the first step (Trigger)
2. Choose **Gmail** (or any app you use)
3. Event: **New Email**
4. Connect your Gmail account (click "Sign in")
5. Set up the filter: Label = "Inbox"; you can leave From empty
6. Click **"Test trigger"**: Zapier shows your most recent email as sample data

### Step 3: Add an AI step

1. Click **"+"** after the trigger
2. Search for **"AI by Zapier"**
3. Action: **Analyze or generate text**
4. In the **Prompt** field, type:
   ```
   You're a sales assistant. Analyze this email:
   
   From: {{From Name}}
   Subject: {{Subject}}
   Body: {{Body Plain}}
   
   Write a short summary (2-3 sentences) and decide: is it worth replying to?
   Answer: [summary] | Priority: High/Medium/Low
   ```
5. Click **"Test action"** and look at what the AI generated

### Step 4: Send the result to Slack (or get it by email or text)

1. Add one more step with **"+"**
2. Choose **Slack** (to get an email or a text message instead, pick Gmail or an SMS app; the fields will be a little different)
3. Action: **Send Channel Message**
4. Channel: pick the one you want
5. Message Text:
   ```
   📧 New email from {{From Name}}
   
   {{AI by Zapier - Response}}
   
   Original: {{Message URL}}
   ```
6. Click **"Test action"**: the message will show up in Slack

### Step 5: Turn the Zap on and test it

1. At the top right, switch **"Zap is Off"** → **"Zap is On"**
2. Send yourself a test email from a different email address
3. Wait a few minutes (Zapier checks triggers on a schedule; how often depends on your plan)
4. Get the Slack notification with the AI analysis

Congratulations: your first smart Zap with AI is up and running.

**What to try next:**

- Add a filter: only process emails that contain certain keywords
- Connect Google Sheets: log every analyzed email in a spreadsheet
- Add a second AI step: automatically generate a draft reply

---

## Tools and resources

- **[Zapier](https://zapier.com)**: the main tool in this lesson. Free plan: 100 tasks/month; paid plans from $19.99/month billed yearly, as of October 2026.
- **[Make.com](https://make.com)**: an alternative for complex scenarios. It has a free plan: 1,000 credits a month.
- **[n8n.io](https://n8n.io)**: an alternative you can run on your own server. Cloud from €20 a month billed yearly; the Community Edition for self-hosting is free (under the Sustainable Use License).
- **[Zapier pricing](https://zapier.com/pricing)**: current plans and a task calculator.
- **[Zapier University](https://university.zapier.com)**: free courses on Zapier.
- **[AI by Zapier docs](https://help.zapier.com/hc/en-us/articles/16587495501453-Use-AI-by-Zapier)**: the official documentation for the AI step.

---

## Key takeaways

> "Zapier isn't just automation. It's a way to give any business AI features without a single line of code. Your value as a specialist is knowing which workflow the client needs and building it in hours, not weeks."

> "AI by Zapier turns a Zap from a mail carrier into a sharp assistant. Not just 'got an email → forwarded it,' but 'got an email → understood it → made a decision → acted.' That's the difference between automation and intelligence."

> "Zapier automation services don't require programming. You need to understand the client's business processes and know how to automate them. What you earn depends on your market and your clients; nothing is guaranteed."

---

## Next lesson

→ [AI sandboxes: E2B](80-ai-sandboxes-e2b.md): E2B and Modal for letting agents run code safely
