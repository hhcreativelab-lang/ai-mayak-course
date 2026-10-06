# The factory model: templates for repeatable client work

**Time:** about 25 min reading + 30 min practice

---

## The gist

Your first house takes 3 months to build. Your tenth takes 3 weeks, because by then you have wall templates, suppliers you trust, and a crew that knows what to do. The factory model means every new project of a similar type gets done faster and cheaper than the one before. And you can charge the client a bit more, because a faster result is worth more to them.

If you sell AI services as a freelancer or on the side, this is how you take on similar projects without the hours piling up every time.

The examples in this lesson come from projects built with code: you build those in Claude Code, which the next module of the course and the deep-dive library cover. You don't need to understand every file name. If you work without code for now, take the principle: a template can be a set of prompts, the structure of a proposal or a handoff checklist.

---

## Key concepts

- **Factory**: a system of templates for scaling: 80% standard + 20% customization
- **Template repo**: the starting point for each type of project, so you never start from scratch (a repo, short for repository, is a project folder tracked with Git)
- **SOP (standard operating procedure)**: a documented process for each project type
- **Delivery time**: cut from 2 weeks to 5 business days thanks to templates
- **A team of agents**: specialized Claude subagents (helper agents, each with one narrow job) for each template
- **Price premium**: faster = pricier (value-based, not time-based)

---

## Theory

### The problem with one-off work

🎨 **Picture this:** a cook who reinvents the chili recipe every single day. Every time, they hunt for the proportions, forget how much salt goes in, and spend an hour instead of fifteen minutes. A head chef writes the recipe down once and then repeats it perfectly, for any number of servings.

Starting from scratch every time is expensive and slow:

```
Project 1: Newsletter Automation
- Gmail API OAuth setup: 4 hours
- Cloudflare Worker structure: 3 hours
- Slack bot setup: 2 hours
- Total infrastructure: 9 hours (out of ~40 total)

Project 2: Newsletter Automation (another client)
- Gmail API OAuth setup: 4 hours (again!)
- Cloudflare Worker structure: 3 hours (again!)
- Slack bot setup: 2 hours (again!)
- Total infrastructure: 9 hours (22% of all your time on things you've already done)
```

After 5 similar projects you could be working twice as fast, but you start over every time.

🎨 **Picture this:** your first house takes 3 months. Everything is new: where to buy materials, how to pour the foundation, which crew you can rely on. Your tenth house takes 3 weeks: the materials are ordered ahead from a supplier you trust, the crew knows their roles, and the standard walls are already in the plans. The houses look different on the outside. The system inside is the same.

---

### Three types of templates in a factory

🎨 **Picture this:** builders work with three kinds of ready-made pieces: standard foundation plans (the same for every house), standard floor plans (a few options to pick from), and finishes the client chooses (different every time). Three levels of templates, three levels of speed.

**Type 1: Infrastructure template**

Repeating code that's the same in every project:

```
template-base/
├── cloudflare-worker/
│   ├── worker.js              ← main Worker with routing
│   ├── auth.js                ← OAuth helpers for Google/Microsoft
│   ├── slack-bot.js           ← basic Slack bot setup
│   └── kv-storage.js          ← helpers for Cloudflare KV
├── triggers/
│   ├── cron-template.ts       ← Trigger.dev cron job template
│   └── webhook-template.ts    ← webhook listener template
├── utils/
│   ├── claude-client.js       ← Anthropic API wrapper with retry logic
│   ├── error-handler.js       ← standard error handling
│   └── logger.js              ← structured logging
├── .env.example               ← always the same structure
├── .gitignore                 ← standard
└── README-template.md         ← documentation template
```

