# Claude vs ChatGPT vs Gemini: AI models compared

**Time:** about 30 min reading + 25 min practice

> *Picture choosing a vehicle for different jobs. A Ferrari for the racetrack, a Land Rover for off-road, a Toyota Camry for your daily drive around town. There's no "best car, period," only the best car for a particular road. AI models work exactly the same way. This lesson is your map of the roads and the cars in the AI market. The specific models and prices are as of October 2026. They change fast, so check the current list on the [What's current](https://aimayak.com/en/now/) page.*

---

## The gist

By the end of this lesson you'll understand:
- Which major AI models exist and who makes them
- Where each model is strong and where it falls short
- When to pick Claude, ChatGPT, Gemini, an open model or Mistral
- Why this course uses Claude Code in the lessons where we build, and why that's a deliberate choice, not fandom

---

## Key concepts

**LLM** (Large Language Model): an AI system trained on an enormous amount of text. It can understand language and generate (create) answers.

**Benchmark** (a performance test): a standardized test for comparing models. Think of it as the SAT for AI: MMLU, HumanEval, MATH, GSM8K.

**Context window**: the maximum amount of text an AI can see and keep in mind at one time. Roughly: if the window is 200K tokens, the model can hold a 150,000-word book in memory.

**Token** (the smallest unit of text for an AI): about 0.75 of an English word. "Hello" = 1 token, "Hello world" = 2 tokens. Other languages usually take more tokens per word, and each model counts a little differently. Every token costs money when you work through the API (Application Programming Interface: the channel programs use to talk to the model).

**Open source / open weights**: a model whose weights are published, so you can download it and run it on your own machine. License terms differ from model to model.

**Multimodal** (works with several kinds of data): a model that handles not just text but also images, sound and video.

**Inference**: the moment the model generates an answer to your question. The provider spends computing power; you pay for the tokens.

**Parameters** (also called the model's "weights"): the numbers inside the model's neural network. As a rule, the more there are, the more capable the model, but also the heavier it is to run. They're counted in billions: 8B, 70B, 405B.

---

## Theory

### 1. Why compare models at all?

A lot of people start with AI like this: they hear about ChatGPT and use only that. Or they open Claude and never look at anything else. It's like using only a screwdriver and never reaching for the hammer, just because the screwdriver happened to be the first tool you picked up.

Three reasons to know the whole market:

**Different tasks, different strengths.** Working through a huge 500-page legal document calls for a model with a large context window (as of October 2026, a window of about 1 million tokens is available in Claude Fable 5.1, Opus 5.5 and Sonnet 5.5, in several Gemini models and in the GPT-6 models; check each provider's docs for exact numbers). Writing quality code: Claude and other coding agents. Working with images and voice in a single request: ChatGPT or Gemini. Complete privacy with no cloud: an open model running locally on your own computer.

**Prices differ 10 to 100 times.** As of October 2026, a million input tokens (the text you send to the model) costs $0.10 on GPT-6 Luna and $10 on GPT-6 Astra. Among Claude models, a million input tokens ranges from $1 on Haiku 4.5 to $10 on Fable 5.1. For routine tasks, that's a huge difference in budget.

**The market changes fast.** The model that was the best six months ago may have lost its spot to a newcomer. When you understand the landscape (the overall map of the market), you make an informed choice instead of just following the hype.

🎨 **Picture this:** knowing the whole AI model market is like having a map of your city. You might always drive the same route. But the map shows you the detour around a traffic jam, the road built for trucks, the bike lane.

---

### 2. The main companies and their models, as of October 2026

| Company | What they offer now (October 2026) | Type | Founded |
|----------|--------------------------------|-----|----------|
| Anthropic (US) | Claude Fable 5.1, Opus 5.5, Sonnet 5.5, Haiku 4.5 | Closed | 2021 |
| OpenAI (US) | The GPT-6 family (Astra, Sol, Luna); the regular ChatGPT chat runs on GPT-5.6 family models | Closed | 2015 |
| Google / DeepMind (US/UK) | Gemini 3.x (Flash, Pro, Deep Think); Gemini 4 was announced September 30, 2026, and isn't publicly available yet | Closed | 1998 / 2010 |
| Meta (US) | Muse Spark (since April 2026, it powers the Meta AI assistant); previously released Llama models remain available | Muse Spark is closed, Llama has open weights | 2004 |
| Mistral AI (France) | The Mistral Vibe assistant (formerly Le Chat) and models through the API | Some models have open weights | 2023 |
| SpaceXAI (formerly xAI, US) | Grok 4.x | Closed | 2023 |
| Alibaba (China) | The Qwen family | Some models have open weights | 1999 |
| DeepSeek (China) | DeepSeek V4 (V4.1-Flash came out in September 2026) | Open weights (MIT license) | 2023 |

The difference between "closed" and "open":

- **Closed model**: you use it through an API or an app (chatgpt.com, claude.ai). You pay for usage. The model itself never sits on your machine; it runs on the company's servers.
- **Open model** (open weights): you download it and run it yourself, on your own computer or server. The model itself is free. Your data doesn't go anywhere. But you need the hardware.

---

### 3. Claude (Anthropic): a closer look

Anthropic was founded in 2021 by former OpenAI employees, including Dario Amodei and Daniela Amodei. The company focuses on AI safety; it's one of its core principles.

**The Claude lineup (as of October 2026):**

| Model | Speed | Power | Price per 1M tokens, input / output (API) | When to use it |
|--------|----------|----------|-------------------------------------------|--------------------|
| Claude Haiku 4.5 | Fastest | Basic | $1 / $5 | Simple tasks, short answers, high-volume processing |
| Claude Sonnet 5.5 | Fast | High | $2 / $10 | Everyday tasks, edits, documents, spreadsheets |
| Claude Opus 5.5 | Medium | Very high | $4 / $20 | The main strong model: long work with code and documents; the default in Claude Code |
| Claude Fable 5.1 | Slower | Maximum | $10 / $50 | The hardest multi-step tasks; on the Pro plan it's paid for separately with usage credits (pay-as-you-go credits on top of your plan), and on Max it's included in the plan's limit |

Current prices and the model list are on the [What's current](https://aimayak.com/en/now/) page. There's also an invitation-only model (Mythos 5.1, Project Glasswing); it isn't available to regular users.

**Context window:** as of October 2026, Fable 5.1, Opus 5.5 and Sonnet 5.5 have 1 million tokens (about 555,000 English words by Anthropic's estimate, roughly the whole Lord of the Rings trilogy and then some); Haiku 4.5 has 200K tokens.

**Claude's strengths** (as Anthropic describes them; test them on your own tasks):

- Following instructions: it's built for complex multi-step tasks with precise requirements
- Code: one of its strongest areas. Check current independent benchmarks (for example, SWE-bench), since rankings shift every few months
- Long documents: it analyzes, summarizes and finds contradictions in contracts and reports
- Honesty: Anthropic puts a lot of weight on it. The model tries to admit when it doesn't know something, but hallucinations (AI confidently making things up) still happen, so double-check anything important
- Constitutional AI: Anthropic's approach to safety. The model is trained on a "constitution" of principles, not only on human feedback

**Weaknesses:**

- Without search or connected tools, there's no real-time data: the model has a cutoff date, and it knows nothing after that date (web search is available in the chat)
- Image generation isn't Claude's main strength: for pictures, people usually turn to separate services, such as ChatGPT Images or Nano Banana in Gemini
- Limited multimodality: through the API it takes text and images as input; it doesn't process audio or video directly

**Claude Code** is Anthropic's agent for people who build software and automations. In this course it shows up near the end: in the first-build module and in the library. It isn't just Claude in a browser. It's an agent that can read files, write code, run commands in the terminal (the text window where you type commands to your computer's operating system) and manage projects. It's included in the paid plans (Pro and up).

🎨 **Picture this:** Claude is like a very smart, thoughtful senior colleague. Doesn't rush, thinks before answering, tries to admit when it doesn't know something. It still makes mistakes, so people double-check anything important, and it's sometimes slower than you'd like.

---

### 4. ChatGPT and OpenAI's models

OpenAI makes ChatGPT, one of the most widely used AI apps in the world.

**OpenAI models as of October 2026:**

| What | What's special | When to use it |
|-----|-------------|-------------------|
| GPT-6 Astra | The top model (announced September 3, 2026) | The hardest tasks |
| GPT-6.1 Sol, GPT-6 Sol | The main models in the Work and Codex modes | Work tasks, code, documents |
| GPT-6 Luna | Fast and cheap | Everyday questions, high-volume processing |
| The GPT-5.6 family (Sol, Terra, Luna) | The models in the regular ChatGPT chat | Everyday conversations |

The names and the lineup change every few months: for example, GPT-5.5 leaves ChatGPT on October 14, 2026. The current list is on the [What's current](https://aimayak.com/en/now/) page.

**What changed compared with earlier generations.** The separate "reasoning" models of the o-series, which you used to have to pick by hand, are now built into the main lineup: hard questions are handled by a reasoning mode. That mode "thinks out loud" before it answers. It takes more time and is more accurate on hard logic problems, but on simple questions it's overkill and costs more.

**The OpenAI ecosystem:**
- ChatGPT: the app for a broad audience, with Free, Go ($8), Plus ($20), Pro (from $100) and Business plans; monthly prices as of October 2026
- Work: an agent mode for long tasks (documents, spreadsheets, presentations); it shares limits with Codex
- Codex: the product for software development: background agents, reviewing changes
- Image generation is built into ChatGPT (ChatGPT Images); the older DALL-E 2 and 3 models were shut off in the API on May 12, 2026
- Whisper: open-source speech-to-text
- Shut down: the Sora app (April 26, 2026), the Sora API (September 24, 2026), the Assistants API (August 26, 2026)

**Browsing:** ChatGPT can search the web, which is handy when you need fresh information.

**ChatGPT's strengths:**
- A broad ecosystem of features and integrations
- Built-in image generation, no separate service needed
- Native voice: real spoken conversations
- Web search right in the chat
- A huge user base: lots of tutorials, case studies and community help

**Weaknesses:**
- The feature set depends on your plan and region, and model names change often
- The top models cost a lot more than the light ones (up to 100 times more through the API)
- Reasoning mode is slower, so you have to wait

🎨 **Picture this:** ChatGPT is like a flagship smartphone with a thousand apps. It does everything and has a huge ecosystem, but a specialized tool sometimes beats it in its own niche.

---

### 5. Gemini (Google / DeepMind): a closer look

Google invests heavily in AI: it has the Google DeepMind lab (the makers of AlphaGo and AlphaFold; the Google Brain team merged into it in 2023) and its own AI chips, called TPUs (Tensor Processing Units).

**The Gemini lineup as of October 2026:**

| What | What's special |
|-----|-------------|
| Gemini 3.6 Flash | A fast model for everyday tasks, available for free (released July 21, 2026) |
| Gemini 3.1 Pro | The top model; limited on Free |
| Deep Think | A deep-reasoning mode, on the Ultra plan |
| Gemini 4 (Argon) | Announced September 30, 2026; not publicly available yet |

US plans (as of October 2026): Free, Google AI Plus ($4.99), Google AI Pro ($19.99), Google AI Ultra ($99.99 or $199.99 a month). Outside the US, prices are set in local currency. Current prices and versions are on the [What's current](https://aimayak.com/en/now/) page.

**Context window.** Several Gemini models have a 1-million-token window (check the model's documentation for exact numbers). That once set Gemini apart, but as of October 2026, Claude Fable 5.1, Opus 5.5 and Sonnet 5.5 and the GPT-6 models have a window of about 1M too. For scale: 1 million tokens is roughly 555,000 to 750,000 English words, or 5 to 10 average-length books. You can load the entire codebase (all the source code of a project) of a large project and analyze it as a whole.

**Gemini's multimodality:**
- Text: yes
- Images: yes
- Video: yes (through the API, Claude and GPT-6 take only text and images as input)
- Audio: yes
- Code: yes

In breadth of multimodality, Gemini is one of the strongest (taking video as input is what sets it apart).

**Google Workspace integration:** Gemini is built into Gmail, Google Docs, Google Sheets and Google Meet. If your company runs on Google Workspace, that's a real advantage.

**Google Search integration:** through Google AI Studio and inside Google's products, Gemini has access to fresh data from search.

**Some history:** Google's assistant was first called Bard; it was renamed Gemini in February 2024. To compare its quality with Claude and GPT, look at current independent rankings and try your own tasks: the standings change with every release.

**The 2026 renames:** since July 16, 2026, NotebookLM has been called Gemini Notebook. And on September 30, 2026, Google announced that Skills will replace Gems (saved sets of instructions); personal Gems are set to carry over automatically in November 2026.

**Gemini's strengths:**
- A large context window, up to 1 million tokens
- Takes text, images, video, audio and PDFs as input
- Google Workspace integration
- Access to Google Search
- Low-cost Flash models and a free tier in the API

**Weaknesses:**
- Prices and features depend on your country: some features aren't available everywhere
- The top model is limited on the free plan, and Deep Think is only on Ultra
- Product and plan names change often, so check the current terms

🎨 **Picture this:** Gemini is like a Google employee who knows every one of the company's products by heart and works with text, pictures, video and sound. It's most useful to people who already live in Google's services.

---

### 6. Open models: Llama (Meta) and others

Meta is the company that owns Facebook, Instagram and WhatsApp. In 2023-2024 it released the Llama models with open weights, which made it possible to run strong models on your own hardware.

**Why did Meta release open models?**

Mark Zuckerberg explained it in an open letter in July 2024. Meta doesn't sell access to AI models, so releasing them openly doesn't cut into its revenue. An open model gets improved by the whole community and becomes a shared standard. And Meta itself doesn't want to depend on competitors' closed platforms.

**An important 2026 update.** In April 2026, Meta introduced a model called Muse Spark, and the Meta AI assistant now runs on it rather than on Llama. Muse Spark's weights aren't published: you get it through Meta's products, select partners get it through an API, and about future versions Meta says only that it hopes to open-source them. Previously released Llama models are still available to download. Other companies release open weights today too: DeepSeek (V4 under the MIT license), Alibaba (the Qwen models), Mistral (some models). The principles below hold for any open model; in the table, Llama is just an example of model sizes.

**Size examples (the Llama 3.x family):**

| Model | Parameters | File size in Ollama | Where it runs |
|--------|-----------|--------------------------|---------|
| Llama 3.1 8B | 8 billion | 4.9 GB | An ordinary modern computer |
| Llama 3.3 70B | 70 billion | 43 GB | A powerful workstation with a lot of memory |
| Llama 3.1 405B | 405 billion | 243 GB | A server. When it came out in July 2024, Meta called it the first open model on the level of the best closed ones |

The whole model loads into memory, so your computer needs more free memory than the size of the file.

**What "open weights" means:**
- You download the model's weights (its numerical parameters): a big file, from a couple of gigabytes for small models to 240+ GB for the largest
- You run it locally with special software
- Your data doesn't go anywhere; everything stays on your computer
- You can fine-tune the model (train it further) on your own data
- The model itself is free, but the license may come with restrictions: read the terms

**Ollama** is one of the most popular tools for running open models. Running models on your own computer with it is free (the paid plans are only for cloud features). It works on Mac, Windows and Linux. Installation takes a few minutes.

**When to choose an open model (Llama or another one):**

- Data that can't go to the cloud (medical records, legal documents, clients' financial information)
- You want zero API costs at high volume
- You want to fine-tune a model on specialized data (for example, your company's documents)
- You need to work offline (without internet)

💡 If you work in healthcare, law or finance, your employer's or practice's rules for client data come first (patient records, for example, are covered by HIPAA). Ask before you put that kind of data into any AI tool, local or not.

**Strengths of open models:**
- Free when you run them yourself
- Full privacy: your data never leaves your computer
- You can fine-tune them
- No dependence on an outside API

**Weaknesses:**
- You need memory: more free memory than the size of the model file (about 5 GB for the 8B version, 43 GB for 70B)
- A model you can run on a home computer usually trails the top closed models on tasks that demand precision
- Many open models work with text only; only certain versions understand images
- It takes technical setup

🎨 **Picture this:** an open model is like Linux: free, powerful, full control, but you need technical know-how. Claude, ChatGPT and Gemini are like macOS: you pay for convenience, speed and quality right out of the box.

---

### 7. Mistral (Mistral AI): the European alternative

Mistral AI was founded in 2023 in France by three researchers from Google DeepMind and Meta AI. The company raised one of the largest first funding rounds in Europe: €105 million.

**What Mistral offers as of October 2026:**

- **Mistral Vibe** (formerly Le Chat; renamed August 12, 2026, with the same address and account): an assistant with three modes: Vibe Chat (regular chat), Vibe Work (research, documents, emails) and Vibe Code (code). Plans: Free, Pro ($14.99 a month), Team ($24.99 per user), prices as of October 2026.
- **Models through the API** for developers, some of them with open weights. Mistral doesn't say on its pricing pages which models run inside Vibe; see the company's website for the list of models and licenses.
- Historically known for the Mistral Large, Mixtral and Codestral models (Codestral specializes in code).

**Mixture of Experts**: an architecture Mistral popularized with its Mixtral 8x7B model. Instead of one big neural network, there are several specialized "experts." For each request, only some of them switch on (in Mixtral, 2 out of 8). The idea: quality closer to a big model at a resource cost closer to a small one. Many model makers use this idea today.

**Why Mistral matters:**

**GDPR compliance** (General Data Protection Regulation, the EU's data protection law): the regulation limits transferring personal data outside the EU without proper safeguards. Mistral, a French company, stores data in the EU by default, so if you work with large European companies, it's often easier to get Mistral through their review. But "GDPR-friendly" doesn't mean "safe by default": read the data processing terms. For example, on Vibe's free plan your data goes into model training by default; you can turn that off in the privacy settings.

**Mistral's strengths:**
- Price: the Pro plan is $14.99 a month, compared with $20 for Claude Pro and ChatGPT Plus (October 2026)
- A European company: data is stored in the EU by default
- Some models have open weights, so you can run them locally
- European languages: the company describes its top model as natively fluent in English, French, Spanish, German and Italian
- A mode for programming (Vibe Code)

**Weaknesses:**
- On the free plan, messages and web searches are limited
- In the independent LMArena rankings, Mistral's models aren't in the top ten as of October 2026: test them on your own examples

🎨 **Picture this:** Mistral is like Airbus: the European option alongside the American manufacturers. People choose it when it matters that the provider and the data are in Europe.

---

### 8. Other players worth knowing

**Grok (SpaceXAI, formerly xAI):** in February 2026, SpaceX bought xAI, and the company now goes by SpaceXAI. The current lineup is Grok 4.x. It searches the web and X in real time, handles voice, and creates images and video. You can start for free at grok.com; paid plan prices are on the [What's current](https://aimayak.com/en/now/) page.

**Qwen (Alibaba Cloud):** Alibaba's family of models. The open versions are released under the permissive Apache 2.0 license and, according to the developers, support more than a hundred languages. The models are built in China, so people often consider them for work in Chinese and for Asian markets. New versions come out several times a year; check the site for the current one.

**DeepSeek (China):** became widely known in January 2025, when it released its R1 reasoning model with open weights. The current lineup is DeepSeek V4 (V4.1-Flash came out in September 2026), with weights published under the MIT license. Data privacy remains an important question: according to the service's privacy policy, data is stored and processed in the People's Republic of China, so don't paste client data into the chat. To opt out of training on your data, send a request to privacy@deepseek.com.

**Meta AI** runs on the Muse Spark model and is built into Meta's apps (WhatsApp, Instagram and others). **Perplexity** is a search engine that gives answers with links to its sources; it uses models from different companies. **Microsoft Copilot** is Microsoft's assistant: the paid Copilot Pro is no longer sold, and the Microsoft 365 Premium plan ($19.99 a month as of October 2026) replaced it. Details on each one are on the pages of the [Tools](https://aimayak.com/en/tools/) section.

---

### 9. Comparison table, as of October 2026

| Model | Company | API price* | Context window | What it takes as input | Open weights |
|--------|----------|-----------|----------------|-------------------|---------------|
| Claude Haiku 4.5 | Anthropic | $ | 200K | Text + images | No |
| Claude Sonnet 5.5 | Anthropic | $$ | 1M | Text + images | No |
| Claude Opus 5.5 | Anthropic | $$$ | 1M | Text + images | No |
| Claude Fable 5.1 | Anthropic | $$$$ | 1M | Text + images | No |
| GPT-6 Luna | OpenAI | $ | see docs | Text + images | No |
| GPT-6.1 Sol | OpenAI | $$ | see docs | Text + images | No |
| GPT-6 Astra | OpenAI | $$$$ | see docs | Text + images | No |
| Gemini 3.x Flash | Google | $ | up to 1M (see docs) | Text + images + video + audio | No |
| Gemini 3.1 Pro | Google | $$ | up to 1M (see docs) | Text + images + video + audio | No |
| DeepSeek V4.1-Flash | DeepSeek | $ | see docs | Text + images | Yes (MIT) |
| Llama 3.3 70B | Meta | Free\*\* | 128K | Text only | Yes |

\*Prices are approximate and refer to the API: $ = up to $1 per million input tokens, $$ = about $2, $$$ = about $4, $$$$ = $10 and up. Exact prices and versions: [What's current](https://aimayak.com/en/now/).

\*\*Free = open weights, but you need your own hardware to run the model. Through API hosting services (Together.ai, Groq, Fireworks), you pay.

The table deliberately leaves out "Code" and "Documents" columns with scores: quality rankings change with every new release. Test a model on your own tasks and check independent benchmarks.

---

### 10. A practical decision tree: what to pick when

Use this whenever the question comes up: "Which model should I use for this task?"

```
TASK → CONDITION → GOOD CHOICE (as of October 2026)

Writing code / building a system → precise instruction-following matters most
  → Claude (Sonnet 5.5 or Opus 5.5) + Claude Code

Analyzing a very long document (100+ pages, a book, a codebase)
  → a model with a window of about 1M tokens: Claude Sonnet / Opus / Fable, Gemini or GPT-6

Working with images + voice + video in one request
  → ChatGPT or Gemini

Data can't go to the cloud (medical, legal, client finances)
  → an open model (Llama, DeepSeek, Qwen, Mistral) run locally with Ollama

Need speed + the lowest cost for routine tasks
  → Claude Haiku 4.5, the fast Gemini Flash models or GPT-6 Luna

Your company operates in the EU, strict GDPR
  → Mistral (check the data processing terms) or any service that hosts data in the EU

Hard math / logic / algorithm problems
  → reasoning mode in Claude or ChatGPT, or Gemini Deep Think

Starting from zero, want to try it for free
  → claude.ai, chatgpt.com or gemini.google.com: all three have a free plan

Want local AI with no dependence on the internet
  → Ollama + any open model that fits your computer

Working with X/Twitter data, need real-time information
  → Grok

Analyzing the Chinese market / working in Chinese
  → Qwen or DeepSeek
```

---

### 11. An important detail: prices change fast

Over the past few years, the cost of AI APIs for models at the same quality level has dropped noticeably. The reasons:

- Competition between companies
- Better efficiency in chips and algorithms
- Open models pushing down the prices of closed ones

The takeaway: don't memorize specific numbers; they'll go out of date. Remember the principle instead: always check current prices before you launch a project, on the [What's current](https://aimayak.com/en/now/) page and on the providers' own sites: Anthropic (claude.com/pricing), OpenAI, Google AI Studio.

---

### 12. Why this course chose Claude Code

In the lessons where we build something (the first-build module and the library), this course uses Claude Code. It's a deliberate choice, not fandom. You don't need it for the early modules: a regular chat is enough there.

**Reason 1: Code quality.** Claude is among the strongest models for programming. Check current independent benchmarks (SWE-bench is a test built on solving real GitHub issues); rankings change with every release.

**Reason 2: A large context window.** Up to 1M tokens (as of October 2026) lets you load a whole project into context and work with it as a single whole. That's critical for building real systems.

**Reason 3: Claude Code as a specialized tool.** It's not just a chat on top of an API. It's an agent wired into the terminal, the file system and git (a version control system that keeps the history of your changes). Other companies have their own coding agents (for example, OpenAI's Codex, Cursor, Devin Desktop), and the ideas in this course carry over to them. Claude Code was chosen because it's a convenient tool for showing the practice.

**Reason 4: Following instructions.** Complex workflows (with agents, automatic rules and skills) need a model that carries out multi-step instructions precisely, without drifting. Claude handles that well.

**What this does NOT mean:**

- Claude isn't the best at everything; you've already seen that in the table and the decision tree
- In real professional work, you'll use several models
- A multi-model strategy is the norm for serious projects: Claude for code, Gemini for video and the Google world, ChatGPT for voice and images, an open model for private data

Understand the whole landscape, and know one tool really well: that's the right approach.

---

## Practice

### Exercise 1. A side-by-side test (20 min)

1. Open **claude.ai** (free). If you haven't signed up yet, you'll need an email and a phone number that can receive a verification code by text
2. Open **chatgpt.com** (free; you need an email to sign up), or use Gemini or any other assistant from the [Tools](https://aimayak.com/en/tools/) section
3. Give both of them the same prompt:

```
Explain how compound interest works in plain English, 
with an example for $1,000 at 10% a year over 10 years. 
No formulas; use an everyday analogy instead.
```

4. Compare the answers: which is clearer? Which is better organized? And check the accuracy: after 10 years the total should come to about $2,594 (multiply $1,000 by 1.1 ten times in a row)

There's no right answer to "which is clearer"; that's your own hands-on comparison. The final amount, though, is something you can check, and that's a good habit to build.

---

### Exercise 2. Try local AI (30 min, optional)

1. You need a computer for this one; it won't work on a phone. Go to **ollama.com**, then download and install Ollama (running models on your own computer is free; it works on Mac, Windows and Linux)
2. On Mac and Windows, a chat window opens after installation, and you can pick and download a model right there. The other way is to open the terminal (a window for typing text commands) and run:

   ```bash
   ollama pull llama3.2
   ollama run llama3.2
   ```

3. Talk to the model. It runs entirely on your computer: once it's downloaded, it needs no internet and no API key (an access key)
4. Notice the difference in speed and quality compared with claude.ai

llama3.2 is a small Llama 3.2 model with 3 billion parameters; the file takes up about 2 GB. If that model is no longer in the Ollama catalog, pick any small model from the catalog.

---

### Exercise 3. Reflection (5 min)

Write down your answer to this (in a notebook, or right in claude.ai):

> "For the work I do as a [your job title / field], which AI model seems most useful, and why?"

Save your answer. At the end of the course, it'll be interesting to reread it and see whether your view has changed.

---

## Key takeaways

**There's no "best AI," only the best one for a particular task.** Just as there's no best car, period, only the best one for your road.

**Claude is a strong choice for code, long documents and precise instruction-following.** That's why the course uses Claude Code in the lessons where we build.

**Gemini is a strong choice for multimodal tasks and the Google world.** Video and audio as input, Workspace integration.

**ChatGPT is a strong choice for voice, images and a broad ecosystem.** Text + images + voice, natively.

**An open model is the choice when data must not leave your computer.** Open weights, full privacy, but you need the hardware.

**Mistral suits European companies with GDPR requirements**, but check its data processing terms all the same.

**Prices are dropping fast.** Check current prices before every major project.

**A multi-model strategy is the norm for professionals.** Know the tools, and use the best one for the job.

---

## Lesson glossary

| Term | What it means |
|--------|---------|
| LLM | Large Language Model |
| API | Application Programming Interface: a way for programs to access a service |
| Token | The smallest unit of text for an AI, about 0.75 of a word |
| Context window | The maximum amount of text a model can see at one time |
| Benchmark | A standardized performance test |
| Multimodal | Works with several kinds of data (text, photos, audio, video) |
| Open source | Source code that's open and available for free |
| Fine-tuning | Training a model further on specialized data |
| Inference | The process of a model generating an answer |
| Parameters | The numbers inside a neural network, counted in billions (B) |
| Reasoning | The ability to work through a problem in several logical steps |
| GDPR | The European law that protects personal data |
| RAG | Retrieval-Augmented Generation: search + generation grounded in a knowledge base |
| Constitutional AI | Anthropic's approach: training a model on a set of principles (a "constitution") |
| Codebase | The full set of a project's source code |
| Weights | The numerical parameters of a trained neural network |

---

## Next lesson

**→ [Writing with AI](67-ai-copywriting.md): the first lesson of the module "AI for everyday work: writing, email, meetings, translation."**

You've picked your models. Next we put them to work on everyday tasks: writing, email, meetings, presentations, translation. We'll come back to your subscription budget in the lesson [How much to spend on AI](00e-investment-roadmap.md), and to agents in the lesson [What is an AI agent, and why it matters now](01-agentic-market.md) near the end of the course.

---

*Comparing AI models | AI Mayak, updated October 2026*
