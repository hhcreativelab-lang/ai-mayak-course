# What is an AI agent, and why it matters now

**Time:** about 25 min reading + 20 min practice

---

## The gist

Picture the construction business back when one builder laid every brick personally: slow, expensive, limited. Now there are construction crews you can simply tell, "I want this kind of house," and they build it. Agentic AI is that kind of shift for business automation.

**What is an AI agent, in simple terms?** It's an AI system that doesn't just answer you but carries out a task in several steps on its own: it looks up data, makes decisions along the way, calls other programs and services, and deals with errors. A chatbot is only the window you talk to it through.

---

## Key concepts

- The agentic AI market: where we are now and where it's heading
- Why the mid-2020s are an entry point, not "too early" and not "too late"
- What made agentic systems possible in production (real, everyday business use, not a demo)
- The role of Claude Code as a tool you can use without being a developer

---

## Theory

### Market numbers: from niche to mainstream

🎨 **Picture this:** the smartphone market in 2007, the moment the first iPhone came out. People who started building apps in 2008-2009 were working in a young, growing market; later on it got more crowded. Agentic AI today looks a lot like the early years of mobile apps.

Estimates of the size of the agentic AI market differ widely from one research firm to the next, so this lesson doesn't quote specific dollar amounts. If you come across a number in an article, check whose report it is and what year it's projecting for. Look for fresh overviews from Gartner and McKinsey (search tips at the end of this lesson).

A sense of direction: in August 2025, the research firm Gartner forecast that by the end of 2026, up to 40% of enterprise applications would include task-specific AI agents, compared with fewer than 5% in 2025 (Gartner press release, August 26, 2025). That's a forecast, not a fact. But it shows the scale: the technology is already inside products people use every day.