(A cron job is a task that runs on a schedule. A webhook is a message one app sends to another when something happens. A .env file holds a project's settings and secret keys.)

New project = `git clone template-base new-project-name` (a Git command that copies the template into a new folder). The infrastructure is ready in 30 minutes, not 9 hours.

**Type 2: Workflow template**

A complete template for one specific type of project:

```
template-newsletter/           ← for Newsletter Automation
template-lead-gen/             ← for Lead Generation
template-exec-assistant/       ← for Executive Assistant
template-content-pipeline/     ← for Content Creation
template-crm-integration/      ← for CRM integrations
```

Each one contains: the core workflow logic, the standard tools, a CLAUDE.md with a specialized prompt (CLAUDE.md is the instruction file Claude Code reads when it works in that project), and a .env.example listing the API keys you'll need.

**Type 3: CLAUDE.md templates**

Specialized instructions for agents, one set for each type of task:

```markdown
# CLAUDE.md for the Newsletter Automation Agent

You are a newsletter automation agent.
Your job: gather news, generate content, coordinate sending.

## Working rules:
- ALWAYS show a preview before sending
- Use brand_guidelines.md for the tone of the email
- If an API returns an error, log it and continue with partial data
- No more than 5 news items per issue unless told otherwise

## Format for each news item: headline + 2 sentences + link
...
```

---

### 80% template + 20% customization

🎨 **Picture this:** a suit from a tailor. 80% is the standard patterns the tailor has used for years: the cut of the jacket, the shoulder width, the sleeve length. 20% is about you: your measurements, the fabric you picked, the color of the buttons. The client gets a custom suit. The tailor doesn't cut from scratch every time.

This is the key ratio of the factory:

**80% standard (from the template):**
- File structure
- Connections to API services
- Error handling and logging
- Basic Slack bot features
- Handoff documentation (take README-template.md and fill it in)

**20% customization (for the client):**
- The client's specific data sources
- Brand voice and content style
- Business rules (what counts as a "hot lead" for this company)
- Integration with the client's specific CRM
- Specific notifications and thresholds

You customize 20% for the client, but they get a 100% product. For you, 80% is already done.

---

### How a factory cuts delivery time

**Without a factory:**
```
Week 1: infrastructure setup + core workflow
Week 2: customization + testing + documentation
Total: 2 weeks
```

**With a factory:**
```
Day 1: clone the template + set up .env + first run
Days 2-3: customization for the client (20% of the logic)
Day 4: testing + fixes
Day 5: handoff + demo
Total: 5 business days (1 week)
```

Twice as fast, with the same result for the client.

---

### Price premium: faster = pricier

🎨 **Picture this:** express shipping. Regular mail: 5 days, $5. A courier who delivers by tonight: $50. The product is the same, an envelope with documents. But speed costs 10 times more. The client isn't paying for the miles. They're paying to have the problem solved today instead of on Friday.

It sounds backwards, but it often works. The client isn't paying for your time; they're paying for the result. If the result arrives sooner, it's worth more.

**Positioning:**

❌ "I can do it in 1 week instead of 2 because I have templates"

✅ "Because I specialize in this type of project, I launch the system in 5 days. For most clients that matters: the sooner the system is running, the sooner the savings start."

**Pricing with a factory, in practice:**

| Type | Without a factory | With a factory | Your revenue per hour |
|---|---|---|---|
| Newsletter Automation | $2,000 for 2 weeks | $2,200 for 5 days | Up about 2.2x |
| Lead Gen Pipeline | $3,000 for 3 weeks | $3,200 for 8 days | Up about 2x |
| Executive Assistant | $4,500 for 3 weeks | $5,000 for 10 days | Up about 2.2x |

The client pays a little more and gets the result twice as fast. In this hypothetical calculation, the revenue per hour of your work doubles. The numbers are illustrative: your hours and prices will be different, and this is not a promise of income.

---

### A team of agents for each template

Each workflow template comes with specialized subagents. Claude Code looks for them in the `.claude/agents/` folder inside the project:

**template-newsletter:**
```
.claude/agents/
├── researcher.md     ← finds and evaluates news
├── writer.md         ← writes content in the brand voice
├── assembler.md      ← builds the HTML email
└── coordinator.md    ← orchestrates the whole process
```

**template-lead-gen:**
```
.claude/agents/
├── prospector.md     ← finds potential clients
├── personalizer.md   ← writes personalized emails
├── qualifier.md      ← rates lead quality
└── crm-updater.md    ← updates data in the CRM
```

When you start a new newsletter project, you take the ready-made agents from the template and change only the CLAUDE.md with that client's specific details.

---

### An SOP for each project type

🎨 **Picture this:** a pilot's checklist in the cockpit. Before takeoff, it's the same checklist every time: flaps, pressure, contact with the tower. The pilot doesn't improvise. That doesn't make them a robot; it means they don't forget to check the tire pressure when they're nervous.

A standard operating procedure is a document for you (not for the client): how to launch a project of this type, step by step:

```markdown
# SOP: Newsletter Automation Project

## Day 1: Setup (2-3 hours)
□ git clone template-newsletter [project-name]
□ Create .env from .env.example, get the API keys from the client
□ Run a basic test: python test_connections.py
□ Set up the Cloudflare Worker (wrangler deploy)
□ First test run of the workflow with mock data

## Days 2-3: Customization (4-6 hours)
□ Load the client's brand_guidelines
□ Set up the news sources (Perplexity query, RSS feeds)
□ Set up the HTML template to match the client's brand
□ Set up the recipient list (test mode)
□ Slack bot: add the client as an admin

## Day 4: Testing (3-4 hours)
□ Full run with real data
□ Send a test email to your own address
□ Check the logging in Google Sheets
□ Fix all issues

## Day 5: Handoff (2-3 hours)
□ Record a Loom walkthrough (20 min)
□ Update README-template.md for this project
□ Final demo with the client
□ Hand over access using the checklist
□ Send the final project-completion email
```

An SOP takes 30 minutes to write, and it saves hours on every project after that.

---

### When a factory pays off

🎨 **Picture this:** sharpening the saw before you start cutting. The first 20 minutes go into sharpening, and it feels like lost time. But with a dull saw, one tree takes an hour. With a sharp one, 15 minutes. The more trees ahead of you, the more those 20 minutes pay off.

An honest estimate:

- **1-2 projects of one type:** building the template hasn't paid off yet
- **3rd project:** the template starts saving time
- **5th project:** you're 2-3x faster than a beginner doing it from scratch
- **10th project:** your factory is fully formed; you've mastered this type of project

Start building the template after your second project of the same type. That's the right moment. Any earlier is premature optimization.

---

## Practice

**Exercise: create your first template**

1. Take a piece of work you've already done at least once: a service from your packages, or an automation if you've already built one (the example below uses the newsletter automation from the deep-dive library)

2. Create a folder `templates/newsletter-automation-template/` (swap newsletter-automation for the name of your own work):
   - Copy in all the project files: documents, prompts, spreadsheets, and code if there is any
   - Replace all client-specific data with placeholders (`[CLIENT_NAME]`, `[BRAND_COLOR]`, `[API_KEY]`)
   - Make a checklist of what needs replacing during customization

3. Write an SOP for this project type (5 days, as in the example above):
   - Day 1: what do you do?
   - Days 2-3: customization: which specific files do you change?
   - Day 4: testing: which checks do you run?
   - Day 5: handoff: which documents do you create?

4. Estimate: if you'd had this template from the start, how many days faster would the project have been?

5. Work out the price premium: if without a template a project takes you 10 days and you charge $2,000, how many days does it take with a template, and what's the new price? Check yourself against the example in this lesson: twice as fast and a little pricier, so about 5 days and about $2,200. Your revenue per day then goes from $200 to $440.

**Goal:** one working template in the `templates/` folder. That's the first brick of your factory.

---

## Quick reference: factory efficiency metrics

| Project type | Without a factory | With a factory | Savings | Effective rate |
|---|---|---|---|---|
| Newsletter Automation | 40 hours / 2 wks | 20 hours / 5 days | 50% of time | $2,200 for 20h = $110/hour |
| Lead Gen Pipeline | 60 hours / 3 wks | 30 hours / 8 days | 50% of time | $3,200 for 30h = $107/hour |
| Executive Assistant | 80 hours / 3 wks | 40 hours / 10 days | 50% of time | $5,000 for 40h = $125/hour |
| Content Pipeline | 45 hours / 2 wks | 22 hours / 5 days | 51% of time | $2,400 for 22h = $109/hour |
| CRM Integration | 70 hours / 3 wks | 35 hours / 8 days | 50% of time | $4,200 for 35h = $120/hour |

**Bottom line:** in this example, a factory doubles your effective rate: $50-60/hour without templates → $107-125/hour with templates, at almost the same price for the client. This is a practice calculation, not an earnings forecast.

---

## Common mistakes

- **Scaling before you have an SOP.** Without a documented process, you're scaling chaos. First an SOP for one project type → then a second → then an assistant.
- **Optimizing too early.** A template after your first project is premature optimization. After your second project OF THE SAME TYPE is the right time.
- **Template = a copy of your last project.** Don't copy blindly. Remove the client-specific data, swap in placeholders, add a "what to replace" checklist. Otherwise the next client gets the previous client's data.
- **Never updating your templates.** APIs change, and best practices evolve. After every 3rd project, review the template: what could be better?

---

## Related lessons

- **→ [Packaging](42-packaging.md)**: Basic/Pro/Enterprise packages = ready-made configurations for your factory
- **→ [Delivery and retention](46-delivery-retention.md)**: the handoff kit from that lesson = part of the SOP for your next project
- **→ [Monetization case studies](47-monetization-cases.md)**: the patterns from the 5 cases = the basis for 5 types of templates

---

## Tools and resources

- **GitHub**: a private repo for storing your templates (so they don't get lost between computers)
- **Cookiecutter** (Python): a tool for creating projects from templates on the command line
- **Notion**: [notion.com/templates](https://www.notion.com/templates), for storing SOP documents (easy to search and organize)
- **GitHub Actions**: automatic testing of your templates whenever they change
- **Loom**: [loom.com](https://www.loom.com/), for recording SOP videos so you can hand the work to an assistant
- **Upwork**: [upwork.com](https://www.upwork.com/), for hiring an assistant for operational tasks once your factory is running
- **Fiverr**: [fiverr.com](https://www.fiverr.com/), for quick hires on one-off tasks (design, testing)
- **Contra**: [contra.com](https://contra.com/), a platform for freelancers; as of October 2026 it says freelancers pay no commission

---

## Key takeaways

> 80% standard + 20% customization: that's the factory formula. Not 100% custom every time.

> Faster = pricier. The factory paradox: the less time you spend, the more you can often ask for. Clients value the result, not the process.

> An SOP is for you, not for the client. Document the process so the next project of this type runs almost on autopilot.

> Start building a template after your second project. Any earlier is premature optimization; any later is lost time.

---

## Next lesson

→ [Graduation](49-graduation.md): your 30-60-90 day AI business plan
