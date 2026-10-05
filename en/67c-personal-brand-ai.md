# How to build a personal brand with AI

**Time:** about 25 min reading + 35 min practice

---

## The gist

In 2026, a personal brand isn't a résumé. It isn't an "About me" page. It's **your recognizable voice, repeated across platforms**, steadily feeding the same funnel for years, until at some point clients, investors and employers can start coming to you on their own.

AI doesn't replace your thinking here. AI is an **amplifier for your presence**. You have 15 minutes in the morning and real thoughts. AI helps you turn them into 5 to 10 posts a week across up to three platforms, instead of the 4 hours a day you don't have anyway.

🎨 **Picture this:** you're a water tower. Your thoughts are the water. AI is the network of pipes that carries the water to several buildings at once. Without water, the pipes just push air. Without pipes, the water pours out in one spot and soaks into the ground.

The biggest mistake people made from 2024 to 2026 was hoping AI would **create** a personal brand for them. It won't. AI scales what's already in your head. If your head is full of generic marketing soup, you'll get generic AI slop (bland, machine-sounding filler), which readers can smell a mile away and mute within a week.

In this lesson: how to capture your own voice, how to set up a ghostwriting pipeline with Claude, which tools actually work in 2026, when voice cloning makes sense, and 6 anti-patterns that instantly give away a post written by a machine with nobody behind it.

---

## 🎯 Which platform is yours: a decision tree

The question isn't how to be everywhere. It's where **your audience** is and what **your format** is.

**LinkedIn if:**

- ✓ Your target is B2B clients, executives, hiring managers
- ✓ You're a consultant or a B2B SaaS founder, or you're looking for a well-paid job
- ✓ You're ready to write long-form posts (200-500 words) once or twice a week
- ✓ You're comfortable with the "corporate" tone (even if you break it, it's the baseline)

**X (formerly Twitter) if:**

- ✓ You're an indie hacker, a developer, a marketer, a SaaS founder
- ✓ You like short thoughts and the reply game
- ✓ You're ready to post 1-3 times a day
- ✓ You want viral upside (one thread can reach a lot of people)

**YouTube if:**

- ✓ You're an educator, a coach, or in a deep-content niche (finance, programming, philosophy)
- ✓ You're ready to put 4-8 hours into one video once a week
- ✓ You want the most out of every subscriber you win (people keep finding videos for years)
- ✓ You're playing the long game: the first 6 months bring almost no response, then it compounds

**Instagram, TikTok, a newsletter or a podcast?** Ask the same two questions: is your audience there, and can you keep up that format week after week? Short video (TikTok, Instagram Reels, YouTube Shorts) has the fast rhythm of X; a newsletter or a podcast is closer to YouTube: slower, deeper, and it builds over time.

**By default, pick ONE platform for your first 6 months.** Spread across three at once, a beginner makes noise on all of them and builds an audience on none.

🎨 **Picture this:** digging a well. Better one deep well that reaches water than three holes a couple of feet deep.

---

## Key concepts

- **Brand voice**: your recognizable style: vocabulary, sentence rhythm, favorite turns of phrase, the perspectives you keep coming back to
- **Voice profile**: a written description of your voice in a file (brand-voice.md) that AI reads before every draft
- **Content seed**: a short thought of yours (3-10 lines) that AI expands into a post
- **Ghostwriting**: AI writes for you, but from your material and with your final edit
- **Voice cloning**: synthesizing your voice (audio) with ElevenLabs or Resemble for podcasts, YouTube voiceovers, multilingual content
- **Anti-pattern**: text markers that immediately give away AI generation ("delve into", "in conclusion", "fast-paced world")
- **Persona maintenance**: the discipline of not drifting away from your own voice under pressure from the algorithm (viral hooks vs your real style)
- **Engagement game**: targeted replies under other people's posts in your niche as a way to grow (often more important than the posts themselves)

---

## Theory

### Your 2026 personal brand stack: three platforms, three formats

