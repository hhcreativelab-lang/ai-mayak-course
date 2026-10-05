# How to write a good prompt

**Time:** about 15 min reading + 20 min practice

---

## The gist

A prompt is the text request you give an AI: the task you're handing it. Think of it as a work order for a contractor. A vague work order gets a poor result, and that isn't the contractor's fault. A clear work order gets an accurate result much sooner, often on the first try. This lesson teaches you how to write good work orders for any AI assistant: Claude, ChatGPT, Gemini. The examples come from everyday work: an email, a summary, a plan. If you go on to build with Claude Code later (it's an agent, a program that carries out tasks on your computer on its own), the principles stay the same, and there's a short note in this lesson for that.

---

## Key concepts

- An AI assistant = a capable contractor who knows only what you've told it
- How specific your prompt is directly decides the quality of the result
- The difference between a bad prompt and a good one, with real examples
- Questions and a plan first: what to do when you're not sure what you want (in Claude Code this is called Plan Mode)
- How the quality of the output depends on how well you understand the subject

---

## Theory

### AI is a contractor, not a magician

It's tempting to think of AI as a magic wand: "I say what I want and get it done." A better way to think about it:

**An AI assistant is a capable contractor** with broad knowledge who can write, calculate, explain and plan. But it only has what you've given it:

- The text of your request
- The files and documents you attached to the conversation
- What's already been said in this conversation (and, if the assistant's memory feature is on, some things from earlier ones)

It doesn't know your company, your customers or the tone you usually write in unless you explain them.

That's exactly why **vague requests get vague results**, and specific requests get precise results.

🎨 **Picture this:** a prompt is the work order you hand a general contractor. Say "Build something nice," and the contractor will build something. Maybe you'll like it, maybe you won't. Say "Build a two-story house, about 1,300 square feet, three bedrooms, a one-car garage, brick exterior, metal roof," and the contractor knows exactly what to build.

### Anatomy of a bad prompt

Let's take apart a typical bad request:

```
Write an email to a customer about a delayed order
```

What the assistant can't tell from this request:

- Who is the customer, and how formal should you be with them?
- What exactly is delayed, and by how long?
- What's the reason, and should the email mention it?
- What are you offering to make up for it: a discount, free delivery, nothing?
- What tone: formal or warm?
- How long should the email be?
- Who is it from, and what contact details go at the end?

The assistant will write something. But that "something" will be based on its guesses, not on your situation. As a result you'll get:

- 3-4 rounds of revisions ("no, that's not it, rewrite this part")
- Wasted time and extra messages that count against your plan's limit
- Frustration

### Anatomy of a good prompt

The same request, written well:

```
Write an email to a customer about a delayed order.

Who I am: the manager of a small custom furniture shop.
Who it's for: Maria, a repeat customer who ordered kitchen cabinets from us.
What happened: we promised delivery on March 15, but the cabinet doors arrived from our supplier with defects. The new date is March 29.
What we're offering: free delivery and installation.
Tone: warm and respectful, no corporate jargon, no long excuses.
Length: 120 words or fewer.
At the end: leave a spot for my phone number and sign it "Dan, shop manager."
```

Now the assistant has very little left to guess, so the first version usually lands close to what you wanted, with far fewer rounds of revisions.

**What changed:** you gave specifics on every point the assistant would otherwise have had to guess.

💡 Leave real last names, phone numbers and addresses out of the prompt, and add them to the finished email yourself. The lesson on AI safety later in this module explains why.

### The five parts of a good prompt

🎨 **Picture this:** the five parts of a prompt are like a reporter's five W's: Who? What? Where? When? Why? A news story missing even one of them loses its point. A good prompt works the same way.

**1. The result (what you get in the end)**

Not "help me with this report," but "turn this report into a half-page summary."

