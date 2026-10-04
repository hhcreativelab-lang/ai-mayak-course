# How to write a good prompt for Claude Code

**Time:** about 35 min reading + 20 min practice

---

## The gist

A prompt (the text request you give an AI) is a work order for an agent (a program that carries out tasks on its own). A vague work order gets a poor result, and that isn't the contractor's fault. A clear work order gets an accurate result much sooner, often on the first try. This lesson teaches you how to write good work orders for Claude Code. The same principles work in any AI assistant (ChatGPT, Gemini, Claude in your browser): the only thing that changes is where you paste the text.

---

## Key concepts

- Claude Code = a brilliant contractor with access to your tools
- How specific your prompt is directly decides the quality of the result
- The difference between a bad prompt and a good one, with real examples
- Plan Mode: use it when you're not sure what you want
- How the quality of the output depends on how well you understand the subject

---

## Theory

### Claude Code is a contractor, not a magician

It's tempting to think of Claude Code as a magic wand: "I say what I want and get it done." A better way to think about it:

**Claude Code is a brilliant contractor** with a huge amount of experience who can build almost anything. But it only has access to what you've given it:

- The files in the project folder you opened
- The tools you've connected
- The information you described in the task

It doesn't know your brand, your customers or your design preferences unless you explain them.

That's exactly why **vague requests get vague results**, and specific requests get precise results.

🎨 **Picture this:** a prompt is the work order you hand a general contractor. Say "Build something nice," and the contractor will build something. Maybe you'll like it, maybe you won't. Say "Build a two-story house, about 1,300 square feet, three bedrooms, a one-car garage, brick exterior, metal roof," and the contractor knows exactly what to build.

### Anatomy of a bad prompt

Let's take apart a typical bad request:

```
Build me a website for a dog-walking business
```

What the agent can't tell from this request:

- What style and colors? (Buttoned-up corporate? Playful and bright?)
- Which sections? (Just a home page? Prices? Reviews? A booking form?)
- Which city or area? (Does it need a map?)
- One page or several?
- Does it need a booking form? Online payment?
- What language? (English only, or Spanish too?)
- Is there a logo?

The agent will make something. But that "something" will be based on its guesses, not on what you actually need. As a result you'll get:

- 3-4 rounds of revisions ("no, that's not it, do it like this")
- A lot of tokens used up (tokens are the small chunks of text an AI reads and writes)
- Frustration

### Anatomy of a good prompt

The same request, written well:

```
Build a landing page for a dog-walking business in Austin, Texas.

Requirements:
- Hero section: headline "Professional Dog Walking", subheadline "Every day, any weather, experienced walkers", button "Book a Walk"
- Services section: 3 cards: solo walk (1 hour, $35), group walk (1.5 hours, $25), training + walk (2 hours, $55)
- Reviews section: 3 blocks with a quote and the client's name (make them up)
- Booking form: name, phone, dog's breed, service choice, "Request a Booking" button
- Footer: phone (512) 555-0123, email hello@example.com, Instagram @dogwalk_austin

Style: color scheme blue #2563EB and white, system font, cards with rounded corners
Tech: HTML and CSS only, no frameworks, a single index.html file
Responsive: works on phones
```

Now the agent has very little left to guess, so the first version usually lands close to what you wanted, with far fewer rounds of revisions.

**What changed:** you gave specifics on every point the agent would otherwise have had to guess.

### The five parts of a good prompt

🎨 **Picture this:** the five parts of a prompt are like a reporter's five W's: Who? What? Where? When? Why? A news story missing even one of them loses its point. A good prompt works the same way.

**1. The result (what you get in the end)**

Not "create an automation," but "create a Python script (Python is a programming language) that..."

**2. Context (why you need it)**

Context is everything in the conversation that the AI can see, so this is where you tell it the purpose: "This script will run every day at 9:00 a.m. and send..."

**3. Constraints (what not to do)**

"Don't use any outside libraries except requests. Don't create a database, just a CSV file."

**4. Examples (what it should look like)**

"The email format: the subject line is 'Report for [date]', and the body is a table with the columns Name, Amount, Status."

**5. Definition of done (how to check it)**

"It's done when the script runs without errors, creates a report.csv file and sends an email to test@example.com."

You don't always need all five; sometimes two or three are enough. But the more complex the task, the more each one matters.

### Plan Mode: when you're not sure what you want

🎨 **Picture this:** Plan Mode is like meeting with an architect before construction starts. You say: "I want a cozy house for a family with kids." The architect asks questions: How many kids? Do you need a garage? What's the budget? Then they bring you a plan, not a construction crew. First you look at the blueprint, and only then do you give the go-ahead to break ground.

Sometimes you know the problem but not how to solve it technically. Or you know the result you want but don't understand what parts it should be made of.

That's what **Plan Mode** in Claude Code is for.

How to turn it on: write your request and add at the end "Before you start, ask me clarifying questions," or switch Plan Mode on in the interface. In the terminal you cycle through the modes with Shift+Tab (or type the `/plan` command); in the desktop app you pick the mode from the list next to the send button.

Example:

```
I want to automate a daily email digest of real estate news for my clients.
Before you start, ask me clarifying questions so you understand exactly what to build.
```

The agent will ask questions like:

- "Where should the news come from: specific websites, or an API (Application Programming Interface: a way for one program to request data from another)?"
- "How many news items should each email include?"
- "Should it be personalized by each client's city?"
- "Where do you keep your client list: Google Sheets, a CRM (Customer Relationship Management: software for keeping track of your customers), a CSV file?"
- "What time should it go out?"

After you answer, the agent puts together a plan, and only then does it start building.

**When to use Plan Mode:**

- The task is complicated and has many moving parts
- You're not sure how to break it into pieces
- You want to make sure the agent understood you before it starts
- A mistake would be expensive (a lot of time or money)