| Platform | Audience | How often | Format | Best for |
|---|---|---|---|---|
| **LinkedIn** | B2B, executives, hiring | 1-2 posts/week + 3-5 comments/day | Long-form, 200-500 words | Consultants, B2B founders, job seekers |
| **X (Twitter)** | Founders, indie hackers, developers | 1-3 posts/day + reply game | Short posts + threads | SaaS founders, developers, marketers |
| **YouTube** | Deep audience | 1 long video/week (10-20 min) | Video | Educators, coaches, deep niches |

**The cross-platform pattern:** a YouTube video → 60-second clips for X (or TikTok and Instagram Reels) → a written breakdown as a LinkedIn post. One piece of thinking, three formats. That's exactly where AI helps.

---

### The ghostwriting workflow in 5 steps

This isn't "AI writes for you." It's a **system** where you stay the author but don't spend 4 hours a day on it.

#### Step 1: Voice extraction (one time, about 4 hours)

The goal is to put your voice into words so Claude can reproduce it.

**What you do:**

1. Collect **50+ samples of your own, authentic writing**:
   - Old posts from LinkedIn or X
   - Long messages from chats and emails to clients
   - Transcripts of your voice memos (made with Whisper or a dictation app)
   - Notes and drafts
2. Give them to Claude and ask it to pull out a profile:

```
Read these 50 texts and write a brand-voice.md:
- Favorite words and phrases (top 30)
- Banned words and phrases (what I never write)
- Sentence structure: length, rhythm, favorite constructions
- Tone: serious / ironic / warm / direct / etc.
- Perspective: where I usually speak from (observer, practitioner, skeptic)
- Topics I keep coming back to
- Metaphors and images that are typical for me
- What kind of real-life examples I use
```

3. **Save the file `brand-voice.md`**: this is now your voice profile, kept in the same folder (or repo) as your content. AI reads it before every draft.

🎨 **Picture this:** sheet music for your voice. Without it, AI can play any tune, just not yours.

#### Step 2: Content seeds (your actual thinking, 15 min/day)

Every morning, spend 15 minutes jotting down ideas. **This is the real part.** AI scales what's in your head. Skip this step and you'll get generic AI slop.

```markdown
# seeds/2026-10-05.md

1. Yesterday a client asked why we don't use X. I said: because of Y.
   Then it hit me: that's a pattern I've repeated three times this month.

2. Noticed that in my last 3 projects, the most expensive mistake happened in the first 2 weeks.
   Not at the scaling stage. At the foundation stage.

3. A counterpoint I don't even like myself: maybe growth hacking
   just doesn't work in B2B enterprise. And never did.

4. Story: how in 2019 I lost $40K testing a channel
   that "worked for everyone."

5. Tactical: the prompt I use before every client call.
```

**5 seeds = 5 potential posts** across three platforms (a long-form LinkedIn post, 2-3 posts on X, a YouTube Short).

#### Step 3: AI expansion (Claude does the work, 10 min per seed)

Take one seed plus your voice profile and ask Claude to expand it.

```
Read brand-voice.md.

Take this seed:
"Noticed that in my last 3 projects, the most expensive mistake happened
in the first 2 weeks. Not at the scaling stage. At the foundation stage."

Write a LinkedIn post (250-350 words) in my voice.
3 versions with different hooks.
```

Claude gives you 3 versions. You pick one.

#### Step 4: Edit (your final pass, 5-10 min)

This is the **critical step**: skip it and you get AI slop. What you do:

1. **Remove the AI tells** ("delve", "fast-paced", "in conclusion", "it's worth noting")
2. **Add specifics**: names, numbers, dates and times, real ones from your own life
3. **Punch up the first line**: it decides whether people open the post or scroll past
4. **Cut the length** by 15-20% (AI is always wordy)
5. **Add one personal beat**: a small detail only you could know

#### Step 5: Schedule and publish

