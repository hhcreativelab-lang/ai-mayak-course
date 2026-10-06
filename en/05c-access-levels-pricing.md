# Claude Code pricing: Free, Pro, Max, Team or API?

**Time:** about 25 min reading + 10 min to pick a plan

---

## The gist

Anthropic offers **5 levels of access to Claude** (plus the API, which is separate). Each level comes with its own set of features, its own price and its own limits. Pick the wrong one and you either overpay or hit the ceiling every couple of hours.

The most important thing to understand from the start: **Claude Code doesn't work on a free account.** So if you're wondering whether Claude Code is free, the short answer is no. A free account gives you the chat at claude.ai, in the desktop app and on your phone. To use Claude Code (in the desktop app, in the terminal or in VS Code), you need a paid plan (Pro at minimum) or an API key with pay-per-token billing.

This lesson is a map as of October 2026. Prices and limits change, so always check the current numbers on the [What's current](https://aimayak.com/en/now/) page and on the official pricing page. Below: who gets what for their money, which plan fits whom, and how paying works.

🎨 **Picture this:** AI access works like a cell phone plan. Free is the basic plan for the occasional call. Pro is the everyday plan you actually work on. Max is the premium plan for heavy users. Team is the family plan for a group. The API is a cab with the meter running: you pay for every second of the ride. Enterprise is a private jet with a pilot on contract.

---

## 🎯 Decision tree: which plan do I need

The key question isn't "which plan is the coolest." It's "how many hours a day will I actually work with Claude?"

```
I want to try AI for the first time
  → Free ($0)

I use it every day for 1-3 hours and need Claude Code in the terminal
  → Pro ($20/month billed monthly, or $17/month billed yearly = $200/year)

I use it 6-8 hours a day (developer / builder)
  → Max 5x (from $100/month)

I use it intensively 8+ hours a day (full-time in Claude Code)
  → Max 20x ($200/month)

There are two or more of us, and we need shared projects and one bill
  → Team Standard ($25/seat billed monthly, $20/seat billed yearly)
  → Team Premium ($125/seat billed monthly, $100/seat billed yearly; 5x the usage of Standard)

A large company or a regulated industry (healthcare/finance)
  → Enterprise ($20/seat per month billed yearly + usage at API rates)

I'm building a program or chatbot that calls Claude from code
  → API (a separate account and separate billing, not Pro/Max)
```

**The default for most builders:** Pro ($20). It covers most tasks. Move to Max when you actually hit the limit several times a week.

The hours in this chart are a rough guide. Anthropic doesn't measure your limit in hours but in how much work you do: how long your conversations are, how big your files are and which model you pick. The one reliable signal is how often you hit the limit.

🎨 **Picture this:** a bike vs. an SUV. For the store a mile away, take the bike. For off-road trails, take the SUV. Don't buy a Land Cruiser to pick up a gallon of milk.

---

## Key concepts

- **Plan (also called a tier):** your Claude subscription level. It decides which models you can use, your message limit and which features you get
- **Usage limit:** how much you can use Claude in a given period. It isn't a fixed number of messages: long conversations, big files and heavier models use it up faster. It resets every five hours, and paid plans also have a weekly limit
- **Claude Code:** an AI agent for programming that runs in the terminal, VS Code, the desktop app or the browser. It requires a paid plan (Pro, Max, Team, Enterprise) or an API key
- **Fable / Opus / Sonnet / Haiku:** four model families. Haiku is fast and cheap, Sonnet is the balance, Opus is smarter and is the default in Claude Code on paid plans, and Fable is the strongest and the most expensive
- **Token:** a unit of text. On current Claude models, roughly 2.5 characters, or a little over half a word, of English text (on older models about 4 characters, or 0.75 of a word). An English text of 1,500 words ≈ 2,700 tokens on current Claude models (about 2,000 on older ones)
- **Prompt caching:** Anthropic caches context that repeats; reading from the cache costs 10% of the input price (even less on some models)
- **Batch API:** an asynchronous mode. You send requests, Claude processes them within 24 hours, and you get a 50% discount
- **Computer Use:** a feature in research preview where Claude controls your computer (moves the cursor, types). In the app, it's available on Pro and Max
- **Console:** a separate account dashboard at platform.claude.com (the old address, console.anthropic.com, redirects there) where you manage API keys and API billing (not Pro/Max)

---

## The plans in detail

### Tier 1: Claude Free ($0/month)

**What you get:**

- claude.ai in the browser, plus the desktop and phone apps
- A small usage limit that resets every five hours. There's no fixed number of messages: it depends on how long and complex your conversations are
- The Sonnet and Haiku models (Opus and Fable aren't included on Free)
- Artifacts, Skills, web search, file creation, memory
- Projects: up to 5
- **NO Claude Code**
- The API is a separate account in the Console and has nothing to do with Free

**Who it's for:**

- An adult trying AI for the first time (Claude is for people 18 and older)
- A journalist who writes one article a week with AI's help
- Anyone who wants to see "how does this even work" before paying for anything

**When to move up:**

- You keep hitting the limit and want to keep going
- You realize you want to work in Claude Code
- You need more than five Projects or more usage

**Link:** [claude.ai](https://claude.ai) (sign-up is free)

🎨 **Picture this:** the city bus. The ride is free, but at rush hour it's standing room only. Fine for getting to class; not for commuting to work every day.

---

### Tier 2: Claude Pro ($20/month billed monthly, or $17/month billed yearly = $200/year)

This is **the basic working plan**. Most people start here.

**What you get (everything in Free, plus):**

- More usage: per the pricing page, at least 5 times more per 5-hour session than Free, with a weekly limit on top
- Opus 5.5 (the default model in Claude Code), Sonnet 5.5, Haiku 4.5. Fable 5.1 costs extra, through usage credits (pay-as-you-go usage at API rates on top of your subscription)
- **Claude Code** in the desktop app, the terminal, VS Code and the browser: the main difference from Free
- Projects without the cap of five: folders where Claude keeps your documents and instructions on hand
- Research (deeper search across many sources), Claude Design, Slides and Docs
- Cowork: Claude carries out multi-step tasks on its own and can run them on a schedule (since September 2026, Anthropic has been merging Cowork into the regular chat)
- Claude in Chrome and in Microsoft 365
- Computer Use (research preview, turned on in the app's settings)

**Savings:** the yearly plan costs $200, which works out to about $16.67 a month (the pricing page rounds it to $17) instead of $20. That's $40 a year, or about 17% less.

**Claude Code limits:**

- Limits are counted per 5-hour session and per week, and chat and Claude Code draw from the same pool. Anthropic doesn't publish exact numbers
- To see how much you have left: the `/usage` command in Claude Code, or the Usage page in settings
- The most powerful models (Opus, Fable) burn through the limit faster than Sonnet and Haiku. On Pro, Fable isn't part of the limit at all and is paid for with usage credits

**⚠️ Important note about the tokenizer:** models 4.7 and newer (including Opus 5.5, Sonnet 5.5 and Fable 5.1) use a new tokenizer: the same text takes about 30% more tokens than on Sonnet 4.6 and older. You'll use up your limit faster than the amount of text suggests.

**Who it's for:**

- A developer who writes code 2-4 hours a day
- A content marketer writing articles and posts
- A solo founder running projects
- Anyone who works with AI 1-3 hours a day

**When to move up:**

- You hit the limit several times a week
- You work in Claude Code 6+ hours a day
- The warning that you're close to the limit shows up almost every day

**Link:** [claude.com/pricing](https://claude.com/pricing) or [claude.ai/upgrade](https://claude.ai/upgrade)

🎨 **Picture this:** a regular sedan. You drive whenever you want, the monthly payment is fixed, and a tank of gas covers your everyday routes. It's not built for long-haul trucking, but it handles 95% of the trips you'll ever make.

---

### Tier 3: Claude Max (from $100/month, two levels)

Max is for people who work with Claude **a lot**. There are two levels: 5x and 20x the Pro limit (prices as of October 2026). Max is billed monthly only; there's no yearly option.

#### Max 5x (from $100/month)

- 5x the Pro limit per 5-hour session
- The same features as Pro
- Fable is included: you can spend up to 50% of your weekly limit on it
- Early access to new features
- Priority access at peak times
- Higher output limits

#### Max 20x ($200/month)

- 20x the Pro limit
- The same features as Max 5x
- The highest usage limit of any individual plan

**Who it's for:**

- A developer who spends 6-8 hours a day in Claude Code (Max 5x)
- A specialist handling several client projects at once on their own (Max 5x or 20x)
- A builder working intensively 8+ hours a day (Max 20x)
- A solo founder producing a large volume of content and code every day

**The trap (is Max worth it?):**

- It's easy to switch to Max just "because it's cool and I can"
- Without a real 6+ hours a day, the money won't pay off
- Max makes sense when you regularly hit the Pro limit
- Check your actual usage on Pro before you upgrade

**Link:** [claude.com/pricing](https://claude.com/pricing) or [claude.ai/upgrade](https://claude.ai/upgrade), the same place as Pro

🎨 **Picture this:** a Tesla Plaid. Fast, long range, takes you wherever you want whenever you want. But if you only drive it to the grocery store, you're overpaying. Bought for a real job, it earns its keep.

---

### Tier 4: Claude Team (two levels: Standard and Premium)

This is **the team plan** for small businesses: teams of 2 to 150 people. You pay per seat, meaning per member. There are two kinds of seats, and you can mix them in one team:

#### Team Standard

- **Monthly:** $25/seat/month
- **Yearly:** $20/seat/month, a 20% savings
- All Claude features, plus more usage than Pro

#### Team Premium

- **Monthly:** $125/seat/month
- **Yearly:** $100/seat/month
- **5x more usage** than Standard seats
- Fable is included (up to 50% of the weekly limit); on a Standard seat, Fable is paid for with usage credits

**What you get (on both):**

- Everything in Pro for each user, including Claude Code
- **Shared projects:** several people work from the same context
- Centralized billing: one bill for the whole team
- Admin controls: who can do what
- SSO (single sign-on) integration
- Team usage analytics: you see who used how much
- No model training on your team's content by default

**What Team does NOT give you (that's Enterprise territory):**

- SCIM provisioning and full audit logs
- The Compliance API and custom data retention periods
- HIPAA readiness

**Sample math (Standard, billed yearly):**

- 5 seats = $100/month
- 10 seats = $200/month
- 50 seats = $1,000/month

**Who it's for:**

- A small company of up to 150 people (Standard for moderate use, Premium for people who spend whole days in Claude Code)
- A small AI agency with a team
- A family business where 3-5 people use AI every day

**Link:** [claude.com/pricing](https://claude.com/pricing)

🎨 **Picture this:** an office parking lot. Everyone parks there, there's one gate, and the bill is shared. Convenient, but too small for a big company (that's Enterprise, with its own garage).

---

### Tier 5: Claude Enterprise (seat price plus usage)

**What you get (everything in Team, plus):**

- SCIM provisioning (automatic management of user accounts)
- Audit logs
- A HIPAA-ready offering (for healthcare data)
- The Compliance API and custom data retention controls
- IP allowlisting and network-level access control
- Claude Security (beta)
- Role-based access with fine-grained permissions
- Spending limits per user and for the whole organization

**Price (as of October 2026):**

- **$20/seat per month, billed yearly, + usage at API rates:** you pay for the seat and for what you actually use
- Usage is billed at the official model rates
- Billed yearly only
- You can sign up self-serve on the pricing page or ask the sales team for a quote

**Who it's for:**

- Large companies
- Regulated industries (healthcare, finance, legal)
- Organizations that need SCIM, audit logs and their own data retention periods
- Government and quasi-government customers

**How to buy:** the pricing page has a "Get Enterprise plan" button (self-serve) and a way to talk to a sales specialist

**Link:** [claude.com/pricing](https://claude.com/pricing) → Get Enterprise plan or Contact sales

🎨 **Picture this:** a private jet with a crew. Expensive, fully customized, built for specific jobs. Buying one "just in case" is silly. Buying one when you really do fly overseas on business every week makes sense.

---

### Tier 6: Anthropic API (pay for what you use)

The API is **a different story**. It's not a monthly subscription; it's pay-as-you-go.

**What it is:**

- Programmatic access to the models through HTTP requests
- Not a chat interface but **building material** for your own programs
- You use it in code: Python, TypeScript, Go, any language
- You pay for every token that gets processed

**Important:**

- The API does **NOT depend** on a Pro/Max subscription. It's a separate account
- You can have Pro for chat and the API for your own programs at the same time
- The API is paid through the Console at platform.claude.com (a separate account dashboard)

**Prices as of October 2026** (per million tokens, from Anthropic's official pricing page; current numbers are always on the [What's current](https://aimayak.com/en/now/) page):

#### Claude (Anthropic)

| Model | Input | Output | When to use it |
|---|---|---|---|
| Haiku 4.5 | $1.00 | $5.00 | Simple tasks: classification, translation, short answers |
| Sonnet 5.5 | $2.00 | $10.00 | The price/quality balance for most tasks, 1M context |
| Opus 5.5 | $4.00 | $20.00 | Complex reasoning, architecture, deep analysis, 1M context |
| Fable 5.1 | $10.00 | $50.00 | The longest and hardest tasks, 1M context |

Model prices change from generation to generation: a new Opus generation can cost noticeably less than the one before it. So don't memorize the numbers; check the table before you run any calculation.

**⚠️ Tokenizer:** models 4.7 and newer (in this table, Opus 5.5, Sonnet 5.5 and Fable 5.1) use a newer tokenizer: the same text takes about 30% more tokens than on Sonnet 4.6 and older. The exact increase depends on the text. Your real bill may come out higher than your estimate, so add a 30% buffer when you carry calculations over from older models.

**Mythos:** Claude Mythos 5.1 is available by invitation only (Project Glasswing); a regular user can't get it.

**Models being retired from the API:** older models get shut down. Claude Opus 4, Opus 4.1, Sonnet 4 and Haiku 3.5 have already been retired from the Claude API (some are still available on Amazon Bedrock and Google Cloud). Claude Haiku 4.5 may be retired no earlier than October 15, 2026. If you have an outdated model in production, keep an eye on the [model deprecations](https://platform.claude.com/docs/en/about-claude/model-deprecations) page and migrate ahead of time.

#### OpenAI (for comparison, as of October 2026)

| Model | Input | Output | When |
|---|---|---|---|
| gpt-6-luna | $0.10 | $0.50 | The cheapest and fastest |
| gpt-6.1-sol | $2.00 | $10.00 | The balance |
| gpt-6-astra | $10.00 | $50.00 | The strongest |

OpenAI's model names and prices change often; check the current numbers on OpenAI's official API pricing page.

**What a token means in practice:**

- About 4 characters of English text, or about 0.75 of a word, = 1 token
- For models 4.7 and newer, add about **+30%** for the new tokenizer
- One prompt like "write a LinkedIn post" with 10K tokens of input context + 2K of output ≈ $0.04 on Sonnet 5.5

**Sample math (Sonnet 5.5):**

- 1,000 requests with 500 input + 500 output (nominal) tokens each
- With the +30% tokenizer buffer: ~650 input + ~650 output
- Input: 650 × 1,000 / 1,000,000 × $2 = $1.30
- Output: 650 × 1,000 / 1,000,000 × $10 = $6.50
- Total: **~$7.80** per 1,000 requests

**Sample math (Opus 5.5):**

- The same 1,000 requests, ~650 input + ~650 output with the tokenizer buffer
- Input: 650 × 1,000 / 1,000,000 × $4 = $2.60
- Output: 650 × 1,000 / 1,000,000 × $20 = $13.00
- Total: **~$15.60** per 1,000 requests (twice as much as Sonnet 5.5 for the same task)

**Ways to save:**

- **Prompt caching:** reading from the cache costs 10% of the input price (details below and in the lesson [Prompt caching and the Batch API](34-prompt-caching-batch-api.md))
- **Batch API:** 50% off if you're willing to wait up to 24 hours for processing. Details are in the same lesson
- **Haiku 4.5 instead of Sonnet 5.5:** half the cost on simple tasks
- **Fewer output tokens:** keep the output short, because output costs 5x more than input

#### Prompt caching: the detailed breakdown (as of October 2026)

| Operation | Multiplier on the base price | TTL (how long it lasts) |
|---|---|---|
| Cache write, 5 min | **1.25x** (25% more than the base input price) | 5 minutes |
| Cache write, 1 hour | **2.0x** (twice the price) | 1 hour |
| Cache read (hit) | **0.1x, a 90% discount** (0.05x on Opus 5.5, 0.025x on Fable 5.1) | as long as the cache is alive; each read extends it |

**Examples on Sonnet 5.5 ($2/MTok input):**

- Cache write, 5 min: $2.50/MTok
- Cache write, 1 hour: $4.00/MTok
- Cache read (hit): $0.20/MTok

**When it pays off:** the cache pays for itself after 1 read (with a 5-minute write) or 2 reads (with a 1-hour write).

#### Paid API tools (as of October 2026)

- **Web Search:** $10 per 1,000 searches (+ standard tokens)
- **Web Fetch:** free (tokens only)
- **Code Execution:** billed by container time, with a free allowance; current terms are on the [official pricing page](https://platform.claude.com/docs/en/about-claude/pricing)
- **Managed Agents (Claude Managed Agents):** billed per session-hour of running time; check the [official pricing page](https://platform.claude.com/docs/en/about-claude/pricing) for the rate

#### What's new at Anthropic (as of October 2026)

- **Fable 5.1** (September 1, 2026): the strongest of the generally available models
- **Opus 5.5** (September 22, 2026) and **Sonnet 5.5** (September 28, 2026): the main workhorse models
- **Claude Mythos 5.1**: invitation only (Project Glasswing); it hasn't been released to the public
- **1M context window:** included at the standard price, with no surcharge, on Fable 5.1, Opus 5.5 and Sonnet 5.5; Haiku 4.5 has a 200K window

**Who it's for:**

- A developer building a chatbot, a service or an automation
- A SaaS company building Claude into its product
- Any program that calls Claude from code more than 100 times a day

**When to move from Pro to the API:**

- You want to automate processing (a bot, a scheduled cron job, batch processing)
- You need to build Claude into your own product
- Your volume of calls goes beyond what Pro gives you through chat

**Link:** [platform.claude.com](https://platform.claude.com) (Console) → the Billing page, where you add funds

**The minimum top-up amount and the payment methods** are listed in Console → Billing.

🎨 **Picture this:** a cab on the meter. You pay only when you ride. That's handy if you ride rarely or unpredictably. It's a bad deal if you ride 8 hours a day; at that point a Pro/Max subscription is cheaper.

---

### Comparison table (October 2026)

| Feature | Free | Pro | Max 5x | Max 20x | Team Standard | Team Premium | Enterprise | API |
|---|---|---|---|---|---|---|---|---|
| **Monthly price** | $0 | $20/month | from $100/month | $200/month | $25/seat | $125/seat | — | pay-per-use |
| **Yearly price** | — | $17/month ($200/year) | — | — | $20/seat | $100/seat | $20/seat + usage at API rates | — |
| **Claude Code** | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ with an API key, billed per token |
| **Usage** | small limit | at least 5x Free per session | 5x Pro | 20x Pro | more than Pro | 5x Standard | billed by usage | Start / Build / Scale rate-limit tiers |
| **Models** | Sonnet, Haiku | Opus, Sonnet, Haiku; Fable via usage credits | all; Fable up to 50% of the weekly limit | all; Fable up to 50% of the weekly limit | Opus, Sonnet, Haiku; Fable via usage credits | all; Fable up to 50% of the weekly limit | all available | all (prices above) |
| **Projects** | up to 5 | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | — |
| **Shared team projects** | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | — |
| **SSO** | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ + SCIM | API keys |
| **HIPAA-ready** | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | — |
| **Computer Use** (in the app) | ❌ | research preview | research preview | research preview | ❌ | ❌ | ❌ | via the API |
| **Prompt caching** | — | — | — | — | — | — | — | ✅ (cache reads 90% off or more) |
| **Batch API** | — | — | — | — | — | — | — | ✅ (50% off) |

---

### Common myths and mistakes

**❌ "I'll get Max right away because it's cool"**

Without a real 6-8 hours of work a day, Max won't pay off. Pro already gives you noticeably more usage than Free. Start with Pro, and upgrade when you keep hitting the limit.

**❌ "The API is cheaper than Pro for chatting with Claude"**

For interactive chat, the API is usually **more expensive** than Pro: with every reply, the whole conversation history goes into the request. An example on Sonnet 5.5 (prices as of October 2026): 100 requests a day, each with 20K input tokens and 1K output tokens = 2M input × $2 + 0.1M output × $10 = $5 a day, or about $150 a month. Pro costs a flat $20 (or $17 billed yearly).

The API is cheaper only for **automation in code**: one service makes 5K calls a day, each with 500 input tokens and 100 output tokens = 2.5M × $2 + 0.5M × $10 = $10 a day. You'd never get through that much by chatting.

**❌ "Pro + API replaces Team"**

Only partly. Pro + API gives you personal access plus automation. But it does NOT give you:

- Shared projects among team members
- Centralized billing
- Admin controls
- Team usage analytics

If 3 people work together, Pro × 3 = $60 (or $51 billed yearly). If people need shared projects and one bill, Team Standard makes more sense: $100/month for 5 seats, billed yearly.

**❌ "Free is enough for everything"**

For chat, maybe. For Claude Code, **no**: it simply isn't available on Free. To work in Claude Code, you need a paid plan (Pro at minimum) or an API key.

**❌ "I bought Pro, so Claude Code works right away"**

Not right away. Pro gives you the **right** to use Claude Code, but you still have to install it. The easiest way is the Claude desktop app and its Code tab, which is the next lesson. The terminal and VS Code route is covered in the library lesson [Installing and setting up Claude Code](05-setup.md).

**❌ "I can pause my subscription"**

Don't count on a pause: the pricing page describes only canceling and switching plans. You can cancel anytime in Settings → Billing → Cancel. Your plan stays active until the end of the period you've paid for; to avoid the next charge, cancel at least 24 hours before the renewal date. Canceling doesn't delete your data: your chats, projects and files stay with your account, though some features aren't available on Free.

---

### Paying for your plan

Anthropic offers access and takes payment only in supported countries. The US is on the list; if you live or travel outside the US, check the official page before you buy: [anthropic.com/supported-countries](https://www.anthropic.com/supported-countries). The list changes.

**Payment methods:**

- A credit or debit card is the main method for subscriptions and the API
- Enterprise customers can be invoiced under a contract
- You can also subscribe in the phone app through the App Store or Google Play; in that case you cancel through the app store
- Other methods depend on your country; see Settings → Billing

**A backup card:**

A payment can fail for everyday reasons: for example, your bank's fraud protection flags the charge by mistake. Add a second card from a different bank to your account and make sure it has enough funds or available credit.

**If a payment fails:**

1. Don't panic. First check the reason in Settings → Billing (a "card declined by issuer" message usually means it's time to call your bank)
2. Update your card or add a backup one
3. If nothing helps, contact Anthropic support from your account and include the transaction details

**Refunds:** payments are generally non-refundable. The exceptions are the cases in Anthropic's terms of service and whatever local law requires: in the European Economic Area and the UK, for example, there's a 14-day withdrawal period. You request a refund in the app through the Get help menu; if you subscribed through the App Store, Apple handles the refund. Details are in Anthropic's help center ([support.claude.com](https://support.claude.com)); for Team and Enterprise, see your contract.

**Auto-renewal:**

- It's on by default
- You can turn it off in Settings → Billing
- You keep access until the end of the period you've paid for

---

### Combining plans: which combinations work

A builder often needs more than one plan at a time. That's normal:

**Pro + API** (the most common combo for a solo developer)

- Pro at $20 (or $17 billed yearly) for chat and Claude Code
- The API at $20-50/month for your own programs and automations
- Total: $37-70/month, which covers most tasks well

**Max 5x + API** (for a serious builder)

- Max from $100/month for intensive work in Claude Code
- The API at $50-200/month for production systems
- Total: $150-300/month. Worth it if you regularly hit the limit and your production systems are actually running

**Team Standard + API** (for an agency)

- Team Standard billed yearly = $100/month for 5 seats (a team can start at 2 people)
- The API for shared automations, $100-500/month
- A convenient base for an agency with several clients

**Free + API** (for a minimalist developer)

- Free at $0 for occasional questions
- The API for your own programs
- Only if you **don't need** Claude Code in the terminal

**What doesn't combine:**

- ❌ Several paid subscriptions on one account: an account has one plan, and you change it by upgrading or downgrading

---

### Is it worth it? How to figure out the right plan

Don't guess. Look at your own usage for a couple of weeks.

**Step 1: Start with Pro ($20)**

It's inexpensive, it includes Claude Code, and you can cancel anytime.

**Step 2: After 2 weeks, check Settings → Usage:**

- How many times did you hit the limit? (0-2 = Pro is enough, 5+ = time for Max)
- How many hours a day do you spend in Claude Code? (1-3 = Pro, 6+ = Max)
- Did you use Opus, and did you run into its limit?

**Step 3: Decide based on the data:**

- Never hit a limit → stay on Pro
- Hit it 2-3 times → try Max 5x for a month
- Hit it 10+ times → Max 20x is justified
- Want automation on the side → add the API at $20-50

**Step 4: Recheck every quarter**

Your usage changes. If your work has changed, sometimes it's better to downgrade to Pro.

---

## Checklist (✅)

Before you buy a subscription:

- [ ] You understand the difference between Free / Pro / Max 5x / Max 20x
- [ ] You know when you need Team vs. Enterprise
- [ ] You understand that the API is a separate account with separate billing through the Console (platform.claude.com)
- [ ] You've decided which plan to use for the next month (Pro by default)
- [ ] You know how to turn off auto-renewal if you need to
- [ ] You know that Claude Code requires a paid plan (Pro at minimum) or an API key

---

## Tools and resources

- **[Claude pricing overview](https://claude.com/pricing)**: the official page with every plan
- **[Claude.ai upgrade](https://claude.ai/upgrade)**: upgrade from Free to Pro/Max
- **[Claude Team](https://claude.com/pricing)**: the Standard and Premium team plans
- **[Claude Enterprise](https://claude.com/pricing)**: a sales call for large companies
- **[Anthropic Console](https://platform.claude.com)**: your API dashboard for keys, billing and usage
- **[API pricing in detail](https://platform.claude.com/docs/en/about-claude/pricing)**: a detailed price breakdown by model
- **[Token counting](https://platform.claude.com/docs/en/build-with-claude/token-counting)**: count how many tokens are in your prompt
- **[Status page](https://status.anthropic.com)**: real-time status of the API and services
- **[Supported countries](https://www.anthropic.com/supported-countries)**: where Claude is available, if you live or travel outside the US

---

## Key takeaways

> Don't pick a plan "because it's cool." Pick it for your real usage. Start with Pro ($20 billed monthly, or $17/month billed yearly = $200/year), and upgrade when you actually hit the limit several times a week.

> Model prices change from generation to generation. As of October 2026, Opus 5.5 costs $4/$20 per million tokens and Sonnet 5.5 costs $2/$10, while earlier Opus generations cost noticeably more. Models 4.7 and newer use a new tokenizer: about 30% more tokens for the same text, so build a buffer into your math.

> Older models get retired from the API. If you have an outdated model in production, keep an eye on the model deprecations page and migrate ahead of time, or your calls will start failing.

> The API and Pro are **different things**; don't mix them up. Pro gives you the chat and Claude Code. The API gives your program access to the models, billed separately per token through the Console. A builder usually needs both side by side.

---

## Next lesson

→ [Claude Code desktop: start without the terminal](05b-claude-code-desktop.md): your first step into Claude Code, in the Claude desktop app

In the library, optional: [Installing and setting up Claude Code](05-setup.md): Claude Code in the terminal and in VS Code
