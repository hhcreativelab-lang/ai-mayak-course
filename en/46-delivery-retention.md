# How to hand off a project and keep the client

**Time:** about 25 min reading + 30 min practice

---

## The gist

Selling a house isn't finished when you hand over the keys. It's finished when you've shown the buyer where the light switches are, how the water heater works and which neighbor is easy to deal with, and made sure the new owner feels at home. A handoff is a guided tour of the system for your client. Retention is when you call a month later and ask, "How's the water heater holding up?" Many freelancers hand over the keys and disappear. That's a mistake.

---

## Key concepts

- **Handoff protocol**: a structured handoff: documentation, training, access
- **An SOP for the client**: instructions written for someone who isn't a programmer
- **A Loom walkthrough**: a 5-minute video walkthrough (better than 10 pages of text)
- **One month of support included**: the period when the client gets used to the system
- **Upsell**: "you could also automate..." as the natural next step
- **A monthly report**: numbers that show what the system is worth, every month
- **NPS score**: one question that shows how satisfied the client is

---

## Theory

### Why the handoff matters more than the product itself

A good system plus a poor handoff = an unhappy client.
An average system plus a great handoff = a happy client who recommends you.

The client isn't buying code or Cloudflare Workers. They're buying **a solution to a problem** and **the confidence that it works without them**. Your job is to build that confidence through the handoff.

🎨 **Picture this:** you're selling a furnished house. You don't just leave the keys on the kitchen counter. You walk the buyer through it: here are the light switches, here's the furnace filter (swap it every few months), here's the number of a plumber I trust. The buyer walks out feeling like the owner of the place, not a guest.

---

### The handoff protocol: 5 steps

**Step 1: Access and accounts**

Give the client everything they need to run things on their own:

```
Access checklist:
□ Cloudflare Workers / Trigger.dev: add the client as a team member
□ Google Sheets / Notion: share with edit rights
□ Slack bot (or wherever the system sends its updates): the client should be an admin or have access to the bot's settings
□ API keys: hand over instructions on how to renew them if they expire
□ GitHub repo: add the client as a collaborator (if needed)
□ Billing access: who pays for the API (agreed on in advance)
```

When you hand over keys and passwords, use the service's own team access or a password manager, not a plain email or chat message.

**Step 2: A Loom video walkthrough (up to 5 minutes)**

Record your screen while you show:
1. How to run the main workflow (every step)
2. Where to find logs and stats (point to the exact cells in Sheets)
3. How to add a new user or change settings
4. What to do if the system stops responding (3 troubleshooting steps)
5. How to reach you if they need help

Upload it to Loom and send the client the link. On Loom's free plan a video can be up to 5 minutes long; if you can't fit everything in, record two short ones. Most people will watch a short video sooner than read PDF instructions.

**Step 3: An SOP document (1-2 pages)**

An SOP (Standard Operating Procedure) is written so that someone with no technical background can handle things:

```markdown
# How to use [System name]

## Day to day
1. The system runs automatically; you don't need to do anything
2. Every [day/week] you'll get a notification in Slack (or by email) with a preview
3. Click "Send" to approve it, or "Edit" to make changes

## How to change settings
If you need to change [setting], message me in Slack or email me: [contact]
It usually takes 1-2 hours.

## What if something goes wrong?
1. Check [specific step]: most problems start here
2. Restart it with [specific button/command]
3. If that doesn't help, message me: [contact] + a screenshot of the error

## Maintenance schedule
- Every 90 days: renew the API keys (I'll remind you ahead of time)
- Once a month: check the error log in [Sheets/Notion]
```

🎨 **Picture this:** the final demo is like starting the engine after a repair at the shop. You can say "it's all done" as many times as you like. Until the key turns and the engine runs, the client doesn't believe it. Start it together, and they see the car drive.

**Step 4: A final demo before closing**

Run the system together with the client once, so they see the whole process with their own eyes. Answer their questions. Make sure they understand the basic operations.

**Step 5: Officially closing the project**

An email, or a message in Slack or your client portal:

