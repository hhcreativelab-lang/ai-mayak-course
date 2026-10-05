# AI copywriting: a prompt pipeline that sounds like you

**Time:** about 25 min reading + 40 min practice

---

## The gist

Asking AI to just "write me a post" gives you generic AI text that everyone recognizes and nobody reads. The approach that works is a prompt pipeline of several steps, plus a brand voice file that teaches Claude to write in your style.

Everything in this lesson works in a regular Claude chat, in your browser or on your phone. No coding needed. The code task at the end of Practice is optional: it's for people who build their own tools.

🎨 **Picture this:** asking Claude to write copy with no context is like asking a painter for "something nice." You'll get a painting, but it won't be yours. A prompt pipeline is a proper brief for the painter: style, palette, format, mood, reference images. Then you get not "something" but exactly what you had in mind.

---

## Key concepts

- The ChatGPT pattern is easy to spot, and specifics are how you avoid it
- The prompt pipeline: idea → outline → draft → edit → final (5 steps)
- A brand voice file: standing context that makes Claude sound like you
- Formats: LinkedIn and Instagram posts, YouTube scripts, landing pages, email (each one has its own rules)
- Batch generation: 30 draft posts at once from a single prompt
- AI detectors: what works is specifics, not disguise

---

## Theory

### Why ChatGPT-style copy is so easy to spot

There's a standard set of words and constructions AI falls back on by default, because they show up so often in its training data:

```
❌ AI patterns that kill trust:
- "In today's fast-paced world..."
- "In the digital age..."
- "Unleash your potential"
- "Game-changing solution"
- "Leverage your strengths"
- "It's important to note that..."
- Three bullet points with dashes and an exclamation point at the end
- An opening line that's a rhetorical question
```

🎨 **Picture this:** it's like canned soup. Technically it's soup, but everyone can tell it came out of a can. Homemade soup smells different, looks different, tastes different. Good AI copy should taste like you, not like the can.

**Why this happens:**
Without context, Claude writes for "the average reader of an average text." Your job is to give it enough specifics that "average" turns into "yours."

---

### The prompt pipeline: 5 steps from idea to final copy

Instead of one big prompt, you run a sequence of small, precise steps. Each step is a separate message in the same chat.

**Step 1: Idea → Angle**

```
Topic: [what you want to write about]
Audience: [who will read it]
Goal of the piece: [what the reader should do or feel]
Angle: [a less obvious take on the topic, if you already have one; if not, delete this line]

Suggest 5 different angles for a post on this topic.
One sentence per angle. No filler.
```

**Step 2: Angle → Outline**

```
Chosen angle: [copied from step 1]
Format: [LinkedIn post / Instagram caption / YouTube script / email / landing page]
Length: [number of words or characters]

Write an outline without writing the actual copy.
Just the section headings and one line on what each one covers.
```

**Step 3: Outline → Draft**

```
[Paste the outline from step 2]
[Paste your brand voice file or a short description of your style]

Write a draft that follows the outline exactly.
Specifics instead of general statements.
Use only the examples and numbers I gave you. If you need more, ask me.
```

**Step 4: Draft → Edit**

```
[Paste the draft]

Review and improve:
1. Does the first sentence grab attention? Rewrite it if not
2. Any AI clichés? Replace them with specifics
3. Does every paragraph add a new idea? Cut the repetition
4. Is the call to action at the end specific, and is there only one?
```

**Step 5: Edit → Final**

```
[The draft after edits]

Final check:
- Does the length fit the format?
- Does the tone fit [platform]?
- One reader, one action at the end?

Give me the final text.
```

A pipeline like this takes longer than a single request, but the text comes out noticeably better. Read the final version yourself before you publish: checking the facts, numbers and names is your job.

---

### The brand voice file: your style as a document

A brand voice file is a document you give Claude before every piece of writing. It describes how you write, what you never write, who your audience is, and it includes examples of your best work.

**Structure of a `brand-voice.md` file:**