**2. Context (why you need it and who it's for)**

Context is everything in the conversation that the assistant can see, so this is where you tell it the purpose: "My director will read the summary before a meeting with the bank and will have five minutes."

**3. Constraints (what not to do)**

"Don't add any numbers that aren't in my text. No filler. No more than 150 words."

**4. Examples (what it should look like)**

"Use this format: a headline, three takeaways with numbers, one line on the biggest risk." Even better, paste a sample: "Here's my last summary; match its style."

**5. Definition of done (how to check it)**

"It's done when the summary covers revenue, costs and the biggest risk, and every number comes from my report."

You don't always need all five; sometimes two or three are enough. But the more complex the task, the more each one matters.

### Plan first (Plan Mode): when you're not sure what you want

🎨 **Picture this:** it's like meeting with an architect before construction starts. You say: "I want a cozy house for a family with kids." The architect asks questions: How many kids? Do you need a garage? What's the budget? Then they bring you a plan, not a construction crew. First you look at the blueprint, and only then do you give the go-ahead to break ground.

Sometimes you know the problem but not how to approach it. Or you can picture the result but don't understand what parts it should be made of.

There's a simple technique for that: ask the assistant to **ask you questions and show you a plan first**, and to start the actual work only after you say yes. Just add this to the end of your request: "Before you start, ask me clarifying questions." It works in any assistant.

Example:

```
I need to organize moving our office to a new address within one month.
Before you make a plan, ask me clarifying questions so you understand the situation.
Then show me a short plan, and only after I say yes, break it down day by day.
```

The assistant will ask questions like:

- "How many people work in the office?"
- "What's being moved: just equipment and documents, or furniture too?"
- "Is there a hard date for being out of the old space?"
- "What's the budget, and who's in charge of the move?"
- "Can work stop for a day or two, or does the move have to happen with no downtime?"

After you answer, the assistant puts together a plan, and only then does it fill in the details.

**When to use this technique:**

- The task is big and has many moving parts
- You're not sure how to break it into pieces
- You want to make sure the assistant understood you before it starts
- A mistake would be expensive (a lot of time or money)

💡 **If you go on to build with Claude Code.** This technique has its own mode there, called Plan Mode: Claude studies the project and proposes a plan first, and starts changing files only after you approve it. In the terminal (a window for typing text commands) you cycle through the modes with Shift+Tab or type the `/plan` command; in the desktop app you pick the mode from the list next to the send button. The five parts of a prompt are the same there: result, context, constraints, an example and a definition of done.

### Quality depends on how well you understand the work

Here's an uncomfortable truth that's worth accepting early on:

**The better you understand the subject, the better the result.**

Say you ask an assistant to put together a budget for a kitchen remodel, but you don't know what goes into one: materials, labor, permits, delivery, debris removal, a cushion for surprises. Then you won't be able to tell whether it did a good job. You'll get a tidy table that looks convincing but may be missing half the line items.

If you do understand how a remodel budget works, you'll give the right instructions, notice when the assistant misses something and be able to check the result.

This doesn't mean you have to become an expert in everything. But you do need to understand the **task you're handing off**:

- How is it done today (by hand)?
- What unusual cases come up?
- What does "done right" mean for this task?

That's why the people who usually get the most out of AI are the ones who know their own field well (marketing, sales, finance, logistics) and learn the tool afterward.

### Revisions are normal, not a failure

🎨 **Picture this:** an artist makes thumbnail sketches, then a rough draft, then the detailed painting. Nobody expects a finished canvas from the first brushstroke. Your first prompt is your rough sketch. The goal isn't "perfect from scratch" but "reach the goal in as few steps as possible."

A revision is one more pass: you look at the answer and ask for a fix. Even a well-written prompt rarely gives a perfect result on the first try. And that's fine.

How working with an assistant usually goes (the percentages below are a rough guide, not a measurement):

1. You write a good prompt → you get 70-80% of what you need
2. You see what's off → you ask for specific fixes in the same chat
3. You get to 90-95% → one more pass on the small details
4. Done

The goal of a good prompt isn't "perfect the first time" but "as close to the target as possible, with as few revisions as possible."

A bad prompt gets you 30-40% on the first try and needs 5-7 revisions.

A good prompt gets you 70-80% on the first try and needs 1-2 revisions.

The difference is several extra rounds on every task. On big tasks, that's hours of work.

### Cheat sheet: bad prompt → good prompt

| Bad prompt | Good prompt | Why it's better |
|---|---|---|
| "Write an email" | "Write an email to a client about moving our meeting from June 10 to June 12: polite, 80 words or fewer, offer two time slots" | Who it's for, what it's about, tone, length |
| "Summarize this" | "Summarize this report in half a page for my director: the three main takeaways and one risk, using only facts from the text" | Length, reader, structure, no making things up |
| "Make a plan" | "Make a two-week plan for getting ready for my vacation: a day-by-day to-do list, plus a separate list of what to hand off to a coworker" | Time frame, format, what matters |
| "Fix this text" | "Fix the errors and typos in this text. Don't change the meaning or the style. List your changes at the end" | What to fix, what to leave alone, how to report back |
| "Make it look nice" | "Reformat this text: short paragraphs, subheadings, a bulleted list instead of the long run-on sentence" | Specific settings instead of "nice" |

---

## Practice

**Exercise:** write one bad prompt, rewrite it well and compare the results.

**Step 1: The bad prompt (5 min):**

1. Open your assistant (Claude, ChatGPT or Gemini) and start a new chat
2. Type this prompt exactly as written:
   ```
   Write a job posting for our company
   ```

3. Look at what you got. Write down: what's missing? What did the assistant decide for you?

**Step 2: The good prompt (10 min):**

1. Start another new chat, so the first answer doesn't influence the second, and write a prompt using the five parts:
   - **Result:** "Write a job posting for a [job title]..."
   - **Context:** "...at [your company, or a made-up one]. The posting will go on [website or social network]. We're looking for someone who [the main requirement]"
   - **Constraints:** length and what to leave out, for example: "150 words or fewer, no phrases like 'fast-paced environment' or 'we're like a family'"
   - **Example:** describe the format ("short paragraphs and bulleted lists") or paste a posting you like
   - **Definition of done:** "The posting covers responsibilities, requirements, pay and benefits, and how to apply"
2. Send this prompt
3. Compare the result with the first one

**Step 3: Review (5 min):**

Answer these for yourself:

- How many rounds of revisions would the first posting have needed before you could publish it?
- How many would the second one need?
- Which parts of the second prompt would you have had to explain separately the first time?

Here's an easy way to check yourself: the second posting has all four blocks from your definition of done, while in the first one the assistant made some of them up or left them out.

---

## Common mistakes

❌ **Mistake:** Writing one huge 500-word prompt right from the start.

✅ **Instead:** Start with the essentials (result + context), get a first version, then refine step by step. Two or three short prompts beat one giant one.

❌ **Mistake:** Not stating your constraints: "no longer than one page," "no jargon," "don't make up numbers."

✅ **Instead:** Without constraints, the assistant decides for itself how long the answer is and what kind of language it uses. If it matters to you, say so explicitly. Constraints save you revisions.

❌ **Mistake:** Not checking the result and passing it along "as is."

✅ **Instead:** Always check: are the facts and numbers right (an assistant can make mistakes and make things up), is the tone right, is there anything extra? If you're not sure how to break the task down, ask for questions and a plan first.

---

## Tools and resources

- **[Claude Code](https://code.claude.com/docs/en/overview)**: Anthropic's agent for people who go on to build; you don't need it for this lesson
- **[Anthropic Prompt Engineering Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)**: Anthropic's official guide to writing prompts
- **[Anthropic API docs](https://docs.anthropic.com/en/api/getting-started)**: documentation for developers who connect Claude to their own software; beginners don't need it
- **[Claude Code docs: setup](https://code.claude.com/docs/en/getting-started)**: how to install and set up Claude Code

→ See the lesson [The Default Shift](03-default-shift-mindset.md): how to give an assistant tasks the way you'd give them to a contractor (it comes next)

→ Optional, from the library: [Installing and setting up Claude Code](05-setup.md): if you decide to install Claude Code

→ Optional, from the library: [CLAUDE.md](07-claude-md.md): a standing set of instructions for Claude Code, so you don't have to repeat your context in every request

→ Optional, from the library: [Managing context: advanced techniques](29-context-management-advanced.md): how to work with prompts in large projects

---

## Key takeaways

> A bad prompt = a bad work order. The assistant will make something, but not what you need.

> The five parts of a good prompt: result, context, constraints, examples, definition of done.

> Not sure how to break a task into parts? Ask for questions and a plan first. In Claude Code there's a Plan Mode for this.

> The quality of the result depends on how well you understand the subject. The assistant builds from your blueprints.

---

## Next lesson

→ [The Default Shift](03-default-shift-mindset.md): how to make AI your first helper at work