```
[Name], the project is complete!

Here's what you're getting:
✅ [List of features]
✅ Loom walkthrough: [link]
✅ SOP document: [link]
✅ Access to [list]

One month of support is included, so if any questions come up, just reach out.
The second payment ($X): here's the invoice [link].

Thank you for working with me!
```

---

### One month of support: why it's the standard

🎨 **Picture this:** a month of support is like a new hire's first month on the job. They're already doing the work and getting paid, but HR checks in often during that first month. The client gets used to the system, asks questions and sees that it's reliable. After that, they run it on their own and trust it.

An included month of support isn't charity. It's an investment:

**For the client:** it lowers the "what if I can't handle it" risk. They know you're there.

**For you:**
- You see how the system works in real conditions
- You get feedback that improves your template
- You build trust for the next contract
- Clients who got good help in the first month are more willing to sign a maintenance contract

**How to run support:**
- A separate channel just for this client: a shared Slack channel (invite everyone on their side who needs it), a client portal, or one dedicated email thread
- Response time: within one business day for non-critical questions
- Critical issues (the system is down): 4 hours at most
- After the month: offer a maintenance contract, or simply explain that the support period has ended

---

### Upsell: "you could also automate..."

Every conversation with the client during support is a chance to learn what else is causing them trouble.

**How to upsell naturally:**

Not "I've got a new product, buy it." Instead, an observation plus a question:

```
Client during the demo: "Too bad it can't add these to our CRM automatically..."
You: "That's technically doable. An integration with your CRM would take about a week.
Want me to put together a price for it?"
```

**Typical upsell opportunities:**
- Adding a new integration (a CRM, a payment system, another messaging app)
- Extending it to another business process
- A version for phones (a Slack app or text-message alerts instead of only a web dashboard)
- An analytics dashboard for management
- Training for the team

Keep a backlog for each client: a list of what they mentioned as "it would be nice if..." Every 2-3 months, come back to it: "Remember you mentioned X? I just built that for another client. Want me to show you?"

---

### A monthly report: make the value visible

🎨 **Picture this:** a monthly report is like the display on a treadmill. You're already running and don't notice how many calories you've burned. The display shows you, and you remember why you keep going. The client "runs" every day without noticing the savings. The report reminds them.

The problem: the client gets used to the automation and forgets how much it saves. Three months later they think, "Well, it works. Why pay for support?"

The fix: a monthly report that shows the numbers.

**Report template (simple, 1 page):**

```markdown
# Report for [Month]: [System name]

## What the system did this month
- Requests handled: [X]
- Emails sent: [X]
- Reports generated: [X]

## Your savings
- Hours saved: [X hours] (at $[Y]/hour = $[Z])
- Errors prevented: [X] (manual errors across X operations)

## System status
- Uptime this month: [99%+]
- Errors: [0 / description if there were any]
- API costs: $[X] (within plan)

## Next month
- [Any planned changes]
```

This report takes 15 minutes to put together (or automate it!). It reminds the client why they pay for support. Put only real numbers in it.

---

### NPS: one question that tells you a lot

🎨 **Picture this:** NPS is like a thermometer. One instrument, one scale, and you can tell right away: fever (0-6), normal (7-8), feeling great (9-10). You don't need complicated surveys. One number shows how the client is doing and what to do next.

NPS (Net Promoter Score) is the simplest way to measure satisfaction:

**Two to three weeks after launch, ask:**

```
"[Name], the system has been running for a few weeks now.
On a scale of 0 to 10, how likely are you to recommend
me to your colleagues or business partners?"
```