```markdown
# Brand Voice: [Your name / project name]

## Who I am
[2-3 sentences: who you are, what you do, who you do it for]

## Audience
- Who: [description]
- What matters to them: [3-5 points]
- What annoys them: [2-3 points]

## Tone
- I write: [conversational / businesslike / casual / expert]
- I do NOT write: [coaching jargon / industry jargon / numbers without a source]
- Examples of a tone I like: [links or samples]

## Style
- Sentences: [short / medium / long / mixed]
- Paragraphs: [1-3 lines / longer]
- Structure: [lists / prose / mixed]
- Emoji: [none / rarely / often]

## Banned words and phrases
- "synergy", "think outside the box", "step out of your comfort zone"
- "it's important to note", "in today's fast-paced world"
- [add your own]

## Examples of my best writing
[Paste 2-3 of your best posts or emails]

## Formulas that work for me
- Post formula: [hook → story → takeaway → question]
- Email formula: [subject line that names the pain → story → solution → CTA]
```

CTA stands for call to action: the one thing you ask the reader to do.

`brand-voice.md` is a plain text file: write it in any editor or notes app and paste its text at the start of a chat. If you organize your files with the PARA system, this file goes in `areas/marketing/brand-voice.md` (that's an optional library lesson: [Organizing your folders: the PARA system for AI entrepreneurs](66-folder-structure-philosophy.md)). So you don't have to paste the file in every time, you can turn it into a Claude Skill: a saved instruction that Claude loads on its own when it fits the task. Skills live under Customize → Skills, and as of October 2026 they are available on all plans.

🎨 **Picture this:** a brand voice file is like the onboarding guide you'd hand a new copywriter on your team. Without it, they write "fine." With it, they write like you.

---

### Formats: each one has its own rules

**LinkedIn post or Instagram caption (up to 1,000 characters):**

```
Rules:
- First line = the hook (no warm-up words)
- Paragraphs of 1-2 lines with a blank line between them
- One takeaway or question at the end
- Emoji only if that's your style

Prompt:
"Write a LinkedIn post of up to 800 characters.
Topic: [topic]. Hook in the first line, no warm-up.
Paragraphs of 2 lines max.
No exclamation points at the end."
```

**YouTube script (8-12 minutes = about 1,200-1,800 words):**

```
Structure:
[0:00-0:30] Hook: what the viewer will get
[0:30-1:30] Problem: why it matters
[1:30-8:00] Main content: 3-5 sections
[8:00-9:30] Recap + practice
[9:30-10:00] CTA: subscribe / link

Prompt:
"Write a 10-minute YouTube script.
Topic: [topic]. Hook in the first 30 seconds.
Conversational style. Mark the timestamps.
Each section leads into the next one."
```

**Landing page copy:**

```
Structure:
Hero: headline + subheadline + CTA
Problem: the reader's pain points (3 of them)
Solution: how you solve them
How it works: 3 steps
Proof: social proof (testimonials, reviews, client logos)
FAQ: 5 questions
CTA: the final call to action

Prompt:
"Write the copy for a landing page.
Product: [description].
Target audience: [description].
The customer's biggest worry: [worry].
The main result they get: [result].
Tone: [professional / friendly]."
```

💡 Social proof has to be real. Don't let AI write testimonials or reviews for you; give it the actual words your customers used.

---

### Batch generation: 30 posts at once

Instead of writing one post at a time, generate a whole batch:

```
Here's my content calendar for the month. Topics:
1. [topic 1]
2. [topic 2]
...
30. [topic 30]

Brand voice: [paste the text or attach the file]
Format: LinkedIn post, up to 600 characters each

Write all 30 posts, one after another.
Number each one.
Put a --- divider between posts.
```

The result: 30 draft posts from a single request. Then you polish the best ones and archive the rest.

**Important:** batch mode lowers the quality of each individual post. Use it for drafts, not for final copy.

---

### What about AI detectors?

An AI detector is a service that tries to guess whether a text was written by a machine. The truth is simple: AI detectors don't catch "AI style," they catch predictability. They also make mistakes in both directions and can't prove who wrote a text. So the goal isn't to slip past a check; it's to write specific copy that people actually enjoy reading.

What makes text predictable:

- General statements with no specifics
- Sentences that are all the same length
- No conversational turns of phrase
- Zero personal experience

**The fix is specifics, not disguise:**

```
❌ "Many entrepreneurs struggle with scaling their business"
✅ "In April my conversion rate dropped from 4% to 1.8%. Here's what I found."

❌ "Artificial intelligence is transforming business"
✅ "Claude wrote 47 posts in one evening. I edited 12. Here's which ones."
```

Add this to your prompt:

```
In the text, include:
- One specific number from my own experience: [type the number]
- One unexpected detail: [type the detail]
- One sentence that sounds like you're saying it out loud
```

Give Claude the real number and the real detail yourself. If you leave it to guess, it may simply make them up (AI confidently making things up is called a hallucination), and a made-up figure in your marketing is worse than no figure at all.

---

## Practice

1. Create a `brand-voice.md` file for your project, using the template from this lesson. Any text editor or notes app will do: you need the file so you can paste its text into a chat. You're done when every section is filled in and the examples section holds 2-3 of your own real pieces. The command below is only for people who work in a terminal and keep their files in folders; everyone else can skip it:

```bash
mkdir -p ~/workspace/areas/marketing
# Create the file and fill in every section
```

2. Write your first LinkedIn post (or Instagram caption) with the 5-step pipeline:

```
Topic: [pick something from your own work]
Run each step as a separate prompt
Save the result of each step
```

3. When the pipeline is done, ask Claude to grade the final text:

```
Rate this text on a scale of 1-10 on these criteria:
- Specificity (no generic wording)
- Match with my brand voice
- Strength of the first sentence
- Clarity of the call to action

For each criterion: a score and one sentence on what to improve.
```

4. Generate a batch of 10 draft posts. Type your list of 10 topics right in the chat. The command below makes the same list as a file in a terminal; it's optional:

```bash
# Create a file with your topics
echo "1. [topic 1]
2. [topic 2]
...
10. [topic 10]" > content-plan.txt
```

Give Claude the topic list plus your brand voice, get 10 drafts back, and pick the best 3.

5. Optional, for people who build their own tools and already work with code: a generator script in Python. Everyone else can skip this task; the lesson is complete without it.

```python
import os
import anthropic

client = anthropic.Anthropic()
os.makedirs("posts", exist_ok=True)

with open("brand-voice.md", encoding="utf-8") as f:
    brand_voice = f.read()

topics = [
    "topic 1",
    "topic 2",
    "topic 3",
]

for i, topic in enumerate(topics, 1):
    message = client.messages.create(
        model="claude-sonnet-5-5",  # for current model IDs, see Anthropic's documentation
        max_tokens=4000,  # generous on purpose: the model's "thinking" counts toward this limit
        messages=[{
            "role": "user",
            "content": f"""Brand voice:
{brand_voice}

Write a LinkedIn post about: {topic}
Up to 600 characters. Hook in the first line."""
        }]
    )
    # The reply may contain "thinking" blocks: keep only the text
    text = "".join(block.text for block in message.content if block.type == "text")

    with open(f"posts/post-{i:02d}.md", "w", encoding="utf-8") as f:
        f.write(f"# Post {i}: {topic}\n\n")
        f.write(text)

    print(f"Post {i} is ready")
```

The script reads your API key from the `ANTHROPIC_API_KEY` environment variable. Never paste the key into the code itself.

---

## Tools and resources

- **[Claude.ai](https://claude.ai)**: your main tool for the pipeline
- **[Anthropic API](https://claude.com/api)**: for batch generation with code (prices and models: [What's current](https://aimayak.com/en/now/))
- **[Hemingway App](https://hemingwayapp.com)**: checks how readable your text is (built for English)
- **[QuillBot](https://quillbot.com)**: rephrasing for a final polish
- **[GPTZero](https://gptzero.me)**: an AI detector you can run your text through (to see where you stand)

---

## Key takeaways

> A 5-step prompt pipeline produces a different quality of text than one big prompt. It's the difference between fast food and a meal at a good restaurant: both are made from ingredients, but the process isn't the same.

> A brand voice file is a one-time investment: write it well, and every piece you write with Claude after that comes out closer to your voice, with no extra explaining.

> AI detectors catch predictability, not "AI style." Add specific numbers, personal experience and conversational phrasing, and your text will feel alive no matter what tool you wrote it with.

---

## What's next

→ [AI for email: a smarter inbox, drafts and replies](73-ai-email-communications.md): sorting your inbox and drafting replies

Optional, in the library: [AI voiceover: ElevenLabs, text-to-speech and voice content](68-voice-tts-elevenlabs.md): turning your finished copy into audio