### Quality depends on how well you understand the work

Here's an uncomfortable truth that's worth accepting early on:

**The better you understand the subject, the better the agent's result.**

If you ask an agent to build newsletter automation but don't understand how email newsletters work (SPF/DKIM, unsubscribes, bounce handling), you won't be able to tell whether the agent did a good job. You'll get something that works in theory but may have hidden problems.

If you do understand how newsletters work, you'll give the right instructions, notice when the agent misses something important and be able to check the result.

This doesn't mean you have to become a developer. But you do need to understand the **business process** you're automating:

- How does the process work today (by hand)?
- What edge cases come up (the unusual situations that break the normal routine)?
- What does "done right" mean for this process?

That's why the best builders of agent systems are people who understood a field first (marketing, sales, finance, logistics) and learned the tools afterward.

### Revisions are normal, not a failure

🎨 **Picture this:** an artist makes thumbnail sketches, then a rough draft, then the detailed painting. Nobody expects a finished canvas from the first brushstroke. Your first prompt is your rough sketch. The goal isn't "perfect from scratch" but "reach the goal in as few steps as possible."

Even a well-written prompt rarely gives a perfect result on the first try. And that's fine.

The pattern for working with an agent (the percentages below are a rough guide, not a measurement):

1. You write a good prompt → you get 70-80% of what you need
2. You see what's off → you send a follow-up prompt with specific fixes
3. You get to 90-95% → one more pass on the small details
4. Done

The goal of a good prompt isn't "perfect the first time" but "as close to the target as possible, with as few revisions as possible."

A bad prompt gets you 30-40% on the first try and needs 5-7 revisions.

A good prompt gets you 70-80% on the first try and needs 1-2 revisions.

The difference is 3-4 revisions. On complex tasks, that's hours of work.

### Cheat sheet: bad prompt → good prompt

| Bad prompt | Good prompt | Why it's better |
|---|---|---|
| "Make a website" | "Create a landing page in HTML+CSS, one page, blue and white, sections: hero, services, form" | Specific result, style, structure |
| "Write a script" | "Write a Python script that reads a CSV, keeps the rows where the amount is > 1000 and saves them to a new CSV" | Language, input, logic, output |
| "Automate email" | "Create a workflow (a sequence of steps that runs on its own): every Monday, collect 5 news items from RSS, generate an HTML email and send it through the Gmail API to the list in Google Sheets" | Schedule, source, format, channel, recipients |
| "Fix the bug" | "In main.py, line 42: TypeError: expected str, got int. The process_data function gets a number instead of a string from the API response" | File, line, error type, context |
| "Make it look nice" | "Add: 8px rounded corners, card shadows, 24px spacing between sections, Inter font" | Specific design settings |

---

## Practice

**Exercise:** write one bad prompt, rewrite it well and compare the results.

**Step 1: The bad prompt (5 min):**

1. Open Claude Code in an empty folder
2. Type this prompt exactly as written:
   ```
   Create a form for collecting customer inquiries
   ```

3. Look at what you got. Write down: what's missing? What did the agent decide for you?

**Step 2: The good prompt (10 min):**

1. Write a new prompt using the five parts:
   - **Result:** "Create an HTML form..."
   - **Context:** "...for clients to book a first consultation about [your topic]"
   - **Fields:** list the exact fields you need
   - **Style:** colors, fonts, the overall look
   - **Definition of done:** "The form must work without any JavaScript frameworks" (JavaScript is a programming language)
2. Run this prompt
3. Compare the result with the first one

**Step 3: Review (5 min):**

Answer these for yourself:

- How many revisions did the first prompt need?
- How many did the second one need?
- What did you have to explain separately the first time?

---

## Common mistakes

❌ **Mistake:** Writing one huge 500-word prompt right from the start.

✅ **Instead:** Start with the essentials (result + context), get a first version, then refine step by step. Two or three short prompts beat one giant one.

❌ **Mistake:** Not stating your constraints: "don't use frameworks," "Python only," "no database."

✅ **Instead:** Without constraints, the agent picks its own set of technologies. If it matters to you what gets used, say so explicitly. Constraints save you revisions.

❌ **Mistake:** Not checking the result and deploying it (deploying means putting it live, publishing it) "as is."

✅ **Instead:** Always check: does it run without errors, does it do what you expected, does it handle edge cases? Use Plan Mode if you're not sure how to break the task down.

---

## Tools and resources

- **[Claude Code](https://code.claude.com/docs/en/overview)**: the main tool in this lesson
- **[Anthropic Prompt Engineering Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)**: the official guide to writing prompts
- **[Anthropic API docs](https://docs.anthropic.com/en/api/getting-started)**: API documentation (to understand how the model works)
- **[Claude Code docs: CLI usage](https://code.claude.com/docs/en/getting-started)**: how to use Claude Code effectively

→ See the lesson [The Default Shift](03-default-shift-mindset.md): the contractor mindset behind good prompts

→ See the lesson [Installing and setting up Claude Code](05-setup.md): if you haven't set up your workspace yet

→ See the lesson [CLAUDE.md](07-claude-md.md): a system prompt that's always on (so you don't have to repeat your context)

→ See the lesson [Managing context: advanced techniques](29-context-management-advanced.md): how to scale your prompting up for complex systems

---

## Key takeaways

> A bad prompt = a bad work order. The agent will make something, but not what you need.

> The five parts of a good prompt: result, context, constraints, examples, definition of done.

> Plan Mode: use it when you don't know how to break a task into parts. The agent will ask the right questions.

> The quality of the result depends on how well you understand the subject. The agent builds from your blueprints.

---

## Next lesson

→ [CLAUDE.md: your project's system prompt](07-claude-md.md)
