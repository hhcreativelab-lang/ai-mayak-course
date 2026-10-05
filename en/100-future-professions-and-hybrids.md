# Jobs of the future: 100 new and hybrid AI careers

**Time:** about 2 hours to read in full (it's a reference: read the parts you need)

---

> **A reference guide from this course.**
> If you've been asking "will AI take my job?", this is the long answer: a full map of careers in the AI era. What's brand new, what's being reshaped by AI, and what's disappearing.
> Updated: October 2026.

---

## 🔥 The big picture: AI as a forest fire

AI didn't arrive in the working world **as an upgrade**. It arrived like a forest fire:

- **Some trees (jobs) burn down**: the routine, template-driven, repetitive ones
- **New seeds sprout**: jobs that didn't exist three years ago (Prompt Engineer, AI Agent Architect)
- **Old stumps send up new shoots (hybrids)**: doctors, lawyers and designers don't disappear; they become `profession + AI = hybrid`

**What to keep in mind:**

- The change is already underway. Learning how it works is the best way to protect your own career
- Strong professionals don't "compete with AI". They "manage AI"
- The most valuable skill set in 2026 is **AI literacy + domain expertise**

---

## ⚠️ Disclaimer

This is a reference map of careers and a scenario-based forecast, not research data.

- Salary estimates, growth percentages and market sizes have been removed: they weren't verified against primary sources. For current numbers for your state and your job title, check official labor statistics (in the US, the Occupational Outlook Handbook from the Bureau of Labor Statistics, bls.gov/ooh), plus job boards and salary surveys
- The demand stars (⭐) and the 2027–2030 forecasts are the author's estimates and scenarios, not measurements, and they may not come true
- On medicine, law and finance: AI helps a professional, but it doesn't replace licensed work and doesn't give personal advice
- This is not financial or investment advice and not a promise of income

---

## 📑 How this guide is organized

1. [Section A: 50 NEW careers (rooted in AI)](#section-a)
   - A1: AI Engineering / Building (15)
   - A2: AI Content / Creative (10)
   - A3: AI Business / Strategy (10)
   - A4: AI Operations (8)
   - A5: AI Specialized (7)
2. [Section B: 50 HYBRID careers (an existing job + AI)](#section-b)
   - B1: Knowledge Work (15)
   - B2: Creative Work (10)
   - B3: Business / Sales (10)
   - B4: Trades + Services (10)
   - B5: Education + Wellness (5)
3. [Section C: What's disappearing (10 jobs at risk)](#section-c)
4. [Section D: Skills for the future (25 skills)](#section-d)
5. [Section E: Decision tree: which career to choose](#section-e)
6. [Salary benchmarks 2026](#salary-benchmarks)
7. [Top 10 emerging careers 2026-2030](#top-10)
8. [Checklist and next steps](#next-steps)
9. [Sources](#sources)

---

## <a id="section-a"></a>🌱 Section A: 50 NEW careers

Jobs that **didn't exist before 2022**. They appeared as a direct result of generative AI.

---

### A1. AI Engineering / Building (15 careers)

These are **the builders of the AI era**. The most talked-about category of 2026.

---

#### 1. Prompt Engineer

- **What they do:** Design and fine-tune prompts for LLMs (large language models such as Claude, GPT, Gemini and others). Get the most out of a model at the lowest cost.
- **Key skills:**
  - Understanding how LLMs work (tokens, context, attention)
  - A/B testing prompts
  - Cost optimization (Sonnet vs Opus tradeoffs)
  - Chain-of-thought, few-shot, structured outputs
  - Eval design (how to measure a "good prompt")
  - Knowing each model's quirks
- **Demand:** ⭐⭐⭐⭐ (the junior level is getting crowded; senior people are still in short supply)
- **How to get there:**
  1. Work through Anthropic's free interactive prompt engineering tutorial (it's on GitHub)
  2. Build 5 portfolio prompts with measured impact
  3. Contribute to open prompt libraries (PromptHub)
- **Picture this:** a winemaker. The same grapes turn into a great bottle or into swill, depending on whose hands they're in.

---

#### 2. AI Application Engineer

- **What they do:** Build production-grade applications on top of LLM APIs. Backend + frontend + AI integration.
- **Key skills:**
  - Full-stack Python/TypeScript
  - LLM APIs (Anthropic SDK, OpenAI, etc.)
  - Vector databases (Pinecone, Weaviate, Qdrant)
  - Streaming responses, async patterns
  - Error handling, retries, fallbacks
  - Cost monitoring per request
- **Demand:** ⭐⭐⭐⭐⭐ (the main new career of 2026)
- **How to get there:**
  1. Learn one LLM SDK in depth (Anthropic recommended)
  2. Build 3 production projects (shipped, not "practice" projects)
  3. An open-source AI app on GitHub (1,000+ stars)
- **Picture this:** an architect building houses from a new material. The bricks (LLMs) are known, but the building that comes out is completely new.

---

#### 3. LLM Operations (LLMOps) Engineer

- **What they do:** Deploy, monitor and scale LLM applications in production. DevOps, but for AI.
- **Key skills:**
  - Kubernetes, Docker
  - Observability (Datadog, New Relic, custom)
  - Token-level cost tracking
  - Rate limiting, queueing
  - Multi-region failover
  - Model versioning + rollback
- **Demand:** ⭐⭐⭐⭐⭐ (grows as more companies run AI in production)
- **How to get there:**
  1. A DevOps foundation (1-2 years of experience)
  2. Add the LLM-specific parts (cost, latency, evals)
  3. An AWS/GCP AI/ML certification
- **Picture this:** a freight train engineer. The locomotive (the model) already exists; your job is to get the cargo there without a wreck.

---

#### 4. AI Agent Architect

- **What they do:** Design multi-agent systems. Decide who delegates to whom, how agents coordinate, and how orchestration works.
- **Key skills:**
  - Agent design patterns (orchestrator, supervisor, swarm)
  - LangGraph, Microsoft Agent Framework (the successor to AutoGen), Claude Agent SDK
  - State management between agents
  - Error propagation
  - Cost budgeting at the agent level
  - Tool design (when to give the model a function call vs build it into the prompt)
- **Demand:** ⭐⭐⭐⭐⭐ (a top-3 emerging role)
- **How to get there:**
  1. A senior engineer foundation
  2. Build 2-3 agent systems in production
  3. Speak at an AI Engineer conference (the World's Fair, the Code Summit)
- **Picture this:** an orchestra conductor. Each agent is a musician. The conductor doesn't play, but without one you get noise.

---

#### 5. RAG Pipeline Engineer

- **What they do:** Build retrieval-augmented generation (RAG) systems, which let a model answer from a company's own documents. They connect private data → embeddings → vector DB → LLM.
- **Key skills:**
  - Embeddings (OpenAI, Voyage, Cohere)
  - Vector databases
  - Chunking strategies
  - Re-ranking
  - Hybrid search (semantic + keyword)
  - Evaluating RAG quality
- **Demand:** ⭐⭐⭐⭐ (enterprise adoption is very high)
- **How to get there:**
  1. Learn one vector DB in depth
  2. Build RAG for 3 different domains
  3. Publish a comparison of chunking strategies
- **Picture this:** a librarian who's also an interpreter. Finds the right book and translates it into the customer's language.

---

#### 6. AI Integration Engineer

- **What they do:** Bring AI into existing enterprise systems (Salesforce, SAP, ERP, CRM).
- **Key skills:**
  - Enterprise integration patterns
  - REST/GraphQL APIs
  - SSO, auth, compliance
  - Change management
  - AI vendor evaluation
- **Demand:** ⭐⭐⭐⭐ (the corporate AI adoption wave)
- **How to get there:**
  1. A backend engineer foundation
  2. Experience with enterprise software
  3. An AI/LLM certification
- **Picture this:** a plumber running new pipes (AI) through an old house (enterprise software).

---

#### 7. AI Quality Engineer (Eval Engineer)

- **What they do:** Design evals (systematic tests) for LLM applications. Shipping without evals is like flying without instruments.
- **Key skills:**
  - Eval frameworks (LangSmith, Braintrust)
  - LLM-as-judge patterns
  - Golden dataset curation
  - Regression testing for prompts
  - Cost-quality tradeoffs
  - Statistical significance in LLM testing
- **Demand:** ⭐⭐⭐⭐⭐ (one of the industry's biggest gaps)
- **How to get there:**
  1. A QA engineer foundation
  2. Study LLM behavior in depth
  3. Publish an eval methodology
- **Picture this:** a wine taster. Doesn't make the wine, but without them the winery doesn't know what to improve.

---

#### 8. Multi-Agent Orchestrator

- **What they do:** A specialized AI Agent Architect, focused on coordinating 5-50 agents at once.
- **Key skills:**
  - Distributed systems
  - Event-driven architecture
  - Agent communication protocols
  - Deadlock detection
  - Cost optimization across agents
- **Demand:** ⭐⭐⭐⭐ (a hot niche inside Agent Architect)
- **How to get there:**
  1. Agent Architect → specialize in orchestration
- **Picture this:** an air traffic controller. 50 planes in the air, and none of them can collide.

---

#### 9. AI Security Engineer

- **What they do:** Protect LLM applications from prompt injection, jailbreaks and data leakage.
- **Key skills:**
  - Prompt injection patterns
  - Output filtering
  - Tool use guardrails
  - PII detection (personally identifiable information)
  - Adversarial testing
  - OWASP Top 10 for LLMs
- **Demand:** ⭐⭐⭐⭐⭐ (regulated industries: banking, healthcare)
- **How to get there:**
  1. A security engineer foundation
  2. Learn the LLM attack surface
  3. CTF in AI security competitions
- **Picture this:** a Secret Service agent. Knows every angle a threat could come from.

---

#### 10. AI Cost Optimization Engineer

- **What they do:** Cut the LLM bill through model routing, caching and prompt compression.
- **Key skills:**
  - Model tiering (picking the model for the task: Haiku / Sonnet / Opus / Fable; check prices on the [What's current](https://aimayak.com/en/now/) page)
  - Prompt caching (with Anthropic, reading from the cache costs a small fraction of the regular input price, while writing to the cache costs extra; current rates are on the [What's current](https://aimayak.com/en/now/) page)
  - Batch API: a 50% discount for asynchronous processing
  - Semantic caching
  - Request batching
  - Token-level analytics (newer models may count the same text as a different number of tokens, so measure on your own data)
  - Cost dashboards
- **Demand:** ⭐⭐⭐⭐ (grows once a company's LLM bill becomes a real budget line)
- **How to get there:**
  1. An engineer with a business mindset
  2. Publish a case study of saving \$X
- **Picture this:** a home energy auditor. The house is lit and running, but it burns twice the electricity it needs.

---

#### 11. Vector Database Engineer

- **What they do:** A vector database specialist. Sharding, performance, hybrid search.
- **Key skills:**
  - Pinecone, Weaviate, Qdrant, Milvus in depth
  - HNSW, IVF algorithms
  - Embedding model selection
  - Cost-performance tradeoffs
- **Demand:** ⭐⭐⭐ (specialized, a smaller market)
- **How to get there:**
  1. A database engineer foundation
  2. Specialize in one vector DB
- **Picture this:** an archivist with a photographic memory. Knows where a million documents are and pulls any one in a millisecond.

---

#### 12. AI Pipeline Architect

- **What they do:** Design end-to-end ML/AI pipelines (data → training → deployment → monitoring).
- **Key skills:**
  - MLOps platforms (MLflow, SageMaker, Google Cloud's Gemini Enterprise Agent Platform, formerly Vertex AI)
  - Data engineering
  - Model versioning
  - CI/CD for models
  - Feature stores
- **Demand:** ⭐⭐⭐⭐ (steadily high)
- **How to get there:**
  1. 2-3 years as an ML engineer
  2. Architect-level system design
- **Picture this:** the chief engineer of a factory. Every assembly line (data flow) runs back to them.

---

#### 13. Fine-tuning Specialist

- **What they do:** Further train foundation models on private data. RLHF, DPO, LoRA.
- **Key skills:**
  - PyTorch, Hugging Face
  - Training infrastructure (GPU clusters)
  - Dataset curation
  - Evaluation methodology
  - Cost (training models can be very expensive)
- **Demand:** ⭐⭐⭐ (shrinking as foundation models improve, but the specialty is alive)
- **How to get there:**
  1. An ML research background
  2. Hands-on experience training models
- **Picture this:** a national team coach. The raw talent (the foundation model) is already there; your job is to bring it up to Olympic level.

---

#### 14. Custom Model Engineer

- **What they do:** Build specialized models from scratch (when foundation models don't fit).
- **Key skills:**
  - Deep learning fundamentals
  - Transformer architecture in depth
  - Distributed training
  - Custom CUDA kernels (advanced level)
- **Demand:** ⭐⭐ (a narrow niche with a very high entry bar)
- **How to get there:**
  1. A PhD or equivalent research experience
  2. Published papers
- **Picture this:** a Swiss watchmaker. Makes what mass production can't.

---

#### 15. AI Infrastructure Engineer (vLLM/SGLang specialist)

- **What they do:** Inference infrastructure. Make models faster and cheaper to run on GPU clusters.
- **Key skills:**
  - vLLM and SGLang in depth
  - CUDA basics
  - GPU memory optimization
  - Batching strategies
  - KV cache optimization
- **Demand:** ⭐⭐⭐⭐ (very high at frontier labs)
- **How to get there:**
  1. A systems engineer foundation
  2. Contribute to an open-source inference engine
- **Picture this:** a race car tuner. The same car runs 20% faster.

---

### A2. AI Content / Creative (10 careers)

---

#### 16. AI Content Producer

- **What they do:** Create content (text, video, audio) with AI as the main tool. Not an editing assistant: the primary producer.
- **Key skills:**
  - Claude/GPT for long-form
  - Midjourney/gpt-image-2/Flux for images
  - Suno for music
  - Runway/Kling for video
  - Brand voice consistency
  - Multi-platform repurposing
- **Demand:** ⭐⭐⭐⭐ (easy to get into, but the senior bar is high)
- **How to get there:**
  1. Learn 3-4 AI content tools in depth
  2. Build a portfolio (channels with real reach)
  3. Specialize in a niche (B2B SaaS, e-commerce, etc.)
- **Picture this:** a chef cooking with store-bought ingredients. The skill isn't in growing the carrots; it's in how you combine them.

---

#### 17. AI Music Composer (Suno specialist)

- **What they do:** Generate music with AI tools for commercial use (jingles, ambient, soundtracks).
- **Key skills:**
  - Suno (current model versions: see [What's current](https://aimayak.com/en/now/)) and similar generators, with in-depth prompting
  - Music theory basics (to guide the AI)
  - Audio editing (Logic, Ableton for post-production)
  - Copyright awareness
- **Demand:** ⭐⭐⭐ (growing, but the rules keep changing: Udio, for example, turned off track downloads after its 2025 deal with Universal Music)
- **How to get there:**
  1. Learn Suno and one more music generator
  2. A music theory crash course
  3. Before you sell, read the license of your plan and the rules of the marketplace: stock libraries such as Pond5 and AudioJungle don't accept AI-generated tracks
- **Picture this:** a sculptor. The clay (the AI output) is the material. The shape (your taste) is the art.

---

#### 18. AI Video Producer (Runway/Kling)

- **What they do:** Create video with AI (Runway, Kling and other video models). Marketing, ads, short films.
- **Key skills:**
  - Prompting video models (Runway, Kling and others)
  - Storyboarding
  - Post-production (DaVinci Resolve)
  - Cinematography basics
- **Demand:** ⭐⭐⭐⭐ (growing fast in 2026)
- **How to get there:**
  1. Master 2 AI video tools
  2. Build 10 portfolio pieces
  3. Find a niche (real estate, fashion, tech)
- **Picture this:** a one-person short-film director. What used to take a crew of 20, you now do yourself.

---

#### 19. AI Voice Director (ElevenLabs)

- **What they do:** Produce voice content with AI voice cloning (audiobooks, podcasts, character voices, dubbing).
- **Key skills:**
  - ElevenLabs in depth
  - The ethics and law of voice cloning
  - Multi-language production
  - Audio editing
- **Demand:** ⭐⭐⭐⭐ (especially for multilingual content)
- **How to get there:**
  1. Master ElevenLabs Pro
  2. Build a voice library (with consent)
  3. Audiobook production projects
- **Picture this:** a dubbing director. Casts voices for each character, except now the voices are virtual.

---

#### 20. AI Game Designer (procedural worlds)

- **What they do:** Use AI to generate game worlds, NPC dialogue and level design.
- **Key skills:**
  - Unity/Unreal with AI integration
  - LLMs for dynamic dialogue
  - Procedural generation
  - Game design fundamentals
- **Demand:** ⭐⭐⭐ (a specialized niche)
- **How to get there:**
  1. A game dev foundation
  2. AI integration projects
- **Picture this:** the architect of an endless city. Every house is different, but the style is recognizable.

---

#### 21. AI Animator

- **What they do:** Create animation with AI (Runway, Kaiber, animation-specific tools).
- **Key skills:**
  - AI animation tools in depth
  - Traditional animation principles (timing, weight)
  - After Effects integration
- **Demand:** ⭐⭐⭐ (specialized)
- **Picture this:** a puppeteer who doesn't pull the strings but describes what the puppets should do.

---

#### 22. AI Photographer / Image Director

- **What they do:** Create commercial photography with Midjourney/Flux/gpt-image-2. Product shots, lifestyle, fashion.
- **Key skills:**
  - Midjourney and Flux (current versions) in depth
  - Photography fundamentals (composition, lighting)
  - Brand consistency through style references
  - Post-processing (Lightroom)
- **Demand:** ⭐⭐⭐⭐ (massive e-commerce demand)
- **Picture this:** a photographer without a camera. The same eye, a different tool.

---

#### 23. AI Comic / Manga Creator

- **What they do:** Produce comics/manga with AI. A niche, mostly in self-publishing.
- **Key skills:**
  - Character consistency (LoRA training)
  - Panel layout
  - Storytelling
- **Demand:** ⭐⭐ (growing, but a small niche)
- **Picture this:** a solo comic artist who used to finish one volume a year and now finishes six.

---

#### 24. AI Narrative Designer

- **What they do:** Design branching narratives for interactive fiction, games and training simulations.
- **Key skills:**
  - Twine, Ink scripting
  - Dynamic generation with LLMs
  - Narrative structure
- **Demand:** ⭐⭐⭐ (the games and training markets)
- **Picture this:** the writer of a TV series with a million episodes, where every viewer watches their own.

---

#### 25. AI Brand Voice Architect

- **What they do:** Create and maintain a consistent brand voice across AI workflows. Style guides, brand fine-tunes, voice evals.
- **Key skills:**
  - Brand strategy fundamentals
  - LLM customization (system prompts, fine-tuning)
  - Voice eval methodology
- **Demand:** ⭐⭐⭐⭐ (companies are realizing AI wrecks a brand voice if nobody sets it up)
- **Picture this:** the program director of a radio station. Every host has their own voice; the job is to keep the station's overall tone.

---

### A3. AI Business / Strategy (10 careers)

---

#### 26. AI Strategy Consultant

- **What they do:** Help companies design an AI roadmap. Not implementation: strategy, as in "where to put the AI dollars".
- **Key skills:**
  - Business strategy fundamentals
  - The AI landscape (vendors, capabilities, limits)
  - ROI modeling
  - Change management
  - Executive communication
- **Demand:** ⭐⭐⭐⭐⭐ (many companies are looking for guidance)
- **How to get there:**
  1. A consulting background OR an AI engineering background
  2. 5+ years of business experience
  3. Build 3 case studies
- **Picture this:** a ship's captain who knows where the icebergs are. Doesn't run the engine; knows the course.

---

#### 27. AI Product Manager (AI-PM)

- **What they do:** A product manager who specializes in AI products. Understands what LLMs can and can't do; runs an eval-driven roadmap.
- **Key skills:**
  - Classic PM skills
  - LLM capabilities + limits
  - Eval-driven product development
  - Cost-aware feature prioritization
  - User research for AI features
- **Demand:** ⭐⭐⭐⭐⭐ (a top-5 emerging role)
- **How to get there:**
  1. A PM foundation of 3+ years
  2. Ship an AI feature to production
  3. Speak at AI Engineering / Product conferences
- **Picture this:** conducting an orchestra where half the musicians are robots. You know what a robot can and can't do on the violin.

---

#### 28. AI Transformation Lead

- **What they do:** Lead the AI transformation at a large company. Org change + technology + culture.
- **Key skills:**
  - Executive leadership
  - Org design
  - Change management
  - AI literacy
  - P&L responsibility
- **Demand:** ⭐⭐⭐⭐ (large companies are creating these roles)
- **Picture this:** a general reforming the army in the middle of a war.

---

#### 29. AI Adoption Specialist

- **What they do:** Help mid-size companies (50-500 employees) put AI workflows in place. Hands-on, not a strategy deck.
- **Key skills:**
  - Practical mastery of AI tools (10+ tools)
  - Delivering training
  - Workflow design
  - Stakeholder management
- **Demand:** ⭐⭐⭐⭐⭐ (mid-size companies are where most of this work is)
- **Picture this:** a driving instructor for people who've only ever been passengers.

---

#### 30. AI Ethics Officer

- **What they do:** Make sure AI is deployed responsibly. Bias audits, transparency, fairness.
- **Key skills:**
  - AI ethics frameworks (NIST, EU AI Act)
  - Bias detection methodology
  - Stakeholder engagement
  - Legal awareness
- **Demand:** ⭐⭐⭐ (regulated industries, companies operating in the EU)
- **Picture this:** a referee. Doesn't play the game; enforces the rules.

---

#### 31. AI Compliance Officer

- **What they do:** The EU AI Act, US executive orders, ISO 42001. AI regulation.
- **Key skills:**
  - The AI regulation landscape
  - Compliance frameworks
  - Rigorous documentation
  - Audit preparation
- **Demand:** ⭐⭐⭐⭐ (the EU AI Act takes effect in stages through 2028)
- **Picture this:** an IRS auditor for AI. Boring, but necessary.

---

#### 32. AI ROI Analyst

- **What they do:** Calculate the real ROI of AI initiatives. Cost vs productivity gain vs revenue impact.
- **Key skills:**
  - Financial modeling
  - AI cost structures
  - Productivity metrics
  - A/B testing
- **Demand:** ⭐⭐⭐ (the CFO's office)
- **Picture this:** an accountant with special clearance. Counts not only the numbers but the "magic" too.

---

#### 33. AI Procurement Specialist

- **What they do:** Buy AI tools and services for large companies. Vendor evaluation, contract negotiation.
- **Key skills:**
  - Procurement fundamentals
  - The AI vendor landscape
  - Contract negotiation
  - Total cost of ownership
- **Demand:** ⭐⭐⭐ (steady)
- **Picture this:** a shopaholic with a CFO's mindset. Buys a lot, but on purpose.

---

#### 34. AI Vendor Manager

- **What they do:** Manage relationships with AI vendors (Anthropic, OpenAI, vector DB providers).
- **Key skills:**
  - Vendor management
  - SLA monitoring
  - Multi-vendor strategy
  - Cost optimization
- **Demand:** ⭐⭐⭐
- **Picture this:** a diplomat who knows whom to talk to and about what.

---

#### 35. AI Risk Officer

- **What they do:** Identify and reduce AI risks (technical, business, regulatory, reputational).
- **Key skills:**
  - Risk frameworks
  - AI-specific risk categories (hallucination, meaning AI confidently making things up; bias; drift)
  - Crisis communication
- **Demand:** ⭐⭐⭐⭐ (banking, healthcare, insurance)
- **Picture this:** a weather forecaster for the business. Predicts the storm before the ship leaves port.

---

### A4. AI Operations (8 careers)

---

#### 36. AI Trainer (RLHF specialist)

- **What they do:** Rank AI outputs and give feedback for RLHF training (reinforcement learning from human feedback). Human-in-the-loop work.
- **Key skills:**
  - Domain expertise (in a specific field)
  - Critical thinking
  - A consistent rating method
- **Demand:** ⭐⭐⭐⭐ (AI labs and their contractors hire for this work)
- **Picture this:** a teacher grading an endless series of exams.

---

#### 37. AI Auditor (independent verification)

- **What they do:** Independently audit AI systems for compliance, fairness and performance.
- **Key skills:**
  - Audit methodology
  - AI evaluation
  - Rigorous reporting
- **Demand:** ⭐⭐⭐ (the EU AI Act is creating this market)
- **Picture this:** a Big Four financial auditor, only for AI.

---

#### 38. AI Red Team Specialist

- **What they do:** Try to break AI systems. Adversarial testing, jailbreaks, edge cases.
- **Key skills:**
  - Creative attack design
  - A security mindset
  - Documentation
  - Red-teaming methods published by AI labs
- **Demand:** ⭐⭐⭐⭐⭐ (frontier labs keep dedicated red teams)
- **Picture this:** a professional bank burglar who gets paid to find the holes.

---

#### 39. AI Behavior Researcher

- **What they do:** Study how AI behaves in edge cases. Close to alignment research.
- **Key skills:**
  - Research methodology
  - Statistical analysis
  - Understanding LLM internals
- **Demand:** ⭐⭐⭐ (a narrow niche)
- **Picture this:** a zoologist studying a new species. Only the species is AI, and we created it without fully understanding it.

---

#### 40. Synthetic Data Engineer

- **What they do:** Generate synthetic training data. Critical for fields where real data is rare or private.
- **Key skills:**
  - Data generation techniques
  - Quality validation
  - Privacy-preserving methods
- **Demand:** ⭐⭐⭐⭐ (healthcare, finance, robotics)
- **Picture this:** a useful kind of liar. Creates data that looks real.

---

#### 41. AI Knowledge Curator

- **What they do:** Curate knowledge bases for RAG systems. An editorial role for the AI age.
- **Key skills:**
  - Information architecture
  - Editorial judgment
  - Search optimization
  - Domain expertise
- **Demand:** ⭐⭐⭐ (enterprise RAG adoption)
- **Picture this:** the editor-in-chief of a library that helps AI find the truth.

---

#### 42. AI Workflow Designer

- **What they do:** Design human-AI workflows. Where AI does the work, where a human approves, how the handoff works.
- **Key skills:**
  - Process design
  - UX principles
  - Knowing what AI can do
- **Demand:** ⭐⭐⭐⭐
- **Picture this:** a choreographer for a dance between a person and a robot.

---

#### 43. Human-AI Interface Designer

- **What they do:** UX/UI for AI-augmented interfaces. Streaming responses, citations, confidence indicators.
- **Key skills:**
  - UX design fundamentals
  - AI interaction patterns
  - Information design
- **Demand:** ⭐⭐⭐⭐ (growing fast)
- **Picture this:** the architect of a bridge between a person and a robot.

---

### A5. AI Specialized (7 careers)

---

#### 44. AI Voice Agent Developer (Vapi/Bland.ai)

- **What they do:** Build AI agents that make and take phone calls for sales, support and scheduling.
- **Key skills:**
  - Vapi, Bland.ai, Retell in depth
  - Voice UX design
  - Telephony integration (Twilio)
  - Real-time latency optimization
- **Demand:** ⭐⭐⭐⭐⭐ (a top-5 emerging role in 2026)
- **Picture this:** a puppeteer who makes a robot sound like a person on the phone.

---

#### 45. Computer Use Operator

- **What they do:** Build AI workflows that operate a desktop or browser (Anthropic's computer use, OpenAI's agent features in ChatGPT).
- **Key skills:**
  - The Computer Use API
  - Browser automation
  - Identifying UI elements
  - Error recovery
- **Demand:** ⭐⭐⭐⭐ (a new category in 2025-2026)
- **Picture this:** a marionettist moving the agent's hands across the keyboard.

---

#### 46. Local AI Deployment Engineer

- **What they do:** Deploy AI locally (for privacy, cost or latency reasons). Ollama, llama.cpp, on-device.
- **Key skills:**
  - Open-weights models (Llama, Mistral, Qwen)
  - Quantization
  - Local inference engines
  - Edge deployment
- **Demand:** ⭐⭐⭐ (privacy-sensitive sectors)
- **Picture this:** someone building an off-grid cabin in the woods: everything is their own, nothing is connected to the grid.

---

#### 47. AI Therapy Researcher (companion AI ethics)

- **What they do:** Research and design ethical AI companions and therapy tools. The aftermath of Replika and Character.ai.
- **Key skills:**
  - A psychology background
  - Ethics
  - AI interaction design
  - User safety
- **Demand:** ⭐⭐⭐ (growing after public concerns)
- **Picture this:** a new kind of psychologist who studies not patients but the relationships between people and AI.

---

#### 48. Robotics + AI Integration Engineer

- **What they do:** Connect LLMs to physical robots. The Figure, 1X and Tesla Optimus ecosystem.
- **Key skills:**
  - Robotics fundamentals
  - LLMs for planning
  - Sensor fusion
  - Real-time control
- **Demand:** ⭐⭐⭐⭐ (the humanoid robotics wave)
- **Picture this:** the person who teaches robots to think before they take a step.

---

#### 49. Smart Glasses App Developer (Ray-Ban Meta, Apple Vision Pro)

- **What they do:** Apps for AR glasses and headsets with AI assistants (Ray-Ban Meta, Apple Vision Pro).
- **Key skills:**
  - AR SDKs (Meta, Apple)
  - LLM integration
  - Voice UX
  - Always-on AI patterns
- **Demand:** ⭐⭐⭐ (an early market that could take off in 2027+)
- **Picture this:** an iPhone app developer in 2008. The platform is young, and nobody knows yet which apps will matter.

---

#### 50. AI Accessibility Specialist

- **What they do:** Use AI to make technology accessible to people with disabilities. Image descriptions, voice control, cognitive aids.
- **Key skills:**
  - WCAG and accessibility standards
  - AI tools for visual, audio and cognitive support
  - User research with disability communities
- **Demand:** ⭐⭐⭐⭐ (regulatory and ethical pressure)
- **Picture this:** the person who builds wheelchair ramps in the digital world. Makes the invisible visible and the unheard heard.

---

## <a id="section-b"></a>🌳 Section B: 50 HYBRID careers

An existing job + AI = a new version of it. Not "AI replaces", but "AI augments".

---

### B1. Knowledge Work (15 hybrids)

---

#### 51. Lawyer + AI = AI-Augmented Lawyer

- **What changes:** AI does research, drafts contracts and summarizes case law. A large share of the routine goes away.
- **Where the human stays:** Strategy, client relationships, court appearances, judgment calls, negotiation. Legal advice and the license stay with the attorney.
- **AI tools:** Harvey, CoCounsel, Lexis+ with Protégé (formerly Lexis+ AI), custom Claude workflows

---

#### 52. Doctor + AI = AI-Assisted Physician

- **What changes:** AI helps with diagnostics (radiology, pathology), drafts notes and suggests treatment options.
- **Where the human stays:** Patient interaction, judgment calls, procedures, ethical decisions. The diagnosis and the treatment decision stay with the licensed physician.
- **AI tools:** Abridge, Microsoft Dragon Copilot (it absorbed Nuance DAX), AI radiology tools (Aidoc), specialty-specific tools

---

#### 53. Accountant + AI = AI-Enabled Accountant

- **What changes:** Bookkeeping is automated. Audits are semi-automated. Forecasting gets better.
- **Where the human stays:** Strategy, tax planning, client advisory work, complex judgment.
- **AI tools:** Vic.ai, MindBridge, custom AI workflows

---

#### 54. Teacher + AI = AI-Augmented Educator

- **What changes:** Personalized lesson plans, automated grading, an AI tutor for every student.
- **Where the human stays:** Motivation, social-emotional learning, mentoring, classroom management.
- **AI tools:** Khanmigo, MagicSchool, custom Claude workflows

---

#### 55. Translator + AI = AI Translation Specialist

- **What changes:** Basic translation is fully handled by AI. The translator now post-edits and handles nuance.
- **Where the human stays:** Cultural nuance, marketing copy, critical legal/medical work, literary translation.
- **AI tools:** DeepL, GPT/Claude, custom translation memories

---

#### 56. Researcher + AI = AI-Powered Researcher

- **What changes:** A literature review takes hours instead of months. Data analysis is faster.
- **Where the human stays:** Hypothesis design, original insights, peer review judgment.
- **AI tools:** Elicit, Consensus, Perplexity Pro, Claude with web search

---

#### 57. Journalist + AI = AI-Augmented Reporter

- **What changes:** Research, transcription and first drafts are AI-assisted.
- **Where the human stays:** Source relationships, investigative work, editorial judgment, on-the-ground reporting.
- **AI tools:** Otter.ai (transcription), Claude/GPT (drafts), Perplexity (research)

---

#### 58. Therapist + AI = Hybrid Mental Health Practitioner

- **What changes:** Note-taking is automated. AI check-ins between sessions. Pattern detection.
- **Where the human stays:** The therapeutic alliance (the core of the work), crisis intervention, complex cases. Therapy itself stays with the licensed clinician.
- **AI tools:** Eleos Health, Lyssn, custom Claude workflows

---

#### 59. Architect + AI = Generative Design Architect

- **What changes:** Generative design produces 100 options. Permit and code-compliance checks are automated.
- **Where the human stays:** The client's vision, site context, aesthetic judgment, construction oversight.
- **AI tools:** Autodesk Forma (formerly Spacemaker), custom diffusion models

---

#### 60. Engineer + AI = AI-Assisted Engineer

- **What changes:** Coding gets noticeably faster (Claude Code, Copilot, Cursor). Debugging is faster.
- **Where the human stays:** Architecture, system design, judgment calls, mentoring.
- **AI tools:** Claude Code, Cursor, Copilot, domain-specific tools

---

#### 61. Project Manager + AI = AI-PM Hybrid

- **What changes:** Status reports are generated automatically. Risk detection is AI-assisted. Resource planning gets smarter.
- **Where the human stays:** Stakeholder management, judgment calls, motivation, escalation.
- **AI tools:** Asana AI, ClickUp AI, custom Claude workflows

---

#### 62. Recruiter + AI = AI-Augmented Recruiter

- **What changes:** Sourcing is automated. AI does the first screening. Matching gets smarter.
- **Where the human stays:** Building relationships, closing candidates, assessing culture fit.
- **AI tools:** Eightfold, Paradox (now part of Workday), custom workflows

---

#### 63. Consultant + AI = AI-Native Consultant

- **What changes:** Research, analysis and deck production are AI-assisted. The same deliverable in a third of the time.
- **Where the human stays:** Client relationships, executive presence, judgment, strategy.
- **AI tools:** Claude/GPT for analysis, Gamma for decks, custom tools

---

#### 64. Coach + AI = AI-Powered Coach

- **What changes:** AI check-ins between sessions. Goal tracking is automated. Pattern detection.
- **Where the human stays:** Accountability, deep listening, breakthrough moments.
- **AI tools:** Coachvox, custom Claude workflows

---

#### 65. Financial Advisor + AI = AI-Augmented Advisor

- **What changes:** Portfolio analysis is automated. Rebalancing suggestions. AI-driven tax-loss harvesting.
- **Where the human stays:** Trust, behavioral coaching, complex planning, the relationship. Personal financial advice stays with the licensed advisor.
- **AI tools:** Wealthbox AI, custom robo-advisor integration

---

### B2. Creative Work (10 hybrids)

---

#### 66. Designer + AI = AI-Native Designer

- **What changes:** Mockups, variations and A/B options are AI-generated. The same role with 5 to 10 times the output.
- **Where the human stays:** Brand strategy, taste, user research, judgment.
- **AI tools:** Figma AI, Google Stitch, Midjourney, Claude for copy

---

#### 67. Copywriter + AI = AI-Augmented Writer

- **What changes:** AI writes the first drafts. AI handles bulk content. AI generates headline variants.
- **Where the human stays:** Voice, strategy, editing, hooks, taste.
- **AI tools:** Claude, GPT, Jasper

---

#### 68. Photographer + AI = AI-Hybrid Photographer

- **What changes:** Post-processing is 10 times faster. AI fills in crowds in landscape shots. Product shots come from AI generation.
- **Where the human stays:** Vision, on-location work, client relationships, the key moments.
- **AI tools:** Lightroom AI, Topaz, Midjourney for composites

---

#### 69. Filmmaker + AI = AI-Enabled Director

- **What changes:** VFX gets cheaper. B-roll is generated. Editing is assisted. Localization is automated.
- **Where the human stays:** Vision, casting, directing performances, story.
- **AI tools:** Runway, Kling, AI editing tools

---

#### 70. Musician + AI = AI-Collaborative Musician

- **What changes:** AI assists with composition. Stem generation. Mixing is automated.
- **Where the human stays:** Performance, emotion, originality, personal brand.
- **AI tools:** Suno, Udio, Mubert, AI mixing

---

#### 71. Actor + AI = AI-Voice Talent / Digital Performer

- **What changes:** Licensing a cloned voice. Digital doubles. International dubs without re-recording.
- **Where the human stays:** Live performance, on-camera work, real emotional range.
- **AI tools:** ElevenLabs licensing, digital double services
- **Note:** Since 2023, SAG-AFTRA's union contracts have included rules on the use of AI

---

#### 72. Illustrator + AI = AI-Hybrid Illustrator

- **What changes:** Background generation. Color variations. Early concepts are AI-assisted.
- **Where the human stays:** Style, character design, storytelling, polish.
- **AI tools:** Midjourney, Krea, custom LoRAs

---

#### 73. Animator + AI = AI-Powered Animator

- **What changes:** In-betweens are automated. AI lip sync. Background animation is generated.
- **Where the human stays:** Key poses, performance, story timing.
- **AI tools:** Cascadeur, Toon Boom, Runway

---

#### 74. Video Editor + AI = AI-Enhanced Editor

- **What changes:** The rough cut is automated. Instant subtitles. Automatic reframing for vertical video.
- **Where the human stays:** Story rhythm, emotional pacing, final polish.
- **AI tools:** Descript, Adobe AI, CapCut AI

---

#### 75. Production Designer + AI = Virtual Production Designer

- **What changes:** AI concept art. Exploring set designs with AI. Virtual location scouting.
- **Where the human stays:** Physical builds, on-set decisions, the client's vision.
- **AI tools:** Midjourney, Unreal Engine + AI plugins

---

### B3. Business / Sales (10 hybrids)

---

#### 76. Salesperson + AI = AI-Enabled SDR

- **What changes:** Prospecting is automated. AI drafts the emails. Call summaries are instant.
- **Where the human stays:** Closing, complex deals, relationships, judgment.
- **AI tools:** Apollo AI, Clay, Outreach AI, Gong

---

#### 77. Marketer + AI = AI-Native Marketer

- **What changes:** 5x the content production. A/B testing is automated. Personalization at scale.
- **Where the human stays:** Strategy, brand, creative direction, choosing channels.
- **AI tools:** Adobe AI, Jasper, Claude/GPT, HubSpot AI

---

#### 78. Customer Support + AI = Hybrid Support Specialist

- **What changes:** Tier 1 is fully handled by AI. Tier 2 is AI-assisted. Sentiment detection is automated.
- **Where the human stays:** Complex issues, moments that need empathy, escalations.
- **AI tools:** Intercom Fin, Zendesk AI, Ada
- **Note:** Headcount goes down, but senior roles remain

---

#### 79. HR Manager + AI = AI-Augmented HR Lead

- **What changes:** Recruiting is automated. AI personalizes onboarding. Performance trends get flagged.
- **Where the human stays:** Conflict resolution, culture, sensitive conversations.
- **AI tools:** Workday AI, BambooHR AI, custom tools

---

#### 80. Operations Manager + AI = AI-Powered Ops Manager

- **What changes:** AI monitors processes. Anomaly detection. Optimization suggestions.
- **Where the human stays:** Cross-functional coordination, judgment, change management.
- **AI tools:** Process mining tools + AI, custom tools

---

#### 81. Account Manager + AI = AI-Enabled CSM

- **What changes:** Churn risk detection. Renewal prep is automated. Account research is instant.
- **Where the human stays:** Relationships, strategic conversations, escalations.
- **AI tools:** Gainsight AI, Catalyst, custom tools

---

#### 82. Business Analyst + AI = AI-Augmented Analyst

- **What changes:** SQL queries in plain English. Report generation. Insight detection.
- **Where the human stays:** Asking the right questions, business context, stakeholder management.
- **AI tools:** Hex (with its built-in AI agent), Claude data analysis

---

#### 83. Product Marketer + AI = AI-Native PMM

- **What changes:** Competitive intel is automated. AI writes launch content. Deeper persona research.
- **Where the human stays:** Positioning, messaging, go-to-market strategy.
- **AI tools:** Claude/GPT, Crayon, custom tools

---

#### 84. Brand Manager + AI = AI-Hybrid Brand Strategist

- **What changes:** Brand monitoring is automated. Content production scales. Real-time sentiment analysis.
- **Where the human stays:** Brand vision, key creative decisions, partnerships.
- **AI tools:** Brandwatch + AI, custom tools

---

#### 85. Real Estate Agent + AI = AI-Augmented Realtor

- **What changes:** AI writes listing descriptions. Lead qualification is automated. AI-enhanced virtual tours.
- **Where the human stays:** Negotiation, local knowledge, trust, getting to closing.
- **AI tools:** Restb.ai, AI listing tools, custom tools

---

### B4. Trades + Services (10 hybrids)

---

#### 86. Chef + AI = AI-Hybrid Chef

- **What changes:** AI-assisted menu design. Nutrition optimization. Inventory forecasts.
- **Where the human stays:** Cooking, taste, creativity, running the kitchen.
- **AI tools:** Custom Claude workflows, AI features in restaurant software (ordering, inventory, point of sale)

---

#### 87. Personal Trainer + AI = AI-Coach Hybrid

- **What changes:** AI builds personalized programs. Form analysis from video. Progress tracking is automated.
- **Where the human stays:** Motivation, hands-on coaching, group dynamics.
- **AI tools:** Tonal, coaching apps such as Future, custom tools

---

#### 88. Nutritionist + AI = AI-Enabled Dietitian

- **What changes:** AI does meal planning. Tracking is automated. Pattern detection.
- **Where the human stays:** Behavior change, complex cases, accountability.
- **AI tools:** Lumen, custom tools

---

#### 89. Mechanic + AI = AI-Diagnostic Technician

- **What changes:** Diagnosis is 2x faster (AI reads the codes and the symptoms). Predictive maintenance.
- **Where the human stays:** The physical repair, customer trust, complex cases.
- **AI tools:** Bosch diagnostic software, custom dealer tools

---

#### 90. Electrician + AI = Smart Home Specialist

- **What changes:** AI-assisted smart home design. Energy optimization. Predictive maintenance.
- **Where the human stays:** Installation, troubleshooting, meeting electrical code.
- **AI tools:** Custom integration platforms

---

#### 91. Plumber + AI = IoT-Enabled Plumbing Specialist

- **What changes:** Leak detection with IoT sensors + AI. Smarter system diagnostics. AI-generated quotes.
- **Where the human stays:** The physical work, emergency calls.
- **AI tools:** Moen Flo, smart plumbing platforms

---

#### 92. Tailor + AI = AI-Pattern Designer

- **What changes:** AI pattern generation. Fit prediction. Automated 3D body scans.
- **Where the human stays:** Construction, fittings, fine handwork.
- **AI tools:** Browzwear, Clo3D + AI plugins

---

#### 93. Carpenter + AI = Parametric Furniture Designer

- **What changes:** Exploring designs with AI. Material optimization. CNC planning is automated.
- **Where the human stays:** Craftsmanship, finishing, complex builds.
- **AI tools:** Autodesk Fusion, Rhino + Grasshopper

---

#### 94. Florist + AI = AI-Augmented Floral Designer

- **What changes:** Order automation. Design suggestions. Inventory forecasts.
- **Where the human stays:** The craft of arranging, client events, taste.
- **AI tools:** Flower shop software, custom tools

---

#### 95. Hairstylist + AI = AI Style Consultant

- **What changes:** AI style previews. Color matching. Client preferences are tracked.
- **Where the human stays:** The craft of cutting and coloring, client relationships.
- **AI tools:** Modiface, custom apps

---

### B5. Education + Wellness (5 hybrids)

---

#### 96. University Professor + AI = AI-Augmented Academic

- **What changes:** AI handles the research literature review. AI-assisted grading. Faster lecture prep.
- **Where the human stays:** Mentoring, original research, judgment.
- **AI tools:** Elicit, Consensus, Claude

---

#### 97. Personal Tutor + AI = AI-Enabled Tutor (Khanmigo-style)

- **What changes:** AI-personalized practice. AI concept explanations. Progress tracking.
- **Where the human stays:** Motivation, test prep strategy, accountability.
- **AI tools:** Khanmigo, custom GPTs

---

#### 98. Yoga Instructor + AI = AI-Powered Wellness Coach

- **What changes:** Form analysis through a camera. AI-personalized sequences.
- **Where the human stays:** Energy, presence, hands-on adjustments.
- **AI tools:** Smart yoga mats and pose-tracking apps, custom tools

---

#### 99. Childcare + AI = AI-Augmented Parent Coach

- **What changes:** AI tracks child development. Activity suggestions. Q&A around the clock.
- **Where the human stays:** Physical care, attachment, judgment.
- **AI tools:** Custom apps

---

#### 100. Eldercare + AI = AI-Assisted Caregiver

- **What changes:** AI monitoring. Medication reminders. Fall detection. AI companionship (controversial).
- **Where the human stays:** Physical care, emotional connection, judgment.
- **AI tools:** Care.coach, custom devices

---

## <a id="section-c"></a>🔥 Section C: What's disappearing (10 jobs at risk in 2026-2030)

An honest list. Not to scare you: to give you practical direction.

---

### 1. Entry-level basic translation

- **What AI replaces it with:** DeepL, GPT, Claude (quality on popular language pairs is already high)
- **What professionals can do:** Move to hybrid #55, AI Translation Specialist (post-editing + a specialty)
- **Timeline:** by the author's estimate, the pressure is strongest in 2026-2027

### 2. First-draft copywriting (commodity content)

- **What AI replaces it with:** Claude, GPT, Jasper (good enough for mass SEO content)
- **What to do:** Hybrid #67, AI-Augmented Writer (a strategy + editing role)
- **Timeline:** by the author's estimate, the pressure is strongest in 2026

### 3. Tier-1 customer support (chat-based)

- **What AI replaces it with:** Intercom Fin, Zendesk AI, Ada (they close a significant share of routine requests)
- **What to do:** Move to Tier 2/Tier 3 (sensitive cases, escalations)
- **Timeline:** by the author's estimate, the pressure is strongest in 2026-2027

### 4. Data entry

- **What AI replaces it with:** OCR + AI extraction (Hyperscience, custom workflows)
- **What to do:** Data quality specialist, AI workflow design
- **Timeline:** by the author's estimate, the pressure is strongest in 2026 (it's already shrinking fast)

### 5. Basic bookkeeping

- **What AI replaces it with:** Vic.ai, Botkeeper, QuickBooks AI
- **What to do:** Hybrid #53, AI-Enabled Accountant (advisory, strategy)
- **Timeline:** by the author's estimate, the pressure is strongest in 2027-2028

### 6. Routine legal research (entry-level paralegal)

- **What AI replaces it with:** Harvey, CoCounsel, Lexis+ with Protégé
- **What to do:** Move into AI training, prompt engineering for law firms, or a specialty
- **Timeline:** by the author's estimate, the pressure is strongest in 2027

### 7. Stock photography (commodity)

- **What AI replaces it with:** Midjourney, Flux, gpt-image-2 (cheap, good-enough images)
- **What to do:** Hybrid #68, AI-Hybrid Photographer (a specialty, events, exclusive content)
- **Timeline:** by the author's estimate, the pressure is strongest in 2026

### 8. Generic commercial voice-over

- **What AI replaces it with:** ElevenLabs, custom voices
- **What to do:** Career #19, AI Voice Director, or specialty acting (premium voices)
- **Timeline:** by the author's estimate, the pressure is strongest in 2026-2027

### 9. Basic graphic design (templates)

- **What AI replaces it with:** Canva AI, Figma AI, Midjourney
- **What to do:** Hybrid #66, AI-Native Designer (a strategy + brand role)
- **Timeline:** by the author's estimate, the pressure is strongest in 2027

### 10. Routine code (boilerplate)

- **What AI replaces it with:** Cursor, Copilot, Claude Code
- **What to do:** Hybrid #60, AI-Assisted Engineer (architecture + senior judgment)
- **Timeline:** by the author's estimate, the pressure is strongest in 2026 (the junior developer market has already changed)

---

## <a id="section-d"></a>💪 Section D: 25 skills for the future

Universal skills you'll need in **any** career in 2026-2030.

---

### Universal Top 10

1. **AI literacy**: knowing what AI can and can't do (it's probabilistic, it hallucinates, it can be biased)
2. **Prompt engineering / instruction design**: even non-tech roles know how to prompt
3. **Critical thinking**: AI can be wrong with total confidence; without critical thinking, that's a disaster
4. **Verification skills**: how to check AI output (fact-check, cite sources)
5. **Systems thinking**: seeing AI as one part of a workflow, not as magic
6. **Communication**: with AI, and with people **about** AI
7. **Continuous learning**: AI changes monthly; you can't learn it once and be done
8. **Domain expertise**: deeper and narrower = your moat against AI
9. **Ethics literacy**: understanding AI bias and privacy implications
10. **Adaptability**: careers will change more often

### Technical (10)

11. **Python basics**: even for non-engineers; you need it for integrations
12. **Git / version control**: a must-have for anyone working with code or AI configs
13. **Using APIs**: REST/GraphQL, reading API docs
14. **Data analysis fundamentals**: pandas basics, SQL queries
15. **SQL basics**: data is everywhere, and you often need to pull it yourself
16. **Comfort with the command line**: the terminal isn't scary
17. **Markdown / documentation**: documentation is the main artifact of the AI era
18. **Cloud basics**: at least a working awareness of Cloudflare/Vercel/AWS
19. **Security awareness**: secrets, authentication, basic threats
20. **Cost / budget thinking**: AI calls cost money, and someone has to do the math

### Soft (5)

21. **Sales / negotiation**: still very human; AI doesn't close deals
22. **Relationship building**: trust grows slowly, and AI can't speed it up
23. **Empathy**: AI imitates it but doesn't feel it
24. **Leading AI-augmented teams**: managing people + agents
25. **Storytelling**: facts used to be scarce; now the value is in context + story

---

## <a id="section-e"></a>🧭 Section E: Decision tree: which career to choose

```
START

Do I love technical / code work?
├─ Yes → AI Engineering / AI Application / LLMOps (A1)
│        → Sub-profile:
│           - Hardcore systems? → A1.15 Infrastructure
│           - Building apps? → A1.2 AI Application
│           - Multi-agent? → A1.4 Agent Architect
│           - Optimization? → A1.10 Cost Optimization
└─ No → continue

Am I a creative person?
├─ Yes → AI Content / Creative (A2)
│        → Sub-profile:
│           - Text? → A2.16 Content Producer
│           - Visual? → A2.22 AI Photographer
│           - Audio? → A2.19 AI Voice Director
│           - Video? → A2.18 AI Video Producer
│           - Music? → A2.17 AI Music Composer
└─ No → continue

Do I work with people / in sales / in management?
├─ Yes → AI Business / Strategy (A3)
│        → Sub-profile:
│           - Strategy? → A3.26 AI Strategy Consultant
│           - Product? → A3.27 AI Product Manager
│           - Adoption? → A3.29 AI Adoption Specialist
│           - Ethics? → A3.30 AI Ethics Officer
└─ No → continue

Do I work in a specific field (medical/legal/finance/education)?
├─ Yes → The hybrid version of my profession (B1)
│        → B1.51 Lawyer + AI
│        → B1.52 Doctor + AI
│        → B1.53 Accountant + AI
│        → B1.54 Teacher + AI
│        → etc.
└─ No → continue

Am I studying / teaching?
├─ Yes → AI Education hybrids (B5)
│        → B5.96 Professor + AI
│        → B5.97 Tutor + AI
└─ No → continue

Do I work in a trade / in services?
├─ Yes → The AI-hybrid version of my trade (B4)
│        → B4.86 Chef + AI
│        → B4.89 Mechanic + AI
│        → B4.90 Electrician + AI (Smart Home)
│        → etc.
└─ No → AI Adoption Specialist (A3.29): you help other people
         or AI Trainer (A4.36): your domain knowledge → AI training
```

---

## <a id="salary-benchmarks"></a>💰 Salary benchmarks 2026 (overview)

The salary tables and regional multipliers have been removed: they weren't verified against primary sources, and the numbers depend heavily on the state and city, the company, the person's level and how well they negotiate. For current numbers for your job title and your area, look at official labor statistics (in the US, bls.gov), job boards and salary surveys, not at this guide.

---

## <a id="top-10"></a>⭐ Top 10 emerging careers 2026-2030 (the author's estimate)

1. **AI Application Engineer**: the main new career of the era
2. **AI Agent Architect**: the multi-agent systems boom
3. **AI Safety / Red Team**: frontier labs keep dedicated teams
4. **Prompt Engineer** (still strong at the junior level): easy to get into
5. **AI Voice Agent Developer**: phone agents built on platforms like Vapi and Bland are in demand
6. **AI-Augmented Lawyer**: tools like Harvey are changing the day-to-day work
7. **AI Adoption Specialist** (enterprise): large companies need help rolling AI out
8. **AI Content Producer**: an AI-native content economy
9. **AI Cost Optimization Engineer**: companies have seen their bills
10. **AI Ethics / Compliance Officer**: the EU AI Act is taking effect in stages

---

## <a id="next-steps"></a>🎯 Checklist and next steps

After reading this guide:

- [ ] I picked 3 candidate careers (out of the 100)
- [ ] I identified the skill gaps for each one (what's missing?)
- [ ] I looked up pay in **my own** area (national averages and big-city numbers can mislead you)
- [ ] I picked 1 and wrote a 90-day learning plan
- [ ] I connected with 3+ people in that career (LinkedIn, X, conferences)
- [ ] I started a portfolio in that career (3 deliverables in 30 days)
- [ ] I'll re-evaluate in 90 days: is this still my path?

**Picture this:** a career isn't a tattoo. In the AI era you can switch every 2-3 years without losing momentum, as long as your skills are universal (Section D).

---

## 🎬 Practical advice from this course

1. **Don't study "AI"; study a specific tool in depth.** Master one tool (Claude, for example) → the second one comes easier → and so does the next.
2. **Build, don't just learn.** One production project beats 10 courses.
3. **Specialty + AI.** A generic AI engineer becomes a commodity. An AI engineer plus healthcare, legal or finance knowledge has a moat.
4. **Network in the AI community.** X (formerly Twitter), Hacker News, AI Engineer conferences.
5. **Don't chase the highest salary.** Choose a career with durable demand for 5-10 years (Section A1, A3.26, A3.27, B1).

---

## <a id="sources"></a>📚 Sources

- **Hacker News Jobs**: https://news.ycombinator.com/jobs (live AI job listings)
- **Anthropic Careers**: https://www.anthropic.com/careers
- **OpenAI Careers**: https://openai.com/careers
- **WEF Future of Jobs Report**: https://www.weforum.org/reports
- **McKinsey Future of Work**: https://www.mckinsey.com/featured-insights/future-of-work
- **Pew Research on AI in the workplace**: https://www.pewresearch.org

These sources are starting points for checking things yourself. No numbers from them were carried over into this guide.

---

## 🔗 Related lessons in the course

| Topic | Course lessons |
|-------|-------------|
| AI fundamentals | [What AI is](00-what-is-ai.md), [How an LLM works](00b-how-llm-works.md), [Comparing AI models](00c-ai-models-comparison.md), [AI without fear](00d-ai-without-fear.md) |
| Setup + Claude Code | [Installation and setup](05-setup.md), [Claude Code Desktop](05b-claude-code-desktop.md), [Plans and access](05c-access-levels-pricing.md) |
| Prompting | [Prompting fundamentals](06-prompting-fundamentals.md) |
| CLAUDE.md / Memory | [CLAUDE.md](07-claude-md.md) |
| Building apps | [Websites and web apps](15-websites-webapps.md), [APIs and integrations](16-apis-integration.md), [Deploying to Cloudflare](18-deployment-cloudflare.md) |
| Multi-agent systems | [Agent teams](26-agent-teams.md), [Multi-agent orchestration](82-multiagent-orchestration.md) |
| RAG | [RAG](14-rag.md) |
| Evals | [Evals](22-evals-system.md) |
| Security | [Permissions and security](28-permissions-security.md), [Prompt injection defense](107b-prompt-injection-defense.md) |
| Cost optimization | [Prompt caching and the Batch API](34-prompt-caching-batch-api.md), [Cost engineering](48b-cost-engineering.md) |

To see which lessons matter for a specific career, check the site's Professions page: that's where career-to-lesson links are kept.

---

**Version:** updated October 2026

🔥 **The forest is changing. Some trees are going down, seeds are sprouting, and new shoots are coming up from old stumps. Pick your place in the new forest.**

---

## 🆕 V2.0 EXPANSION: 200 careers + a forecast to 2030

> **Added:** 2026-05-11. Version 2.0.
> We double the number of careers to 200, plus a year-by-year forecast for 2027-2030 and the hybrid economy.
>
> **Picture this:** if v1.0 is a map of the forest today, v2.0 is a map of the forest five years out, plus a weather forecast for each year.

---

## 📑 How V2.0 is organized

- [Section A6-A11: + 50 NEW careers = 100 NEW in total](#a-v2)
- [Section B6-B10: + 50 HYBRID careers = 100 HYBRID in total](#b-v2)
- [Section C-extended: 25 disappearing jobs (up from 10)](#c-extended)
- [Section D-extended: 50 skills (up from 25)](#d-extended)
- [Section F: Year-by-year forecast 2027-2030](#section-f)
- [Section G: Geographic shifts](#section-g)
- [Section H: How skills evolve year by year](#section-h)
- [Section I: What AI WON'T do before 2030](#section-i)
- [Section J: The hybrid economy: 3 archetypes for 2030](#section-j)
- [Top 30 emerging careers 2026-2030 (expanded from 10)](#top-30)
- [Salary projections 2030 (regional)](#salary-2030)

---

## <a id="a-v2"></a>🌱 Section A6-A11: 50 more NEW careers

---

### A6. AI Hardware / Robotics (10 careers)

These are **the hands of the AI era**. Software meets hardware.

---

#### 51. Humanoid Robot Operator

- **What they do:** Operate and train humanoid robots (Figure, Tesla Optimus, Unitree). Train them through teleoperation + RLHF.
- **Key skills:**
  - Teleoperation rigs (VR controllers, motion capture)
  - Behavioral cloning datasets
  - Safety protocols around live people
  - Basic ML (an intuition for RLHF)
  - Mechatronics troubleshooting
- **Demand:** ⭐⭐⭐⭐ (several makers have announced plans for a wider rollout; treat the dates as plans, not facts)
- **How to get there:**
  1. An entry-level operator or technician job at a robotics company (Figure, Agility and others)
  2. Build a teleoperation rig in your garage + record a dataset
  3. An open-source contribution to the LeRobot framework
- **Picture this:** a 21st-century puppeteer. The puppet learns on its own; your job is to show it the first 1,000 moves.

---

#### 52. AI Chip Designer (TPU/NPU engineering)

- **What they do:** Design ASIC chips optimized for inference or training. Compete with NVIDIA through specialization.
- **Key skills:**
  - Verilog / SystemVerilog
  - Memory hierarchy for transformer architectures
  - Power efficiency (performance per watt)
  - Understanding the matrix operations behind attention
  - EDA tools (Cadence, Synopsys)
- **Demand:** ⭐⭐⭐⭐⭐ (many big tech companies and startups are building their own AI chips)
- **How to get there:**
  1. An EE/CS degree + a chip design specialization
  2. 3-5 years in traditional chip design (Intel, AMD, Apple)
  3. Pivot into AI-specific work (Tenstorrent, Groq, Cerebras)
- **Picture this:** the architect of a skyscraper where every floor is a layer of the AI model. Design it well, and you get 10 times more out of the same foundation.

---

#### 53. Smart Glasses Application Developer

- **What they do:** Build apps for Ray-Ban Meta, Apple Vision Pro and Snap Specs, plus real-time AI overlays.
- **Key skills:**
  - AR/VR SDKs (Meta SDK, ARKit, WebXR)
  - Computer vision (object detection, OCR)
  - Voice-first UX (there's no keyboard)
  - Latency budgets (<100ms is critical)
  - Privacy design (the camera is always ready)
- **Demand:** ⭐⭐⭐⭐ (an early market: several makers already ship AI glasses, and the app platforms are young)
- **How to get there:**
  1. A mobile dev foundation (iOS/Android)
  2. An AR portfolio (3 production apps)
  3. AI integration (Claude + vision)
- **Picture this:** the architect of an invisible layer of reality. Sees the world twice: with their eyes and through data.

---

#### 54. AI Wearable Engineer

- **What they do:** Build AI-powered wearables (AI pins and pendants such as Friend, the Rabbit R1, smart rings).
- **Key skills:**
  - Embedded systems (Rust, C++)
  - Power management (battery life is critical)
  - On-device ML (TinyML, quantization)
  - Always-on audio processing
  - Sensor fusion (microphone + accelerometer + GPS)
- **Demand:** ⭐⭐⭐ (the category is still taking shape: Humane, the maker of an early AI pin, sold its technology to HP in 2025)
- **How to get there:**
  1. An embedded systems foundation
  2. An on-device ML certification
  3. Build a prototype in your garage (Raspberry Pi + Whisper running locally)
- **Picture this:** a 21st-century watchmaker. Builds a tiny mechanism that knows you better than you know yourself.

---

#### 55. Autonomous Vehicle AI Engineer

- **What they do:** Build the self-driving stack (Waymo, Tesla FSD, Wayve). Perception → planning → control, plus LLMs for edge cases.
- **Key skills:**
  - Computer vision in depth
  - SLAM (simultaneous localization and mapping)
  - Reinforcement learning
  - Simulation (CARLA, the Waymo Open Dataset)
  - Safety case engineering
- **Demand:** ⭐⭐⭐⭐ (concentrated in a few well-funded companies such as Waymo, Tesla and Wayve)
- **How to get there:**
  1. A CS degree + an ML specialization
  2. A robotics PhD (optional, but it helps for research roles)
  3. An internship at one of the top-5 AV companies
- **Picture this:** a driving instructor for a cab driver who never gets tired. You train it for 100 million kilometers (about 62 million miles) in a simulator.

---

#### 56. Drone Swarm Coordinator

- **What they do:** Program the coordination of dozens or hundreds of drones at once, for inspection, agriculture, security and light shows.
- **Key skills:**
  - ROS2, PX4 firmware
  - Distributed systems (consensus algorithms)
  - Mesh networking
  - Regulatory compliance (FAA, EASA)
  - Real-time computer vision
- **Demand:** ⭐⭐⭐ (niche, but growing in agriculture + inspection)
- **How to get there:**
  1. A robotics or embedded foundation
  2. Competence with a single drone (DJI SDK)
  3. Move on to swarm patterns (ROS2 + multi-agent)
- **Picture this:** a choreographer for a swarm of bees. Each bee is dumb; the swarm is brilliant.

---

#### 57. AI Sensor Network Architect

- **What they do:** Design distributed sensor networks (smart city, factory, farm) plus AI inference at the edge.
- **Key skills:**
  - LoRaWAN, 5G, satellite IoT
  - Edge compute (NVIDIA Jetson, Coral)
  - Time-series databases (InfluxDB, TimescaleDB)
  - Anomaly detection ML
  - Industrial protocols (Modbus, OPC-UA)
- **Demand:** ⭐⭐⭐ (a B2B niche, but stable)
- **How to get there:**
  1. An IoT engineer foundation
  2. Industrial automation experience
  3. An AI/edge specialization
- **Picture this:** a neurologist for the planet. Every sensor is a nerve. Without them, the world is numb.

---

#### 58. BCI (Brain-Computer Interface) Engineer

- **What they do:** Build BCI systems (Neuralink, Synchron, Precision Neuroscience). Decode neural signals into actions.
- **Key skills:**
  - Neuroscience basics (spike sorting, LFP)
  - Signal processing (Kalman filters, decoders)
  - ML on neural data
  - Biocompatibility and medical regulation (FDA)
  - C/C++ for real-time decoders
- **Demand:** ⭐⭐ (narrow: a handful of companies worldwide, though the field is growing)
- **How to get there:**
  1. A neuroscience or EE PhD
  2. A postdoc in a BCI lab
  3. A pivot into industry (Neuralink, Synchron)
- **Picture this:** an interpreter between the brain and the machine. Interpreters used to work between English and Spanish; now it's neurons and bytes.

---

#### 59. AI-Augmented Manufacturing Engineer

- **What they do:** Bring AI vision, predictive maintenance and generative design into factories.
- **Key skills:**
  - Industrial vision systems (Cognex, Keyence)
  - PLC programming
  - Predictive maintenance ML
  - Generative design (Autodesk Fusion)
  - Lean / Six Sigma awareness
- **Demand:** ⭐⭐⭐⭐ (Industry 4.0 + the onshoring wave)
- **How to get there:**
  1. A mechanical/manufacturing engineering foundation
  2. An AI certification (NVIDIA DLI, Coursera ML)
  3. Industrial AI deployments in your portfolio
- **Picture this:** a doctor for the factory. It used to treat symptoms; now it works from a continuous MRI of every machine.

---

#### 60. Edge AI Hardware Specialist

- **What they do:** Optimize AI models for edge devices (Jetson, Coral, mobile NPUs, microcontrollers).
- **Key skills:**
  - Quantization (INT8, INT4)
  - Model distillation
  - ONNX, TensorRT, CoreML conversion
  - Hardware-aware NAS
  - Power profiling
- **Demand:** ⭐⭐⭐⭐ (the on-device AI wave)
- **How to get there:**
  1. An ML engineer foundation
  2. Embedded systems experience
  3. Specialize in one target platform (mobile or industrial)
- **Picture this:** a jeweler. Takes a cut diamond of 7B parameters and carves it down to 100MB so it fits in a pendant.

---

### A7. AI Research / Science (10 careers)

These are **the explorers**. Right at the frontier.

---

#### 61. AI Alignment Researcher

- **What they do:** Study how to make AI safe and aligned with human values. Not "forbid it" but "teach it to want the right things".
- **Key skills:**
  - RLHF, DPO, Constitutional AI
  - Formal verification basics
  - Game theory, decision theory
  - Philosophy (utilitarianism, deontology)
  - Research methodology
- **Demand:** ⭐⭐⭐⭐⭐ (one of the central research areas of the decade)
- **How to get there:**
  1. An ML PhD or the MATS program
  2. Anthropic Fellows, or apply directly
  3. Publish on the Alignment Forum, at NeurIPS, ICML
- **Picture this:** an animal trainer working with a predator. The lion is stronger than you, so you can't just give orders. But you can train it to eat only what it should.

---

#### 62. Mechanistic Interpretability Researcher

- **What they do:** Study what's **inside** AI models. Which neurons are responsible for what, how circuits form.
- **Key skills:**
  - Linear algebra in depth
  - Probing classifiers
  - Activation patching
  - Sparse autoencoders
  - Visualization tools
- **Demand:** ⭐⭐⭐⭐ (a small field with teams at a few labs)
- **How to get there:**
  1. An ML PhD focused on interpretability
  2. Replicate Anthropic's state-of-the-art papers
  3. Apply to Anthropic / Apollo Research / Redwood
- **Picture this:** a neuroscientist for an artificial brain. Biology students used to dissect frogs; now we look into LLMs through a "microscope" of activations.

---

#### 63. AI Scaling Researcher

- **What they do:** Study the scaling laws (compute, data, model size). Figure out where the next frontier is.
- **Key skills:**
  - Distributed training (DeepSpeed, Megatron)
  - The math of scaling laws (Chinchilla, etc.)
  - Compute budgeting for very large training runs
  - Failure mode analysis
  - Statistical inference
- **Demand:** ⭐⭐⭐ (a handful of places worldwide, but critically important)
- **How to get there:**
  1. An ML PhD with large-model experience
  2. Industry experience with large training runs
  3. Apply to a frontier lab
- **Picture this:** a mapmaker on an unexplored continent. Every step costs millions, so you'd better know where you're going.

---

#### 64. Synthetic Biology AI Engineer

- **What they do:** Apply AI to biology: protein design, drug discovery, CRISPR optimization.
- **Key skills:**
  - Molecular biology basics
  - AlphaFold / RoseTTAFold patterns
  - Sequence-to-structure models
  - Wet lab basics (or a partnership)
  - GPU compute optimization
- **Demand:** ⭐⭐⭐⭐ (Isomorphic Labs + Cradle Bio + many startups)
- **How to get there:**
  1. A CS/ML + bio crossover (or bio + ML)
  2. Build a prediction model on public protein data
  3. A pivot into industry (Insitro, Recursion)
- **Picture this:** the architect of living machines. Biologists used to discover what exists. Now they design what never existed.

---

#### 65. Drug Discovery AI Specialist

- **What they do:** Use AI for molecule screening, drug repurposing and clinical trial optimization.
- **Key skills:**
  - Cheminformatics (RDKit, DeepChem)
  - Molecular dynamics
  - Clinical trial design
  - The FDA regulatory pathway
  - Bayesian optimization
- **Demand:** ⭐⭐⭐⭐ (big pharma companies and AI drug discovery startups)
- **How to get there:**
  1. A PharmD or a chemistry PhD
  2. An ML certification
  3. An industry research role
- **Picture this:** a chef who simulates a million recipes a day. Ten of them turn out to be medicines.

---

#### 66. Climate AI Researcher

- **What they do:** AI for climate modeling, weather forecasting, carbon capture optimization and the energy grid.
- **Key skills:**
  - Atmospheric science basics
  - PDE solvers (graph neural networks for weather)
  - Satellite data processing
  - Climate models (CESM, etc.)
  - Visualization
- **Demand:** ⭐⭐⭐⭐ (Google GraphCast, Microsoft Aurora: big investments)
- **How to get there:**
  1. A PhD in climate science or ML + earth science
  2. An open-source contribution to WeatherBench
  3. Apply to Google DeepMind's climate team, NVIDIA Earth-2, Microsoft
- **Picture this:** a weather forecaster for the whole planet. AI weather models now produce forecasts much faster, and their useful range keeps getting longer.

---

#### 67. AI Material Scientist

- **What they do:** AI for discovering new materials: batteries, semiconductors, sustainable composites.
- **Key skills:**
  - Solid state physics basics
  - DFT (density functional theory)
  - Graph neural networks for crystals
  - The Materials Project database
  - High-throughput experimentation
- **Demand:** ⭐⭐⭐ (narrow, but there's Google DeepMind's GNoME + battery startups)
- **How to get there:**
  1. A materials science or physics PhD
  2. An ML specialization
  3. A pivot into industry (Citrine, Kebotix, Google DeepMind)
- **Picture this:** a 21st-century alchemist. Alchemists looked for gold; now AI finds the "gold" for electric cars and solar panels.

---

#### 68. Quantum-AI Researcher

- **What they do:** The intersection of quantum computing and AI. Hybrid algorithms, quantum machine learning.
- **Key skills:**
  - Quantum computing basics (Qiskit, Cirq)
  - Variational quantum algorithms
  - Classical ML in depth
  - Advanced linear algebra
  - Hardware-aware optimization (IBM, IonQ)
- **Demand:** ⭐⭐ (narrow: a small number of companies and national labs; a long-term bet)
- **How to get there:**
  1. A physics PhD with a quantum focus
  2. An ML crossover
  3. A pivot into industry or a national lab
- **Picture this:** a scientist standing between two eras. It doesn't pay off for industry yet, but in 10 years it could become the main thing.

---

#### 69. AI Astronomer

- **What they do:** AI for analyzing astronomical data: exoplanet detection, gravitational waves, galaxy classification.
- **Key skills:**
  - Astronomy basics
  - Time-series ML
  - Image processing (Hubble, JWST data)
  - Anomaly detection
  - Big data pipelines (LSST scale)
- **Demand:** ⭐⭐ (narrow: academia + NASA + a few startups)
- **How to get there:**
  1. An astronomy PhD
  2. An ML specialization
  3. Postdoc → research scientist
- **Picture this:** a telescope spends seconds on an image. An astronomer used to spend years on the data. Now AI takes minutes.

---

#### 70. Neuro-AI Researcher

- **What they do:** The intersection of neuroscience and AI. Use the brain as inspiration for architectures, and AI to understand the brain.
- **Key skills:**
  - Neuroscience in depth
  - Computational neuroscience
  - Neural architecture design
  - fMRI / electrophysiology data
  - Cross-domain research methodology
- **Demand:** ⭐⭐⭐ (Apical Intelligence, formerly Numenta; BrainGate; academic labs)
- **How to get there:**
  1. A neuroscience PhD
  2. A computational specialty
  3. A crossover into industry
- **Picture this:** an archaeologist of the biological mind. Every discovery about the brain is a potential architecture for AI.

---

### A8. AI Healthcare (10 careers)

> AI helps a professional, but it doesn't replace licensed medical work and doesn't give personal medical advice.

These are **the doctors of the AI era**. Where the stakes are highest.

---

#### 71. AI Radiologist Assistant

- **What they do:** Use AI (Aidoc, Viz.ai, Harrison.ai) to triage X-rays, CT and MRI scans. A human in the loop for critical decisions.
- **Key skills:**
  - Radiology basics (or a board-certified radiologist)
  - AI tool literacy
  - Handling DICOM data
  - Clinical workflow integration
  - Patient safety protocols
- **Demand:** ⭐⭐⭐⭐ (the FDA's list of AI-enabled medical devices keeps growing)
- **How to get there:**
  1. An MD + a radiology residency
  2. AI literacy + training on the tools your hospital uses (Aidoc, Viz.ai)
  3. A role leading adoption at a hospital
- **Picture this:** radiologist + AI = pilot + autopilot. AI looks at every image; the human makes the call. Faster work, and fewer things slip through.

---

#### 72. Medical NLP Specialist

- **What they do:** Build NLP (natural language processing) systems for EHRs (electronic health records): extract structured data, clinical decision support, billing optimization.
- **Key skills:**
  - NLP in depth
  - Medical terminology (SNOMED, ICD-10)
  - HIPAA compliance
  - EHR APIs (Epic, Oracle Health, formerly Cerner)
  - Privacy-preserving ML
- **Demand:** ⭐⭐⭐⭐ (hospitals want to put their EHR data to use)
- **How to get there:**
  1. An NLP engineer foundation
  2. A healthcare domain certification
  3. Build a portfolio of EHR projects
- **Picture this:** an archaeologist of medical records. Digs structured data out of millions of unstructured notes.

---

#### 73. AI Diagnostic Engineer

- **What they do:** Build diagnostic AI systems (skin cancer, retinopathy, cardiac).
- **Key skills:**
  - Computer vision
  - Medical imaging
  - Clinical validation
  - The FDA 510(k) pathway
  - Multimodal models
- **Demand:** ⭐⭐⭐⭐ (huge investment in medical AI)
- **How to get there:**
  1. An ML engineer foundation + a medical specialty
  2. An industry job (Tempus, PathAI, Paige)
  3. Experience with an FDA submission
- **Picture this:** the eyes of thousands of pathologists in one algorithm. It never gets tired.

---

#### 74. AI Drug Repurposing Specialist

- **What they do:** Use AI to find new uses for existing drugs (often cheaper than developing a new drug).
- **Key skills:**
  - Pharmacology basics
  - Knowledge graphs (drug-disease-gene)
  - Causal inference
  - Clinical trial design
  - Regulatory pathways
- **Demand:** ⭐⭐⭐ (BenevolentAI, Healx)
- **How to get there:**
  1. A PharmD or a pharma research foundation
  2. An ML specialization
  3. An industry research role
- **Picture this:** a locksmith trying keys. A key made for one door may open another, and AI finds which one.

---

#### 75. AI Mental Health Researcher

- **What they do:** Develop AI for mental health support (apps like Wysa) that is ethical, safe and evidence-based.
- **Key skills:**
  - Clinical psychology basics
  - NLP in depth
  - Safety + harm reduction
  - Designing for long-term engagement
  - Privacy + consent
- **Demand:** ⭐⭐⭐⭐ (the mental health crisis + AI's accessibility)
- **How to get there:**
  1. A PhD in psychology, or an ML + psychology crossover
  2. An industry job (Wysa, Spring Health)
  3. Clinical validation studies
- **Picture this:** a support counselor in every pocket. It doesn't replace a psychiatrist or a licensed therapist, but it's a first line available 24/7.

---

#### 76. AI Pathology Specialist

- **What they do:** AI for digital pathology: cancer detection, prognosis and treatment selection from biopsies.
- **Key skills:**
  - Pathology basics
  - Whole slide imaging
  - Computer vision (gigapixel images)
  - Multi-instance learning
  - Clinical validation
- **Demand:** ⭐⭐⭐⭐ (Paige, PathAI, Roche Digital Pathology)
- **How to get there:**
  1. An MD in pathology + AI, or ML + a pathology certification
  2. An industry job
  3. Experience with FDA-approved tools
- **Picture this:** a microscope with the eyes of 10,000 pathologists. It can catch what a tired eye might miss.

---

#### 77. AI Genomics Engineer

- **What they do:** AI for variant calling, polygenic risk scores and personalized medicine.
- **Key skills:**
  - Bioinformatics (BWA, GATK)
  - Population genetics
  - Variant interpretation (ACMG guidelines)
  - Deep learning on sequence data
  - Privacy-preserving computation
- **Demand:** ⭐⭐⭐ (Tempus, Verily, Color Health)
- **How to get there:**
  1. A bioinformatics PhD, or ML + genetics
  2. Experience with population data
  3. A pivot into industry
- **Picture this:** an interpreter from the language of the genome into the language of diagnoses. It used to take years. Now it takes seconds.

---

#### 78. AI Surgical Robotics Operator

- **What they do:** Operate AI-augmented surgical robots (next-generation da Vinci, Vicarious Surgical) and interpret the AI's suggestions.
- **Key skills:**
  - Surgical training (residency or a specialty)
  - Mastery of the robotic interface
  - Real-time decision-making
  - Evaluating AI suggestions
  - Crisis management
- **Demand:** ⭐⭐⭐⭐ (Intuitive Surgical adoption + new entrants)
- **How to get there:**
  1. An MD + a surgical residency (8-10 years)
  2. A robotic surgery certification
  3. Experience with AI tools
- **Picture this:** surgeon + robot + AI = a team of three specialists in one body. A precision no single person can reach.

---

#### 79. AI Clinical Trial Optimizer

- **What they do:** Optimize clinical trials with AI: patient matching, protocol design, real-world evidence.
- **Key skills:**
  - Clinical research basics
  - EHR mining
  - Statistical inference
  - Regulatory awareness
  - Health economics
- **Demand:** ⭐⭐⭐ (Saama, Medable)
- **How to get there:**
  1. A pharma or clinical research foundation
  2. An ML/data science certification
  3. A job at a pharma company or a CRO
- **Picture this:** the casting director of a clinical trial. Picks the ideal candidates out of millions of patients in minutes.

---

#### 80. AI Public Health Analyst

- **What they do:** AI for epidemiology, outbreak prediction, public health surveillance and vaccine distribution.
- **Key skills:**
  - Epidemiology basics
  - Time-series forecasting
  - Geospatial analysis
  - Integrating public data
  - Communicating with non-technical audiences
- **Demand:** ⭐⭐⭐ (CDC, WHO, BlueDot)
- **How to get there:**
  1. An MPH or an epidemiology degree
  2. Data science skills
  3. A job in government or at a nonprofit
- **Picture this:** a lookout on the city wall. Watches for the first signs of an outbreak.

---

### A9. AI Education / Edtech (5 careers)

---

#### 81. AI Curriculum Designer

- **What they do:** Design curricula with AI built in: the student as a co-creator with AI, not "AI does the homework".
- **Key skills:**
  - Pedagogy / learning science
  - AI tool literacy
  - Assessment design
  - Curriculum mapping
  - Change management in schools
- **Demand:** ⭐⭐⭐⭐ (many school districts are still working out how to handle AI)
- **How to get there:**
  1. A teaching foundation
  2. An EdTech / AI literacy certification
  3. A district-level role
- **Picture this:** an architect of learning. It used to be "memorize the fact". Now it's "learn to dance with AI and notice when it's wrong".

---

#### 82. AI Tutor System Architect

- **What they do:** Build AI tutoring systems (Khanmigo, Anthropic's education partnerships) that are personalized, safe and pedagogically sound.
- **Key skills:**
  - LLM application engineering
  - Educational psychology
  - Safety + child-safe content design
  - Long-term engagement metrics
  - Multimodal learning (text, voice, visual)
- **Demand:** ⭐⭐⭐⭐ (Khan Academy, Speak, Carnegie Learning)
- **How to get there:**
  1. An AI Application Engineer foundation
  2. Experience in education
  3. A job in the EdTech industry
- **Picture this:** the builder of a personal teacher. Every child gets their own pace, their own style, their own examples.

---

#### 83. AI Assessment Designer

- **What they do:** Design assessments that **measure thinking**, not "memorization or AI skill". Assessment design that resists AI cheating.
- **Key skills:**
  - Psychometrics
  - Item response theory
  - AI detection (to prevent cheating)
  - Authentic assessment design
  - Fairness evaluation
- **Demand:** ⭐⭐⭐ (College Board, ETS, edtech, universities)
- **How to get there:**
  1. An education research foundation
  2. A psychometrics specialty
  3. Literacy in AI and cheating
- **Picture this:** a designer of tests where "copying is impossible". Not because you block it, but because there's nothing to copy.

---

#### 84. AI Learning Analytics Engineer

- **What they do:** Build data pipelines and dashboards for learning analytics at the school or university level.
- **Key skills:**
  - Data engineering
  - LMS APIs (Canvas, Moodle, Blackboard)
  - Privacy-preserving analytics (FERPA compliance)
  - Visualization
  - Predictive modeling (at-risk students)
- **Demand:** ⭐⭐⭐ (universities, EdTech vendors)
- **How to get there:**
  1. A data engineer foundation
  2. A job in the education sector
  3. A privacy compliance certification
- **Picture this:** a progress radar. A teacher used to see a student twice a week; now you can see each student's path minute by minute.

---

#### 85. AI Accessibility in Education Specialist

- **What they do:** Use AI to make education accessible for students with disabilities, English language learners and neurodiverse students.
- **Key skills:**
  - Disability awareness
  - Accessibility standards (WCAG, ADA)
  - AI tools (speech-to-text, text-to-speech, summarization)
  - Curriculum adaptation
  - Advocacy + change management
- **Demand:** ⭐⭐⭐ (huge need, but underfunded)
- **How to get there:**
  1. A special education or accessibility background
  2. AI tool literacy
  3. A job with a school district or a nonprofit
- **Picture this:** a bridge between the world and a student who couldn't get there before. AI is a wheelchair ramp for learning.

---

### A10. AI Finance / Quant (5 careers)

> The careers below describe what professionals do. This is not investment advice and not a promise of trading income.

---

#### 86. AI Quant Researcher

- **What they do:** Use AI for alpha generation, factor research and trading strategies. Hedge funds.
- **Key skills:**
  - Statistics + ML in depth
  - Time-series prediction
  - Market microstructure
  - Backtesting frameworks
  - Risk management
- **Demand:** ⭐⭐⭐⭐⭐ (quant funds such as Renaissance, Two Sigma, D. E. Shaw and Citadel)
- **How to get there:**
  1. A PhD in math, physics or CS
  2. An internship at a quant fund
  3. A full-time offer after strong performance
- **Picture this:** a poker player who plays a trillion hands a day. AI sees patterns a person never would.

---

#### 87. AI Fraud Detection Engineer

- **What they do:** Build anti-fraud systems: payment fraud, identity theft, money laundering.
- **Key skills:**
  - Anomaly detection
  - Graph neural networks (transactions = a graph)
  - Real-time inference
  - Regulatory compliance (KYC, AML)
  - Adversarial robustness
- **Demand:** ⭐⭐⭐⭐ (banks, payment processors and fintechs)
- **How to get there:**
  1. An ML engineer foundation
  2. A job at a fintech
  3. Compliance certifications (CFE)
- **Picture this:** bank security for the 21st century. It used to be a guard's eyes. Now a million AI eyes catch anomalies in milliseconds.

---

#### 88. AI Underwriter (insurance/lending)

- **What they do:** AI-augmented underwriting: life, health, auto and home insurance, lending decisions.
- **Key skills:**
  - Actuarial basics or underwriting experience
  - ML models (XGBoost, neural nets)
  - Fairness + bias auditing
  - Regulatory compliance (state-level, ECOA)
  - Explainability tools
- **Demand:** ⭐⭐⭐⭐ (insurtech + lending fintech)
- **How to get there:**
  1. An underwriting or actuarial foundation
  2. An ML certification
  3. A job at an insurtech (Lemonade, Root)
- **Picture this:** a risk calculator that sees 1,000 factors at once. A decision in seconds, not days.

---

#### 89. AI Compliance Engineer (banking)

- **What they do:** Build compliance automation for banks and fintechs: KYC, AML, transaction monitoring, reporting.
- **Key skills:**
  - Banking regulations (BSA, OFAC, FATCA)
  - NLP for regulatory text
  - Workflow automation
  - Audit trails
  - Compliance across jurisdictions
- **Demand:** ⭐⭐⭐⭐ (compliance is a bottleneck at many banks)
- **How to get there:**
  1. A compliance or legal background
  2. An engineering certification
  3. A job at a RegTech company (Hummingbird, ComplyAdvantage)
- **Picture this:** a robot compliance lawyer for the bank. It never misses a regulatory update.

---

#### 90. AI Trading Systems Architect

- **What they do:** Design the architecture of high-frequency and algorithmic trading systems with AI components.
- **Key skills:**
  - Low-latency systems (C++, Rust)
  - Network engineering (microseconds matter)
  - Risk systems
  - Exchange protocols (FIX, ITCH)
  - ML inference at scale
- **Demand:** ⭐⭐⭐ (narrow: HFT shops + prop trading)
- **How to get there:**
  1. Deep systems engineering
  2. Exposure to quant work
  3. An industry job (Jane Street, Jump Trading, HRT)
- **Picture this:** the architect of a race at the speed of light. A microsecond = a million dollars.

---

### A11. AI Specialty Emerging (10 careers)

These are **narrow specialists where industries meet**.

---

#### 91. AI Climate / ESG Specialist

- **What they do:** AI for ESG reporting, carbon accounting and climate risk assessment.
- **Key skills:**
  - Carbon accounting standards (GHG Protocol)
  - Satellite data analysis
  - Climate models
  - ESG regulatory frameworks (the EU's CSRD and the rules of your own country)
  - Data integration
- **Demand:** ⭐⭐⭐⭐ (EU sustainability reporting rules such as the CSRD, even with recent delays, plus investor pressure)
- **How to get there:**
  1. A sustainability or environmental science background
  2. An AI/data science certification
  3. An industry job (Watershed, Persefoni)
- **Picture this:** an accountant on a planetary scale. Counts not dollars but tons of CO2.

---

#### 92. AI Agriculture Engineer (precision farming)

- **What they do:** AI for farming: yield prediction, pest detection, irrigation optimization, autonomous tractors.
- **Key skills:**
  - Agronomy basics
  - Computer vision (drone imagery)
  - IoT / edge compute
  - Geospatial analysis
  - Sustainability metrics
- **Demand:** ⭐⭐⭐ (John Deere, Climate FieldView, Indigo Ag, FBN)
- **How to get there:**
  1. An AgTech or agronomy background
  2. An AI/data certification
  3. A job at an AgriTech company
- **Picture this:** a farm adviser with a drone sidekick. Sees the field through an eagle's eyes. Every plant is accounted for.

---

#### 93. AI Legal Tech Engineer

- **What they do:** Build legal AI tools: contract review, case law research, eDiscovery (Harvey, CoCounsel, Spellbook).
- **Key skills:**
  - NLP in depth
  - Legal domain knowledge
  - Long-context handling
  - Citation accuracy
  - Privilege + confidentiality
- **Demand:** ⭐⭐⭐⭐⭐ (Harvey + many legal tech startups)
- **How to get there:**
  1. An ML engineer foundation
  2. A legal domain certification or a partnership
  3. A job at a LegalTech company
- **Picture this:** a paralegal who remembers every law on the books. Reads 1,000 pages in seconds.

---

#### 94. AI Real Estate Analyst

- **What they do:** AI for real estate valuation, market prediction, property management automation and tenant matching.
- **Key skills:**
  - Real estate market knowledge
  - Geospatial ML
  - Computer vision (satellite + street view)
  - Time-series prediction
  - Regulatory awareness (zoning, fair housing)
- **Demand:** ⭐⭐⭐ (Zillow, Compass, Opendoor, Redfin + property managers)
- **How to get there:**
  1. A real estate or finance background
  2. An ML certification
  3. A job at a PropTech company
- **Picture this:** an appraiser who has seen all 100 million transactions in the world. A price for a house in seconds.

---

#### 95. AI Sports Analytics Engineer

- **What they do:** AI for sports: player performance, injury prediction, game strategy, fan engagement.
- **Key skills:**
  - Sports domain knowledge
  - Computer vision (tracking)
  - Biomechanics basics
  - Time-series ML
  - Visualization
- **Demand:** ⭐⭐⭐ (the NBA, NFL, soccer clubs, F1 teams)
- **How to get there:**
  1. A data science foundation
  2. A sports analytics course, or a project you can show at a conference such as the MIT Sloan Sports Analytics Conference (SSAC)
  3. A job with a team or in sports media
- **Picture this:** a coach with a microscope. Sees what a person can't: micro-patterns in movement, fatigue, an opening.

---

#### 96. AI Cybersecurity Hunter

- **What they do:** AI-augmented threat hunting: adversarial ML, anomaly detection, threat intel, incident response.
- **Key skills:**
  - A cybersecurity foundation
  - Adversarial ML techniques
  - SIEM / SOAR platforms
  - Threat intelligence
  - Reverse engineering
- **Demand:** ⭐⭐⭐⭐⭐ (AI-powered attacks → a need for AI-powered defense)
- **How to get there:**
  1. A cybersecurity foundation (OSCP, etc.)
  2. An ML specialty
  3. An industry job (CrowdStrike, Mandiant, Palo Alto Networks)
- **Picture this:** a safari guide who tracks hackers. AI helps you spot the tracks in a jungle of logs.

---

#### 97. AI Government / Civic Tech

- **What they do:** AI for government services: benefits processing, services for the public, policy analysis. Often through government digital service teams and groups like Code for America.
- **Key skills:**
  - Government domain knowledge
  - Procurement awareness
  - Plain language design
  - Compliance (Section 508, FedRAMP)
  - Stakeholder management
- **Demand:** ⭐⭐⭐ (rising as AI executive orders roll out)
- **How to get there:**
  1. A tech career foundation
  2. A government job (federal, state or city digital service teams)
  3. Civic tech projects (Code for America)
- **Picture this:** a reformer of bureaucracy. AI breaks up the lines and cuts the paperwork, like a DMV with no waiting room.

---

#### 98. AI Energy Grid Engineer

- **What they do:** AI for the smart grid: demand prediction, renewable integration, outage detection, EV charging optimization.
- **Key skills:**
  - Power systems engineering
  - Time-series forecasting
  - Optimization (linear/non-linear)
  - Edge compute
  - Regulatory awareness (FERC, ISO)
- **Demand:** ⭐⭐⭐⭐ (the energy transition + the EV wave)
- **How to get there:**
  1. A power engineering foundation
  2. An ML certification
  3. A job at a utility or a grid software company (the Tesla Powerwall team, Uplight, GridX)
- **Picture this:** the conductor of the power grid. Balances millions of devices every second.

---

#### 99. AI Logistics Optimizer

- **What they do:** AI for supply chain optimization: routing, inventory, demand forecasting, last mile.
- **Key skills:**
  - Operations research in depth
  - ML forecasting
  - Geospatial / routing algorithms
  - SAP/Oracle integration
  - Real-time systems
- **Demand:** ⭐⭐⭐⭐ (Amazon, FedEx, DHL, project44)
- **How to get there:**
  1. An OR or industrial engineering foundation
  2. An ML + supply chain specialty
  3. An industry job
- **Picture this:** a chess player on a board with a million squares. Every move is a shipment crossing the world.

---

#### 100. AI Supply Chain Architect

- **What they do:** Strategy and architecture for an AI-enabled supply chain: resilience, sustainability, transparency.
- **Key skills:**
  - Supply chain strategy
  - Multi-tier visibility (graph data)
  - Risk modeling
  - ESG integration
  - Vendor management
- **Demand:** ⭐⭐⭐⭐ (the post-COVID focus on resilience + decoupling from China)
- **How to get there:**
  1. A supply chain career of 7-10 years
  2. An AI/digital transformation specialty
  3. A senior consulting or industry role
- **Picture this:** the architect of the circulatory system of world trade. AI = an MRI of every junction.

---

## <a id="b-v2"></a>🌳 Section B6-B10: 50 more HYBRID careers

---

### B6. Healthcare hybrids (10 careers)

> AI helps the clinician, but it doesn't replace licensed work and doesn't give personal medical advice.

---

#### 101. Surgeon + AI = AI-Augmented Surgeon

- **What they do:** A surgeon working with da Vinci + an AI overlay for real-time guidance, anatomy recognition and complication prediction.
- **Key skills:**
  - Surgical residency (8-10 years, the base)
  - Robotic surgery certification
  - Fluency with AI tools
  - Real-time decision-making
  - Multitasking (watching both the AI and the patient)
- **Demand:** ⭐⭐⭐⭐ (in demand at large hospitals)
- **How to get there:**
  1. An MD + a surgical residency + a fellowship
  2. A robotic surgery certification
  3. AI augmentation training
- **Picture this:** an airline pilot with autopilot plus a super-radar. Flies the plane together with the AI.

---

#### 102. Radiologist + AI = Diagnostic AI Specialist

- **What they do:** A radiologist + AI triage (Aidoc, Rad AI). Reads more cases per shift, with AI as a second pair of eyes.
- **Key skills:**
  - A radiology foundation (residency)
  - AI tool literacy
  - Quality assurance methods
  - Managing a high-volume workflow
  - Patient communication
- **Demand:** ⭐⭐⭐⭐ (a radiologist shortage, and AI helps with the workload)
- **How to get there:**
  1. An MD + a radiology residency
  2. Training on AI tools (Aidoc, Harrison.ai)
  3. A role as the hospital's AI champion
- **Picture this:** a hawk's eye + AI = a radiologist. AI looks at every shadow; the human makes the call.

---

#### 103. Pharmacist + AI = AI-Enabled Pharmacist

- **What they do:** A pharmacist + AI tools for drug interaction checks, personalized dosing and medication therapy management.
- **Key skills:**
  - A PharmD foundation
  - Clinical decision support tools
  - Pharmacogenomics basics
  - Patient education
  - Navigating the EHR
- **Demand:** ⭐⭐⭐⭐ (retail pharmacy + hospital roles)
- **How to get there:**
  1. A PharmD degree
  2. An AI tool certification
  3. Specialty MTM (medication therapy management) training
- **Picture this:** a watchdog for the interactions of a million drugs. It used to all be in the pharmacist's head. Now AI helps.

---

#### 104. Nurse + AI = AI-Augmented Practitioner

- **What they do:** A nurse + AI for triage, early warning systems, patient monitoring and documentation.
- **Key skills:**
  - An RN/BSN/NP foundation
  - Comfort with AI tools
  - Critical thinking when the AI throws false positives
  - Patient advocacy
  - Fitting AI into the workflow
- **Demand:** ⭐⭐⭐⭐⭐ (the nursing shortage + AI boosts productivity)
- **How to get there:**
  1. A nursing degree
  2. Training on AI clinical tools
  3. A specialty certification (NP, CNS)
- **Picture this:** a nurse with a third eye. AI can flag a patient who is deteriorating hours before a crisis.

---

#### 105. Dentist + AI = AI Diagnostic Dentist

- **What they do:** A dentist + AI vision on X-rays (Pearl, VideaHealth) for cavity detection and treatment planning.
- **Key skills:**
  - A DDS/DMD foundation
  - Literacy in AI X-ray tools
  - Treatment planning
  - Patient communication (explaining what the AI found)
  - Navigating insurance
- **Demand:** ⭐⭐⭐⭐ (Pearl + VideaHealth + newcomers)
- **How to get there:**
  1. A DDS/DMD degree
  2. An AI tool certification
  3. Practice management
- **Picture this:** a dentist and a radiologist in one person. AI can flag what the eye might miss.

---

#### 106. Veterinarian + AI = AI Vet Assistant

- **What they do:** A veterinarian + AI vision (cancer on scans), telemedicine triage, breed-specific dosing.
- **Key skills:**
  - A DVM foundation
  - Literacy in AI imaging tools
  - Knowledge across species
  - Telemedicine workflow
  - Communicating with owners
- **Demand:** ⭐⭐⭐ (a vet shortage + AI speeds things up)
- **How to get there:**
  1. A DVM degree
  2. An AI tool certification
  3. A specialty practice
- **Picture this:** a family doctor for patients who can't talk. AI helps you hear them.

---

#### 107. Physical Therapist + AI = AI Movement Coach

- **What they do:** A PT + AI motion analysis (Sword Health, Hinge Health) for personalized rehab and injury prevention.
- **Key skills:**
  - A DPT foundation
  - Literacy in motion analysis tools
  - Tele-rehab workflows
  - Patient engagement
  - Measuring outcomes
- **Demand:** ⭐⭐⭐⭐ (platforms such as Sword Health and Hinge Health)
- **How to get there:**
  1. A DPT degree
  2. Training on a tele-PT platform
  3. A specialty certification
- **Picture this:** an Olympic-level coach and analysis for an ordinary patient. AI sees how you move.

---

#### 108. Psychiatrist + AI = AI-Augmented Mental Health Specialist

- **What they do:** A psychiatrist + AI for symptom tracking, predicting medication response and support between visits.
- **Key skills:**
  - An MD + psychiatry foundation
  - AI literacy + safety
  - Integrating digital therapeutics
  - Privacy + ethics
  - Navigating the patient-AI relationship
- **Demand:** ⭐⭐⭐⭐ (the mental health crisis + the telepsychiatry explosion)
- **How to get there:**
  1. An MD + a psychiatry residency
  2. A digital health certification
  3. Setting up a hybrid practice
- **Picture this:** a psychiatrist with an AI journal for every patient. Sees patterns over months, not just during the office visit.

---

#### 109. Optometrist + AI = AI Vision Specialist

- **What they do:** An optometrist + AI retinal scans (Eyenuk, LumineticsCore, formerly IDx-DR) to detect diabetic retinopathy, glaucoma and AMD.
- **Key skills:**
  - An OD foundation
  - Literacy in AI screening tools
  - Patient education
  - Referral pathways
  - Telehealth integration
- **Demand:** ⭐⭐⭐ (FDA-cleared AI screening tools are already in use)
- **How to get there:**
  1. An OD degree
  2. An AI tool certification
  3. Integrating it into a practice
- **Picture this:** eye doctor + AI = an eye disease detector in a minute. Problems that used to go unnoticed for years.

---

#### 110. Cardiologist + AI = AI Cardiology Specialist

- **What they do:** A cardiologist + AI on ECG, echo and cardiac MRI (Ultromics and similar tools). Helps spot heart problems earlier.
- **Key skills:**
  - An MD + cardiology foundation
  - Literacy in AI imaging tools
  - Integrating wearable data (Apple Watch, KardiaMobile)
  - Patient-facing AI tools
  - Quality assurance
- **Demand:** ⭐⭐⭐⭐⭐ (cardiovascular disease is the leading cause of death worldwide, and AI tools for it are relatively mature)
- **How to get there:**
  1. An MD + a cardiology fellowship
  2. An AI imaging certification
  3. A research role or a role as the clinic's AI champion
- **Picture this:** cardiologist + AI = an early-warning system for the heart. Prevention instead of resuscitation.

---

### B7. Government / Public Sector (10 careers)

---

#### 111. Police Officer + AI = AI-Augmented Officer

- **What they do:** An officer + body cam AI + predictive analytics + AI report writing (Axon Draft One).
- **Key skills:**
  - A police academy foundation
  - AI tool literacy
  - Bias awareness
  - Knowledge of civil liberties
  - Community engagement
- **Demand:** ⭐⭐⭐ (Axon is the best-known vendor; the debate over these tools continues)
- **How to get there:**
  1. The police academy
  2. An AI body cam certification
  3. Community policing training
- **Picture this:** an officer with an AI partner. AI writes the reports; the officer works with people.

---

#### 112. Judge + AI = AI-Assisted Judiciary

- **What they do:** A judge + AI for legal research, precedent search and sentencing recommendations (controversial).
- **Key skills:**
  - A JD + judicial experience
  - AI tool literacy
  - Awareness of AI bias
  - Constitutional law
  - Ethics
- **Demand:** ⭐⭐⭐ (slow adoption because of ethical concerns)
- **How to get there:**
  1. A JD + the bar
  2. Legal AI training
  3. Judicial appointment or election
- **Picture this:** a judge and a librarian of all the law in one person. AI suggests; the human decides.

---

#### 113. Urban Planner + AI = Smart City Planner

- **What they do:** An urban planner + AI simulation for traffic, zoning, public services and climate adaptation.
- **Key skills:**
  - An urban planning foundation
  - GIS + ML
  - Stakeholder engagement
  - Simulation tools
  - Equity analysis
- **Demand:** ⭐⭐⭐⭐ (the smart city investment wave)
- **How to get there:**
  1. An MPA or an urban planning degree
  2. A GIS + data science certification
  3. A job with a city or county
- **Picture this:** the architect of a city that runs like a machine. Every decision is tested in a simulation 1,000 times.

---

#### 114. Social Worker + AI = AI-Enabled Caseworker

- **What they do:** A social worker + AI for prioritizing cases, checking benefit eligibility and assessing risk.
- **Key skills:**
  - An MSW foundation
  - AI tool literacy
  - Bias + ethics awareness
  - Trauma-informed care
  - Navigating resources
- **Demand:** ⭐⭐⭐⭐ (reducing caseloads is the mission)
- **How to get there:**
  1. An MSW degree
  2. AI tool training
  3. A job with an agency
- **Picture this:** a social worker with an AI assistant who handles the documentation. More time with people, less with paperwork.

---

#### 115. Tax Auditor + AI = AI-Augmented Auditor

- **What they do:** An auditor + AI for anomaly detection, recognizing fraud patterns and selecting returns for audit.
- **Key skills:**
  - An accounting/audit foundation
  - AI tool literacy
  - Data analysis
  - Communication
  - Regulatory awareness
- **Demand:** ⭐⭐⭐⭐ (the Big Four + IRS modernization)
- **How to get there:**
  1. A CPA foundation
  2. A data analytics specialization
  3. A job at a Big Four firm or an agency
- **Picture this:** an auditor with a million AI eyes on every transaction. Anomalies show up in seconds.

---

#### 116. Customs Officer + AI = AI Border Specialist

- **What they do:** A border agent + AI scanning (cargo, faces, behavior). Tradeoffs against civil liberties.
- **Key skills:**
  - Customs/border training
  - Literacy in AI scanning tools
  - Knowledge of international trade
  - Bias awareness
  - Languages + cultural knowledge
- **Demand:** ⭐⭐⭐ (ICE, CBP modernization)
- **How to get there:**
  1. Federal law enforcement training
  2. An AI tool certification
  3. A specialty assignment
- **Picture this:** a customs officer with an X-ray that sees for miles around. Controversial, but real.

---

#### 117. Military Officer + AI = AI Strategy Officer

- **What they do:** A military officer + AI for intelligence analysis, mission planning and battlefield awareness.
- **Key skills:**
  - Military training (academy + experience)
  - AI tool literacy
  - International law (LOAC)
  - Strategic thinking
  - Cybersecurity
- **Demand:** ⭐⭐⭐⭐ (Palantir, Anduril, traditional defense)
- **How to get there:**
  1. A military academy or a commission
  2. An AI defense certification
  3. A joint duty or specialty assignment
- **Picture this:** commander + AI = a general who sees the whole field at once. Decisions in seconds, not days.

---

#### 118. Diplomat + AI = AI Translation/Analysis Specialist

- **What they do:** A diplomat + AI translation + sentiment analysis + cultural intelligence.
- **Key skills:**
  - An international relations background
  - Literacy in AI translation tools (their limits + risks)
  - A multilingual baseline
  - Cultural intelligence
  - Negotiation
- **Demand:** ⭐⭐⭐ (State Department modernization, NGOs)
- **How to get there:**
  1. An IR degree + the Foreign Service exam
  2. AI tool training
  3. A posting abroad
- **Picture this:** a diplomat with an AI assistant. Understands not just the words but the context across cultures.

---

#### 119. Public Health Officer + AI = AI Epidemiologist

- **What they do:** Public health + AI for epidemic forecasting, contact tracing and planning interventions.
- **Key skills:**
  - An MPH foundation
  - Time-series ML
  - Geospatial analysis
  - Public communication
  - Crisis management
- **Demand:** ⭐⭐⭐⭐ (post-COVID investment + ongoing threats)
- **How to get there:**
  1. An MPH degree
  2. Data science training
  3. A job at the CDC, the WHO or a state health department
- **Picture this:** a lookout for epidemics. AI can pick up the signs of an outbreak before it makes the news.

---

#### 120. Election Officer + AI = AI Verification Specialist

- **What they do:** An election administrator + AI for signature verification, ballot processing and misinformation detection.
- **Key skills:**
  - Election administration
  - AI tool literacy
  - Security + audit trails
  - Public trust + transparency
  - Regulatory compliance
- **Demand:** ⭐⭐ (slow adoption, controversial)
- **How to get there:**
  1. A career in election administration
  2. AI tool training
  3. A job with a state or county
- **Picture this:** the guardian of an honest vote. AI speeds things up; a human guarantees the result.

---

### B8. Religion / Philosophy / Coaching (5 careers)

---

#### 121. Pastor / Priest + AI = AI-Augmented Spiritual Counselor

- **What they do:** A member of the clergy + AI for sermon prep, biblical research and following up with congregants (boundaries are critical).
- **Key skills:**
  - A theological foundation
  - AI tool literacy
  - Boundaries + discernment
  - Pastoral care
  - Community building
- **Demand:** ⭐⭐ (slow adoption, but growing)
- **How to get there:**
  1. Seminary/ministry training
  2. AI tool training
  3. A congregation or community role
- **Picture this:** pastor + AI = an expanded library. The human heart always comes first.

---

#### 122. Philosophy Professor + AI = AI Ethics Educator

- **What they do:** A philosophy professor with an AI ethics specialty. Teaches students to think critically about AI ethics.
- **Key skills:**
  - A philosophy PhD
  - The AI ethics literature
  - Pedagogy
  - Engaging with industry
  - Public communication
- **Demand:** ⭐⭐⭐⭐ (more and more universities offer AI ethics courses)
- **How to get there:**
  1. A philosophy PhD
  2. An AI ethics specialization
  3. Faculty work + consulting
- **Picture this:** a teacher of wisdom in an age of speed. AI is fast; wisdom is slow. You need both.

---

#### 123. Life Coach + AI = AI Personal Development Coach

- **What they do:** A coach + AI for goal tracking, habit reinforcement and support between sessions (Replika-style, done right).
- **Key skills:**
  - A coaching certification (ICF)
  - AI tool literacy
  - Boundaries
  - Marketing + sales
  - Privacy awareness
- **Demand:** ⭐⭐⭐ (the coaching industry is growing, and AI fits it)
- **How to get there:**
  1. An ICF coaching certification
  2. AI tool training
  3. Build a practice
- **Picture this:** a coach + the client's AI journal. Sees patterns over months while meeting once a week.

---

#### 124. Career Counselor + AI = AI Career Navigator

- **What they do:** A career counselor + AI for job market analysis, skill gap assessment and personalized career paths.
- **Key skills:**
  - A counseling foundation
  - AI tool literacy
  - Job market data analysis
  - Industry awareness
  - Empathy
- **Demand:** ⭐⭐⭐⭐ (career disruption = a need for guides)
- **How to get there:**
  1. An MS in counseling or a career development certificate
  2. AI tool training
  3. A university, a nonprofit or a private practice
- **Picture this:** a navigator in turbulent times. AI sees the map; the human knows you.

---

#### 125. Meditation Teacher + AI = AI Mindfulness Guide

- **What they do:** A meditation teacher + AI personalization (Headspace, Calm, Balance + AI).
- **Key skills:**
  - A meditation teaching certification
  - AI tool literacy
  - Personalization design
  - Boundaries
  - Cultural sensitivity
- **Demand:** ⭐⭐⭐ (the mental health crisis + technology)
- **How to get there:**
  1. Meditation teacher training (MBSR, etc.)
  2. Collaborating with AI apps
  3. Build an audience
- **Picture this:** teacher + AI = a personal meditation for everyone. Not "one size fits all" but "for you, right now".

---

### B9. Sports / Athletics (10 careers)

---

#### 126. Athlete + AI = AI-Trained Performer

- **What they do:** An athlete + AI for biomechanics analysis, nutrition optimization, sleep and mental prep.
- **Key skills:**
  - An elite athletic foundation
  - Comfort with AI tools
  - Interpreting data
  - Self-discipline
  - Working with coaches
- **Demand:** ⭐⭐⭐ (elite athletes increasingly work with data teams)
- **How to get there:**
  1. Athletic excellence (one path)
  2. Data literacy
  3. A coach + tech partnership
- **Picture this:** Olympic athlete + AI = a 1% improvement every day. A year later, a level nobody else can reach.

---

#### 127. Coach + AI = AI Performance Coach

- **What they do:** A coach + AI for video analysis, scouting opponents and optimizing training plans.
- **Key skills:**
  - A coaching foundation (years of experience)
  - AI video analysis tools (Hudl, Sportscode)
  - Interpreting data
  - Communicating with athletes
  - Strategy
- **Demand:** ⭐⭐⭐⭐ (data + AI are now table stakes)
- **How to get there:**
  1. A coaching career
  2. A sports analytics certification
  3. Moving up through results
- **Picture this:** a coach with a second brain. Sees patterns in every game and predicts what opponents will do.

---

#### 128. Referee + AI = AI-Augmented Official

- **What they do:** A referee + VAR-style AI for decision support during the game.
- **Key skills:**
  - A refereeing foundation
  - AI tool literacy
  - Real-time decision-making
  - Communication
  - Handling pressure
- **Demand:** ⭐⭐⭐ (the controversy continues, but it's growing)
- **How to get there:**
  1. Officiating training + experience
  2. An AI tool certification
  3. Moving up the levels
- **Picture this:** referee + AI = fewer mistakes, more trust. (If it's implemented well.)

---

#### 129. Sports Scout + AI = AI Talent Scout

- **What they do:** A scout + AI for player evaluation, draft prediction and tracking prospects.
- **Key skills:**
  - Deep sports knowledge
  - Data analytics
  - Travel + networking
  - Pattern recognition
  - Communication
- **Demand:** ⭐⭐⭐ (the data-driven scouting wave)
- **How to get there:**
  1. A playing or coaching foundation
  2. An analytics specialty
  3. A job with a team
- **Picture this:** scout + AI = spotting a future star in a high school kid. It used to be gut feel. Now it's gut feel + 1,000 metrics.

---

#### 130. Sports Commentator + AI = AI Multilingual Caster

- **What they do:** A broadcaster + AI for real-time stats, multilingual translation and fact-checking.
- **Key skills:**
  - A broadcasting foundation
  - Deep sports knowledge
  - Comfort with AI tools
  - Performing live under pressure
  - Storytelling
- **Demand:** ⭐⭐⭐ (streaming + multilingual content)
- **How to get there:**
  1. A journalism / broadcasting foundation
  2. A sports specialty
  3. Integrating AI tools
- **Picture this:** commentator + AI = stats in real time. Every player, every game.

---

#### 131. Trainer + AI = AI Conditioning Specialist

- **What they do:** A strength and conditioning coach + AI for load management, injury prevention and timing peak performance.
- **Key skills:**
  - An S&C certification (NSCA CSCS)
  - Interpreting data from AI wearables
  - Periodization
  - Sport-specific training
  - Communicating with athletes
- **Demand:** ⭐⭐⭐⭐ (pro teams)
- **How to get there:**
  1. An exercise science degree + CSCS
  2. AI tool training (Catapult, Whoop)
  3. A job with a pro team
- **Picture this:** trainer + AI = training under a microscope. Knows when to push and when to rest.

---

#### 132. Sports Medicine + AI = AI Injury Prediction Specialist

- **What they do:** A sports medicine physician + AI for injury risk prediction, return-to-play decisions and recovery optimization.
- **Key skills:**
  - An MD/DO in sports medicine
  - AI tool literacy
  - Biomechanics
  - Interpreting imaging
  - Relationships with players
- **Demand:** ⭐⭐⭐⭐ (injuries are costly for teams, and AI helps manage the risk)
- **How to get there:**
  1. An MD + a sports medicine fellowship
  2. An AI tool certification
  3. A job with a team
- **Picture this:** a team doctor with a crystal ball. Predicts an injury weeks ahead.

---

#### 133. Sports Manager + AI = AI Team Strategist

- **What they do:** A general manager + AI for player valuation, contract negotiation analytics and salary cap optimization.
- **Key skills:**
  - An MBA or an extensive sports business background
  - Advanced analytics
  - Negotiation
  - Mastery of the salary cap
  - Long-term planning
- **Demand:** ⭐⭐⭐ (few top jobs, but they're big ones)
- **How to get there:**
  1. A sports business career
  2. Working your way up the front office
  3. Fluency in analytics
- **Picture this:** GM + AI = chess 50 moves ahead. Players + contracts + the salary cap.

---

#### 134. E-sports Coach + AI = AI Gaming Performance Coach

- **What they do:** An e-sports coach + AI replay analysis + opponent prediction + the mental game.
- **Key skills:**
  - Gaming expertise (specific titles)
  - AI replay tools
  - Mental performance
  - Communicating with young players
  - Streaming awareness
- **Demand:** ⭐⭐⭐ (e-sports is professionalizing)
- **How to get there:**
  1. A gaming career or an analyst path
  2. Coaching certifications
  3. A job with a team
- **Picture this:** a coach for gaming, where reflexes + AI analysis = a championship.

---

#### 135. Sports Journalism + AI = AI Sports Analyst

- **What they do:** A journalist + AI for data-driven storytelling, real-time analysis and multi-platform content.
- **Key skills:**
  - A journalism foundation
  - Sports knowledge
  - AI tool literacy
  - Multi-platform content
  - Audience engagement
- **Demand:** ⭐⭐⭐ (The Athletic + ESPN + newcomers)
- **How to get there:**
  1. A journalism degree or path
  2. A sports beat
  3. Integrating AI tools
- **Picture this:** journalist + AI = data + story. It used to be the fact. Now it's the fact + 1,000 pieces of context.

---

### B10. Manufacturing / Logistics (15 careers)

---

#### 136. Assembly Worker + AI = AI-Augmented Operator

- **What they do:** A factory worker + AR glasses + AI guidance for assembly and quality checks.
- **Key skills:**
  - A manufacturing foundation
  - Comfort with AR glasses
  - AI tool literacy
  - Quality awareness
  - Adaptability
- **Demand:** ⭐⭐⭐ (Industry 4.0 adoption)
- **How to get there:**
  1. A manufacturing job
  2. AR/AI tool training
  3. Upskilling into a specialty
- **Picture this:** worker + smart glasses = every part done right. AI catches mistakes before they leave the line.

---

#### 137. Warehouse Worker + AI = AI-Picker Hybrid

- **What they do:** A warehouse worker + AI picking guidance + working alongside robots (Amazon, GXO, Locus Robotics).
- **Key skills:**
  - A warehouse foundation
  - Working alongside robots
  - AI tool literacy
  - Physical fitness
  - Safety awareness
- **Demand:** ⭐⭐⭐⭐ (large warehouses automate first, and others follow)
- **How to get there:**
  1. Get hired at a warehouse
  2. Robot training
  3. Lead/specialist roles
- **Picture this:** picker + AI robot = a team. The robot hauls; the person thinks.

---

#### 138. Truck Driver + AI = AI-Autonomy Supervisor

- **What they do:** A truck driver + monitoring autonomous trucks (Aurora, Kodiak).
- **Key skills:**
  - A CDL foundation
  - Skills for supervising AI
  - Edge case decision-making
  - Safety
  - Logistics awareness
- **Demand:** ⭐⭐⭐ (a transition phase in 2026-2030)
- **How to get there:**
  1. CDL training
  2. An autonomous truck certification
  3. A job at Aurora, Kodiak or a similar company
- **Picture this:** a ship's captain + autopilot. The autopilot steers; the captain takes the edge cases.

---

#### 139. Pilot + AI = AI-Augmented Pilot

- **What they do:** A commercial pilot + AI autopilot + AI flight planning + AI fatigue monitoring.
- **Key skills:**
  - An ATP certificate or military flying experience
  - AI tool literacy
  - Crisis management
  - CRM (crew resource management)
  - Continuous training
- **Demand:** ⭐⭐⭐ (a pilot shortage, and AI augments)
- **How to get there:**
  1. Flight training (a long road)
  2. Working your way up at an airline
  3. AI augmentation training
- **Picture this:** pilot + AI = a double cockpit. Neither one replaces the other; AI augments.

---

#### 140. Air Traffic Controller + AI = AI Traffic Optimizer

- **What they do:** An air traffic controller + AI for traffic optimization, conflict prediction and weather routing.
- **Key skills:**
  - ATC certification (FAA / EASA)
  - AI tool literacy
  - Crisis management
  - Multitasking
  - Staying calm under pressure
- **Demand:** ⭐⭐⭐ (FAA modernization)
- **How to get there:**
  1. The FAA Academy
  2. ATC certification
  3. AI tool training
- **Picture this:** a conductor of the sky + AI. AI warns about conflicts minutes ahead.

---

#### 141. Ship Captain + AI = AI Marine Operator

- **What they do:** A captain + monitoring autonomous ships (Yara Birkeland, ASKO autonomous vessels).
- **Key skills:**
  - Maritime training
  - AI tool literacy
  - Weather + navigation
  - Crisis management
  - Logistics
- **Demand:** ⭐⭐ (slow adoption, but growing)
- **How to get there:**
  1. A maritime academy
  2. Sea time + certifications
  3. Training on AI vessels
- **Picture this:** captain + autonomous ship = a smaller crew, more technology.

---

#### 142. Postal Worker + AI = AI-Augmented Delivery Specialist

- **What they do:** Delivery + AI routing + drone integration + optimizing every customer touchpoint.
- **Key skills:**
  - A delivery foundation
  - Literacy in AI routing tools
  - Drone basics (where it applies)
  - Customer service
  - Physical fitness
- **Demand:** ⭐⭐⭐⭐ (Amazon, UPS, FedEx, USPS)
- **How to get there:**
  1. A delivery job
  2. AI tool training
  3. Specialty roles
- **Picture this:** mail carrier + AI = a route optimized every day. Happy customers.

---

#### 143. Cleaner + AI = AI-Powered Facility Manager

- **What they do:** A cleaner + managing a fleet of AI robots (Avidbots, Whiz robots).
- **Key skills:**
  - A cleaning industry foundation
  - Robot fleet management
  - AI tool literacy
  - Quality assurance
  - Customer service
- **Demand:** ⭐⭐⭐ (the commercial cleaning automation wave)
- **How to get there:**
  1. Cleaning industry experience
  2. A robot operation certification
  3. A management role
- **Picture this:** cleaner + a fleet of robots = cleaner, faster, cheaper. Managing, not mopping.

---

#### 144. Security Guard + AI = AI Surveillance Operator

- **What they do:** A guard + AI cameras + behavior analysis + threat prediction.
- **Key skills:**
  - Security training
  - AI tool literacy
  - Bias awareness
  - Staying calm under pressure
  - Customer service
- **Demand:** ⭐⭐⭐ (Verkada, Rhombus, growing)
- **How to get there:**
  1. A security guard license or certification
  2. AI tool training
  3. A specialty assignment
- **Picture this:** a guard + 1,000 AI cameras = one person sees what 10 couldn't before.

---

#### 145. Construction Worker + AI = AI-Augmented Builder

- **What they do:** Construction + AI plan visualization + AR guidance + safety monitoring.
- **Key skills:**
  - A construction trade foundation
  - AR/AI tool literacy
  - Safety awareness
  - Reading plans
  - Teamwork
- **Demand:** ⭐⭐⭐⭐ (the construction tech wave)
- **How to get there:**
  1. A trade apprenticeship
  2. AI/AR tool training
  3. Specialty roles
- **Picture this:** builder + AR glasses = the blueprint right there on site. Fewer mistakes, faster work.

---

#### 146. Quality Inspector + AI = AI Vision Inspector

- **What they do:** Quality control + AI computer vision for defect detection in manufacturing.
- **Key skills:**
  - A QC foundation
  - Literacy in AI vision tools
  - Statistical process control
  - Reading specifications
  - Communication
- **Demand:** ⭐⭐⭐⭐ (factories of every kind)
- **How to get there:**
  1. QC training
  2. An AI tool certification
  3. An industry specialization
- **Picture this:** QC + an AI eye = every part checked. A 100% sample size, which used to be impossible.

---

#### 147. Logistics Manager + AI = AI Supply Chain Coordinator

- **What they do:** A logistics manager + AI for route optimization, exception management and vendor coordination.
- **Key skills:**
  - A supply chain foundation
  - AI tool literacy (TMS, WMS)
  - Vendor management
  - Handling exceptions
  - Data analysis
- **Demand:** ⭐⭐⭐⭐ (shippers and carriers)
- **How to get there:**
  1. A logistics career
  2. AI tool training
  3. Moving up into management
- **Picture this:** logistics + AI = fewer exceptions, better service.

---

#### 148. Procurement Specialist + AI = AI Buyer

- **What they do:** Procurement + AI for vendor analysis, spend optimization and contract intelligence.
- **Key skills:**
  - A procurement foundation
  - AI tool literacy
  - Negotiation
  - Contract review
  - Spend analysis
- **Demand:** ⭐⭐⭐ (large companies)
- **How to get there:**
  1. A procurement career
  2. AI tool training
  3. A specialty (direct/indirect, services)
- **Picture this:** buyer + AI = knows the market as well as the vendors do. Fewer overpayments.

---

#### 149. Inventory Manager + AI = AI Stock Optimizer

- **What they do:** An inventory manager + AI for demand forecasting, optimization and replenishment.
- **Key skills:**
  - An inventory management foundation
  - AI forecasting tools
  - ERP fluency
  - Statistical understanding
  - Communication
- **Demand:** ⭐⭐⭐⭐ (retail + e-commerce + manufacturing)
- **How to get there:**
  1. An SCM degree or experience
  2. AI tool training
  3. An industry specialization
- **Picture this:** inventory + AI = the right stock at the right time. Not "how much we'd like" but "how much we need".

---

#### 150. Production Manager + AI = AI Manufacturing Engineer

- **What they do:** A production manager + AI for scheduling, capacity planning and OEE optimization.
- **Key skills:**
  - A manufacturing foundation
  - AI tool literacy
  - Lean / Six Sigma
  - Team management
  - Interpreting data
- **Demand:** ⭐⭐⭐⭐ (Industry 4.0)
- **How to get there:**
  1. A manufacturing/IE degree
  2. Plant experience
  3. AI tool training
- **Picture this:** production manager + AI = less downtime, more output. Every minute counts.

---

## <a id="c-extended"></a>🔥 Section C-Extended: 25 disappearing jobs

We're expanding the list from 10 to 25: here are 15 more.

---

#### 11. Bookkeeper (basic)

- **What's being replaced:** AI bookkeeping (Pilot, QuickBooks automation and similar tools).
- **What survives:** Senior accountants + CPAs + specialists in complex entities.
- **Picture this:** the Excel ninja loses the job. The CPA with an advisory mindset wins.

---

#### 12. Court Stenographer

- **What's being replaced:** AI transcription + summarization (Verbit, Trint).
- **What survives:** Realtime captioners for accessibility, specialty legal recording.
- **Picture this:** the courtroom typist is on the way out. The certified court reporter for critical cases stays.

---

#### 13. Travel Agent (basic)

- **What's being replaced:** AI travel planning (ChatGPT + Booking.com + Kayak).
- **What survives:** Luxury/specialty travel agents (for personal connections and concierge service).
- **Picture this:** the basic 1990s-style agent is on the way out. The concierge with private contacts stays.

---

#### 14. Drive-Through Cashier

- **What's being replaced:** AI voice ordering (pilots at several fast-food chains, such as Wendy's).
- **What survives:** Friendly hosts in customer experience roles.
- **Picture this:** a drive-through window with no person: an AI voice takes your order.

---

#### 15. Telemarketer

- **What's being replaced:** AI voice agents (cheaper, never tired).
- **What survives:** High-value B2B SDRs for complex sales (where the relationship matters).
- **Picture this:** the cold caller making routine calls is on the way out. The SDR with domain expertise stays.

---

#### 16. Library Cataloger

- **What's being replaced:** AI metadata extraction + classification.
- **What survives:** Librarians as research consultants, digital archivists.
- **Picture this:** the cataloger is on the way out. The librarian who helps people find information stays.

---

#### 17. Toll Booth Operator

- **What's being replaced:** Electronic tolling + license plate readers (it's almost gone already).
- **What survives:** It barely exists anymore.
- **Picture this:** a booth with a person in it is a leftover. Everything is cashless now, like E-ZPass.

---

#### 18. Bank Teller

- **What's being replaced:** Mobile banking + AI customer service.
- **What survives:** Wealth management advisors, specialists in complex transactions.
- **Picture this:** the basic teller window is on the way out. The personal banker for \$1M+ accounts stays.

---

#### 19. Newspaper Delivery

- **What's being replaced:** Digital subscriptions, a shrinking print industry.
- **What survives:** A much smaller service (kept mostly for long-time subscribers).
- **Picture this:** the kid on a bike at 5 a.m. is gone. A push notification shows up instead.

---

#### 20. Movie Ticket Sales

- **What's being replaced:** Self-serve kiosks + mobile apps.
- **What survives:** Cinema experience hosts (specialty IMAX, premium screens).
- **Picture this:** the box office window is on the way out. The QR code is in.

---

#### 21. Encyclopedia Salesperson (already gone)

- **What it was:** Selling full sets door to door.
- **What replaced it:** Wikipedia + Google + Claude.
- **Picture this:** it's already history. A memento mori that other professions can learn from.

---

#### 22. Print Magazine Editor (basic)

- **What's being replaced:** Digital-first publishing + AI content generation.
- **What survives:** Specialty/luxury print (Monocle, Apartamento), digital editors-in-chief.
- **Picture this:** the mass-market magazine is on the way out. Niche print + digital stay.

---

#### 23. Phone Book Publisher (already gone)

- **What it was:** The Yellow Pages + White Pages, every year.
- **What replaced it:** Google Maps + LinkedIn + Yelp.
- **Picture this:** memento mori. A heavy book on the doorstep belongs only in the archive now.

---

#### 24. Stockbroker (entry-level retail)

- **What's being replaced:** Robo-advisors (Wealthfront, Betterment) + commission-free trading.
- **What survives:** Advisors for high-net-worth clients, specialists in options + alternatives.
- **Picture this:** the retail broker working on commission is on the way out. The wealth manager doing holistic planning stays.

---

#### 25. Travel Booking Clerk

- **What's being replaced:** Self-service booking + AI assistants.
- **What survives:** Specialty corporate travel managers.
- **Picture this:** the clerk who types up bookings at the travel agency is on the way out. The corporate travel architect stays.

---

## <a id="d-extended"></a>🛠 Section D-Extended: 50 skills for the future

Expanding from 25 to 50.

### AI-Specific Technical (25 new)

#### 26. AI Prompt Versioning

A systematic approach to version-controlling prompts like code: git, A/B tests, rollback.

#### 27. LLM Cost Forecasting

Forecasting costs from usage patterns. Capacity planning in \$\$\$.

#### 28. Multi-Agent Debugging

Tracing how agents communicate, finding failure modes, getting to the root cause of distributed bugs.

#### 29. Voice Agent Tuning

Optimizing latency + naturalness + how interruptions are handled.

#### 30. RAG Architecture Design

Chunking strategies, retrieval rerankers, multimodal RAG.

#### 31. Local Model Fine-Tuning

LoRA, QLoRA, hardware-aware optimization on consumer GPUs.

#### 32. AI Safety Auditing

Red-teaming, adversarial probing, alignment evaluation.

#### 33. Constitutional AI Design

Translating principles into behaviors for AI systems.

#### 34. AI Ethics Judgment

Resolving conflicts between competing principles; contextual ethics.

#### 35. Cross-Cultural AI Deployment

Tuning AI behavior for different cultures, languages and value systems.

#### 36. AI Procurement

Vendor evaluation, contracts, SLAs, data ownership.

#### 37. AI Vendor Negotiation

Pricing, commitments, data clauses, awareness of switching costs.

#### 38. Tax/Legal AI Implications

Understanding the tax implications of using AI and its impact on employment law (the details are a question for your accountant or attorney).

#### 39. AI Insurance Literacy

Understanding insurance for AI deployments (errors, IP, liability).

#### 40. Hybrid Workflow Design

Designing human-AI workflows (handoffs, oversight, the limits of autonomy).

#### 41. AI-Human Team Management

Managing teams where people and agents work together.

#### 42. AI Cost Benchmarking

Comparing costs across providers + workloads.

#### 43. AI Evaluation Methodology

Building evals, golden datasets, regression testing.

#### 44. AI Red Teaming

Adversarial testing of systems before deployment.

#### 45. AI Bias Testing

Fairness across demographics; discovering edge cases.

#### 46. Agent Capability Assessment

Evaluating what an agent can and can't do reliably.

#### 47. AI Memory Architecture

Designing long-term, working and episodic memory for agents.

#### 48. Tool Use Design

When and how to give agents tools vs keeping them prompt-only.

#### 49. MCP Server Creation

Building Model Context Protocol servers.

#### 50. Local AI Ops

Running on-premises AI infrastructure (Ollama, LM Studio, vLLM).

---

## <a id="section-f"></a>📅 Section F: Year-by-year forecast 2027-2030

> **Disclaimer:** These are the author's scenarios, not facts. The numbers in this section have been removed; only the directions remain.

---

### 2027: the year of agents

**The main shift:** Autonomous agents move from demos into production. Voice AI becomes the default interface for many use cases.

**Key technical shifts:**

- Reliable autonomous agents in production (mainstream adoption in the Fortune 500)
- Voice-first interfaces become familiar
- AI cost: tokens are expected to get noticeably cheaper (a forecast, not a fact)
- Multi-agent systems with 5-20 agents become routine in production

**Growing careers (top 10 by growth in demand):**

| # | Career |
|---|---|
| 1 | AI Agent Architect |
| 2 | Voice AI Developer |
| 3 | AI Cost Optimizer |
| 4 | AI Adoption Specialist |
| 5 | Smart Glasses App Developer |
| 6 | AI Ethics Officer |
| 7 | AI-Augmented Lawyer/Doctor |
| 8 | AI Quality Engineer |
| 9 | AI Auditor |
| 10 | AI Education Designer |

**Declining careers (top 5):**

| # | Career |
|---|---|
| 1 | Junior copywriter |
| 2 | Tier-1 support |
| 3 | Entry-level translator |
| 4 | Routine paralegal |
| 5 | Data entry |

---

### 2028: the year of specialization

**The main shift:** The commodity layer of AI matures. The winners are vertical AI specialists (healthcare, legal, finance).

**Key technical shifts:**

- The commodity layer of AI matures (differences between frontier models shrink for most use cases)
- Vertical AI winners emerge (healthcare, legal, finance), with moats built on domain data + compliance
- Local AI gets close to frontier models in quality (a forecast)
- Multimodal becomes the default (text + voice + vision in every app)

**Growing careers:**

- Vertical AI specialists (deep industry knowledge): demand for AI in healthcare, legal, finance
- Local AI deployment engineers
- AI safety / red team
- AI compliance roles
- AI procurement managers

**Declining:**

- The generic "AI engineer" (a commodity)
- Junior software engineers (replaced by senior people + AI; companies hire fewer)
- Mid-level analysts (AI does the work; companies hire fewer)

**New careers emerging in 2028:**

- **AI Litigation Specialist**: lawsuits between AI and people (IP, harm, wrongful decisions)
- **AI Insurance Adjuster**: handling AI-related claims (errors, accidents, liability)
- **AI Public Defender Tech**: using AI to provide legal services to underserved people
- **AI Patent Specialist**: IP for AI-generated works
- **AI Restitution Counselor**: helping people displaced by AI find new paths

---

### 2029: pre-AGI tension

**The main shift:** Models approach near-unbounded reasoning. Some professions are disrupted dramatically. Regulatory frameworks are fully active.

**Key technical shifts:**

- Models approach unbounded reasoning (mathematical problem solving, original research)
- Some professions are disrupted dramatically (research, complex code, even creative work)
- Regulatory frameworks are fully in place (the EU AI Act, US federal and state rules, China's AI rules)
- Discussions about an AI treaty begin (geopolitics)
- AI-mediated economic activity = a significant % of GDP

**Growing:**

- AI Safety Researchers (rare expertise)
- AI Alignment Engineers
- AI Constitutional Engineers (designing value systems)
- AI Governance Specialists (policy + technical)
- AI Insurance/Liability specialists

**Declining (sharply):**

- Many entry-level knowledge jobs (a "gap year" crisis for new graduates)
- Mid-level managers (AI flattens hierarchies)
- Generic content creators (AI has raised the bar dramatically)

**Crisis points:**

- Universities struggle to define what to teach graduates
- A generation gap (people born in 2010+ never experienced work before AI)
- Some countries turn protectionist (job preservation laws)

---

### 2030: a new equilibrium

**The main shift:** AI is universal in knowledge work (assuming no AGI breakthrough). Human-AI augmentation is the norm.

**Key technical shifts:**

- AI is universal in knowledge work (if there's no AGI yet)
- Human-AI augmentation = the new norm (like computers in the 2000s)
- Companies appear where one or two founders work with a large number of AI agents (a forecast)
- Specialized B2B vertical AI winners dominate
- Owning a personal AI becomes part of the culture (like owning a domain name in the 1990s)

**Long-term winners (stable through the AI shift):**

- **AI Safety / Ethics / Compliance**: the need doesn't go away
- **AI-augmented professionals** (doctors, lawyers, etc. with deep domain knowledge): higher productivity, which can mean higher earnings
- **AI Strategy Consultants**: helping companies adopt AI (large companies need guides)
- **Creative directors**: taste matters (AI executes, a human decides)
- **Sales / relationships**: people buy from people (high-trust transactions)

**Long-term losers:**

- Mid-skill routine work (a commodity)
- Generic content production (its price has deflated)
- Basic analyst work (AI did the work)
- Standardized education paths (the world needs adaptive learners)


---

## <a id="section-g"></a>🌍 Section G: Geographic shifts 2026-2030

| Region | Likely to grow | Likely to decline | Why |
|--------|---------|-----------|-----|
| **San Francisco / NYC** | AI safety, frontier research, AI in legal/finance | Generic engineering | Remote AI work commoditizes it |
| **London / Berlin** | Compliance, regulation, AI ethics | Less competitive in pure tech | A hub for EU AI Act compliance |
| **Singapore / Dubai** | AI finance, AI healthcare | Manufacturing | Regulation-friendly + capital |
| **Mumbai / Bangalore** | AI services / outsourcing, hybrid roles | Basic IT services | Hybrid roles dominate |
| **Eastern Europe / Latin America** | AI freelancers / contractors | Local IT support | Cost arbitrage + AI speeds things up |
| **Markets cut off by sanctions or data-sovereignty rules** | Self-hosted AI / "sovereign" AI | Jobs tied to Western platforms | Sanctions + regulation |
| **Tokyo / Seoul** | AI hardware + robotics | Service jobs | Demographics + investment |
| **Tel Aviv** | AI security, defense AI | Generic startups | Specialization + geopolitics |
| **Mexico City / Bogotá** | Nearshore AI engineering for the US | Call centers | Time zone + cost advantage |
| **Lagos / Nairobi** | AI agriculture, AI fintech | Manual labor | Local solutions + leapfrogging |

---

## <a id="section-h"></a>📚 Section H: How skills evolve year by year

### 2026 critical skills (NOW)

- **Prompt engineering** (still high value; the bar for juniors is lower)
- **Python + LLM APIs**
- **MCP integration**
- **Cost engineering** (token budgets, model selection)
- **Basic AI safety** (awareness of prompt injection and jailbreaks)

### 2027 critical skills

- **Multi-agent orchestration** (5+ agents, coordination patterns)
- **Voice AI development** (Vapi, Bland, Retell)
- **Local AI deployment** (Ollama, vLLM, on-premises)
- **Deep AI cost optimization** (caching, distillation, routing)
- **Regulation literacy** (the key articles of the EU AI Act, US federal and state AI rules)

### 2028 critical skills

- **Deep vertical AI domain expertise** (healthcare/legal/finance/etc.)
- **AI safety / red team** (adversarial testing, alignment)
- **Local AI fine-tuning** (LoRA for specific tasks)
- **AI procurement / vendor management**
- **Cross-cultural AI deployment** (multi-region, multilingual)

### 2029-2030 critical skills

- **Understanding AI alignment** (not just safety: alignment)
- **Navigating AI governance** (policy + technical)
- **Hybrid human-AI workflow design**
- **Tax / legal AI literacy**
- **Navigating AI treaties** (geopolitics)
- **AI economics** (jobs, displacement, transition)

---

## <a id="section-i"></a>🛡 Section I: What AI WON'T do before 2030

10 things AI is **very unlikely** to replace by 2030:

### 1. Genuine empathy in moments of crisis

AI imitates empathy, but in moments of real loss, fear or joy, people want people. Hospice, grief counseling, support after a tragedy: these stay human.

### 2. Physical childbirth / breastfeeding

Biology. No AI will give birth to a child. Supporting a birth also stays intimately human.

### 3. Real-time martial arts / combat sports

Physical embodiment + millisecond reflexes + lived training. Robotics is far from Olympic level in 2030.

### 4. Authentic religious / spiritual leadership

Lived experience + community connection + sacred traditions. AI can assist, not lead.

### 5. Original scientific breakthroughs

AI finds patterns in existing data. Breakthroughs often take intuition + serendipity + leaps across fields. Human + AI = a breakthrough, not AI alone.

### 6. Political leadership that requires democratic legitimacy

Voters won't elect an AI. Even if AI were better at policy, legitimacy belongs to humans only.

### 7. Top-tier negotiation involving high-stakes trust

\$100M+ deals, M&A, international treaties. AI prepares; people close.

### 8. Live performance art

Theater, concerts, sports: charisma + presence + risk = people. AI can perform, but the audience experience is different.

### 9. Care work that requires sustained physical presence

Childcare, elder care, hospice care, intimate physical care. Even with robots, people want people.

### 10. Creative direction that requires taste + cultural understanding

AI does most of the hands-on creative execution. The question of "what to make and why" stays with a person (taste, the cultural moment, vision).

---

## <a id="section-j"></a>👥 Section J: The hybrid economy: 3 archetypes for 2030

By 2030, most knowledge workers will fit one of 3 archetypes:

---

### Archetype 1: AI-Native Specialist

**Pattern:**

- 60-70% of their time working with AI
- 100% specialized in a domain (legal, medical, engineering, etc.)
- High productivity through AI augmentation

**Examples:** AI-Augmented Surgeon, AI Cardiologist, AI Lawyer, AI Architect


**Lifestyle:**

- Deep work + occasional time with clients or patients
- Continuous learning (AI tools update quarterly)
- Higher productivity, which can mean higher earnings (but a risk of burnout)
- Often anchored to a city (clients, hospitals, courts)

**Picture this:** an Olympic athlete in their own field. AI is the coach + the analytics + the scoreboard.

---

### Archetype 2: Human-Centric Connector

**Pattern:**

- 20% AI / 80% relationships
- Sales, leadership, therapy, religion, hospitality
- Trust + presence = the main value

**Examples:** Sales executive, CEO, therapist, pastor, concierge, executive coach


**Lifestyle:**

- Travel, meetings, building a network
- Emotional intelligence as the primary skill
- AI handles the admin; the human handles the relationships
- Geographic flexibility (go where the people are)

**Picture this:** a human conductor. AI is an orchestra of instruments; the human is the chemistry in the room.

---

### Archetype 3: Solo AI Empire

**Pattern:**

- 90% AI / 10% strategy
- A founder with 10 agents
- High autonomy, high risk

**Examples:** A solo SaaS founder, an AI agency owner, a content creator-entrepreneur, a real estate investor with AI-run operations


**Lifestyle:**

- High autonomy, location-independent
- Income that swings a lot
- A risk of loneliness (no team)
- Constant experimentation

**Picture this:** a ship's captain whose 10 sailors are all AI. Sets the course and reaps the rewards. (Or sinks.)

---

### Plus 4 mini-archetypes:

- **Hands Worker + AI** (Archetype 4): the trades + AR (electrician, plumber). Protected from disruption for years (the work is physical).
- **Educator-Navigator** (Archetype 5): teaches people to live with AI. Demand is growing.
- **Compliance Sentinel** (Archetype 6): a regulation expert. A stable, protected role.
- **Safety Researcher** (Archetype 7): a narrow, high-level research role.

---

## <a id="top-30"></a>⭐ Top 30 emerging careers 2026-2030 (expanded from 10)

The order is the author's estimate (demand, prospects, stability over 5 years), not a measurement:

| # | Career |
|---|---|
| 1 | AI Safety / Alignment Researcher |
| 2 | AI Agent Architect |
| 3 | AI-Augmented Surgeon |
| 4 | AI Application Engineer |
| 5 | AI Cardiology Specialist |
| 6 | AI Legal Tech Engineer |
| 7 | AI Cybersecurity Hunter |
| 8 | AI Quant Researcher |
| 9 | AI Strategy Consultant |
| 10 | AI Quality / Eval Engineer |
| 11 | AI Mechanistic Interpretability |
| 12 | AI Chip Designer |
| 13 | AI Drug Discovery |
| 14 | AI Ethics Officer |
| 15 | AI Compliance Engineer (banking) |
| 16 | Voice AI Developer |
| 17 | AI Climate / ESG |
| 18 | Humanoid Robot Operator |
| 19 | AI Education Designer |
| 20 | AI Healthcare Diagnostic |
| 21 | AI Adoption Specialist |
| 22 | AI Cost Optimization Engineer |
| 23 | AI Trading Systems |
| 24 | AI Supply Chain Architect |
| 25 | Smart Glasses App Developer |
| 26 | AI Tutor System Architect |
| 27 | AI Patent Specialist |
| 28 | AI Litigation Specialist |
| 29 | AI Insurance Adjuster (AI claims) |
| 30 | AI Constitutional Engineer |

---

## <a id="salary-2030"></a>💰 Salary benchmarks 2030 (regional)

The regional salary forecast has been removed: there's no way to verify it. When you plan your career, rely on current data for your state and city (official labor statistics, job postings), and on your own conversations with people in the field.

---

## 🎬 Final practical advice (V2.0)

After 200 careers and a forecast:

### 5 mental models for finding your way

1. **Don't pick a "future job"; pick a long-term skill set.** Section H shows how skills evolve year by year. A job is how you apply your skills right now. Skills are portable.

2. **Specialty beats generality in 2030.** The generic "AI engineer" becomes a commodity. An AI engineer with a healthcare, legal or finance specialty has a moat.

3. **Hybrid beats pure.** A pure profession (doctor, lawyer, accountant) is under pressure. A hybrid (doctor + AI, lawyer + AI) = a productivity premium + more protection.

4. **Trust grows slowly, so relationships are protected.** AI won't close a \$10M deal. It won't treat a complex mental health case. Relationships stay human.

5. **Geographic arbitrage exists, but it's expected to narrow.** Pay for remote work depends on the region and the client; check real rates where you live.

### 90-day plan template (updated for V2.0)

**Days 1-30: Map.**

- Read this whole guide
- Pick 5 candidate careers
- Find where your domain and AI tools overlap
- Look up pay in **your own** area (from official labor statistics, current job postings and salary surveys)

**Days 31-60: Validate.**

- Connect with 5 people in each career (LinkedIn)
- Build 1 portfolio project in your top career
- Learn 1 key skill (from Section H, for your time horizon)

**Days 61-90: Commit.**

- Pick 1 career + 1 fallback
- Plan a 12-month learning path
- Schedule a re-evaluation in 6 months

---

## 📚 Sources V2.0 (in addition to v1.0)

- **WEF Future of Jobs Report**: https://www.weforum.org
- **McKinsey Global Institute, Future of Work**: https://www.mckinsey.com
- **Anthropic Economic Index**: https://www.anthropic.com/economic-index
- **OpenAI Economic Impacts**: https://openai.com/research
- **AI Now Institute**: https://ainowinstitute.org
- **Stanford AI Index**: https://aiindex.stanford.edu

These are starting points for checking things yourself. No numbers from them were carried over into this guide.

---

## 🔗 Related lessons (V2.0)

| Topic | Course lessons |
|-------|-------------|
| AI Research / Science (A7), the future of work | [AI roadmap 2027–2030](108-ai-roadmap-2027-2030.md) |
| Healthcare AI (A8, B6), AI Finance (A10) | [AI ethics and safety](61b-ai-ethics-safety.md), [AI regulation and compliance](61c-ai-regulation-compliance.md) |
| Future archetypes (Section J) | [What AI is](00-what-is-ai.md), [What to become: choose your path](49b-choose-your-path.md) |

---

**Version:** 2.0, updated October 2026

**200 careers in total** (100 NEW + 100 HYBRID)

**25 disappearing jobs** (expanded from 10)

**50 skills** (expanded from 25)

**Forecast:** year by year for 2027-2030, scenarios without numbers

🔥 **V1.0 is a map of the forest today. V2.0 is the map plus a 5-year weather forecast. Pick your place on the new map.**