**What's happening right now:**
- Agentic features are built into everyday products: Claude has Claude Code and Cowork, ChatGPT has a Work mode for tasks, and most major assistants now have "agent" modes. What's available on which plan is on the [What's current](https://aimayak.com/en/now/) page.
- Companies in banking, retail, logistics, media and more are launching agents. The results vary: in some places the gain is obvious right away, and in others the systems have to be put back under human supervision (see the Klarna example below).

The careful conclusion: many companies are trying to roll out agents, and not all of them succeed. People who know how to build agentic systems and check how well they work have an advantage, especially where there's no in-house tech person.

### Why now: three factors came together

**Factor 1: LLMs (large language models, the AI behind assistants like Claude and ChatGPT) became reliable enough**

🎨 **Picture this:** early LLMs were like a first-year intern: smart, full of energy, but now and then confidently saying complete nonsense. Today's models are more like an employee with 5 years on the job: they still make mistakes sometimes, but with a person reviewing the results, they're reliable enough for real work.

As recently as 2023, language models often "hallucinated" (a hallucination is when AI confidently makes up a fact), giving confident but false answers. In production, that's a serious problem: if a system automatically sends emails to clients based on false data, that isn't automation, it's a disaster.

Since mid-2024, the flagship models (Claude 3.5 Sonnet, GPT-4o and Gemini 1.5 Pro; the model lineups have changed several times since, and the current list is on the [What's current](https://aimayak.com/en/now/) page) have reached a level of reliability where they can be used for repetitive business tasks. Not perfect, but good enough to build production systems with sensible human review.

**Factor 2: The infrastructure showed up**

🎨 **Picture this:** building an agentic system before 2024 was like mining the ore, pouring the steel and welding the frame yourself before you could even start on the house. Now it's like buying ready-made building materials at Home Depot: you grab what you need and put it together following the instructions.

It used to be that to build an agentic system, you had to solve dozens of infrastructure problems on your own: how to run tasks on a schedule, how to keep track of state between steps, how to handle errors, how to deploy (put your system online so it actually runs).

Now ready-made tools take care of these problems:
- **trigger.dev**: runs background jobs and workflows, with error handling out of the box
- **Modal**: runs Python code (Python is a programming language) in the cloud without setting up servers
- **Vercel**: one-click deployment
- **MCP (Model Context Protocol)**: a standard way to connect tools to an LLM
- **Skills (reusable instructions in Claude Code)**: ready-made patterns for common tasks

**Factor 3: Claude Code made it possible without developer skills**

Historically, only a developer could set up automation. Now Claude Code lets you describe a task in plain English, and the agent (a program that carries out tasks on its own) writes the code, creates the files and sets up the structure itself.

That doesn't mean developers are no longer needed; complex systems still need them. But the barrier to building automations that actually work has dropped dramatically.

### The construction crew vs. you and a pile of bricks

**Traditional automation** (without agentic AI):
You lay every brick yourself. You set up each step by hand in Zapier or n8n. When something unusual comes up, the automation breaks and you're back to doing it by hand.

It's like building a house alone: it can be done, but it's slow, expensive and limited in scale.

**Agentic workflows** (with Claude Code):
You hire a construction crew. You explain what you want to end up with. The crew figures out how to build it, adapts to surprises along the way, and asks clarifying questions only when it genuinely doesn't know.

You move from the role of "builder" to the role of "architect."

### Who's already doing this: real examples

**Morgan Stanley**: since 2023, the bank has given its financial advisors an AI assistant built on OpenAI models. It finds what's needed in a large internal library of research and documents and helps advisors answer clients faster. A separate tool takes notes during meetings (with the client's consent) and drafts follow-up emails, which the advisor edits before sending.

**Klarna** (an online payments company): in February 2024, the company said its AI assistant in customer service was doing work comparable to that of 700 full-time agents (Klarna press release). In May 2025, its CEO told Bloomberg that focusing too much on cost had lowered the quality of service, and promised customers they would always be able to talk to a real person. The lesson: the agent handles routine requests, and complex cases have to reach a human.

**Notion**: built an AI agent into its product. When a user asks, it creates pages, fills in databases and puts together reports (for the full list of what it can do, see Notion's documentation).

These aren't futuristic examples. They're already live and running, limitations included.

### Where you come in

🎨 **Picture this:** you don't have to be Nike to sell sneakers. Millions of small shops sell shoes to everyday customers. Agentic systems for small businesses are your "neighborhood stores" in the world of AI. Morgan Stanley is the shopping mall. But there are only so many malls, and neighborhood stores are everywhere.

You're not Morgan Stanley. You don't have a team of 50 developers. But you do have Claude Code, and that's what changes the equation.

Small agentic automations for small and mid-sized businesses (SMBs) are a clear entry point. A small business can't hire its own AI team, but it can order a ready-made solution from someone who knows how to build it.

That's one of the roads this course shows: learn to build, package it as a service, offer it to clients. The course is free, and income from this kind of work depends on your niche, your market and your effort. Nobody can guarantee it.

---

🎨 **Picture this:** the agentic AI market is like the early website market of 1998-2002. Every business was about to want "a website." Back then, the job was called "web developer." Now it's called "agentic systems builder." The difference: back then you had to spend a long time learning HTML/CSS/PHP. Today the basics come together noticeably faster with Claude Code, but quality, security and checking the results still take real learning.

---

## Practice

**Exercise:** Research 3 companies that already use agentic AI systems in production.

1. Find three case studies from different industries (you can search for "AI agents case study 2026")
2. For each one, write down:
   - What task the agentic system handles
   - What result the company got (in numbers, if available) and who reports it: the company itself, the vendor of the solution or an independent source
   - What it looked like before (how they did it without an agent)
3. Write one sentence: "In my business, or for my clients, agentic automation could help with ___"

**Time to set aside:** 20 minutes.

---

## Common mistakes

❌ **Mistake:** Thinking agentic AI is just chatbots like ChatGPT.
✅ **Instead:** Agentic AI means systems that carry out multi-step tasks on their own: they look up data, make decisions, call APIs (application programming interfaces, the way programs talk to each other) and handle errors. A chatbot is just the interface.

❌ **Mistake:** Waiting for the technology to "mature" and go mainstream.
✅ **Instead:** Agentic features are already built into products that huge numbers of people use. Trying them on a small task now is the easiest way to see what they can and can't do.

❌ **Mistake:** Trying to build complex enterprise solutions like Morgan Stanley's right away.
✅ **Instead:** Start small, with automations for small and mid-sized businesses. Simple 3-5 step workflows that solve one specific pain point for a client.

---

## Tools and resources

- **[Claude.ai](https://claude.ai)**: for finding case studies and analyzing them
- **[Claude Code](https://code.claude.com/docs/en/overview)**: the agent's official documentation
- **[Anthropic Blog](https://www.anthropic.com/news)**: examples of Claude used in production
- **Gartner: Agentic AI**: official market forecasts (search: "Gartner Agentic AI forecast 2030")
- **McKinsey: The state of AI**: an annual report on the AI market (search: "McKinsey Global Survey AI")
- **a16z AI Canon**: a 2023 collection of reading on modern AI from the venture firm Andreessen Horowitz

→ In the library, optional: the lesson [Agentic workflows vs. traditional automation](02-why-agentic-beats-traditional.md) for a detailed comparison with Zapier and n8n
→ See the lesson [First clients](38-monetization-clients.md) for how to offer your agentic skills to clients

---

## Key takeaways

> Agentic AI is already built into mainstream products. Market estimates vary, so watch the direction, not one impressive number.

> Large companies are rolling out agents; small businesses can use them too, and someone will have to build them. But the results depend on the task you pick and on quality control.

> Three factors came together right now: reliable LLMs + ready-made infrastructure + Claude Code as a way in that doesn't require developer skills.

---

## Next lesson

→ [No-code AI for non-programmers: v0, Webflow, Framer](77-no-code-ai.md): your first build with AI tools that need no code
