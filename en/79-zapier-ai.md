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
- **AI by Zapier**: a built-in step that calls a language model (you can choose models from OpenAI, Anthropic, Google and others) right inside a Zap
- **Zapier Agents**: Zapier's agents, which decide on their own which tools to use for a task. Zapier is now moving them into the AI by Zapier step
- **Zapier Tables**: Zapier's built-in database, which can also run AI analysis
- **Webhook**: a universal way to receive data from any source, even one with no official integration (paid plans)
- **Task**: the billing unit. Every action a Zap completes successfully uses tasks; the trigger doesn't (see Zapier's help center for exactly how they're counted)
- **Multi-step Zap**: a Zap with more than two steps. It's available on paid plans and during the free trial, and it's where the real work happens

---

## Theory

### Zapier vs Make vs n8n: which to choose when

There are three main players in no-code automation. Each one has its own niche.

| Criterion | Zapier | Make | n8n |
|---|---|---|---|
| Integrations | 9,000+ apps (per Zapier, October 2026) | 3,000+ apps (per Make, October 2026) | hundreds of ready-made nodes + HTTP requests to any service |
| Learning curve | Minimal | Medium | Steep |
| Free plan | 100 tasks/month, two-step Zaps only | 1,000 credits/month | Community Edition on your own server |
| Paid plans start at (as of October 2026) | $19.99/month billed yearly (750 tasks) | Core from $9/month billed monthly (10,000 credits) | Cloud Starter €20/month billed yearly (2,500 executions) |
| AI steps | Built in (AI by Zapier, Agents, Copilot) | Make AI Agents | AI Agent and LLM nodes, MCP |
| Who it's for | Non-technical people, small businesses | Technical users, complex scenarios | Developers, privacy-first teams |
| Where it runs | Cloud | Cloud | Self-hosted or cloud |

