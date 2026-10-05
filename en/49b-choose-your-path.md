# Choose your path: a map of the deep-dive library

**Time:** about 15 min

---

## The gist

Ahead of you is the deep-dive library, full of applied lessons. You won't read them all. This lesson is a map of where *you* should go. Answer 4 questions and you have your route.

Without this lesson, the applied lessons feel like a tool catalog: voice, video, analytics, CRM, support, ads. Everything is interesting, nothing gets built. A student reads the lessons one after another, remembers 10% two months later, and hasn't launched anything.

With this lesson, you leave with one of 5 ready-made routes: 8 to 12 lessons for your goal, in the right order, and a clear sense of why you're NOT reading the rest right now.

The [course page](https://aimayak.com/en/course/) also has three general paths by goal: the **Use AI in my work** path, the **Earn with AI** path and the **Build my own product** path. The map below is finer-grained: it picks a scenario inside the Earn with AI or Build my own product goal.

🎨 **Picture this:** you've finished ski school. The green runs are behind you. In front of you is a mountain with dozens of trails. Which ones are yours? Without a trail map, you'll stand at the lift for an hour reading every name. This lesson is the trail map, color-coded: your level, your direction, your distance.

---

## 🎯 Decision tree: 4 questions to pick your route

The main question of this lesson is **not "what's cool in the course"** but "which of the applied lessons fit the way you plan to work with AI."

Answer the 4 questions in order. At the end you get one of 5 routes (A/B/C/D/E). The lessons that AREN'T on your route, you come back to later, when your scenario changes.

---

### Q1: Who is your client?

| Answer | Route | Why |
|---|---|---|
| Businesses (B2B): I sell to companies | **A: B2B AI Agency** | You need case studies, cold outreach, retention, business integrations |
| End users (B2C): I sell to people | **B: B2C Consumer App** | You need good UX, virality, cheap support, mass scale |
| Myself (B2Me): I automate my own routine | **C: Personal Automation** | You need Obsidian or Notion, an executive assistant, /loop, no public presence |
| Corporations / enterprise (1,000+ people) | **D: Corporate Consulting** | You need the Microsoft stack, compliance, security, Teams |
| An audience, through content | **E: Content Creator** | You need voice, video, social media, brand voice, SEO |

If your answer is "both," pick the main scenario **for the next 3 months**. In 3 months, come back and take the second route.

🎨 **Picture this:** you can't drive to Chicago and to Dallas at the same time. One city first, then the other: months of work in each, not "both at once in a week."

---

### Q2: What are you selling?

| Answer | Add to your route |
|---|---|
| A service (your time, project work) | + [Your first clients](38-monetization-clients.md), [Lead generation](39-lead-generation.md), [Pricing](39-monetization-pricing.md), [Portfolio and case studies](41-portfolio-case-studies.md), [Cold outreach](45-cold-outreach.md), [Delivery and retention](46-delivery-retention.md) (the classic way to sell a service) |
| A product (sells without you, scales) | + [Packaging](42-packaging.md), [Monetization case studies](47-monetization-cases.md), [The factory model](48-factory-model.md) (packaging, the factory model) |
| Content (subscriptions, ads, sponsors) | switch to route E |
| Data or analytics | + [Product analytics](87-product-analytics.md), [Niche and trend analysis](88-niche-trend-analysis.md), [Competitive intelligence](89-competitive-intelligence.md) (analytics and market intelligence) |
| A SaaS subscription | + [Payments and billing](97-payments-stripe.md), [MLOps for indie developers](98-mlops-indie.md), [The final architecture](99-final-architecture.md) |

You've **already covered some of these** before this lesson (in the part of the course about money and clients). This is a reminder: don't skip connecting them to your new route.

---

### Q3: Which stack are you betting on?

| Stack | Applied lessons for you |
|---|---|
| Text and chat (emails, documents) | [AI copywriting](67-ai-copywriting.md), [AI for email](73-ai-email-communications.md), [AI meeting notes](74-ai-meetings.md), [AI translation and localization](75-ai-translation.md), [AI in messaging apps](76-ai-messengers.md) |
| Voice (calls, dictation) | [Voice tools](53-voice-tools.md), [AI voiceover](68-voice-tts-elevenlabs.md), [Voice AI agents](84-voice-ai-agents-vapi.md), [Real-time AI](85-realtime-ai.md), [AI phone support](95-call-support-ai.md) |
| Video and media | [Video editing](54-video-pipeline.md), [The content pipeline](72-content-pipeline-complete.md) and the content lessons around it, [AI video generation](71-ai-video-generation.md) |
| Web app | [Websites and web apps](15-websites-webapps.md), [Chatbots with the Claude API](50-telegram-bots.md) (a chatbot as your interface), [No-code AI](77-no-code-ai.md), [AI sandboxes](80-ai-sandboxes-e2b.md) |
| Automation with no interface | [Loop and scheduled tasks](35-loop-scheduled-tasks.md), [n8n + AI](78-n8n-ai-workflows.md), [Zapier AI](79-zapier-ai.md), [AI sandboxes](80-ai-sandboxes-e2b.md)–[Advanced computer use](83-computer-use-advanced.md) |
| Data and analytics | [Product analytics](87-product-analytics.md), [Niche and trend analysis](88-niche-trend-analysis.md), [Competitive intelligence](89-competitive-intelligence.md) |

A stack isn't a route. The stack tells you **which specific lessons** to add to your route. The route is the **sequence**; the stack is the **content**.

---

### Q4: How ready are you?

| Where you are | What to add |
|---|---|
| A weekend MVP (minimum viable product) | the minimal stack: Claude Code + Cloudflare Workers + one MCP. Leave the production patterns lessons alone for now ([Plugin security](101-plugin-security.md), [Prompt injection defense](107b-prompt-injection-defense.md), [Hook deny-by-design](107-hook-deny-by-design.md), [Portfolio detachability](106-modular-architecture-detachability.md) and the ones around them) |
| A beta product (10 to 50 users) | + monitoring ([Product analytics](87-product-analytics.md)), basic security ([Security in Claude Code](61-security-secrets-env.md)), an audit trail ([Managing agents](62-agent-management-logging.md)) |
| Production with real clients | **The production patterns lessons ([Plugin security](101-plugin-security.md), [Prompt injection defense](107b-prompt-injection-defense.md), [Hook deny-by-design](107-hook-deny-by-design.md), [Portfolio detachability](106-modular-architecture-detachability.md) and the ones around them) are REQUIRED**: without them, problems tend to pile up as soon as real clients rely on your system |
| Enterprise clients | the production patterns lessons ([Plugin security](101-plugin-security.md), [Prompt injection defense](107b-prompt-injection-defense.md), [Hook deny-by-design](107-hook-deny-by-design.md), [Portfolio detachability](106-modular-architecture-detachability.md) and the ones around them) + [Microsoft integration](microsoft-integration.md) + the compliance lessons |

🎨 **Picture this:** you don't buy a Boeing 747 to run to the grocery store. And you don't buy a scooter to cross the Atlantic. Your readiness level means picking the right vehicle for the distance.

---

## 5 routes from Q1 to Q4

After the 4 questions, you're on one of 5 routes. Each route is a table: which lessons, in what order, how many weeks.

---

### Route A: B2B AI Agency (you sell AI services to businesses)

**Client profile:** companies with 10 to 200 people that are looking for automation and are ready to pay for a solution.

**Route logic:** clients → outreach → delivery → retention → packaging → scaling. Without a CRM and sales analytics, it doesn't work.

| Order | Lesson | Why |
|---|---|---|
| 1 | [Your first clients](38-monetization-clients.md) | trust map, warm conversations |
| 2 | [Cold outreach](45-cold-outreach.md) | AI scripts, conversion |
| 3 | [Lead generation](39-lead-generation.md) | an AI funnel |
| 4 | [Pricing](39-monetization-pricing.md) | value-based pricing |
| 5 | [Delivery and retention](46-delivery-retention.md) | keeping clients 12+ months |
| 6 | [The factory model](48-factory-model.md) | from freelancer to agency |
| 7 | [AI for email](73-ai-email-communications.md) | automating your communication |
| 8 | [A CRM on autopilot](90-crm-autopilot.md) | leads without a sales manager |
| 9 | [Sales AI](93-sales-ai.md) | BANT qualification, objections |
| 10 | [Customer support](94-ai-customer-support.md) | tickets answered from your knowledge base (RAG) |
| 11 | The production patterns lessons ([Plugin security](101-plugin-security.md), [Prompt injection defense](107b-prompt-injection-defense.md), [Hook deny-by-design](107-hook-deny-by-design.md), [Portfolio detachability](106-modular-architecture-detachability.md) and the ones around them) | production patterns |

**Time:** 6 to 8 weeks, alongside real clients.
**Skip:** [Voice tools](53-voice-tools.md) and [Video editing](54-video-pipeline.md) (voice and video), the content factory lessons ([AI copywriting](67-ai-copywriting.md)–[The content pipeline](72-content-pipeline-complete.md)), and [Product analytics](87-product-analytics.md)–[Competitive intelligence](89-competitive-intelligence.md) (analytics for your own product; you have a service, not a product).

---

### Route B: B2C Consumer App (you sell an app to people)

**Client profile:** end users, freemium or a subscription; you need virality.

**Route logic:** MVP → UX → marketing → virality → retention → monetization. Mass scale means you need cheap infrastructure.

| Order | Lesson | Why |
|---|---|---|
| 1 | [Websites and web apps](15-websites-webapps.md) | the product itself |
| 2 | [Chatbots with the Claude API](50-telegram-bots.md) | an alternative interface, no app store needed |
| 3 | [Social media](56-social-media-automation.md) | a content pipeline for virality |
| 4 | [AI copywriting](67-ai-copywriting.md) | landing pages, ads, push notifications |
| 5 | [No-code AI](77-no-code-ai.md) | faster prototypes |
| 6 | [Product analytics](87-product-analytics.md) | retention, funnel |
| 7 | [A CRM (simplified)](90-crm-autopilot.md) | retention emails |
| 8 | [An AI chat on your website](96-ai-chat-widget.md) | support without the cost |
| 9 | [Stripe](97-payments-stripe.md) | subscriptions |
| 10 | [The SEO machine](91-seo-machine.md) | organic traffic |
| 11 | The production patterns lessons ([Plugin security](101-plugin-security.md), [Prompt injection defense](107b-prompt-injection-defense.md), [Hook deny-by-design](107-hook-deny-by-design.md), [Portfolio detachability](106-modular-architecture-detachability.md) and the ones around them) | production patterns |

**Time:** 8 to 10 weeks.
**Skip:** the B2B monetization lessons ([Your first clients](38-monetization-clients.md)–[The factory model](48-factory-model.md)), [Voice AI agents](84-voice-ai-agents-vapi.md)–[Chatbot managers](86-chatbot-managers.md) (voice is premature for an MVP), and [Niche and trend analysis](88-niche-trend-analysis.md) and [Competitive intelligence](89-competitive-intelligence.md) (competitive intelligence comes later).

---

### Route C: Personal Automation (automating your own routine)

**Client profile:** you. Nothing is for sale; the payoff is indirect, in hours freed up for other work.

**Route logic:** find the routine → automate it → build up knowledge → scale it across all your projects. No public presence needed.

| Order | Lesson | Why |
|---|---|---|
| 1 | [An AI executive assistant](34-executive-assistant.md) | calendar, email, tasks |
| 2 | [Loop and scheduled tasks](35-loop-scheduled-tasks.md) | work that runs on its own while you sleep |
| 3 | [Obsidian as a second brain](64-obsidian-second-brain.md) | a knowledge base with MCP |
| 4 | [Notion AI](65-notion-ai-team.md) | an alternative or an add-on |
| 5 | [A philosophy of folders](66-folder-structure-philosophy.md) | PARA, structure |
| 6 | [AI for email](73-ai-email-communications.md) | your own inbox |
| 7 | [AI meeting notes](74-ai-meetings.md) | your own meetings |
| 8 | [AI translation](75-ai-translation.md) | working across languages |
| 9 | [AI in messaging apps](76-ai-messengers.md) | Slack or WhatsApp for yourself |
| 10 | [32 Claude Code power tips](60-32-power-hacks.md) | getting more out of Claude Code |

**Time:** 4 to 6 weeks (faster, since there's no outside client).
**Skip:** the monetization lessons ([Your first clients](38-monetization-clients.md)–[The factory model](48-factory-model.md); you don't need them), [Cold outreach](45-cold-outreach.md), [Voice AI agents](84-voice-ai-agents-vapi.md)–[Chatbot managers](86-chatbot-managers.md) (voice is optional), and [Product analytics](87-product-analytics.md)–[The final architecture](99-final-architecture.md) (production is premature).

---

### Route D: Corporate Consulting (you sell integrations to large companies)

**Client profile:** companies with 500+ people, an IT department, compliance requirements and pilot projects, ready to pay for reliability.

**Route logic:** the Microsoft ecosystem + security + audits + Teams. Without compliance and an audit log, you won't get past their review.

| Order | Lesson | Why |
|---|---|---|
| 1 | [AI in messaging apps (Teams)](76-ai-messengers.md) | the company's main channel |
| 2 | Bonus: [Microsoft 365 + Claude](microsoft-integration.md) | Teams webhooks, Graph API, Azure |
| 3 | [AI meeting notes](74-ai-meetings.md) | integration with Teams meetings |
| 4 | [Managing agents](62-agent-management-logging.md) | logs, ClickUp MCP, CRM |
| 5 | [Security and secrets](61-security-secrets-env.md) | production-ready |
| 6 | [AI ethics and safety](61b-ai-ethics-safety.md) | corporate compliance |
| 7 | [Niche and trend analysis](88-niche-trend-analysis.md) | internal research for the client |
| 8 | [Competitive intelligence](89-competitive-intelligence.md) | market intelligence |
| 9 | [The final architecture](99-final-architecture.md) | the full enterprise stack |
| 10 | The production patterns lessons ([Plugin security](101-plugin-security.md), [Prompt injection defense](107b-prompt-injection-defense.md), [Hook deny-by-design](107-hook-deny-by-design.md), [Portfolio detachability](106-modular-architecture-detachability.md) and the ones around them), REQUIRED | production patterns + plugin security |

**Time:** 10 to 12 weeks (slower, because each lesson goes deep).
**Skip:** [Chatbots with the Claude API](50-telegram-bots.md) (a public chatbot isn't a corporate channel in most cases; large companies live in Teams), [Voice tools](53-voice-tools.md) and [Video editing](54-video-pipeline.md) (voice and video can wait), the content factory lessons ([AI copywriting](67-ai-copywriting.md)–[The content pipeline](72-content-pipeline-complete.md); not your core skill), and [No-code AI](77-no-code-ai.md)–[Zapier AI](79-zapier-ai.md) (no-code tools; corporations want custom work).

---

### Route E: Content Creator (you earn through an audience)

**Client profile:** your audience (subscriptions, ads, sponsors, products). A YouTube channel, a newsletter or a blog as the base.

**Route logic:** content pipeline → virality → distribution across channels → monetizing the audience.

| Order | Lesson | Why |
|---|---|---|
| 1 | [AI copywriting](67-ai-copywriting.md) | the foundation of your brand voice |
| 2 | [AI voiceover](68-voice-tts-elevenlabs.md) | text-to-speech for videos |
| 3 | [AI music](69-music-ai-suno.md) | sound design |
| 4 | [AI presentations](70-ai-presentations.md) | slides for your videos |
| 5 | [AI video generation](71-ai-video-generation.md) | generating clips |
| 6 | [The all-in-one content pipeline](72-content-pipeline-complete.md) | 9 stations from idea to publishing |
| 7 | [Voice tools](53-voice-tools.md) | your recording workflow |
| 8 | [Video editing](54-video-pipeline.md) | FFmpeg, DaVinci |
| 9 | [Social media](56-social-media-automation.md) | distribution |
| 10 | [The SEO machine](91-seo-machine.md) | organic search |
| 11 | [AI advertising](92-ai-advertising.md) | boosting posts that are already taking off |

**Time:** 6 to 8 weeks.
**Skip:** the B2B monetization lessons ([Your first clients](38-monetization-clients.md)–[The factory model](48-factory-model.md)), [AI in messaging apps](76-ai-messengers.md) (that's messaging inside a company), [Product analytics](87-product-analytics.md)–[Competitive intelligence](89-competitive-intelligence.md) (you'll need them, but later), and [AI customer support](94-ai-customer-support.md)–[An AI chat on your website](96-ai-chat-widget.md) (customer support; you don't have clients in the traditional sense).

---

## How to decide if you're torn between two routes

A real scenario: you went through Q1 to Q4 and ended up with two possible routes. For example:
- B2B agency (you know business owners who'd buy the service)
- Content creator (you've wanted a YouTube channel for a long time)

**The rule for your first route: pick the one where money comes in faster.**

| Route | Time to first payment (rough guide) | What that payment is |
|---|---|---|
| A: B2B Agency | Usually the fastest: weeks | Payment for a project |
| B: B2C App | Longer: you need to gather users | A payment or a subscription from each user |
| C: Personal | Nobody pays you: the benefit is indirect | Time freed up for other work |
| D: Corporate | Long: approval cycles | Payment for a pilot project |
| E: Content | The longest: you need to build an audience | Subscriptions, ads, sponsors, products |

These are rough guides for comparing routes, not an income forecast: results depend on your niche, your market and your work.

If your budget is tight → A or C. If you have 6+ months of runway → D or E.

🎨 **Picture this:** you're choosing between a vegetable garden (B2B: plant it, harvest in 2 months, money) and an apple orchard (content: plant it, it bears fruit in 3 years, but for longer and in bigger amounts). If there's food on the table today, plant the orchard. If not, dig the vegetable garden first.

---

## Hybrid routes (after your first pass)

Three or four months after you finish your first route, you'll usually want to add a second stack. Typical combinations:

| First route | Natural next step | What you add |
|---|---|---|
| A: B2B Agency | + Route E (Content) | content marketing for your agency, less spent on cold outreach |
| B: B2C App | + Route E (Content) | organic growth through YouTube and social media |
| C: Personal | + Route A (B2B) | you sell what you built for yourself to others |
| D: Corporate | + Route A (a B2B agency for small businesses) | a second funnel for smaller clients |
| E: Content | + Route B (a B2C product) | monetizing your audience through a product |

Never combine D and B at the same time: the rhythms are too different (6-month corporate cycles vs weekly B2C releases).

---

## Not on any route (but good to know they exist)

These lessons are useful but **not critical** for most routes. Come back to them when your scenario calls for it.

| Lesson | Who needs it |
|---|---|
| [CLI and automation](51-cli-tool.md) | developers with a CI/CD pipeline |
| [The competitive landscape](52-competitors-landscape.md) | strategists and investors |
| [Algorithmic trading](55-trading-terminal.md) | traders (a separate scenario; it teaches the tools and isn't investment advice) |
| [Manus AI](57-manus-ai.md) | exploration and R&D |
| [A design atlas](58-design-atlas.md) | designers and agencies |
| [An atlas of products and income models](59-product-atlas.md) | strategists and product managers |
| [Advanced Claude Code tips for 2026](60b-ultra-hacks-2026.md) | advanced users (after your base route) |
| [Local models](63-local-models-ollama.md) | privacy-critical or offline work |
| [Fine-tuning](63b-fine-tuning.md) | the ladder is prompt → RAG → fine-tuning (only when the first two aren't enough) |
| [Advanced orchestration](80-ai-sandboxes-e2b.md)–[Advanced computer use](83-computer-use-advanced.md) | teams of 5+ agents |
| [Voice and real-time](84-voice-ai-agents-vapi.md)–[Chatbot managers](86-chatbot-managers.md) | if voice is your main channel |
| [MLOps for indie developers](98-mlops-indie.md) | production with active monitoring |
| [The lesson you didn't expect](100-intrigue.md) | everyone, after any route; don't skip it |

---

## ❌ Common mistakes when choosing a route

❌ **Reading all the applied lessons in a row over two months.** After 60 days you remember 10% and haven't launched anything. That's catalog thinking: learning for the sake of learning.

❌ **Jumping between routes at random.** "Started route A, a week later jumped to E, two weeks after that to C." You lose the structure. A route is **a sequence with a logic to it**, not a pile of tags.

❌ **Ignoring the production patterns lessons once you're in production.** "My clients pay me, but I skipped plugin security and portfolio detachability." Sooner or later something breaks in production, and it's much harder to fix while a client is waiting. These lessons aren't optional once real clients depend on your work.

❌ **Not picking a route at all ("I'm just reading").** Without a clear goal, the course turns into an encyclopedia. Encyclopedias are useful as a reference, not as a learning path.

❌ **Picking 3 routes at once.** "I'm doing a B2B agency, a B2C app and a YouTube channel." That's 24 weeks of focused work running in parallel. It won't happen. Pick ONE for 3 months and the second one after that.

❌ **Ignoring Q4 (readiness level).** Jumping into the production patterns lessons before your MVP is even live is overengineering. Skipping them once you're in production is underengineering. Your level has to match the distance.

🎨 **Picture this:** the course is a supermarket of tools. Without a shopping list, you wander the aisles for 3 hours, toss whatever looks shiny into the cart, and at home you can't figure out why you bought it. With a list, it's 20 minutes, and you walk out with what you're cooking tonight.

---

## Coming back to the other lessons

A route is your **first pass**. Once you launch the first version (an MVP, a first client, a first paid product), you **come back** and take the remaining lessons, this time **to solve specific problems**.

**Signs it's time to come back:**
- "I realized I'm missing X" → read the lesson on X
- "A client asked for Y" → read the lesson on Y
- "My scenario changed (it was B2B, now it's B2C)" → take the second route all the way through
- "After a year of work, I want to scale" → go back to the production patterns lessons and to [Advanced Claude Code tips for 2026](60b-ultra-hacks-2026.md)

**Bad reasons to come back:**
- "Just curious": you'll spend hours and launch nothing
- "I have to take every lesson": that's catalog thinking again

---

## Key takeaways

> The applied lessons ahead aren't a queue to "read in order." They're a map of tools, and every tool has its own use. Pick the route that fits your scenario and come back to the rest when you need it.

> 5 routes cover the main ways to put Claude Code to work: a B2B agency, a B2C app, personal automation, corporate consulting, a content creator. If your scenario doesn't fit any of them, combine two, one after the other (3 months + 3 months).

> The production patterns lessons are the line between "played around with Claude" and "built a production-grade system." Skipping them for an MVP is fine. Skipping them in production makes trouble much more likely once real clients depend on you.

> This lesson isn't an instruction manual; it's a map. Come back to it every 2 to 3 weeks and check: am I still on my route, or am I drifting into "just curious"?

---

## ✅ Checklist

- [ ] Answered Q1: who my client is (B2B / B2C / B2Me / Corporate / Audience)
- [ ] Answered Q2: what I sell (a service / a product / content / data / SaaS)
- [ ] Answered Q3: which stack I'm betting on (text / voice / video / web / automation / data)
- [ ] Answered Q4: where I am (MVP / Beta / Production / Enterprise)
- [ ] Picked one of the 5 routes (A / B / C / D / E)
- [ ] Wrote down the 8 to 12 lessons on my route in a to-do app, Obsidian or a notebook
- [ ] Understand why I'm NOT reading the other lessons now (I'll come back to them when I need them)
- [ ] Know after which lesson on my route I go back to the production patterns lessons (if I'm in production)
- [ ] Set a start date for my route and an expected finish date (6 to 12 weeks)

---

## Next lesson

→ [Chatbots with the Claude API](50-telegram-bots.md): from your first bot to Cloudflare Workers in production

(or the first lesson on your route, if it starts somewhere else)
