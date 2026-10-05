# Claude Code pricing: Free, Pro, Max, Team or API?

**Time:** about 25 min reading + 10 min to pick a plan

---

## The gist

Anthropic offers **5 levels of access to Claude** (plus the API, which is separate). Each level comes with its own set of features, its own price and its own limits. Pick the wrong one and you either overpay or hit the ceiling every couple of hours.

The most important thing to understand from the start: **Claude Code doesn't work on a free account.** So if you're wondering whether Claude Code is free, the short answer is no. A free account gives you the chat at claude.ai, in the desktop app and on your phone. To use Claude in the terminal or in VS Code, you need a paid plan (Pro at minimum) or an API key with pay-per-token billing.

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

I have a team of 5+ people and we need shared projects
  → Team Standard ($25/seat billed monthly, $20/seat billed yearly)
  → Team Premium ($125/seat billed monthly, $100/seat billed yearly; 5x the usage of Standard)

Regulated industry (healthcare/finance) or 100+ users
  → Enterprise ($20/seat + API usage, through a sales call)

I'm building a program, chatbot or Worker that calls Claude from code
  → API (a separate account and separate billing, not Pro/Max)
```

**The default for most builders:** Pro ($20). It covers most tasks. Move to Max when you actually hit the limit several times a week.

🎨 **Picture this:** a bike vs. an SUV. For the store a mile away, take the bike. For off-road trails, take the SUV. Don't buy a Land Cruiser to pick up a gallon of milk.

---

## Key concepts

- **Plan (also called a tier):** your Claude subscription level. It decides which models you can use, your message limit and which features you get
- **Usage limit:** how much you can use Claude in a given period. It isn't a fixed number of messages: long conversations, big files and heavier models use it up faster
- **Claude Code:** an AI agent for programming that runs in the terminal, VS Code, the desktop app or the browser. It requires a paid plan (Pro, Max, Team, Enterprise) or an API key
- **Fable / Opus / Sonnet / Haiku:** four model families. Haiku is fast and cheap, Sonnet is the balance, Opus is smarter and is the default on subscriptions, and Fable is the strongest and the most expensive
- **Token:** a unit of text. Roughly 4 characters, or 0.75 of a word, of English text. An English text of 1,500 words ≈ 2,000 tokens
- **Prompt caching:** Anthropic caches context that repeats; reading from the cache costs 10% of the input price (even less on some models)
- **Batch API:** an asynchronous mode. You send requests, Claude processes them within 24 hours, and you get a 50% discount
- **Computer Use:** a feature in research preview where Claude controls your computer (moves the cursor, types). In the app, it's available on Pro and Max
- **Console:** a separate account dashboard at platform.claude.com (formerly console.claude.com) where you manage API keys and API billing (not Pro/Max)

---

## The plans in detail

### Tier 1: Claude Free ($0/month)

**What you get:**

- claude.ai in the browser, plus the desktop and phone apps
- A small message limit that depends on demand (the exact number isn't fixed)
- The Sonnet and Haiku models (Opus isn't included on Free)
- Artifacts, Skills, web search, file creation, memory
- Projects: up to 5
- **NO Claude Code**
- The API is a separate account in the Console and has nothing to do with Free

**Who it's for:**

- A high school or college student trying AI for the first time
- A journalist who writes one article a week with AI's help
- Anyone who wants to see "how does this even work" before paying for anything

**When to move up:**

- You keep hitting the daily limit and want to keep going
- You realize you want to work in the terminal or in VS Code
- You need more than five Projects or more usage

**Link:** [claude.ai](https://claude.ai) (sign-up is free)

🎨 **Picture this:** the city bus. The ride is free, but at rush hour it's standing room only. Fine for getting to class; not for commuting to work every day.

---

### Tier 2: Claude Pro ($20/month billed monthly, or $17/month billed yearly = $200/year)

This is **the basic working plan**. Most people start here.

**What you get:**

- More usage than Free (per the pricing page: 5 times more per 5-hour session, plus weekly limits)
- Opus 5.5 (the default model in Claude Code), Sonnet 5.5, Haiku 4.5; Fable 5.1 through usage credits
- **Claude Code** in the terminal, VS Code, the desktop app and the browser: the main difference from Free
- File uploads in the chat (PDFs, images, documents)
- Projects: folders with persistent context (connect your codebase and Claude remembers it)
- Artifacts: an HTML/code preview right in the chat
- Claude Cowork, Research, Claude Design / Slides / Docs
- Computer Use (research preview, turned on in the app's settings)

**Savings:** the yearly plan at $200/year works out to $17/month (vs. $20 billed monthly), about 15% less.

**Claude Code limits:**

- Limits are counted per 5-hour session and per week; the exact numbers depend on the model and on demand
- To see how much you have left: the `/usage` command in Claude Code, or the Usage page in settings
- The most powerful models (Opus, Fable) burn through the limit faster than Sonnet and Haiku. On subscriptions, Fable runs on usage credits

**⚠️ Important note about the tokenizer:** models 4.7 and newer (including Opus 5.5, Sonnet 5.5 and Fable 5.1) use a new tokenizer: the same text takes about 30% more tokens than on Sonnet 4.6 and older. You'll use up your limit faster than the amount of text suggests.

**Who it's for:**

- A developer who writes code 2-4 hours a day
- A content marketer writing articles and posts
- A solo founder running projects
- Anyone who works with AI 1-3 hours a day

**When to move up:**

- You hit the Opus limit several times a week
- You work in Claude Code 6+ hours a day
- You see the "Approaching limit" message more than once a day

**Link:** [claude.com/pricing](https://claude.com/pricing) or [claude.ai/upgrade](https://claude.ai/upgrade)

🎨 **Picture this:** a regular sedan. You drive whenever you want, the monthly payment is fixed, and a tank of gas covers your everyday routes. It's not built for long-haul trucking, but it handles 95% of the trips you'll ever make.

---

### Tier 3: Claude Max (from $100/month, two levels)

Max is for people who work with Claude **a lot**. There are two levels: 5x and 20x the Pro limit (prices as of October 2026).

#### Max 5x (from $100/month)

- 5x the Pro limit per 5-hour session
- The same features as Pro
- Early access to new features
- Priority access at peak times
- Higher output limits

#### Max 20x ($200/month)

- 20x the Pro limit
- The same features as Max 5x
- The highest usage limit of any individual plan

**Who it's for:**

- A developer who spends 6-8 hours a day in Claude Code (Max 5x)
- An AI agency handling 5+ clients at once (Max 5x or 20x)
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

This is **the team plan** for small businesses. In 2026, Anthropic split Team into two levels:

#### Team Standard

- **Monthly:** $25/seat/month
- **Yearly:** $20/seat/month, a 20% savings
- All Claude features, SSO, centralized billing

#### Team Premium

- **Monthly:** $125/seat/month
- **Yearly:** $100/seat/month
- **5x more usage** than Standard seats
- Higher limits on the heavy models

**What you get (on both):**

- Everything in Pro for each user, including Claude Code
- **Shared projects:** several people work from the same context
- Centralized billing: one bill for the whole team
- Admin controls: who can do what
- SSO (single sign-on) integration
- Team usage analytics: you see who used how much
- Separate workspaces for team members

**What Team does NOT give you (that's Enterprise territory):**

- SCIM provisioning and full audit logs
- The Compliance API and custom data retention periods
- HIPAA readiness

**Sample math (Standard, billed yearly):**

- 5 seats = $100/month
- 10 seats = $200/month
- 50 seats = $1,000/month

**Who it's for:**

- A startup of 5-50 people (Standard for moderate use, Premium if you lean heavily on Opus)
- A small AI agency with a team
- A family business where 3-5 people use AI every day

**Link:** [claude.com/pricing](https://claude.com/pricing)

🎨 **Picture this:** an office parking lot. Everyone parks there, there's one gate, and the bill is shared. Convenient, but too small for a big company (that's Enterprise, with its own garage).

---

### Tier 5: Claude Enterprise (custom pricing)

**What you get:**

- SCIM provisioning
- Full audit logs
- HIPAA-ready (for healthcare)
- A DPA (Data Processing Agreement) for GDPR
- IP allowlisting
- Claude Security (beta)
- Advanced SSO + admin controls
- Custom rate limits and model access
- A dedicated support manager

**Price (as of October 2026):**

- **$20/seat per month, billed yearly, + API usage:** a hybrid of "seat + consumption"
- API usage is billed separately, at the official model rates
- Annual contracts are typical
- The final price is negotiated with the sales team

**Who it's for:**

- Companies with 100+ people
- Regulated industries (healthcare, finance, legal)
- Enterprise SaaS companies that build Claude into their product
- Government and quasi-government contracts

**How to buy:** through Anthropic's sales team (Contact Sales), not the self-serve website

**Link:** [claude.com/pricing](https://claude.com/pricing) → Contact Sales

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
| Cache read (hit) | **0.1x, a 90% discount** (0.05x on Opus 5.5; for other models, see the official pricing page) | as long as the cache is alive |

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

- A developer building a Cloudflare Worker, a chatbot or an automation
- A SaaS company building Claude into its product
- Any program that calls Claude from code more than 100 times a day

**When to move from Pro to the API:**

- You want to automate processing (a bot, a scheduled cron job, batch processing)
- You need to build Claude into your own product
- Your volume of calls goes beyond what Pro gives you through chat

**Link:** [platform.claude.com](https://platform.claude.com) (Console) → Billing → Add credit

**The minimum top-up amount and the payment methods** are listed in Console → Billing.

🎨 **Picture this:** a cab on the meter. You pay only when you ride. That's handy if you ride rarely or unpredictably. It's a bad deal if you ride 8 hours a day; at that point a Pro/Max subscription is cheaper.

---

### Comparison table (October 2026)

| Feature | Free | Pro | Max 5x | Max 20x | Team Standard | Team Premium | Enterprise | API |
|---|---|---|---|---|---|---|---|---|
| **Monthly price** | $0 | $20/month | from $100/month | $200/month | $25/seat | $125/seat | $20/seat + API | pay-per-use |
| **Yearly price** | — | $17/month ($200/year) | — | — | $20/seat | $100/seat | $20/seat (billed yearly) | — |
| **Claude Code** | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | through your own code |
| **Usage** | small limit | 5x Free per session | 5x Pro | 20x Pro | more than Pro | 5x Standard | custom | Start / Build / Scale tiers |
| **Models** | Sonnet, Haiku | Opus, Sonnet, Haiku; Fable via usage credits | all available | all available | all available | all available | all available | all (prices above) |
| **Projects** | up to 5 | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | via the API |
| **Shared workspace** | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | — |
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

The API is cheaper only for **automation in code**: one Worker makes 5K calls a day, each with 500 input tokens and 100 output tokens = 2.5M × $2 + 0.5M × $10 = $10 a day. You'd never get through that much by chatting.

**❌ "Pro + API replaces Team"**

Only partly. Pro + API gives you personal access plus automation. But it does NOT give you:

- Shared projects among team members
- Centralized billing
- Admin controls
- Team usage analytics

If 3 people work together, Pro × 3 = $60 (or $51 billed yearly). With 5+ people, Team Standard makes more sense ($100/month billed yearly for 5 seats).

**❌ "Free is enough for everything"**

For chat, maybe. For Claude Code, **no**: it simply isn't available on Free. If you want to write code in the terminal, you need a paid plan (Pro at minimum) or an API key.

**❌ "I bought Pro, so Claude Code works right away"**

Not right away. Pro gives you the **right** to use Claude Code, but you still need a terminal or VS Code, and you install Claude Code separately. See the lesson [Installing and setting up Claude Code](05-setup.md).

**❌ "I can pause my subscription"**

Don't count on a pause. Check in Settings → Billing which options your plan offers: canceling, switching plans or something else. Before you cancel, save your important Projects and conversations, and look up the data retention terms in the official help center.

---

### Paying for your plan

Anthropic offers access and takes payment only in supported countries. The US is on the list; if you live or travel outside the US, check the official page before you buy: [anthropic.com/supported-countries](https://www.anthropic.com/supported-countries). The list changes.

**Payment methods:**

- A credit or debit card is the main method for subscriptions and the API
- Enterprise customers can be invoiced under a contract
- Other methods depend on the platform and your country; see Settings → Billing

**A backup card:**

A payment can fail for everyday reasons: your bank's fraud protection flags the charge by mistake, or your IP address changes. Add a second card from a different bank to your account and make sure it has enough funds or available credit.

**If a payment fails:**

1. Don't panic. First check the reason in Settings → Billing (a "card declined by issuer" message usually means it's time to call your bank)
2. Update your card or add a backup one
3. If nothing helps, contact Anthropic support from your account and include the transaction details

**Refunds:** refund terms depend on the plan and the region. See the current rules in Anthropic's help center ([support.claude.com](https://support.claude.com)); for Team and Enterprise, see your contract.

**Auto-renewal:**

- It's on by default
- You can turn it off in Settings → Billing
- You keep access until the end of the period you've paid for

---

### Combining plans: which combinations work

A builder often needs more than one plan at a time. That's normal:

**Pro + API** (the most common combo for a solo developer)

- Pro at $20 (or $17 billed yearly) for chat and Claude Code
- The API at $20-50/month for your own Workers and automations
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

→ [Installing and setting up Claude Code](05-setup.md): install Claude Code, set up the terminal and VS Code, and run your first command