Current prices and versions: [What's current](https://aimayak.com/en/now/).

🎨 **Picture this:** Zapier is like an iPhone. It costs more, but it works right out of the box, it looks good, and there's an app for everything. Make is like Android: cheaper, more flexible, and it takes a bit of figuring out. n8n is like Linux: full control, but you'll have to roll up your sleeves.

**When Zapier wins:**

- The client wants "set it up and go, I'll take it from here": Zapier is the most intuitive
- You need an unusual integration (a custom CRM, a local service): thousands of ready-made integrations have you covered
- Support and uptime guarantees matter: check the terms of the plan
- A team with no technical background will be adjusting the Zaps themselves

**When Make or n8n wins:**

- You need complex branching and high volume: Make bills in credits, and at high volume it often comes out cheaper. Check both pricing pages with your own numbers
- The data can't pass through outside servers: self-hosted n8n
- The budget is tiny and there aren't many tasks: Make's entry-level paid plan covers a lot of needs

---

### AI by Zapier: the brain inside a Zap

"AI by Zapier" is a built-in step in the Zap editor. It sends a language model your prompt and the data from earlier steps. You can choose the model: models from OpenAI, Anthropic (Claude), Google and other companies are available.

**What AI by Zapier can do:**

- Analyze text (an email, an inquiry, a review)
- Classify data (hot lead or cold lead, positive review or negative)
- Generate text (a draft reply to an email, a product description)
- Extract structured data (pull a name, a company and a budget out of messy text)
- Translate and adapt content

**What it looks like in the editor:**

The "AI by Zapier" step has two panels:

- **Configure**: where you write your prompt (the Prompt field), pick a model and adjust settings. You insert data from earlier steps into the prompt by typing "/"
- **Preview**: a test run that shows what the step returns with real sample data

The AI's answer flows into the next steps. If you need to, you can split it into separate fields (the Output Fields section). In the examples below, double curly braces `{{...}}` mark the spot where you insert a field from an earlier step.

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

The AI processes the inquiry and returns its answer as JSON (a format for writing data so that programs can read it). The next step reads it and sends a notification to the right sales rep.

🎨 **Picture this:** a new inquiry from your website used to land in the CRM and sit there until a sales rep found time for it. Now AI reads it in seconds, tags it "hot" and sends the rep a push notification that says "call right now." The sooner someone calls a hot lead, the better the odds of closing the deal.

---

### Zapier Agents: AI that picks its own tools

Zapier Agents go beyond classic Zaps. An agent is an AI that:

- Starts on its own, on an event or on a schedule
- Can decide on its own which tools to use (read Gmail, post in Slack, add a contact to a CRM)
- Can look for answers in the knowledge sources you connect and on the web
- Takes instructions in plain language

**What's changing (as of October 2026):** Zapier is moving the standalone Agents product (agents.zapier.com) into the AI by Zapier step. You can now give that step tools (apps and knowledge sources), and it acts as an agent right inside a Zap. Zapier hasn't set a date for turning off standalone Agents and says it will email users well ahead of time.

**A real agent example:**
"You're my sales assistant. Every time an email labeled 'from a lead' arrives in Gmail, read it, write a short summary, look up information about the company, add the contact to HubSpot and send me a Slack notification with a short plan for the call."

That's one agent replacing 4-5 manual Zaps, and it works more intelligently: it understands context instead of just shuffling data from place to place.

**Limitations of Agents (as of October 2026):**

- The standalone Agents product is billed separately, in "activities" rather than tasks. An agentic AI step inside a Zap uses regular tasks
- They're less predictable (the AI makes its own decisions)
- They're a worse fit for tightly defined processes

For most business tasks, classic Zaps with AI steps are the better choice: they're more predictable, and you can see what happened at every step.

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

A new transaction in Stripe → AI checks it for anomalies (an unusual amount, a new region, a first purchase) → if something's off → a Slack notification with an explanation. The AI only flags it here; a person decides what to do about the payment.

---

### What it really costs

**Zapier Free:** 100 tasks/month, two-step Zaps only. On this plan you can only try the AI step in an unpublished Zap. Good for getting to know the tool.

**Zapier Professional:** as of October 2026, from $19.99/month billed yearly ($29.99 billed monthly), 750 tasks, multi-step Zaps, webhooks, AI by Zapier. This is the minimum for real-world scenarios.

**Zapier Team:** as of October 2026, from $69/month billed yearly ($103.50 billed monthly), more tasks, multiple users (up to 25).

Current prices and versions: [What's current](https://aimayak.com/en/now/).

**Billing pitfalls:**

- Every completed action uses tasks; the trigger doesn't. An example: a Zap with a trigger and 4 actions that runs 100 times a day = 400 tasks a day = 12,000 tasks a month. The starting allowance on paid plans won't cover that.
- An AI step uses tasks with a multiplier: it depends on the model tier (Standard, Advanced, Premium), and every tool call is counted on top. On a paid plan, a new AI step defaults to Premium, the most expensive tier, so check it and pick the tier yourself. The multipliers are in Zapier's help article "AI by Zapier model tier pricing"
- Keep an eye on your usage in your Zapier account. An AI step has a task limit per run: if a run goes over it, the step pauses and waits for your approval

**A realistic estimate for a small business:**

- 5-10 Zaps
- Each one runs 20-50 times a day
- Each Zap has 3-4 steps: a trigger and 2-3 actions
- Total: from 6,000 tasks a month (5 Zaps × 20 runs × 2 actions × 30 days) to 45,000 (10 × 50 × 3 × 30). That's more than the starting allowance on paid plans, so you'll need to choose a larger task volume and check its price on the pricing page

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

A webhook in Zapier is a unique URL that any program can send data to. If your app doesn't have an official Zapier integration, that's not a problem. Webhooks are available on paid plans.

**How it works:**

1. You create a Zap with the "Webhooks by Zapier" trigger and the Catch Hook event
2. Zapier gives you a unique URL like `https://hooks.zapier.com/hooks/catch/1234567/abc123`
3. Any app that can make an HTTP POST request can send data to that URL
4. The data arrives in the Zap and moves on through the next steps

**A practical example:**
A client has a custom CRM built on WordPress, with no Zapier integration. A developer adds a few lines of code: when a new lead comes in, the contact's details are sent to the Zapier webhook's URL. From there, Zapier runs the data through AI and sends notifications to Slack or by text message. A small job for the developer, and a working automation for the client.

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
TRIGGER: Gmail → New Email Matching Search (search: "label:potential-client")
↓
STEP 2: Formatter by Zapier → Text → Extract Phone Number
  → Pull the phone number out of the email's text
↓
STEP 3: AI by Zapier (output fields: name, company, score, reason, next_action)
  Prompt:
  """
  Email from: {{Sender}}
  Subject: {{Subject}}
  Body: {{Body}}
  
  Find the sender's name and company in the email.
  Rate this lead on a scale of 1-10 and explain why.
  Next action: call / email / don't reply.
  """
↓
STEP 4: HubSpot → Create or Update Contact
  → Name: {{Step 3 - name}}
  → Company: {{Step 3 - company}}
  → Phone: {{Step 2 - Output}}
  → Note: {{Step 3 - reason}}
  → Your own contact field "AI score": {{score}}
↓
STEP 5 (condition): Filter by Zapier → Only if score >= 7
↓
STEP 6: Slack → Send Channel Message, channel #sales
  → "Hot lead: {{name}} from {{company}}
     Score: {{score}}/10
     Reason: {{reason}}
     Action: {{next_action}}
     Email: {{Gmail Link}}"
```

Setup time: about an hour the first time. How much time it saves your sales rep depends on how many emails come in, so work it out from your own numbers.

---

## Practice

### Step 1: Create an account and your first Zap

When you create a new account, Zapier automatically starts a free 14-day trial of the Professional plan, with no credit card required. During the trial, both a three-step Zap and AI by Zapier work. When the trial ends, a Zap like this one turns off until you move to a paid plan.

1. Go to [zapier.com](https://zapier.com) → Sign up (signing up is free)
2. In the left sidebar, click **+ Create** → **Zap workflows** (in some versions the button is called **Create a Zap**)
3. You're now in the Zap editor. The steps are on the left, the settings for the selected step on the right

### Step 2: Set up the trigger

For this practice run, connect a personal or test mailbox. The emails will pass through Zapier and an AI model, so don't connect a work mailbox with other people's data unless you have permission.

1. Click the first step (Trigger)
2. Choose **Gmail** (or another app you use)
3. In the **Trigger event** field, choose **New Email**
4. In the **Account** field, connect your Gmail (**+ Connect a new account**)
5. On the **Configure** tab, choose which mailbox folder to watch (Inbox)
6. On the **Test** tab, click **Test trigger**: Zapier shows a recent email as sample data. Select it and click **Continue with selected record**

### Step 3: Add an AI step

1. Click **+** after the trigger
2. Search for and select **AI by Zapier**: the step opens in the editor
3. Next to the Prompt field, open the model list and choose the Standard tier: it's enough for a task like this and uses fewer tasks
4. In the **Prompt** field, type the text below. Wherever you see curly braces, insert a field from the email: type "/" and pick it from the list
   ```
   You're a sales assistant. Analyze this email:
   
   From: {{From Name}}
   Subject: {{Subject}}
   Body: {{Body Plain}}
   
   Write a short summary (2-3 sentences) and decide: is it worth replying to?
   Answer: [summary] | Priority: High/Medium/Low
   ```
5. Click **Preview**, look at what the AI wrote, and then click **Finish**

### Step 4: Send the result to Slack (or get it by email or text)

You need a Slack workspace where you can post in a channel. If you don't use Slack, pick one of the other options below.

1. Add one more step with **+**
2. Choose **Slack** (to get an email or a text message instead, pick Gmail or an SMS app; the fields will be a little different)
3. In the **Action event** field, choose **Send Channel Message**
4. Channel: pick the one you want
5. Message Text: type the text below. The words in curly braces are fields from earlier steps: click the plus sign icon in the field and pick the one you need from the list
   ```
   📧 New email from {{From Name}}
   
   {{AI by Zapier - Response}}
   
   Original: {{Message URL}}
   ```
6. Click **Test step**: the message will show up in Slack

### Step 5: Turn the Zap on and test it

1. At the top right, click **Publish**: that turns the Zap on
2. Send yourself a test email from a different email address (the Zap only handles emails that arrive after you publish it)
3. Wait a few minutes (Zapier checks for new emails on a schedule; how often depends on your plan)
4. Check the result: a message with the AI's analysis of the email should show up in Slack

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
- **[Zapier pricing](https://zapier.com/pricing)**: current plans and task volumes.
- **[Zapier Learn](https://learn.zapier.com)**: free courses on Zapier.
- **[AI by Zapier docs](https://help.zapier.com/hc/en-us/articles/8496342944013-Use-AI-by-Zapier-to-analyze-and-return-data)**: the official help article for the AI step.

---

## Key takeaways

> "Zapier isn't just automation. It's a way to give a small business AI features without a single line of code. Your value as a specialist is working out which workflow the client needs and building it quickly."

> "AI by Zapier turns a Zap from a mail carrier into a sharp assistant. Not just 'got an email → forwarded it,' but 'got an email → understood it → made a decision → acted.' That's the difference between automation and intelligence."

> "Zapier automation services don't require programming. You need to understand the client's business processes and know how to automate them. What you earn depends on your market and your clients; nothing is guaranteed."

---

## Next lesson

→ [Claude Code pricing: Free, Pro, Max, Team or API?](05c-access-levels-pricing.md): what to buy, and when, to unlock Claude Code

In the library, optional: [AI sandboxes: E2B](80-ai-sandboxes-e2b.md): E2B and Modal for letting agents run code safely