- **9-10** → Promoter (a happy client: ask for a referral right now)
- **7-8** → Passive (neutral: find out what could be better)
- **0-6** → Detractor (there's a problem: fix it right away)

**For promoters (9-10), right away:**

```
"Great to hear! By the way, you mentioned you know other business owners
who are dealing with similar tasks. Is there anyone who might find this useful?
I'd be glad to talk with them."
```

---

### Retention through long-term relationships

The best client is one who pays every month, so you don't have to go looking for a new one.

**Three retention tools:**

1. **A monthly report**: makes the value visible (see above)

2. **Proactive updates**: tell them about new options yourself, don't wait for them to ask:
   ```
   "Anthropic released a new version of Claude, and the system may get faster.
   Want me to update it? It takes 30 minutes, with no downtime."
   ```

3. **A yearly review**: once a year, offer an audit of the system:
   ```
   "It's been a year since launch. I'd suggest an audit:
   we'd look at what can be optimized and which new processes
   are worth automating. The audit costs $[X], and you come away
   with a task list for the year ahead."
   ```

---

## Practice

**Exercise: Build a handoff kit for your project**

Take any piece of work you've done with AI: for a client, for yourself or for someone you know. If you don't have one yet, make up a practice example, such as "answering routine emails for a dental office," and build the kit for that.

1. Write an access checklist: everything the client should receive:
   ```
   □ [Service 1]: [how to hand it over]
   □ [Service 2]: [how to hand it over]
   ```

2. Record a Loom walkthrough (up to 5 minutes):
   - Show the system in action
   - Explain each step in plain language

3. Write an SOP document: 1 page for someone with no technical background

4. Write a template for your final email to the client (closing the project)

5. Write a monthly report template for this project:
   - Which metrics will go into it?
   - How will you collect them (automatically through Sheets, or by hand)?

**Goal:** a complete handoff kit, ready to use. Any client can get it once their project is finished.

---

## Common mistakes

- **No follow-up after delivery.** You hand over the project and vanish. A month later the client has forgotten about you. One "How's the water heater?" call 2-3 weeks later keeps the relationship going and gives you a shot at an upsell.
- **Not asking for referrals.** Happy clients are often willing to refer you, if you ask. Many freelancers never do. The best moment is right after an NPS of 9-10.
- **Loom instead of written instructions, not alongside them.** People watch videos and skip PDFs. But some clients want a written guide they can search quickly. Do BOTH: Loom for learning, the SOP for reference.
- **Not keeping a backlog of upsell opportunities.** Every "it would be great if..." from a client is a future contract. Write it down in a separate spreadsheet and come back to it every 2-3 months.
- **Not automating the monthly report.** A client report is a perfect candidate for automation. Spend 2 hours setting up automatic metric collection, and you save 15 minutes × 12 months × N clients.

---

## Related lessons

- **→ [Portfolio and case studies](41-portfolio-case-studies.md)**: already covered: every delivered project is a new case study for your portfolio, and every testimonial is social proof
- **→ [Packaging](42-packaging.md)**: already covered: the documentation levels (README / Loom / SOP) match the Basic, Pro and Enterprise packages
- **→ [The factory model](48-factory-model.md)**: coming up in the "Your 90-day plan" module: your handoff kit becomes the template for your next projects

---

## Tools and resources

- **Loom**: [loom.com](https://www.loom.com/). Screen recording for walkthroughs; as of October 2026, the free plan is limited to 5 minutes per video and 25 videos per person. Check the website for current terms
- **Notion**: [notion.com](https://www.notion.com/templates). Handy for SOP documents (you can share them by link); a shared Notion page can also work as a simple client portal
- **Google Sheets**: for automatically collecting metrics for the monthly report
- **Slack**: shared channels for client support (many businesses already use it every day)
- **Tally**: [tally.so](https://tally.so/). A form for collecting NPS scores and client feedback (there's a free plan)
- **Calendly**: [calendly.com](https://calendly.com/). For booking the yearly review with the client
- **Stripe**: [stripe.com](https://stripe.com/). For automatic recurring billing on a maintenance contract. It isn't available in every country: the list is at stripe.com/global

---

## Key takeaways

> The client is buying confidence that the system works without them. The handoff is how you create that confidence. Documentation and video matter more than beautiful code.

> An included month of support is an investment. You see real-world use, build trust and get data for your next project.

> A monthly report makes invisible value visible. The client gets used to the automation and forgets why they're paying, so remind them with numbers.

> NPS of 9-10 → ask for a referral right away. Happy clients often give one if you ask. Many people never ask.

---

## Next lesson

→ [How to build a personal brand with AI](67c-personal-brand-ai.md): the first lesson of the "Getting found: content, ads and sales" module

You've already seen project breakdowns with numbers in the lesson [Monetization case studies](47-monetization-cases.md).