- **Typefully**: for X and other networks: a queue, drafts, analytics (there's a free plan with a limit on the number of posts)
- **Hypefury**: a scheduler that reposts your evergreen content (the list of supported networks has changed over time, so check the site)
- **Buffer**: a simple multi-platform scheduler (the free plan is limited by the number of channels; paid plans are priced per channel)

**Best timing** (in your audience's time zone, not yours; these are starting points, so check them against your own analytics):

- LinkedIn: Tuesday-Thursday, 9-11 a.m.
- X: Monday-Friday, 9 a.m. and 4 p.m.
- YouTube: Thursday-Saturday, release in the evening

---

### Tools as of October 2026

Prices are left out on purpose: they change. Current prices and versions are on the [What's current](https://aimayak.com/en/now/) page, and the service catalog is under [Tools](https://aimayak.com/en/tools/).

| Tool | What it does | When it's worth it |
|---|---|---|
| **Hypefury** | Scheduling and reposting evergreen posts, AI helpers | 1K+ followers, ready to invest |
| **Typefully** | Writing, scheduling and analytics for posts | Getting started; there's a free plan |
| **Buffer** | Multi-platform scheduler | You manage 3+ platforms |
| **Taplio** | AI assistant built for LinkedIn | LinkedIn is your main platform |
| **Hootsuite** | Scheduling and analytics for teams | A team or an agency |
| **Claude** | Writing assistant that follows your voice profile | Start on the free plan; you need a paid plan once you keep hitting the limits |
| **ElevenLabs** | Voice cloning for podcasts and video | Audio and video content |
| **Whisper / MacWhisper / Wispr Flow** | Transcribing voice memos | If you think out loud |

**Starter stack:** Claude (free plan) + Typefully (free plan). That's enough for the first few months.

**Mid stack** (1K-5K followers): a paid Claude plan + a scheduler + ElevenLabs, if you need audio content.

**Pro stack** (5K+): add a LinkedIn tool like Taplio and help with the routine (a virtual assistant, or VA, or a ghostwriter).

Work out your budget with the formula from the lesson [What AI tools really cost and how to stop overpaying](d04-ai-stack-costs.md).

---

### Voice cloning: when and how (the ethics in 2026)

Voice cloning with ElevenLabs or Resemble means **synthesizing audio in your voice** from a sample recording. A quick clone is made from a short sample (at ElevenLabs it's available starting with the Starter plan, as of October 2026); a professional clone needs a longer recording and is available starting with the Creator plan. The technology has worked since 2023, and today a clone is often hard to tell apart from the original by ear.

**Legitimate use cases:**

- ✅ A podcast intro and outro in your voice (no need to re-record them every time)
- ✅ YouTube voiceovers for tutorials (say, when you're sick: you write the script, AI voices it)
- ✅ Audio versions of your blog posts (an audiobook of your own content)
- ✅ Multilingual content (you only speak English, and AI reproduces your voice in Spanish)

**The ethical baseline in 2026:**

- 📌 **Disclose:** "Voiceover generated by AI from my own voice recordings" in the episode or video description. This is increasingly the norm among creators.
- 📌 **Don't impersonate** another person (even a public figure, even "as a joke")
- 📌 **Don't use it** for politics, scams or harmful content
- 📌 **Respect the platforms' terms:** platform rules on disclosing a synthetic voice keep changing (YouTube, TikTok, Spotify). Read each platform's current terms before you publish
- 📌 **Anthropic Responsible Scaling Policy**: it's about AI models, but the spirit applies: prevent misuse, watermark, keep an audit trail

**Tools:**

- **[ElevenLabs](https://elevenlabs.io)**: a quick clone from a short sample and a professional clone from a long recording (terms by plan: see their pricing page). One of the highest-quality platforms.
- **Resemble AI**: an alternative; compare the quality on your own voice
- **Open-source cloning models** (for example, XTTS-v2): the company Coqui shut down, the community maintains the project, and the license for the XTTS-v2 weights is non-commercial. Check the license if you need the voice for paid work. It runs on your own computer, if privacy matters to you

**Quality tips for training:**

- A professional clone needs a lot of **clean** audio (about 30 minutes as a guideline; a quick clone only needs a short sample), with no background music, recorded in one room
- Vary your emotion: happy, neutral, serious, a touch of irony
- Include hard-to-pronounce words and foreign terms from your niche
- Re-train every 3 months: your voice changes over time (age, health, a cold)

---

### Persona maintenance: 6 anti-patterns vs 6 humanize-patterns

This is the critical part. The LinkedIn and X algorithms train people to write the same way (viral hooks, the AIDA formula of Attention, Interest, Desire, Action, and broken-line formatting with one sentence per line). After 6 months of that "training," you lose your voice and become indistinguishable from 100K other "AI bro" accounts.

#### 6 anti-patterns (they instantly give away AI generation)

- ❌ **"Let's dive into..."** / **"Let's break it down..."**: a generic opener
- ❌ **"In today's fast-paced world..."** / **"In our ever-changing world..."**: a cliché
- ❌ **"It's worth noting that..."** / **"It's important to note that..."**: empty filler
- ❌ **Perfect grammar without a single typo**: people make mistakes, especially in spontaneous posts
- ❌ **No personal anecdotes, specific dates or names**
- ❌ **A structure that's too symmetrical** ("4 points, each with 4 sub-points": AI loves symmetry, people don't)

#### 6 humanize-patterns (they bring a real voice back)

- ✅ **A specific story with a time and place:** "On Tuesday, at a Starbucks on Congress Avenue, a client told me..."
- ✅ **Numbers from your own experience:** "I tested this on 47 practice calls" (not "many calls")
- ✅ **Disagreement:** "I disagree with the common view here." That's taking a risk, which AI avoids by default
- ✅ **Vulnerability:** "It took 6 failures before I understood..."
- ✅ **A tactical detail:** "I use this prompt: 'Write 3 versions, not one'"
- ✅ **A counterpoint you actually believe**, even an unpopular one

🎨 **Picture this:** AI writes like a straight-A student on an exam: smooth, symmetrical, error-free. A real person writes like an adult who has lived through a few things: rough edges, side stories, numbers from their own life. Bring the rough edges back.

---

### 3 archetypes of a successful personal brand built with AI (2026)

#### Archetype A: The Builder

- **Posts:** behind-the-scenes building, technical observations, product metrics in real time
- **How often:** daily on X + 2 a week on LinkedIn
- **How AI helps:** generating post variants, scheduling, finding relevant posts to reply to
- **Public examples (general, as a direction):** Pieter Levels, Marc Lou, Tony Dinh: the open-builder pattern
- **Stack:** Claude + a scheduler

#### Archetype B: The Consultant

- **Posts:** industry observations, frameworks, case studies (with anonymized clients)
- **How often:** 2 a week on LinkedIn as the main platform + occasional posts on X
- **How AI helps:** summarizing research, drafting posts, turning call transcripts into structured notes
- **Examples:** B2B consultants who left agencies for a LinkedIn-first solo practice
- **Stack:** Claude + a LinkedIn tool (for example, Taplio)

#### Archetype C: The Educator

- **Posts:** tutorials, in-depth guides, mini-courses, breakdowns
- **How often:** 1-2 YouTube videos a week + clips on X + a monthly long-form LinkedIn post
- **How AI helps:** script outlines, cutting clips, generating transcripts, voice in multiple languages
- **Examples:** Tiago Forte (Building a Second Brain), Ali Abdaal (productivity)
- **Stack:** Claude + ElevenLabs + a video editing tool

**Pick your archetype before you start.** Otherwise you'll write about everything and won't grow a single one of those audiences.

---

### Content calendar: a 4-week template

| Week | Long-form LinkedIn post | Daily on X | Extra |
|---|---|---|---|
| 1 | Thread / framework (300-400 words) | 5 short posts + reply game | 50 replies in your niche |
| 2 | Personal story / behind the scenes | 5 short posts + 1 thread | 1 case study |
| 3 | Counterpoint / opinion piece | 5 short posts + reply game | 1 collab post |
| 4 | Tactical guide / framework | 5 short posts + a look back | Monthly retrospective |

Then repeat, adjusting for **seasonality** (industry events, holidays, product releases) and **topical jumps** (a hot topic suddenly comes up in your niche: set the plan aside and respond).

🎨 **Picture this:** four seasons in one month. Frameworks (teach) → Stories (trust) → Opinions (stand out) → Tactics (value). And around again.

---

### The engagement game: why replies matter more than posts

Everyone thinks: I write posts → my audience grows. The reality in 2026: **a noticeable share of growth comes from replies to other people's posts in your niche**.

Why:

- A reply under a post from an account with 50K followers = those followers see your words
- The LinkedIn algorithm boosts activity in the comments (an engagement signal)
- Top accounts notice regular, high-quality replies, and some start following you back

**Tactics:**

- Find 30-50 top accounts in your niche (with Taplio or by hand)
- 50 replies a week on their posts (1-2 on each)
- Replies should add **actual value**, not "great post 👍"; that's exactly the "AI bro" style
- AI helps you find the **best places to reply** with semantic search ("find me 10 fresh posts in the AI agents niche where I can add a tactical reply"), but **you write the reply yourself**

**Don't use:** automated reply bots. They get banned. Their templated replies give them away. The damage to your reputation isn't worth it.

---

### Making money: the stages

There are no income figures here: they depend on your niche, your audience and your country, and nobody can promise them. The stages show the order of steps.

| Stage | Audience | What you do |
|---|---|---|
| **Growth** | 0-1K followers | Build trust, **don't monetize** yet. This is the investment period. |
| **Validation** | 1K-5K | A free newsletter, consultations, soft offers |
| **Established** | 5K-25K | A paid newsletter, mini-courses, ongoing consulting |
| **Authority** | 25K+ | Books, speaking, products under your own brand |

**The biggest beginner mistake:** trying to monetize at 500 followers. Conversion will be tiny, you'll burn out, and your audience will sense the desperation. Patience in the first year is a must. How to price a service without losing money: [How to price your services](d02-pricing-simple.md).

---

### Ethics: what to talk about in 2026

AI for personal branding is a new area, and the norms are still taking shape. Here's what's already mainstream:

- **An "AI-assisted" disclosure**: if AI helped substantially with the writing (more than a grammar check). LinkedIn's rules keep changing, and this kind of disclosure may become required.
- **Authenticity:** AI scales **your** voice; it doesn't create a new character. If you're not a consultant, AI won't make you one. It will only make who you already are more visible.
- **Don't claim expertise you don't have** (especially dangerous in health, finance and law, where real harm is possible). AI can help a licensed professional explain things; it never replaces licensed work or personal advice.
- **Privacy:** don't quote private DMs or client conversations without permission; anonymize them when needed
- **Voice clone disclosure**: the standard in 2026
- **Sponsored content:** if a brand pays you, sends you free products or gives you a commission, the FTC (the US Federal Trade Commission) expects you to disclose that connection clearly in the post itself, in words your audience will understand, not buried in your bio. Use each platform's paid-partnership label too. For the specifics, read the FTC's current guidance or ask a lawyer.

🎨 **Picture this:** AI is your ghostwriter, not an actor playing you. A ghostwriter writes for you based on your ideas. An actor pretends to be you. The first is legitimate; the second is deception.

---

### Anti-patterns: what definitely does NOT work

- ❌ **The same generic AI post on every platform, from one template** ("3 lessons I learned...")
- ❌ **Auto-generating without human editing**: low quality, and the audience can tell
- ❌ **Imitating someone else's voice** with AI (Pieter Levels, Naval, Garry Tan): derivative and faceless
- ❌ **Mass-producing without depth**: more volume means less resonance in each post
- ❌ **A voice clone without disclosure** in public content
- ❌ **Posting at the same time of day forever**: engagement plateaus, and the algorithm wants variety
- ❌ **Posting on 3 platforms at once from day 1**: no focus, and none of them grows
- ❌ **Hooks that overpromise** ("This will change your life"): clickbait → unfollows when the delivery is weaker than the promise
- ❌ **Obvious AI copywriting sound** ("Imagine...", "What if I told you...", "Picture this...")
- ❌ **An emoji on every line** in broken-line format: an AI tell

---

## Practice

### Step 1: Voice extraction in 4 hours

Build a voice profile from the writing you already have.

These are Terminal commands for a Mac; if the terminal isn't your thing, create the same folders by hand in Finder or File Explorer.

```bash
mkdir -p ~/Desktop/personal-brand/{seeds,drafts,published,voice}
cd ~/Desktop/personal-brand

# Gather your sources
# - export your old LinkedIn posts: request a copy of your data in LinkedIn settings
# - download your X (Twitter) archive: in your account settings
# - copy long messages from your email into plain text

# Create one file with 50+ samples
touch voice/sources.md
# (paste your texts in by hand, separated by ---)
```

Then the prompt for Claude:

```
Read voice/sources.md (50+ of my texts).

Write brand-voice.md in this format:

# Brand Voice: [your name]

## Tone
- (1-2 lines)

## Favorite words / phrases (top 30)
- ...

## Banned words / phrases
- (what you would NEVER write)

## Sentence structure
- Average length
- Favorite constructions

## Perspective
- (where I usually speak from)

## Topics I keep coming back to
- ...

## Metaphors / images
- ...

## What kind of real-life examples I use
- (places, profession, period of life)
```

Save the result to `voice/brand-voice.md`. Review it yourself: Claude sometimes overstates a pattern, so correct it by hand.

---

### Step 2: The daily seed habit (15 minutes in the morning)

```bash
# Add a daily calendar reminder at 7:30 a.m.: "5 seeds"

# File template
cat > seeds/_template.md <<EOF
# Seeds $(date +%Y-%m-%d)

1.

2.

3.

4.

5.

EOF

# Every morning
cp seeds/_template.md seeds/$(date +%Y-%m-%d).md
# Open it → write 5 thoughts in 15 minutes → close it
```

**Rules for seeds:**

- A bullet point, not a paragraph (1-3 lines max)
- Something that happened yesterday or in the last 7 days
- Specific, not general ("yesterday a client said X" vs "clients often say")
- No filter: write it down even if it seems dumb. The filtering happens at the expansion stage.

---

### Step 3: Expansion with Claude

Create a reusable prompt template.

```bash
cat > voice/expand-prompt.md <<'EOF'
# Expansion prompt template

Read voice/brand-voice.md: this is my voice.
Read voice/anti-patterns.md: what NOT to write.

Take this seed:

{SEED HERE}

Generate 3 versions of a post for {PLATFORM: LinkedIn | X thread | single X post}.

Requirements:
- The voice exactly as described in brand-voice.md
- A hook in the first line (curiosity / specificity / contrarian)
- {LinkedIn: 250-350 words | X thread: 5-9 posts | Single post: 280 characters}
- At least one specific detail (a number / date / name / place)
- No AI tells: ${LIST FROM anti-patterns.md}
- No preambles like "I want to share..."

Give 3 versions, separated by ---
EOF
```

How to use it:

```bash
# Take one seed
# Paste it into expand-prompt.md
# Run it through Claude or Claude Code
# Get 3 versions
# Pick one and copy it into drafts/
```

---

### Step 4: Editing, 5-10 minutes

Open `drafts/2026-10-05-foundation-mistakes.md`. Go through the checklist:

```markdown
[ ] First line: is the hook strong? (a question / a surprising fact / a number)
[ ] AI tells removed: "delve", "in conclusion", "it's worth noting", "fast-paced"
[ ] A specific detail added (an anonymized client name, a number, a date, a place)
[ ] Length cut by 15-20% (AI is always wordy)
[ ] One personal beat: something only you could know
[ ] Does it sound like YOU when you read it out loud?
[ ] Ethics check: you're not claiming expertise you don't have?
```

---

### Step 5: Scheduling with Typefully (free to start)

```bash
# Sign up: https://typefully.com (there's a free plan with a limit on the number of posts)

# 1. Connect Twitter / X
# 2. Connect LinkedIn (check which networks your plan includes)
# 3. Set up a queue: Monday-Friday at 9 a.m. and 4 p.m.
# 4. Drop in 5 finished posts from drafts/
# 5. Typefully publishes them on schedule
```

Alternatively, if LinkedIn is your main platform, try **Hypefury** (check the list of networks and the terms on their site; they have changed):

- Automatically recycles evergreen posts after 60 days
- AI-generated variants
- Analytics: impressions and engagement

---

### Step 6: Setting up a voice clone (optional, for YouTube or a podcast)

If you make YouTube videos or a podcast:

```
1. Go to https://elevenlabs.io
2. Choose a plan: a quick clone is available starting with Starter, a professional clone starting with Creator (as of October 2026; check the pricing page)
3. Voices section → add a voice → cloning
4. Upload a clean recording (a professional clone needs a long recording, about 30 minutes as a guideline; see ElevenLabs' help pages for the exact requirements):
   - A quiet room, an entry-level USB microphone
   - Vary your emotion (5 min neutral, 5 min upbeat, 5 min serious...)
   - Include difficult words from your niche
5. Wait for the voice to finish processing
6. Test: type any text → listen
```

How to use it:

- A voiceover for a YouTube tutorial: 1,500 words is roughly 10 minutes of audio; check the pricing page for how many credits that uses
- Multilingual: the same voice clone in Spanish (ElevenLabs' multilingual models cover many languages; the current model and language list are on their site and on the [What's current](https://aimayak.com/en/now/) page)

Add a **disclosure footer** to every description:
> Voiceover generated by AI (ElevenLabs) from my own voice recordings. Script written by me.

---

### Step 7: The engagement game with your feed and Taplio

```bash
# Find fresh posts from top accounts by hand in your feed (or with Taplio for LinkedIn)
# What you're looking for: a post where you can add real value

# Taplio for LinkedIn: finding top accounts in your niche

# Workflow:
# 1. 30 minutes in the morning: open your feed
# 2. Find 10 fresh posts where you can add value
# 3. Write each reply BY HAND, not with AI
#    (at most, AI can help you check the tone)
# 4. Daily target: 5-10 replies
# 5. Weekly target: 50 replies total
```

**The metrics you track** (instead of follower count):

- How many of your replies get a response from the author
- How many new profile views you get per week
- How many DM conversations grew out of your replies

---

## Tools and resources

- **[Hypefury](https://hypefury.com)**: scheduling for X and LinkedIn with AI helpers
- **[Typefully](https://typefully.com)**: writing and scheduling for X (free to start)
- **[Buffer](https://buffer.com)**: multi-platform scheduling, a classic
- **[Taplio](https://taplio.com)**: an AI assistant built for LinkedIn
- **[ElevenLabs](https://elevenlabs.io)**: voice cloning for podcasts and YouTube
- **[Resemble AI](https://www.resemble.ai)**: an alternative to ElevenLabs
- **[XTTS-v2 (community fork of Coqui TTS)](https://github.com/idiap/coqui-ai-TTS)**: open-source voice cloning (you host it yourself; the weights license is non-commercial)
- **[LinkedIn Creator Hub](https://www.linkedin.com/creator)**: LinkedIn's official best practices
- **[MacWhisper](https://www.macwhisper.com)** / **[Whisper](https://github.com/openai/whisper)**: transcribing voice memos
- **[Anthropic Responsible Scaling Policy](https://www.anthropic.com/news/anthropics-responsible-scaling-policy)**: about AI model safety, not about content; for content ethics, go by the platforms' rules and the ethics section above
- **Prices and versions:** [What's current](https://aimayak.com/en/now/); the service catalog: [Tools](https://aimayak.com/en/tools/)

---

## 📊 Where you are: three levels

| Level | Where you are | Tools | Time |
|---|---|---|---|
| **Beginner** | No audience yet | Claude + Typefully (free plans) + seeds written by hand | 30 min/day |
| **Intermediate** | 1K-5K followers | A paid Claude plan + Hypefury + ElevenLabs | 1 hour/day |
| **Pro** | 5K+ | A scheduler + Taplio + ElevenLabs + a ghostwriter or VA | 2-3 hours/week of managing |

**Beginner:** focus on **building your voice**, not on growth. A voice profile + 15-minute daily seeds + 1 platform.

**Intermediate:** scale with AI ghostwriting, add a voice clone for your podcast or YouTube channel, and start playing the engagement game systematically.

**Pro:** a full team (a VA or a ghostwriter) + AI orchestration with Claude Code as the director + multi-platform sync.

---

## ✅ Checklist

- [ ] 50+ samples of your writing collected
- [ ] `brand-voice.md` created and reviewed
- [ ] `anti-patterns.md` (your list of AI tells) written
- [ ] **One** main platform chosen for the first 6 months
- [ ] Daily seed habit set up (15 minutes in the morning, calendar reminder)
- [ ] Expansion prompt template saved
- [ ] Editing checklist memorized or printed out
- [ ] Tool stack chosen (the free plans of Claude and a scheduler are enough to start)
- [ ] Engagement target set (5-10 replies a day in your niche)
- [ ] First 30 posts scheduled in the queue
- [ ] Voice clone set up (only if you make YouTube videos or a podcast; otherwise skip it)
- [ ] Disclosure standard adopted (an AI-assisted footer where it applies, and a clear label on any sponsored post)

---

## Key takeaways

> A personal brand in 2026 isn't AI writing in your place. It's AI scaling your voice through a system: voice profile → daily seeds → AI expansion → your edit. Without daily seeds, you get generic AI slop. Without a voice profile, AI writes like anyone, just not like you.

> Pick one platform for your first 6 months. LinkedIn for a B2B audience. X for founders, developers and marketers. YouTube for educators who are in it for the long run. Spreading yourself across three from day 1 is the biggest beginner mistake.

> The 6 anti-patterns ("delve into", perfect grammar, symmetrical structure, no personal details, generic openers, an AI tone) make a post recognizable as AI within 3 seconds. The 6 humanize-patterns (a time + a place + a number + disagreement + vulnerability + a tactical detail) bring a real voice back. That's your final filter before you publish.

> The engagement game (50 quality replies a week to top accounts in your niche) often brings more growth than the posts themselves. AI helps you find **where** to reply, but you write the reply yourself. Automated reply bots are a road to bans and reputation damage.

> Voice cloning is legitimate for podcasts, YouTube voiceovers and multilingual content, always with disclosure. Don't use it to impersonate others, for politics or for scams. ElevenLabs is one of the highest-quality cloning platforms as of October 2026.

---

## Related lessons

- [AI copywriting: a prompt pipeline that sounds like you](67-ai-copywriting.md): copywriting and hooks (the foundation before AI ghostwriting)
- [AI voiceover: ElevenLabs, text-to-speech and voice content](68-voice-tts-elevenlabs.md): voice, text-to-speech and audio content
- [AI video generation](71-ai-video-generation.md): Runway, Kling and other tools for visual content
- [The complete content pipeline](72-content-pipeline-complete.md): multi-platform automation
- [AI competitive intelligence](89-competitive-intelligence.md): niche research for your personal brand

---

## Next lesson

→ [AI voiceover: ElevenLabs, text-to-speech and voice content](68-voice-tts-elevenlabs.md): voice as the new main format
