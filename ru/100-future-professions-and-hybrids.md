# 100 профессий будущего + гибриды (2026-2030)

> **Справочник AI Маяк Академии.**
> Comprehensive map профессий в эру AI: что появилось нового, что переориентируется через AI, что исчезает.
> Актуализировано: октябрь 2026.

---

## 🔥 Главный образ — AI как пожар в лесу

AI пришёл в индустрию **не как обновление**, а как пожар в лесу:

- **Некоторые деревья (профессии) сгорают** — рутинные, шаблонные, повторяемые
- **Новые семена прорастают** — профессии которых не существовало 3 года назад (Prompt Engineer, AI Agent Architect)
- **Старые пеньки дают новые ростки (гибриды)** — врач, юрист, дизайнер не исчезают — они становятся `профессия + AI = hybrid`

**Что нужно понимать:**

- Пожар уже идёт — игнорировать = сгореть вместе с деревом
- Сильные специалисты не "конкурируют с AI" — они "управляют AI"
- Самый ценный навык 2026 — **AI literacy + domain expertise**

---

## ⚠️ Disclaimer

Это справочник-карта профессий и сценарный прогноз, а не данные исследования.

- Зарплатные оценки, проценты роста и размеры рынков убраны: они не проверялись по первоисточникам. Свежие данные для своей страны и должности смотри на сайтах вакансий и в зарплатных обзорах
- Прогнозы на 2027–2030 — сценарии автора, они могут не сбыться
- Про медицину, право и финансы: AI помогает специалисту, но не заменяет лицензированную работу и не даёт персональных рекомендаций
- Это не финансовая и не инвестиционная рекомендация и не обещание дохода

---

## 📑 Структура документа

1. [Section A: 50 НОВЫХ профессий (rooted в AI)](#section-a)
   - A1: AI Engineering / Building (15)
   - A2: AI Content / Creative (10)
   - A3: AI Business / Strategy (10)
   - A4: AI Operations (8)
   - A5: AI Specialized (7)
2. [Section B: 50 ГИБРИДНЫХ профессий (старое + AI)](#section-b)
   - B1: Knowledge Work (15)
   - B2: Creative Work (10)
   - B3: Business / Sales (10)
   - B4: Trades + Services (10)
   - B5: Education + Wellness (5)
3. [Section C: Что исчезает (10 профессий под угрозой)](#section-c)
4. [Section D: Skills для будущего (25 навыков)](#section-d)
5. [Section E: Decision tree — какую профессию выбрать](#section-e)
6. [Salary benchmarks 2026](#salary-benchmarks)
7. [Top 10 emerging professions 2026-2030](#top-10)
8. [Чеклист и next steps](#next-steps)
9. [Sources](#sources)

---

## <a id="section-a"></a>🌱 Section A: 50 НОВЫХ профессий

Профессии которых **не существовало до 2022 года**. Появились как прямой результат генеративного AI.

---

### A1. AI Engineering / Building (15 профессий)

Это **строители AI-эпохи**. Самая горячая категория 2026.

---

#### 1. Prompt Engineer

- **Что делает:** Проектирует и оптимизирует промпты для LLM (Claude, GPT, Gemini и другие модели). Достаёт максимум из моделей при минимальной цене.
- **Ключевые навыки:**
  - Понимание архитектуры LLM (tokens, context, attention)
  - A/B тестирование промптов
  - Cost optimization (Sonnet vs Opus tradeoffs)
  - Chain-of-thought, few-shot, structured outputs
  - Eval design (как измерить "хороший промпт")
  - Понимание model-specific quirks
- **Demand:** ⭐⭐⭐⭐ (junior насыщается, senior всё ещё дефицит)
- **Как стать:**
  1. Пройти Anthropic Prompt Engineering course
  2. Построить 5 portfolio promptов с измеренным impact
  3. Contribute в open prompt libraries (PromptHub)
- **Образ:** Сомелье, который из винограда делает шедевр или помои — зависит от рук.

---

#### 2. AI Application Engineer

- **Что делает:** Строит production-grade приложения поверх LLM API. Backend + frontend + AI integration.
- **Ключевые навыки:**
  - Python/TypeScript fullstack
  - LLM API (Anthropic SDK, OpenAI, etc.)
  - Vector databases (Pinecone, Weaviate, Qdrant)
  - Streaming responses, async patterns
  - Error handling, retries, fallbacks
  - Cost monitoring per request
- **Demand:** ⭐⭐⭐⭐⭐ (главная новая профессия 2026)
- **Как стать:**
  1. Освоить 1 LLM SDK глубоко (Anthropic recommended)
  2. Построить 3 production projects (ship, не "учебных")
  3. Open source AI app на GitHub (1000+ stars)
- **Образ:** Архитектор который строит дома из нового материала — кирпичи (LLM) известны, а здание получается совершенно новое.

---

#### 3. LLM Operations (LLMOps) Engineer

- **Что делает:** Деплоит, мониторит, масштабирует LLM-приложения в production. DevOps но для AI.
- **Ключевые навыки:**
  - Kubernetes, Docker
  - Observability (Datadog, New Relic, custom)
  - Token-level cost tracking
  - Rate limiting, queueing
  - Multi-region failover
  - Model versioning + rollback
- **Demand:** ⭐⭐⭐⭐⭐ (растёт с production adoption)
- **Как стать:**
  1. Базовый DevOps (1-2 года опыта)
  2. Добавить LLM-specific (cost, latency, eval)
  3. Сертификация AWS/GCP AI/ML
- **Образ:** Машинист электровоза. Локомотив (модель) уже есть — твоё дело довезти груз без аварий.

---

#### 4. AI Agent Architect

- **Что делает:** Проектирует multi-agent systems. Решает кто делегирует кому, как координируется, как orchestration работает.
- **Ключевые навыки:**
  - Agent design patterns (orchestrator, supervisor, swarm)
  - LangGraph, AutoGen, Anthropic Agent SDK
  - State management между агентами
  - Error propagation
  - Cost budgeting на agent level
  - Tool design (когда давать function call vs встроить в prompt)
- **Demand:** ⭐⭐⭐⭐⭐ (топ-3 emerging роль)
- **Как стать:**
  1. Senior engineer foundation
  2. Build 2-3 agent systems в production
  3. Спикер на AI Engineering Summit
- **Образ:** Дирижёр оркестра. Каждый агент — музыкант. Дирижёр не играет, но без него — какофония.

---

#### 5. RAG Pipeline Engineer

- **Что делает:** Строит retrieval-augmented generation системы. Связывает private data → embeddings → vector DB → LLM.
- **Ключевые навыки:**
  - Embeddings (OpenAI, Voyage, Cohere)
  - Vector databases
  - Chunking strategies
  - Re-ranking
  - Hybrid search (semantic + keyword)
  - Eval RAG quality
- **Demand:** ⭐⭐⭐⭐ (enterprise adoption очень высокий)
- **Как стать:**
  1. Освоить 1 vector DB глубоко
  2. Построить RAG для 3 разных доменов
  3. Опубликовать сравнение chunking strategies
- **Образ:** Библиотекарь который ещё и переводчик. Достаёт нужную книгу + переводит на язык клиента.

---

#### 6. AI Integration Engineer

- **Что делает:** Внедряет AI в существующие enterprise системы (Salesforce, SAP, ERP, CRM).
- **Ключевые навыки:**
  - Enterprise integration patterns
  - REST/GraphQL API
  - SSO, auth, compliance
  - Change management
  - AI vendor evaluation
- **Demand:** ⭐⭐⭐⭐ (corporate AI adoption wave)
- **Как стать:**
  1. Backend engineer foundation
  2. Опыт работы с enterprise software
  3. AI/LLM certification
- **Образ:** Сантехник который тянет новый водопровод (AI) через старый дом (enterprise software).

---

#### 7. AI Quality Engineer (Eval Engineer)

- **Что делает:** Проектирует evals для LLM applications. Без evals = улетел в продакшен без приборов.
- **Ключевые навыки:**
  - Eval frameworks (Anthropic evals, LangSmith, Braintrust)
  - LLM-as-judge patterns
  - Golden dataset curation
  - Regression testing для prompts
  - Cost-quality tradeoffs
  - Statistical significance в LLM testing
- **Demand:** ⭐⭐⭐⭐⭐ (один из главных gap'ов в индустрии)
- **Как стать:**
  1. QA engineer foundation
  2. Глубоко изучить LLM behavior
  3. Опубликовать eval methodology
- **Образ:** Дегустатор вина. Не делает вино, но без него производитель не знает что улучшать.

---

#### 8. Multi-Agent Orchestrator

- **Что делает:** Specialized AI Agent Architect — focused на coordination 5-50 agents одновременно.
- **Ключевые навыки:**
  - Distributed systems
  - Event-driven architecture
  - Agent communication protocols
  - Deadlock detection
  - Cost optimization across agents
- **Demand:** ⭐⭐⭐⭐ (горячая ниша внутри Agent Architect)
- **Как стать:**
  1. Agent Architect → specialize в orchestration
- **Образ:** Авиадиспетчер. 50 самолётов в воздухе — никто не должен столкнуться.

---

#### 9. AI Security Engineer

- **Что делает:** Защищает LLM-приложения от prompt injection, jailbreaks, data leakage.
- **Ключевые навыки:**
  - Prompt injection patterns
  - Output filtering
  - Tool use guardrails
  - PII detection
  - Adversarial testing
  - OWASP Top 10 for LLMs
- **Demand:** ⭐⭐⭐⭐⭐ (regulated industries — banking, healthcare)
- **Как стать:**
  1. Security engineer foundation
  2. Освоить LLM attack surface
  3. CTF в AI security competitions
- **Образ:** Телохранитель президента. Знает каждый угол с которого может прилететь.

---

#### 10. AI Cost Optimization Engineer

- **Что делает:** Снижает LLM bill через model routing, caching, prompt compression.
- **Ключевые навыки:**
  - Model tiering (выбор модели под задачу: Haiku / Sonnet / Opus / Fable; цены сверяй на странице [Актуальное сейчас](https://aimayak.com/ru/now/))
  - Prompt caching (Anthropic: чтение из кэша стоит около 10% от цены входа, запись на 5 минут дороже обычного входа на 25%, на 1 час — вдвое)
  - Batch API: скидка 50% на асинхронную обработку
  - Semantic caching
  - Request batching
  - Token-level analytics (учитывать новый токенизатор моделей 4.7 и новее — примерно на 30% больше токенов на тот же текст)
  - Cost dashboards
- **Demand:** ⭐⭐⭐⭐ (растёт когда compa LLM bill превышает \$50K/month)
- **Как стать:**
  1. Engineer + business mindset
  2. Опубликовать case study экономии \$X
- **Образ:** Энергоаудитор. Дом светит и работает — но электричества жрёт вдвое больше нужного.

---

#### 11. Vector Database Engineer

- **Что делает:** Специалист по vector databases. Sharding, performance, hybrid search.
- **Ключевые навыки:**
  - Pinecone, Weaviate, Qdrant, Milvus deep
  - HNSW, IVF algorithms
  - Embedding model selection
  - Cost-performance tradeoffs
- **Demand:** ⭐⭐⭐ (specialized, smaller market но высокая зарплата)
- **Как стать:**
  1. Database engineer foundation
  2. Specialize в одной vector DB
- **Образ:** Архивариус с фотопамятью. Знает где лежит миллион документов и достанет за миллисекунду.

---

#### 12. AI Pipeline Architect

- **Что делает:** Проектирует end-to-end ML/AI pipelines (data → train → deploy → monitor).
- **Ключевые навыки:**
  - MLOps platforms (MLflow, Vertex AI, SageMaker)
  - Data engineering
  - Model versioning
  - CI/CD для models
  - Feature stores
- **Demand:** ⭐⭐⭐⭐ (стабильно high)
- **Как стать:**
  1. ML engineer 2-3 years
  2. Architect-level system design
- **Образ:** Главный инженер завода. Все конвейеры (data flows) сходятся к нему.

---

#### 13. Fine-tuning Specialist

- **Что делает:** Дообучает foundation models на private data. RLHF, DPO, LoRA.
- **Ключевые навыки:**
  - PyTorch, HuggingFace
  - Training infrastructure (GPU clusters)
  - Dataset curation
  - Evaluation methodology
  - Cost (обучение моделей может стоить очень дорого)
- **Demand:** ⭐⭐⭐ (decreasing as foundation models improve, но specialty жива)
- **Как стать:**
  1. ML research background
  2. Опыт обучения моделей
- **Образ:** Тренер сборной. Базовый талант (foundation model) есть — твоё дело довести до олимпийского уровня.

---

#### 14. Custom Model Engineer

- **Что делает:** Строит specialized models from scratch (когда foundation models не подходят).
- **Ключевые навыки:**
  - Deep learning fundamentals
  - Transformer architecture deep
  - Distributed training
  - Custom CUDA kernels (продвинутый level)
- **Demand:** ⭐⭐ (узкая ниша, но самые высокие зарплаты в индустрии)
- **Как стать:**
  1. PhD или equivalent research experience
  2. Published papers
- **Образ:** Часовщик швейцарского часового завода. Делает то что массовое производство не сделает.

---

#### 15. AI Infrastructure Engineer (vLLM/SGLang specialist)

- **Что делает:** Инфраструктура для inference. Делает модели быстрее и дешевле на GPU clusters.
- **Ключевые навыки:**
  - vLLM, SGLang, TGI deep
  - CUDA basics
  - GPU memory optimization
  - Batching strategies
  - KV cache optimization
- **Demand:** ⭐⭐⭐⭐ (на frontier labs очень высокая)
- **Как стать:**
  1. Systems engineer foundation
  2. Contribute в open source inference engine
- **Образ:** Тюнер автомобиля Формулы-1. Та же машина едет на 20% быстрее.

---

### A2. AI Content / Creative (10 профессий)

---

#### 16. AI Content Producer

- **Что делает:** Создаёт контент (тексты, видео, аудио) используя AI как основной инструмент. Не editing assistant — primary producer.
- **Ключевые навыки:**
  - Claude/GPT для long-form
  - Midjourney/gpt-image-2/Flux для images
  - Suno/Udio для music
  - Runway/Kling для video
  - Brand voice consistency
  - Multi-platform repurposing
- **Demand:** ⭐⭐⭐⭐ (entry barrier низкий, но senior высокий)
- **Как стать:**
  1. Освоить 3-4 AI content tools deep
  2. Построить portfolio (channels с reach)
  3. Specialize в нише (B2B SaaS, e-commerce, etc.)
- **Образ:** Шеф-повар который готовит из готовых ингредиентов из магазина. Магия не в выращивании моркови, а в комбинации.

---

#### 17. AI Music Composer (Suno/Udio specialist)

- **Что делает:** Генерирует музыку через AI tools для коммерческого использования (jingles, ambient, soundtracks).
- **Ключевые навыки:**
  - Suno v4, Udio deep prompting
  - Music theory basics (для guiding AI)
  - Audio editing (Logic, Ableton для post-production)
  - Copyright awareness
- **Demand:** ⭐⭐⭐ (растёт, но регуляторика непредсказуема)
- **Как стать:**
  1. Освоить Suno + Udio
  2. Music theory crash course
  3. Sell on Pond5, AudioJungle
- **Образ:** Скульптор. Глина (AI output) — материал. Форма (твой taste) — искусство.

---

#### 18. AI Video Producer (Runway/Kling)

- **Что делает:** Создаёт видео через AI (Runway, Kling и другие видеомодели). Marketing, ads, short films.
- **Ключевые навыки:**
  - Промптинг для видеомоделей (Runway, Kling и другие)
  - Storyboarding
  - Post-production (DaVinci Resolve)
  - Cinematography basics
- **Demand:** ⭐⭐⭐⭐ (взрывной рост 2026)
- **Как стать:**
  1. Master 2 AI video tools
  2. Build 10 portfolio pieces
  3. Find niche (real estate, fashion, tech)
- **Образ:** Режиссёр короткометражек на 1 человека. То что раньше требовало команды из 20 — делаешь сам.

---

#### 19. AI Voice Director (ElevenLabs)

- **Что делает:** Производит voice content через AI cloning (audiobooks, podcasts, character voices, dubbing).
- **Ключевые навыки:**
  - ElevenLabs deep
  - Voice cloning ethics + legal
  - Multi-language production
  - Audio editing
- **Demand:** ⭐⭐⭐⭐ (особенно для multilingual content)
- **Как стать:**
  1. Master ElevenLabs Pro
  2. Build voice library (с consent)
  3. Audiobook production projects
- **Образ:** Режиссёр дубляжа. Подбирает голоса под персонажей — только теперь голоса виртуальные.

---

#### 20. AI Game Designer (procedural worlds)

- **Что делает:** Использует AI для генерации игровых миров, NPC dialogues, level design.
- **Ключевые навыки:**
  - Unity/Unreal с AI integration
  - LLM для dynamic dialogue
  - Procedural generation
  - Game design fundamentals
- **Demand:** ⭐⭐⭐ (специализированная ниша)
- **Как стать:**
  1. Game dev foundation
  2. AI integration projects
- **Образ:** Архитектор бесконечного города. Каждый дом отличается, но узнаваем стиль.

---

#### 21. AI Animator

- **Что делает:** Создаёт анимацию через AI (Runway, Kaiber, animation-specific tools).
- **Ключевые навыки:**
  - AI animation tools deep
  - Traditional animation principles (timing, weight)
  - After Effects integration
- **Demand:** ⭐⭐⭐ (специализированная)
- **Образ:** Кукловод который не дёргает за ниточки, а описывает что куклы должны сделать.

---

#### 22. AI Photographer / Image Director

- **Что делает:** Создаёт коммерческие photography через Midjourney/Flux/gpt-image-2. Product shots, lifestyle, fashion.
- **Ключевые навыки:**
  - Midjourney v7+, Flux Pro deep
  - Photography fundamentals (composition, lighting)
  - Brand consistency через style refs
  - Post-processing (Lightroom)
- **Demand:** ⭐⭐⭐⭐ (e-commerce massive demand)
- **Образ:** Фотограф без камеры. Видение то же — инструмент другой.

---

#### 23. AI Comic / Manga Creator

- **Что делает:** Производит comics/manga через AI. Niche но lucrative для self-publishing.
- **Ключевые навыки:**
  - Character consistency (LoRA training)
  - Panel layout
  - Storytelling
- **Demand:** ⭐⭐ (растёт но небольшая ниша)
- **Образ:** Мангака-одиночка. Делал бы 1 том в год — теперь 6.

---

#### 24. AI Narrative Designer

- **Что делает:** Проектирует branching narratives для interactive fiction, games, training simulations.
- **Ключевые навыки:**
  - Twine, Ink scripting
  - LLM dynamic generation
  - Narrative structure
- **Demand:** ⭐⭐⭐ (games + training markets)
- **Образ:** Сценарист сериала с миллионом серий — каждый зритель смотрит свою.

---

#### 25. AI Brand Voice Architect

- **Что делает:** Создаёт + поддерживает консистентный brand voice через AI workflows. Style guides, brand fine-tunes, voice eval.
- **Ключевые навыки:**
  - Brand strategy fundamentals
  - LLM customization (system prompts, fine-tune)
  - Voice eval methodology
- **Demand:** ⭐⭐⭐⭐ (corporates осознают что AI разваливает brand voice если не настроить)
- **Образ:** Звукорежиссёр радио. Каждый ведущий имеет свой голос — задача держать общий tone of voice станции.

---

### A3. AI Business / Strategy (10 профессий)

---

#### 26. AI Strategy Consultant

- **Что делает:** Помогает компаниям спроектировать AI roadmap. Не implementation — стратегия "куда вложить AI bucks".
- **Ключевые навыки:**
  - Business strategy fundamentals
  - AI landscape (vendors, capabilities, limits)
  - ROI modeling
  - Change management
  - Executive communication
- **Demand:** ⭐⭐⭐⭐⭐ (corporates desperately ищут guidance)
- **Как стать:**
  1. Consulting background ИЛИ AI engineering background
  2. 5+ years business experience
  3. Build 3 case studies
- **Образ:** Капитан корабля который знает где айсберги. Не управляет двигателем — знает курс.

---

#### 27. AI Product Manager (AI-PM)

- **Что делает:** PM специализированный на AI products. Понимает что LLM могут/не могут, eval-driven roadmap.
- **Ключевые навыки:**
  - Classic PM skills
  - LLM capabilities + limits
  - Eval-driven product development
  - Cost-aware feature prioritization
  - User research для AI features
- **Demand:** ⭐⭐⭐⭐⭐ (топ-5 emerging роль)
- **Как стать:**
  1. PM foundation 3+ years
  2. Build AI feature в production
  3. Speak at AI Engineering / Product conferences
- **Образ:** Дирижёр оркестра в котором половина музыкантов — роботы. Знает что робот может на скрипке, что не может.

---

#### 28. AI Transformation Lead

- **Что делает:** Возглавляет AI-трансформацию в крупной компании. Org change + technical + culture.
- **Ключевые навыки:**
  - Executive leadership
  - Org design
  - Change management
  - AI literacy
  - P&L responsibility
- **Demand:** ⭐⭐⭐⭐ (Fortune 500 hiring wave)
- **Образ:** Генерал который реформирует армию во время войны.

---

#### 29. AI Adoption Specialist

- **Что делает:** Help mid-size companies (50-500 employees) внедрить AI workflows. Hands-on, not strategy deck.
- **Ключевые навыки:**
  - Practical AI tool mastery (10+ tools)
  - Training delivery
  - Workflow design
  - Stakeholder management
- **Demand:** ⭐⭐⭐⭐⭐ (mid-market is the gold rush)
- **Образ:** Тренер по plumbing для тех кто только электричество видел.

---

#### 30. AI Ethics Officer

- **Что делает:** Обеспечивает responsible AI deployment. Bias audits, transparency, fairness.
- **Ключевые навыки:**
  - AI ethics frameworks (NIST, EU AI Act)
  - Bias detection methodology
  - Stakeholder engagement
  - Legal awareness
- **Demand:** ⭐⭐⭐ (regulated industries, EU companies)
- **Образ:** Судья на спортивных соревнованиях. Не играет — следит за правилами.

---

#### 31. AI Compliance Officer

- **Что делает:** EU AI Act, US executive orders, ISO 42001. Регуляторика AI.
- **Ключевые навыки:**
  - AI regulation landscape
  - Compliance frameworks
  - Documentation rigor
  - Audit preparation
- **Demand:** ⭐⭐⭐⭐ (EU AI Act enforcement 2026-2027)
- **Образ:** Налоговый инспектор для AI. Скучно но нужно.

---

#### 32. AI ROI Analyst

- **Что делает:** Считает реальный ROI от AI initiatives. Cost vs productivity gain vs revenue impact.
- **Ключевые навыки:**
  - Financial modeling
  - AI cost structures
  - Productivity metrics
  - A/B testing
- **Demand:** ⭐⭐⭐ (CFO offices)
- **Образ:** Бухгалтер с супердопуском. Считает не только числа но и магию.

---

#### 33. AI Procurement Specialist

- **Что делает:** Закупает AI tools и services для корпораций. Vendor evaluation, contract negotiation.
- **Ключевые навыки:**
  - Procurement fundamentals
  - AI vendor landscape
  - Contract negotiation
  - Total cost of ownership
- **Demand:** ⭐⭐⭐ (стабильно)
- **Образ:** Шопоголик с CFO mindset. Покупает много но осознанно.

---

#### 34. AI Vendor Manager

- **Что делает:** Управляет relationships с AI vendors (Anthropic, OpenAI, vector DB providers).
- **Ключевые навыки:**
  - Vendor management
  - SLA monitoring
  - Multi-vendor strategy
  - Cost optimization
- **Demand:** ⭐⭐⭐
- **Образ:** Дипломат который знает с кем переговариваться и о чём.

---

#### 35. AI Risk Officer

- **Что делает:** Identifies + mitigates AI risks (technical, business, regulatory, reputational).
- **Ключевые навыки:**
  - Risk frameworks
  - AI-specific risk categories (hallucination, bias, drift)
  - Crisis communication
- **Demand:** ⭐⭐⭐⭐ (banking, healthcare, insurance)
- **Образ:** Метеоролог для бизнеса. Предсказывает шторм до того как корабль вышел.

---

### A4. AI Operations (8 профессий)

---

#### 36. AI Trainer (RLHF specialist)

- **Что делает:** Ranks AI outputs, provides feedback для RLHF training. Human-in-the-loop.
- **Ключевые навыки:**
  - Domain expertise (специфическая область)
  - Critical thinking
  - Consistent rating methodology
- **Demand:** ⭐⭐⭐⭐ (frontier labs hire massively)
- **Образ:** Преподаватель который ставит оценки бесконечной серии экзаменов.

---

#### 37. AI Auditor (independent verification)

- **Что делает:** Independent audits AI systems для compliance, fairness, performance.
- **Ключевые навыки:**
  - Audit methodology
  - AI evaluation
  - Reporting rigor
- **Demand:** ⭐⭐⭐ (EU AI Act создаёт market)
- **Образ:** Финансовый аудитор Big Four — только для AI.

---

#### 38. AI Red Team Specialist

- **Что делает:** Tries to break AI systems. Adversarial testing, jailbreaks, edge cases.
- **Ключевые навыки:**
  - Creative attack design
  - Security mindset
  - Documentation
  - Anthropic/OpenAI red team protocols
- **Demand:** ⭐⭐⭐⭐⭐ (Anthropic, OpenAI hire many)
- **Образ:** Профессиональный взломщик банков. Платят за то чтобы нашёл дыры.

---

#### 39. AI Behavior Researcher

- **Что делает:** Studies how AI behaves в edge cases. Alignment research adjacent.
- **Ключевые навыки:**
  - Research methodology
  - Statistical analysis
  - LLM internals understanding
- **Demand:** ⭐⭐⭐ (узкая ниша, но высокая зарплата)
- **Образ:** Зоолог нового вида. Только вид — это AI, и мы его создали но не понимаем.

---

#### 40. Synthetic Data Engineer

- **Что делает:** Generates synthetic training data. Critical для domains где real data rare/private.
- **Ключевые навыки:**
  - Data generation techniques
  - Quality validation
  - Privacy-preserving methods
- **Demand:** ⭐⭐⭐⭐ (healthcare, finance, robotics)
- **Образ:** Хороший лжец который полезен. Создаёт правдоподобные данные.

---

#### 41. AI Knowledge Curator

- **Что делает:** Curates knowledge bases для RAG systems. Editorial role for AI age.
- **Ключевые навыки:**
  - Information architecture
  - Editorial judgment
  - Search optimization
  - Domain expertise
- **Demand:** ⭐⭐⭐ (enterprise RAG adoption)
- **Образ:** Главный редактор библиотеки которая помогает AI находить правду.

---

#### 42. AI Workflow Designer

- **Что делает:** Проектирует human-AI workflows. Где AI делает, где человек approves, как handoff работает.
- **Ключевые навыки:**
  - Process design
  - UX principles
  - AI capabilities awareness
- **Demand:** ⭐⭐⭐⭐
- **Образ:** Хореограф для танца человек-робот.

---

#### 43. Human-AI Interface Designer

- **Что делает:** UX/UI for AI-augmented interfaces. Streaming responses, citations, confidence indicators.
- **Ключевые навыки:**
  - UX design fundamentals
  - AI interaction patterns
  - Information design
- **Demand:** ⭐⭐⭐⭐ (растёт быстро)
- **Образ:** Архитектор моста между человеком и роботом.

---

### A5. AI Specialized (7 профессий)

---

#### 44. AI Voice Agent Developer (Vapi/Bland.ai)

- **Что делает:** Строит phone-calling AI agents для sales, support, scheduling.
- **Ключевые навыки:**
  - Vapi, Bland.ai, Retell deep
  - Voice UX design
  - Telephony integration (Twilio)
  - Real-time latency optimization
- **Demand:** ⭐⭐⭐⭐⭐ (топ-5 emerging роль 2026)
- **Образ:** Кукловод который заставляет робота звучать как человек по телефону.

---

#### 45. Computer Use Operator

- **Что делает:** Builds AI workflows которые управляют desktop/browser (Anthropic Computer Use, OpenAI Operator).
- **Ключевые навыки:**
  - Computer Use API
  - Browser automation
  - UI element identification
  - Error recovery
- **Demand:** ⭐⭐⭐⭐ (новая категория 2025-2026)
- **Образ:** Marionettist который двигает руками агента по клавиатуре.

---

#### 46. Local AI Deployment Engineer

- **Что делает:** Deploy AI locally (privacy, cost, latency reasons). Ollama, llama.cpp, on-device.
- **Ключевые навыки:**
  - Open weights models (Llama, Mistral, Qwen)
  - Quantization
  - Local inference engines
  - Edge deployment
- **Demand:** ⭐⭐⭐ (privacy-sensitive sectors)
- **Образ:** Тот кто строит автономный домик в лесу — всё своё, без подключения к сети.

---

#### 47. AI Therapy Researcher (companion AI ethics)

- **Что делает:** Research + design ethical AI companions / therapy tools. Replika, Character.ai aftermath.
- **Ключевые навыки:**
  - Psychology background
  - Ethics
  - AI interaction design
  - User safety
- **Demand:** ⭐⭐⭐ (растёт после societal concerns)
- **Образ:** Психолог нового типа. Изучает не пациентов — а отношения между людьми и AI.

---

#### 48. Robotics + AI Integration Engineer

- **Что делает:** Bridges LLMs + physical robots. Figure, 1X, Tesla Optimus ecosystem.
- **Ключевые навыки:**
  - Robotics fundamentals
  - LLM for planning
  - Sensor fusion
  - Real-time control
- **Demand:** ⭐⭐⭐⭐ (humanoid robotics wave)
- **Образ:** Тот кто учит роботов думать прежде чем шагать.

---

#### 49. Smart Glasses App Developer (Meta Ray-Ban, Apple Vision)

- **Что делает:** Apps для AR glasses с AI assistants (Meta Ray-Ban, Apple Vision Pro 2026).
- **Ключевые навыки:**
  - AR SDK (Meta, Apple)
  - LLM integration
  - Voice UX
  - Always-on AI patterns
- **Demand:** ⭐⭐⭐ (early market, может взорваться 2027+)
- **Образ:** Разработчик iPhone apps в 2008. Слот ранний — большие винеры.

---

#### 50. AI Accessibility Specialist

- **Что делает:** Использует AI чтобы сделать tech accessible для disabled users. Visual descriptions, voice control, cognitive aids.
- **Ключевые навыки:**
  - WCAG, accessibility standards
  - AI tools для visual/audio/cognitive support
  - User research с disability communities
- **Demand:** ⭐⭐⭐⭐ (regulatory + ethical pressure)
- **Образ:** Архитектор пандуса в цифровом мире. Делает невидимое видимым, неслышное слышным.

---

## <a id="section-b"></a>🌳 Section B: 50 ГИБРИДНЫХ профессий

Старые профессии + AI = новая версия. Не "AI заменяет" — "AI augmentations".

---

### B1. Knowledge Work (15 hybrids)

---

#### 51. Lawyer + AI = AI-Augmented Lawyer

- **Что меняется:** AI делает research, drafts contracts, summarizes case law. значительная доля рутины уходит.
- **Где human остаётся:** Strategy, client relationships, court appearances, judgment calls, negotiation.
- **AI tools:** Harvey, CoCounsel, Lexis+AI, custom Claude workflows

---

#### 52. Doctor + AI = AI-Assisted Physician

- **Что меняется:** AI делает диагностику (radiology, pathology), drafts notes, suggests treatments.
- **Где human остаётся:** Patient interaction, judgment calls, procedures, ethical decisions.
- **AI tools:** Abridge, Nuance DAX, AI radiology tools (Aidoc), specialty-specific

---

#### 53. Accountant + AI = AI-Enabled Accountant

- **Что меняется:** Bookkeeping автоматизирован. Audits semi-automated. Forecasting лучше.
- **Где human остаётся:** Strategy, tax optimization, client advisory, complex judgment.
- **AI tools:** Vic.ai, MindBridge, custom AI workflows

---

#### 54. Teacher + AI = AI-Augmented Educator

- **Что меняется:** Personalized lesson plans, automated grading, AI tutors для каждого ученика.
- **Где human остаётся:** Motivation, social-emotional learning, mentorship, classroom management.
- **AI tools:** Khanmigo, MagicSchool, custom Claude workflows

---

#### 55. Translator + AI = AI Translation Specialist

- **Что меняется:** Basic translation полностью AI. Translator теперь post-edits + handles nuance.
- **Где human остаётся:** Cultural nuance, marketing copy, legal/medical critical, literary.
- **AI tools:** DeepL, GPT/Claude, custom translation memories

---

#### 56. Researcher + AI = AI-Powered Researcher

- **Что меняется:** Literature review занимает часы вместо месяцев. Data analysis быстрее.
- **Где human остаётся:** Hypothesis design, novel insights, peer review judgment.
- **AI tools:** Elicit, Consensus, Perplexity Pro, Claude with web search

---

#### 57. Journalist + AI = AI-Augmented Reporter

- **Что меняется:** Research, transcription, first-draft writing AI-assisted.
- **Где human остаётся:** Source relationships, investigative work, editorial judgment, on-the-ground reporting.
- **AI tools:** Otter.ai (transcription), Claude/GPT (drafts), Perplexity (research)

---

#### 58. Therapist + AI = Hybrid Mental Health Practitioner

- **Что меняется:** Note-taking automated. Between-session AI check-ins. Pattern detection.
- **Где human остаётся:** Therapeutic alliance (the core), crisis intervention, complex cases.
- **AI tools:** Eleos Health, Lyssn, custom Claude workflows

---

#### 59. Architect + AI = Generative Design Architect

- **Что меняется:** Generative design produces 100 options. Permits/compliance checking automated.
- **Где human остаётся:** Client vision, site context, aesthetic judgment, construction oversight.
- **AI tools:** Autodesk Forma, Spacemaker, custom diffusion models

---

#### 60. Engineer + AI = AI-Assisted Engineer

- **Что меняется:** Coding 2-3x productive (Claude Code, Copilot, Cursor). Debugging faster.
- **Где human остаётся:** Architecture, system design, judgment calls, mentorship.
- **AI tools:** Claude Code, Cursor, Copilot, domain-specific

---

#### 61. Project Manager + AI = AI-PM Hybrid

- **Что меняется:** Status reports auto-generated. Risk detection AI-assisted. Resource planning smarter.
- **Где human остаётся:** Stakeholder management, judgment calls, motivation, escalation.
- **AI tools:** Asana AI, ClickUp AI, custom Claude workflows

---

#### 62. Recruiter + AI = AI-Augmented Recruiter

- **Что меняется:** Sourcing automated. Initial screening AI. Match-making smarter.
- **Где human остаётся:** Relationship building, closing candidates, culture fit assessment.
- **AI tools:** Eightfold, Paradox, custom workflows

---

#### 63. Consultant + AI = AI-Native Consultant

- **Что меняется:** Research, analysis, deck production AI-assisted. Same deliverable за 1/3 времени.
- **Где human остаётся:** Client relationships, executive presence, judgment, strategy.
- **AI tools:** Claude/GPT для analysis, Gamma для decks, custom

---

#### 64. Coach + AI = AI-Powered Coach

- **Что меняется:** Between-session AI check-ins. Goal tracking automated. Pattern detection.
- **Где human остаётся:** Accountability, deep listening, breakthrough moments.
- **AI tools:** Coachvox, custom Claude workflows

---

#### 65. Financial Advisor + AI = AI-Augmented Advisor

- **Что меняется:** Portfolio analysis automated. Rebalancing suggestions. Tax loss harvesting AI.
- **Где human остаётся:** Trust, behavioral coaching, complex planning, relationship.
- **AI tools:** Wealthbox AI, custom robo-advisor integration

---

### B2. Creative Work (10 hybrids)

---

#### 66. Designer + AI = AI-Native Designer

- **Что меняется:** Mockups, variations, A/B options AI-generated. Same role но 5-10x output.
- **Где human остаётся:** Brand strategy, taste, user research, judgment.
- **AI tools:** Figma AI, Google Stitch, Midjourney, Claude для copy

---

#### 67. Copywriter + AI = AI-Augmented Writer

- **Что меняется:** First drafts AI. Bulk content AI. Headlines variants AI.
- **Где human остаётся:** Voice, strategy, editing, hooks, taste.
- **AI tools:** Claude, GPT, Copy.ai, Jasper

---

#### 68. Photographer + AI = AI-Hybrid Photographer

- **Что меняется:** Post-processing 10x faster. AI fills crowds in landscapes. Product shots via AI generation.
- **Где human остаётся:** Vision, on-location work, client relationships, key moments.
- **AI tools:** Lightroom AI, Topaz, Midjourney для composites

---

#### 69. Filmmaker + AI = AI-Enabled Director

- **Что меняется:** VFX cheaper. B-roll generated. Editing assisted. Localization automated.
- **Где human остаётся:** Vision, casting, performance direction, story.
- **AI tools:** Runway, Kling, AI editing tools

---

#### 70. Musician + AI = AI-Collaborative Musician

- **Что меняется:** Composition assists. Stem generation. Mixing automated.
- **Где human остаётся:** Performance, emotion, originality, brand.
- **AI tools:** Suno, Udio, Mubert, AI mixing

---

#### 71. Actor + AI = AI-Voice Talent / Digital Performer

- **Что меняется:** Voice cloning licensing. Digital doubles. International dubs without re-recording.
- **Где human остаётся:** Live performance, on-camera, real emotional range.
- **AI tools:** ElevenLabs licensing, digital double services
- **Note:** SAG-AFTRA 2023 agreements regulate AI use

---

#### 72. Illustrator + AI = AI-Hybrid Illustrator

- **Что меняется:** Background generation. Color variations. Initial concepts AI-assisted.
- **Где human остаётся:** Style, character design, storytelling, polish.
- **AI tools:** Midjourney, Krea, custom LoRAs

---

#### 73. Animator + AI = AI-Powered Animator

- **Что меняется:** Inbetweens automated. Lip sync AI. Background animation generated.
- **Где human остаётся:** Key poses, performance, story timing.
- **AI tools:** Cascadeur, ToonBoom AI, Runway

---

#### 74. Video Editor + AI = AI-Enhanced Editor

- **Что меняется:** Rough cut automated. Subtitles instant. Reframing for verticals automated.
- **Где human остаётся:** Story rhythm, emotional pacing, final polish.
- **AI tools:** Descript, Adobe AI, CapCut AI

---

#### 75. Production Designer + AI = Virtual Production Designer

- **Что меняется:** Concept art AI. Set design exploration via AI. Virtual location scouting.
- **Где human остаётся:** Physical builds, on-set decisions, client vision.
- **AI tools:** Midjourney, Unreal Engine + AI plugins

---

### B3. Business / Sales (10 hybrids)

---

#### 76. Salesperson + AI = AI-Enabled SDR

- **Что меняется:** Prospecting automated. Email drafting AI. Call summaries instant.
- **Где human остаётся:** Closing, complex deals, relationships, judgment.
- **AI tools:** Apollo AI, Clay, Outreach AI, Gong

---

#### 77. Marketer + AI = AI-Native Marketer

- **Что меняется:** Content production 5x. A/B testing automated. Personalization at scale.
- **Где human остаётся:** Strategy, brand, creative direction, channel selection.
- **AI tools:** Adobe AI, Jasper, Claude/GPT, HubSpot AI

---

#### 78. Customer Support + AI = Hybrid Support Specialist

- **Что меняется:** Tier-1 fully AI. Tier-2 AI-assisted. Sentiment detection automated.
- **Где human остаётся:** Complex issues, empathy moments, escalations.
- **AI tools:** Intercom Fin, Zendesk AI, Ada
- **Note:** Headcount уменьшается, но senior роли остаются

---

#### 79. HR Manager + AI = AI-Augmented HR Lead

- **Что меняется:** Recruiting auto. Onboarding personalized AI. Performance trends detected.
- **Где human остаётся:** Conflict resolution, culture, sensitive conversations.
- **AI tools:** Workday AI, BambooHR AI, custom

---

#### 80. Operations Manager + AI = AI-Powered Ops Manager

- **Что меняется:** Process monitoring AI. Anomaly detection. Optimization suggestions.
- **Где human остаётся:** Cross-functional coordination, judgment, change management.
- **AI tools:** Process mining tools + AI, custom

---

#### 81. Account Manager + AI = AI-Enabled CSM

- **Что меняется:** Churn risk detection. Renewal prep automated. Account research instant.
- **Где human остаётся:** Relationships, strategic conversations, escalations.
- **AI tools:** Gainsight AI, Catalyst, custom

---

#### 82. Business Analyst + AI = AI-Augmented Analyst

- **Что меняется:** SQL queries via natural language. Report generation. Insight detection.
- **Где human остаётся:** Asking right questions, business context, stakeholder management.
- **AI tools:** Hex, Hex Magic, Claude data analysis

---

#### 83. Product Marketer + AI = AI-Native PMM

- **Что меняется:** Competitive intel automated. Launch content AI. Persona research deeper.
- **Где human остаётся:** Positioning, messaging, GTM strategy.
- **AI tools:** Claude/GPT, Crayon, custom

---

#### 84. Brand Manager + AI = AI-Hybrid Brand Strategist

- **Что меняется:** Brand monitoring automated. Content production scaled. Sentiment analysis real-time.
- **Где human остаётся:** Brand vision, key creative decisions, partnerships.
- **AI tools:** Brandwatch + AI, custom

---

#### 85. Real Estate Agent + AI = AI-Augmented Realtor

- **Что меняется:** Property descriptions AI. Lead qualification automated. Virtual tours AI-enhanced.
- **Где human остаётся:** Negotiation, local knowledge, trust, closing.
- **AI tools:** Restb.ai, AI listing tools, custom
- **Note:** проект автора курса тоже относится к этой категории

---

### B4. Trades + Services (10 hybrids)

---

#### 86. Chef + AI = AI-Hybrid Chef

- **Что меняется:** Menu design AI-assisted. Nutrition optimization. Inventory predictions.
- **Где human остаётся:** Cooking, taste, creativity, kitchen leadership.
- **AI tools:** Custom Claude workflows, BlueCart AI, Toast AI

---

#### 87. Personal Trainer + AI = AI-Coach Hybrid

- **Что меняется:** Personalized programs AI. Form analysis via video. Progress tracking automated.
- **Где human остаётся:** Motivation, hands-on coaching, group dynamics.
- **AI tools:** Future, Tonal AI, custom

---

#### 88. Nutritionist + AI = AI-Enabled Dietitian

- **Что меняется:** Meal planning AI. Tracking automated. Pattern detection.
- **Где human остаётся:** Behavior change, complex cases, accountability.
- **AI tools:** Lumen, custom

---

#### 89. Mechanic + AI = AI-Diagnostic Technician

- **Что меняется:** Diagnosis 2x faster (AI reads codes + symptoms). Predictive maintenance.
- **Где human остаётся:** Physical repair, customer trust, complex cases.
- **AI tools:** Bosch ESI, custom dealer tools

---

#### 90. Electrician + AI = Smart Home Specialist

- **Что меняется:** Smart home design AI. Energy optimization. Predictive maintenance.
- **Где human остаётся:** Installation, troubleshooting, code compliance.
- **AI tools:** Custom integration platforms

---

#### 91. Plumber + AI = IoT-Enabled Plumbing Specialist

- **Что меняется:** Leak detection IoT + AI. System diagnostics smarter. Quotes AI-generated.
- **Где human остаётся:** Physical work, emergency response.
- **AI tools:** Flo by Moen, smart plumbing platforms

---

#### 92. Tailor + AI = AI-Pattern Designer

- **Что меняется:** Pattern generation AI. Fit prediction. 3D body scans automated.
- **Где human остаётся:** Construction, fitting, fine work.
- **AI tools:** Browzwear, Clo3D + AI plugins

---

#### 93. Carpenter + AI = Parametric Furniture Designer

- **Что меняется:** Design exploration AI. Material optimization. CNC planning automated.
- **Где human остаётся:** Craftsmanship, finishing, complex builds.
- **AI tools:** Fusion 360 AI, Rhino + Grasshopper

---

#### 94. Florist + AI = AI-Augmented Floral Designer

- **Что меняется:** Order automation. Design suggestions. Inventory predictions.
- **Где human остаётся:** Arrangement craft, client events, taste.
- **AI tools:** Bloomerang, custom

---

#### 95. Hairstylist + AI = AI Style Consultant

- **Что меняется:** Style preview via AI. Color match. Client preferences tracked.
- **Где human остаётся:** Cutting, coloring craft, client relationships.
- **AI tools:** Modiface, custom apps

---

### B5. Education + Wellness (5 hybrids)

---

#### 96. University Professor + AI = AI-Augmented Academic

- **Что меняется:** Research literature review AI. Grading AI-assisted. Lecture prep faster.
- **Где human остаётся:** Mentorship, original research, judgment.
- **AI tools:** Elicit, Consensus, Claude

---

#### 97. Personal Tutor + AI = AI-Enabled Tutor (Khanmigo-style)

- **Что меняется:** Personalized practice AI. Concept explanations AI. Progress tracking.
- **Где human остаётся:** Motivation, exam prep strategy, accountability.
- **AI tools:** Khanmigo, custom GPTs

---

#### 98. Yoga Instructor + AI = AI-Powered Wellness Coach

- **Что меняется:** Form analysis via camera. Personalized sequences AI.
- **Где human остаётся:** Energy, presence, hands-on adjustments.
- **AI tools:** YogiFi, custom

---

#### 99. Childcare + AI = AI-Augmented Parent Coach

- **Что меняется:** Development tracking AI. Activity suggestions. Q&A 24/7.
- **Где human остаётся:** Physical care, attachment, judgment.
- **AI tools:** Custom apps

---

#### 100. Eldercare + AI = AI-Assisted Caregiver

- **Что меняется:** Monitoring AI. Medication reminders. Fall detection. Companionship AI (controversial).
- **Где human остаётся:** Physical care, emotional connection, judgment.
- **AI tools:** Care.coach, custom devices

---

## <a id="section-c"></a>🔥 Section C: Что исчезает (10 профессий под угрозой 2026-2030)

Честный список. Не destructive — practical guidance.

---

### 1. Basic translation entry-level

- **Что заменяет AI:** DeepL, GPT, Claude (качество на популярных языковых парах уже высокое)
- **Что делать профессионалам:** Перейти в B1.55 — AI Translation Specialist (post-editing + specialty)
- **Timeline:** Critical 2026-2027

### 2. First-draft copywriting (commodity content)

- **Что заменяет AI:** Claude, GPT, Jasper, Copy.ai (good enough для SEO mass content)
- **Что делать:** B2.67 — AI-Augmented Writer (strategy + editing role)
- **Timeline:** Critical 2026

### 3. Tier-1 customer support (chat-based)

- **Что заменяет AI:** Intercom Fin, Zendesk AI, Ada (закрывают значительную долю рутинных обращений)
- **Что делать:** Move to Tier-2/Tier-3 (sensitive cases, escalations)
- **Timeline:** Critical 2026-2027

### 4. Data entry

- **Что заменяет AI:** OCR + AI extraction (Hyperscience, custom workflows)
- **Что делать:** Data quality specialist, AI workflow design
- **Timeline:** Critical 2026 (уже почти исчезла)

### 5. Basic accounting bookkeeping

- **Что заменяет AI:** Vic.ai, Botkeeper, QuickBooks AI
- **Что делать:** B1.53 — AI-Enabled Accountant (advisory, strategy)
- **Timeline:** Critical 2027-2028

### 6. Routine legal research (entry-level paralegal)

- **Что заменяет AI:** Harvey, CoCounsel, Lexis+AI
- **Что делать:** Move to AI training, prompt engineering для law firms, или specialty
- **Timeline:** Critical 2027

### 7. Stock photography (commodity)

- **Что заменяет AI:** Midjourney, Flux, gpt-image-2 (cheap good-enough images)
- **Что делать:** B2.68 — AI-Hybrid Photographer (specialty, events, exclusive content)
- **Timeline:** Critical 2026

### 8. Voice-over для commercial generic

- **Что заменяет AI:** ElevenLabs, custom voices
- **Что делать:** A2.19 — AI Voice Director, или specialty acting (premium voices)
- **Timeline:** Critical 2026-2027

### 9. Basic graphic design (templates)

- **Что заменяет AI:** Canva AI, Figma AI, Midjourney
- **Что делать:** B2.66 — AI-Native Designer (strategy + brand role)
- **Timeline:** Critical 2027

### 10. Routine code (boilerplate)

- **Что заменяет AI:** Cursor, Copilot, Claude Code
- **Что делать:** B1.60 — AI-Assisted Engineer (architecture + senior judgment)
- **Timeline:** Critical 2026 (junior dev market уже изменился)

---

## <a id="section-d"></a>💪 Section D: 25 навыков для будущего

Универсальные навыки нужные в **любой** profession 2026-2030.

---

### Universal Top 10

1. **AI literacy** — понимать что AI может/не может (probabilistic, hallucinates, biased)
2. **Prompt engineering / instruction design** — даже non-tech роли промптить умеют
3. **Critical thinking** — AI lies confidently, без critical thinking = катастрофа
4. **Verification skills** — как проверить AI output (fact-check, cite sources)
5. **System thinking** — видеть AI как часть workflow, не магию
6. **Communication** — с AI и с людьми **про** AI
7. **Continuous learning** — AI меняется monthly, нельзя один раз выучить
8. **Domain expertise** — deeper, narrower = moat against AI
9. **Ethics literacy** — понимать AI bias, privacy implications
10. **Adaptability** — карьера будет меняться чаще

### Technical (10)

11. **Python basics** — даже для non-engineers, нужно для интеграций
12. **Git / version control** — must-have для anyone working с code or AI configs
13. **API consumption** — REST/GraphQL, читать API docs
14. **Data analysis fundamentals** — pandas basics, SQL queries
15. **SQL basics** — данные везде, доставать руками часто нужно
16. **CLI comfort** — терминал не страшный
17. **Markdown / documentation** — документация — главный actifact AI-эры
18. **Cloud basics** — Cloudflare/Vercel/AWS minimum awareness
19. **Security awareness** — secrets, auth, basic threats
20. **Cost / budget thinking** — AI calls стоят денег, нужно считать

### Soft (5)

21. **Sales / negotiation** — still very human, AI не close deals
22. **Relationship building** — trust scales slowly, AI ускорить не может
23. **Empathy** — AI имитирует, но не чувствует
24. **Leadership in AI-augmented teams** — managing people + agents
25. **Story-telling** — раньше факт был дефицит, сейчас контекст + история

---

## <a id="section-e"></a>🧭 Section E: Decision tree — какую профессию выбрать

```
START

Я люблю technical / code work?
├─ Да → AI Engineering / AI Application / LLMOps (A1)
│        → Subprofile:
│           - Hardcore systems? → A1.15 Infrastructure
│           - Build apps? → A1.2 AI Application
│           - Multi-agent? → A1.4 Agent Architect
│           - Optimization? → A1.10 Cost Optimization
└─ Нет → continue

Я творческий человек?
├─ Да → AI Content / Creative (A2)
│        → Subprofile:
│           - Text? → A2.16 Content Producer
│           - Visual? → A2.22 AI Photographer
│           - Audio? → A2.19 AI Voice Director
│           - Video? → A2.18 AI Video Producer
│           - Music? → A2.17 AI Music Composer
└─ Нет → continue

Я работаю с людьми / sales / management?
├─ Да → AI Business / Strategy (A3)
│        → Subprofile:
│           - Strategy? → A3.26 AI Strategy Consultant
│           - Product? → A3.27 AI Product Manager
│           - Adoption? → A3.29 AI Adoption Specialist
│           - Ethics? → A3.30 AI Ethics Officer
└─ Нет → continue

Я работаю в specific domain (medical/legal/finance/education)?
├─ Да → Hybrid version своей профессии (B1)
│        → B1.51 Lawyer + AI
│        → B1.52 Doctor + AI
│        → B1.53 Accountant + AI
│        → B1.54 Teacher + AI
│        → etc.
└─ Нет → continue

Я учусь / преподаю?
├─ Да → AI Education hybrids (B5)
│        → B5.96 Professor + AI
│        → B5.97 Tutor + AI
└─ Нет → continue

Я в trade / service work?
├─ Да → AI-Hybrid version своего ремесла (B4)
│        → B4.86 Chef + AI
│        → B4.89 Mechanic + AI
│        → B4.90 Electrician + AI (Smart Home)
│        → etc.
└─ Нет → AI Adoption Specialist (A3.29) — помогаешь other people
         или AI Trainer (A4.36) — domain knowledge → AI training
```

---

## <a id="salary-benchmarks"></a>💰 Salary benchmarks 2026 (overview)

Зарплатные таблицы и региональные коэффициенты убраны: они не проверялись по первоисточникам, а цифры сильно зависят от страны, компании, уровня специалиста и умения договариваться. Свежие данные для своей должности и региона ищи на сайтах вакансий и в зарплатных обзорах, а не в этом справочнике.

---

## <a id="top-10"></a>⭐ Top 10 emerging professions 2026-2030 (high demand)

1. **AI Application Engineer** — главная новая профессия эпохи
2. **AI Agent Architect** — multi-agent systems boom
3. **AI Safety / Red Team** — frontier labs hire massively
4. **Prompt Engineer** (junior level still high) — entry barrier низкий
5. **AI Voice Agent Developer** — Vapi/Bland.ai market explosion
6. **AI-Augmented Lawyer** — Harvey + кодирование → massive role shift
7. **AI Adoption Specialist** (enterprise) — Fortune 500 в panic mode
8. **AI Content Producer** — content economy AI-native
9. **AI Cost Optimization Engineer** — компании увидели bills
10. **AI Ethics / Compliance Officer** — EU AI Act enforcement

---

## <a id="next-steps"></a>🎯 Чеклист и next steps

После прочтения этого документа:

- [ ] Выбрал 3 profession candidates (из 100)
- [ ] Identified gaps в skills для каждой (что не хватает?)
- [ ] Researched salaries в **твоём** регионе (не USA если ты не в USA)
- [ ] Pick 1 + написал 90-day learning plan
- [ ] Connect с 3+ people в этой profession (LinkedIn, Twitter, конференции)
- [ ] Start building portfolio в этой profession (3 deliverables за 30 days)
- [ ] Re-evaluate через 90 days — это ещё твой путь?

**Образ:** Профессия — не tatuirovka. В AI-эпохе можно перейти каждые 2-3 года без потери momentum, если skills universal (Section D).

---

## 🎬 Практические советы от AI Маяк Академии

1. **Не учи "AI" — учи specific tool deep.** Master Claude Code → easier learn Cursor → easier learn next thing.
2. **Build, не learn.** Один production project > 10 курсов.
3. **Specialty + AI.** Generic AI engineer commoditizes. AI engineer + healthcare/legal/finance — moat.
4. **Network in AI community.** Twitter (теперь X), Hacker News, AI Engineering Summit.
5. **Don't chase highest salary.** Choose profession где durable demand 5-10 years (Section A1, A3.26, A3.27, B1).

---

## <a id="sources"></a>📚 Sources

- **HackerNews Jobs** — https://news.ycombinator.com/jobs (живые вакансии в AI)
- **Anthropic Careers** — https://www.anthropic.com/careers
- **OpenAI Careers** — https://openai.com/careers
- **WEF Future of Jobs Report** — https://www.weforum.org/reports
- **McKinsey Future of Work** — https://www.mckinsey.com/featured-insights/future-of-work
- **Pew Research AI in Workplace** — https://www.pewresearch.org

Список источников — стартовые точки для самостоятельной проверки. Цифры из них в этот справочник не переносились.

---

## 🔗 Cross-references в курсе

| Topic | Уроки курса |
|-------|-------------|
| AI fundamentals | [Что такое AI](00-what-is-ai.md), [Как работает LLM](00b-how-llm-works.md), [Сравнение моделей](00c-ai-models-comparison.md), [AI без страха](00d-ai-without-fear.md) |
| Setup + Claude Code | [Установка и настройка](05-setup.md), [Claude Code Desktop](05b-claude-code-desktop.md), [Тарифы и доступ](05c-access-levels-pricing.md) |
| Prompting | [Основы промптинга](06-prompting-fundamentals.md) |
| CLAUDE.md / Memory | [CLAUDE.md](07-claude-md.md) |
| Building Apps | [Сайты и веб-приложения](15-websites-webapps.md), [API и интеграции](16-apis-integration.md), [Деплой на Cloudflare](18-deployment-cloudflare.md) |
| Multi-Agent Systems | [Команды агентов](26-agent-teams.md), [Мультиагентная оркестрация](82-multiagent-orchestration.md) |
| RAG | [RAG](14-rag.md) |
| Evals | [Evals](22-evals-system.md) |
| Security | [Разрешения и безопасность](28-permissions-security.md), [Prompt Injection Defense](107b-prompt-injection-defense.md) |
| Cost Optimization | [Prompt Caching и Batch API](34-prompt-caching-batch-api.md), [Cost engineering](48b-cost-engineering.md) |

Какие уроки нужны для конкретной профессии, смотри на странице профессий сайта: связи профессия-урок ведутся там.

---

**Версия:** актуализировано в октябре 2026

🔥 **Лес горит. Деревья сгорают. Семена прорастают. Новые ростки на старых пеньках. Выбери своё место в новом лесу.**

---

## 🆕 V2.0 EXPANSION — 200 профессий + прогноз до 2030

> **Добавлено:** 2026-05-11. Версия 2.0.
> Удваиваем количество профессий до 200 + year-by-year прогноз 2027-2030 + гибридная экономика.
>
> **Образ:** Если v1.0 — карта леса сегодня, то v2.0 — карта леса через 5 лет + прогноз погоды на каждый год.

---

## 📑 Структура V2.0

- [Section A6-A11: + 50 НОВЫХ профессий = 100 total NEW](#a-v2)
- [Section B6-B10: + 50 ГИБРИДНЫХ профессий = 100 total HYBRID](#b-v2)
- [Section C-extended: 25 исчезающих профессий (было 10)](#c-extended)
- [Section D-extended: 50 skills (было 25)](#d-extended)
- [Section F: Year-by-year прогноз 2027-2030](#section-f)
- [Section G: Geographic shifts](#section-g)
- [Section H: Skills evolution year-by-year](#section-h)
- [Section I: Что НЕ сделает AI до 2030](#section-i)
- [Section J: Гибридная экономика — 3 archetypes 2030](#section-j)
- [Top 30 emerging professions 2026-2030 (расширено с 10)](#top-30)
- [Salary projections 2030 (regional)](#salary-2030)

---

## <a id="a-v2"></a>🌱 Section A6-A11: ещё 50 НОВЫХ профессий

---

### A6. AI Hardware / Robotics (10 профессий)

Это **руки AI-эпохи**. Софт встречает железо.

---

#### 51. Humanoid Robot Operator

- **Что делает:** Управляет/обучает гуманоидов (Figure, Tesla Optimus, Unitree). Обучает их через teleoperation + RLHF.
- **Ключевые навыки:**
  - Teleoperation rigs (VR controllers, motion capture)
  - Behavioral cloning datasets
  - Safety protocols вокруг живых людей
  - Базовый ML (RLHF intuition)
  - Mechatronics troubleshooting
- **Demand:** ⭐⭐⭐⭐ (Tesla Optimus + Figure shipping 2026-2027)
- **Как стать:**
  1. Bootcamp в одной из robot-companies (Figure, Agility)
  2. Build teleoperation rig в гараже + record dataset
  3. Open-source contribution в LeRobot framework
- **Образ:** Кукловод XXI века. Кукла учится сама — твоя задача показать первые 1000 движений.

---

#### 52. AI Chip Designer (TPU/NPU engineering)

- **Что делает:** Проектирует ASIC чипы оптимизированные под inference / training. Конкурирует с NVIDIA через специализацию.
- **Ключевые навыки:**
  - Verilog / SystemVerilog
  - Memory hierarchy для transformer architectures
  - Power efficiency (perf-per-watt)
  - Понимание матричных операций attention
  - EDA tools (Cadence, Synopsys)
- **Demand:** ⭐⭐⭐⭐⭐ (NVIDIA monopoly cracks — все строят свой чип)
- **Как стать:**
  1. EE/CS degree + chip design specialization
  2. 3-5 лет в традиционном chip design (Intel, AMD, Apple)
  3. Pivot в AI-specific (Tenstorrent, Groq, Cerebras)
- **Образ:** Архитектор небоскрёба, где каждый этаж — это слой нейросети. Спроектируешь умно — даст в 10 раз больше с того же фундамента.

---

#### 53. Smart Glasses Application Developer

- **Что делает:** Разрабатывает приложения для Meta Ray-Ban, Apple Vision, Snap Spectacles + AI overlay в реальном времени.
- **Ключевые навыки:**
  - AR/VR SDK (Meta SDK, ARKit, WebXR)
  - Computer vision (object detection, OCR)
  - Voice-first UX (нет клавиатуры)
  - Latency budgets (<100ms критично)
  - Privacy design (камера всегда наготове)
- **Demand:** ⭐⭐⭐⭐ (Meta Ray-Ban hit 2M+ sold, Apple Vision на старте)
- **Как стать:**
  1. Mobile dev foundation (iOS/Android)
  2. AR portfolio (3 production apps)
  3. AI integration (Claude + vision)
- **Образ:** Архитектор невидимого слоя реальности. Видит мир дважды — глазами и через данные.

---

#### 54. AI Wearable Engineer

- **Что делает:** Строит AI-powered wearables (Humane AI Pin, Friend.com, Rabbit R1, smart rings).
- **Ключевые навыки:**
  - Embedded systems (Rust, C++)
  - Power management (battery life критично)
  - On-device ML (TinyML, quantization)
  - Always-on audio processing
  - Sensor fusion (микрофон + accelerometer + GPS)
- **Demand:** ⭐⭐⭐ (категория ещё формируется, провалы Humane напугали)
- **Как стать:**
  1. Embedded systems foundation
  2. On-device ML certification
  3. Build prototype в гараже (Raspberry Pi + Whisper local)
- **Образ:** Часовщик XXI века. Делает крошечный механизм, который знает тебя лучше тебя самого.

---

#### 55. Autonomous Vehicle AI Engineer

- **Что делает:** Разрабатывает self-driving stack (Waymo, Tesla FSD, Wayve). Perception → planning → control + LLM для edge cases.
- **Ключевые навыки:**
  - Computer vision deep
  - SLAM (simultaneous localization and mapping)
  - Reinforcement learning
  - Simulation (CARLA, Waymo open dataset)
  - Safety case engineering
- **Demand:** ⭐⭐⭐⭐ (Waymo expanding, Tesla pivots, Wayve raising)
- **Как стать:**
  1. CS degree + ML specialization
  2. Robotics PhD (опционально но помогает в research roles)
  3. Internship в одной из top-5 AV companies
- **Образ:** Тренер таксиста, который никогда не устаёт. Учишь его 100 миллионов километров в симуляторе.

---

#### 56. Drone Swarm Coordinator

- **Что делает:** Программирует координацию десятков/сотен дронов одновременно — для inspection, agriculture, security, shows.
- **Ключевые навыки:**
  - ROS2, PX4 firmware
  - Distributed systems (consensus algorithms)
  - Mesh networking
  - Regulatory compliance (FAA, EASA)
  - Computer vision (real-time)
- **Demand:** ⭐⭐⭐ (нишево, но растёт — agriculture + inspection)
- **Как стать:**
  1. Robotics или embedded foundation
  2. Single-drone competence (DJI SDK)
  3. Move на swarm patterns (ROS2 + multi-agent)
- **Образ:** Хореограф пчелиного роя. Каждая пчела глупая, рой — гениальный.

---

#### 57. AI Sensor Network Architect

- **Что делает:** Проектирует распределённые сенсорные сети (smart city, factory, farm) + AI inference на edge.
- **Ключевые навыки:**
  - LoRaWAN, 5G, satellite IoT
  - Edge compute (NVIDIA Jetson, Coral)
  - Time-series databases (InfluxDB, TimescaleDB)
  - Anomaly detection ML
  - Industrial protocols (Modbus, OPC-UA)
- **Demand:** ⭐⭐⭐ (B2B nicheвая но стабильная)
- **Как стать:**
  1. IoT engineer foundation
  2. Industrial automation опыт
  3. AI/edge specialization
- **Образ:** Невропатолог планеты. Каждый сенсор — нерв. Без них — мир глух.

---

#### 58. BCI (Brain-Computer Interface) Engineer

- **Что делает:** Разрабатывает BCI системы (Neuralink, Synchron, Precision Neuroscience). Декодирует нейросигналы в действия.
- **Ключевые навыки:**
  - Neuroscience basics (spike sorting, LFP)
  - Signal processing (Kalman filters, decoders)
  - ML на neural data
  - Биосовместимость и медицинская regulation (FDA)
  - C/C++ для real-time decoders
- **Demand:** ⭐⭐ (узко — 5-10 компаний globally, но эксплозивно скоро)
- **Как стать:**
  1. Neuroscience или EE PhD
  2. Postdoc в BCI lab
  3. Industry pivot (Neuralink, Synchron)
- **Образ:** Переводчик между мозгом и машиной. Раньше переводили русский-английский, теперь — нейроны-байты.

---

#### 59. AI-Augmented Manufacturing Engineer

- **Что делает:** Внедряет AI vision + predictive maintenance + generative design в заводы.
- **Ключевые навыки:**
  - Industrial vision systems (Cognex, Keyence)
  - PLC programming
  - Predictive maintenance ML
  - Generative design (Autodesk Fusion AI)
  - Lean / Six Sigma awareness
- **Demand:** ⭐⭐⭐⭐ (Industry 4.0 + onshoring wave)
- **Как стать:**
  1. Mechanical/manufacturing engineering foundation
  2. AI certification (NVIDIA DLI, Coursera ML)
  3. Industrial AI deployments в портфолио
- **Образ:** Доктор для завода. Раньше лечил по симптомам, теперь — по непрерывному МРТ всех станков.

---

#### 60. Edge AI Hardware Specialist

- **Что делает:** Оптимизирует AI модели под edge devices (Jetson, Coral, mobile NPU, microcontrollers).
- **Ключевые навыки:**
  - Quantization (INT8, INT4)
  - Model distillation
  - ONNX, TensorRT, CoreML conversion
  - Hardware-aware NAS
  - Power profiling
- **Demand:** ⭐⭐⭐⭐ (on-device AI wave)
- **Как стать:**
  1. ML engineer foundation
  2. Embedded systems opyt
  3. Specialization в одной target platform (mobile или industrial)
- **Образ:** Ювелир. Берёт огранённый алмаз 7B параметров — выпиливает в 100MB чтоб поместился в кулон.

---

### A7. AI Research / Science (10 профессий)

Это **первооткрыватели**. На переднем крае.

---

#### 61. AI Alignment Researcher

- **Что делает:** Изучает как сделать AI safe + aligned с human values. Не "запрети", а "научи правильно хотеть".
- **Ключевые навыки:**
  - RLHF, DPO, Constitutional AI
  - Formal verification basics
  - Game theory, decision theory
  - Philosophy (utilitarianism, deontology)
  - Research methodology
- **Demand:** ⭐⭐⭐⭐⭐ (главная research категория десятилетия)
- **Как стать:**
  1. ML PhD или MATS program
  2. Anthropic Fellows / Apply директно
  3. Publish в alignment forum, NeurIPS, ICML
- **Образ:** Тренер хищника. Лев сильнее тебя — нельзя приказать. Но можно обучить так, чтоб ел только то что нужно.

---

#### 62. Mechanistic Interpretability Researcher

- **Что делает:** Изучает что **внутри** нейросетей. Какие нейроны за что отвечают, как формируются circuits.
- **Ключевые навыки:**
  - Linear algebra deep
  - Probing classifiers
  - Activation patching
  - Sparse autoencoders
  - Visualization tools
- **Demand:** ⭐⭐⭐⭐ (small field, but Anthropic + Apollo Research scaling)
- **Как стать:**
  1. ML PhD с фокусом на interpretability
  2. Replicate AnthropicState-of-art papers
  3. Apply Anthropic / Apollo Research / Redwood
- **Образ:** Нейробиолог для искусственного мозга. Раньше резали лягушек — теперь смотрим в LLM через "микроскоп" активаций.

---

#### 63. AI Scaling Researcher

- **Что делает:** Изучает законы масштабирования (compute, data, model size). Решает где следующая граница.
- **Ключевые навыки:**
  - Distributed training (DeepSpeed, Megatron)
  - Scaling laws math (Chinchilla, etc.)
  - Compute budgeting на \$100M+ runs
  - Failure mode analysis
  - Statistical inference
- **Demand:** ⭐⭐⭐ (5-10 globally, но критично важно)
- **Как стать:**
  1. ML PhD с large-model опытом
  2. Industry training runs \$1M+
  3. Apply frontier lab
- **Образ:** Картограф неизведанного континента. Каждый шаг стоит миллионы — лучше знай куда идти.

---

#### 64. Synthetic Biology AI Engineer

- **Что делает:** Применяет AI к биологии — protein design, drug discovery, CRISPR optimization.
- **Ключевые навыки:**
  - Molecular biology basics
  - AlphaFold / RoseTTAFold patterns
  - Sequence-to-structure models
  - Wet lab basics (или partnership)
  - GPU compute optimization
- **Demand:** ⭐⭐⭐⭐ (Isomorphic Labs + Cradle Bio + many startups)
- **Как стать:**
  1. CS/ML + bio crossover (или bio + ML)
  2. Build prediction model на public protein data
  3. Industry pivot (Insitro, Recursion)
- **Образ:** Архитектор живых машин. Раньше биолог открывал что есть. Теперь проектирует чего не было.

---

#### 65. Drug Discovery AI Specialist

- **Что делает:** Использует AI для screening молекул, drug repurposing, clinical trial optimization.
- **Ключевые навыки:**
  - Cheminformatics (RDKit, DeepChem)
  - Molecular dynamics
  - Clinical trial design
  - FDA regulatory pathway
  - Bayesian optimization
- **Demand:** ⭐⭐⭐⭐ (Pfizer, Moderna, BenevolentAI hire massively)
- **Как стать:**
  1. Pharm-D или chemistry PhD
  2. ML certification
  3. Industry research role
- **Образ:** Шеф-повар который имитирует 1 миллион рецептов в день. Из них 10 — лекарства.

---

#### 66. Climate AI Researcher

- **Что делает:** AI для климатического моделирования, прогноза погоды, carbon capture optimization, energy grid.
- **Ключевые навыки:**
  - Atmospheric science basics
  - PDE solvers (graph neural networks для weather)
  - Satellite data processing
  - Climate models (CESM, etc.)
  - Visualization
- **Demand:** ⭐⭐⭐⭐ (Google GraphCast, Microsoft Aurora — большие investments)
- **Как стать:**
  1. PhD в climate science или ML+earth
  2. Open-source contribution в WeatherBench
  3. Apply Google DeepMind Climate, NVIDIA Earth-2, Microsoft
- **Образ:** Метеоролог для планеты. Раньше прогноз 3 дня — сейчас 14 дней с deterministic точностью.

---

#### 67. AI Material Scientist

- **Что делает:** AI для discovery новых материалов — батареи, semiconductors, sustainable composites.
- **Ключевые навыки:**
  - Solid state physics basics
  - DFT (density functional theory)
  - Graph neural networks для crystals
  - Materials Project database
  - High-throughput experimentation
- **Demand:** ⭐⭐⭐ (узко, но Google DeepMind GNoME + battery startups)
- **Как стать:**
  1. Materials Science или physics PhD
  2. ML specialization
  3. Industry pivot (Citrine, Kebotix, Google DeepMind)
- **Образ:** Алхимик XXI века. Раньше искал золото — сейчас AI находит "золото" для электромобилей и солнечных панелей.

---

#### 68. Quantum-AI Researcher

- **Что делает:** Пересечение quantum computing + AI. Hybrid algorithms, quantum machine learning.
- **Ключевые навыки:**
  - Quantum computing basics (Qiskit, Cirq)
  - Variational quantum algorithms
  - Classical ML deep
  - Linear algebra advanced
  - Hardware-aware optimization (IBM, IonQ)
- **Demand:** ⭐⭐ (узко — 10-20 компаний globally, но futureproof)
- **Как стать:**
  1. Physics PhD с quantum focus
  2. ML crossover
  3. Industry или national lab pivot
- **Образ:** Учёный на стыке двух эпох. Сейчас не работает на индустрию — но через 10 лет может оказаться главной.

---

#### 69. AI Astronomer

- **Что делает:** AI для анализа астрономических данных — exoplanet detection, gravitational waves, galaxy classification.
- **Ключевые навыки:**
  - Astronomy basics
  - Time-series ML
  - Image processing (Hubble, JWST data)
  - Anomaly detection
  - Big data pipelines (LSST scale)
- **Demand:** ⭐⭐ (узко — academia + NASA + few startups)
- **Как стать:**
  1. Astronomy PhD
  2. ML specialization
  3. Postdoc → research scientist
- **Образ:** Телескоп тратит секунды на изображение. Раньше астроном — годы. Сейчас AI — минуты.

---

#### 70. Neuro-AI Researcher

- **Что делает:** Пересечение нейронауки и AI. Использует мозг как inspiration для architectures + AI для понимания мозга.
- **Ключевые навыки:**
  - Neuroscience deep
  - Computational neuroscience
  - Neural architecture design
  - fMRI / electrophysiology data
  - Cross-domain research methodology
- **Demand:** ⭐⭐⭐ (Numenta, BrainGate, academic labs)
- **Как стать:**
  1. Neuroscience PhD
  2. Computational specialty
  3. Industry crossover
- **Образ:** Археолог биологического разума. Каждое открытие в мозге — потенциальная архитектура для AI.

---

### A8. AI Healthcare (10 профессий)

> AI помогает специалисту, но не заменяет лицензированную медицинскую работу и не даёт персональных медицинских рекомендаций.

Это **врачи AI-эпохи**. Где ставки самые высокие.

---

#### 71. AI Radiologist Assistant

- **Что делает:** Использует AI (Aidoc, Viz.ai, Annalise) для триажа рентгенов, КТ, МРТ. Human-in-the-loop для critical decisions.
- **Ключевые навыки:**
  - Radiology basics (или certified radiologist)
  - AI tool literacy
  - DICOM data handling
  - Clinical workflow integration
  - Patient safety protocols
- **Demand:** ⭐⭐⭐⭐ (FDA approved AI products growing 2x/year)
- **Как стать:**
  1. MD + radiology residency
  2. AI literacy + Aidoc/Viz.ai certification
  3. Hospital adoption роль
- **Образ:** Радиолог + AI = пилот + автопилот. AI смотрит каждое изображение, человек принимает решение. Скорость 3х, точность выше.

---

#### 72. Medical NLP Specialist

- **Что делает:** Строит NLP системы для EHR (electronic health records) — extract structured data, clinical decision support, billing optimization.
- **Ключевые навыки:**
  - NLP deep
  - Medical terminology (SNOMED, ICD-10)
  - HIPAA compliance
  - EHR APIs (Epic, Cerner)
  - Privacy-preserving ML
- **Demand:** ⭐⭐⭐⭐ (every hospital wants to mine EHR)
- **Как стать:**
  1. NLP engineer foundation
  2. Healthcare domain certification
  3. Build EHR project portfolio
- **Образ:** Археолог медицинских записей. Раскапывает structured data из миллионов неструктурированных заметок.

---

#### 73. AI Diagnostic Engineer

- **Что делает:** Строит diagnostic AI системы (skin cancer, retinopathy, cardiac).
- **Ключевые навыки:**
  - Computer vision
  - Medical imaging
  - Clinical validation
  - FDA 510(k) pathway
  - Multi-modal models
- **Demand:** ⭐⭐⭐⭐ (huge investment в medical AI)
- **Как стать:**
  1. ML engineer foundation + medical specialty
  2. Industry placement (Tempus, PathAI, Paige)
  3. FDA submission опыт
- **Образ:** Тысячи глаз патологов в одном алгоритме. Никогда не устаёт.

---

#### 74. AI Drug Repurposing Specialist

- **Что делает:** Использует AI чтобы найти новое применение существующим лекарствам (often cheaper than new drug development).
- **Ключевые навыки:**
  - Pharmacology basics
  - Knowledge graphs (drug-disease-gene)
  - Causal inference
  - Clinical trial design
  - Regulatory pathways
- **Demand:** ⭐⭐⭐ (BenevolentAI, Healx)
- **Как стать:**
  1. Pharm-D или pharma research foundation
  2. ML specialization
  3. Industry research role
- **Образ:** Перекладыватель ключей. Один ключ от одной двери может открыть и другую — AI находит какую.

---

#### 75. AI Mental Health Researcher

- **Что делает:** Разрабатывает AI для mental health support (Woebot, Wysa) — ethical, safe, evidence-based.
- **Ключевые навыки:**
  - Clinical psychology basics
  - NLP deep
  - Safety + harm reduction
  - Long-term user engagement design
  - Privacy + consent
- **Demand:** ⭐⭐⭐⭐ (mental health crisis + AI accessibility)
- **Как стать:**
  1. PhD psychology или ML+psych crossover
  2. Industry placement (Woebot, Wysa, Spring Health)
  3. Clinical validation studies
- **Образ:** Терапевт-консультант в каждом кармане. Не заменяет психиатра — но первая линия 24/7.

---

#### 76. AI Pathology Specialist

- **Что делает:** AI для digital pathology — cancer detection, prognosis, treatment selection из биопсий.
- **Ключевые навыки:**
  - Pathology basics
  - Whole slide imaging
  - Computer vision (gigapixel images)
  - Multi-instance learning
  - Clinical validation
- **Demand:** ⭐⭐⭐⭐ (Paige, PathAI, Roche Digital Pathology)
- **Как стать:**
  1. MD pathology + AI или ML + pathology certification
  2. Industry placement
  3. FDA approved tools experience
- **Образ:** Микроскоп с глазами 10,000 патологов. Видит то что человек пропускает.

---

#### 77. AI Genomics Engineer

- **Что делает:** AI для variant calling, polygenic risk scores, personalized medicine.
- **Ключевые навыки:**
  - Bioinformatics (BWA, GATK)
  - Population genetics
  - Variant interpretation (ACMG guidelines)
  - Deep learning на sequence data
  - Privacy-preserving computation
- **Demand:** ⭐⭐⭐ (23andMe, Tempus, Verily, Color Health)
- **Как стать:**
  1. Bioinformatics PhD или ML+genetics
  2. Population data experience
  3. Industry pivot
- **Образ:** Переводчик с языка генома на язык диагнозов. Раньше — годы. Сейчас — секунды.

---

#### 78. AI Surgical Robotics Operator

- **Что делает:** Управляет AI-augmented surgical robots (next-gen Da Vinci, Vicarious Surgical) + интерпретирует AI suggestions.
- **Ключевые навыки:**
  - Surgical training (residency or specialty)
  - Robotics interface mastery
  - Real-time decision making
  - AI suggestion evaluation
  - Crisis management
- **Demand:** ⭐⭐⭐⭐ (Intuitive Surgical adoption + new entrants)
- **Как стать:**
  1. MD + surgical residency (8-10 лет)
  2. Robotic surgery certification
  3. AI tool experience
- **Образ:** Хирург + робот + AI = команда из трёх специалистов в одном теле. Точность недоступна одному человеку.

---

#### 79. AI Clinical Trial Optimizer

- **Что делает:** Оптимизирует clinical trials через AI — patient matching, protocol design, real-world evidence.
- **Ключевые навыки:**
  - Clinical research basics
  - EHR mining
  - Statistical inference
  - Regulatory awareness
  - Health economics
- **Demand:** ⭐⭐⭐ (Deep 6 AI, Saama, Medable)
- **Как стать:**
  1. Pharm or clinical research foundation
  2. ML/data science certification
  3. Pharma или CRO placement
- **Образ:** Кастинг-директор клинических испытаний. Из миллионов пациентов выбирает идеальных кандидатов за минуты.

---

#### 80. AI Public Health Analyst

- **Что делает:** AI для эпидемиологии, outbreak prediction, public health surveillance, vaccine distribution.
- **Ключевые навыки:**
  - Epidemiology basics
  - Time-series forecasting
  - Geospatial analysis
  - Public data integration
  - Communication к non-technical audiences
- **Demand:** ⭐⭐⭐ (CDC, WHO, BlueDot, Metabiota)
- **Как стать:**
  1. MPH или epidemiology degree
  2. Data science skills
  3. Government / NGO placement
- **Образ:** Часовой на стене города. Видит надвигающуюся эпидемию недели до того как взрывается.

---

### A9. AI Education / Edtech (5 профессий)

---

#### 81. AI Curriculum Designer

- **Что делает:** Проектирует учебные программы где AI integrated — student как cocreator с AI, не "AI делает дз".
- **Ключевые навыки:**
  - Pedagogy / learning science
  - AI tool literacy
  - Assessment design
  - Curriculum mapping
  - Change management в школах
- **Demand:** ⭐⭐⭐⭐ (every school district scrambling)
- **Как стать:**
  1. Teaching foundation
  2. EdTech / AI literacy certification
  3. District-level role
- **Образ:** Архитектор обучения. Раньше — "запомни факт". Сейчас — "научись танцевать с AI и понимать когда оно лжёт".

---

#### 82. AI Tutor System Architect

- **Что делает:** Строит AI tutoring системы (Khanmigo, Anthropic education partnerships) — personalized, safe, pedagogically sound.
- **Ключевые навыки:**
  - LLM application engineering
  - Educational psychology
  - Safety + child-safe content design
  - Long-term engagement metrics
  - Multi-modal learning (text, voice, visual)
- **Demand:** ⭐⭐⭐⭐ (Khan Academy, Speak, Carnegie Learning)
- **Как стать:**
  1. AI Application Engineer foundation
  2. Education domain experience
  3. EdTech industry placement
- **Образ:** Конструктор персонального учителя. Каждому ребёнку — свой темп, свой стиль, свой пример.

---

#### 83. AI Assessment Designer

- **Что делает:** Проектирует assessments которые **measure thinking**, not "memorization or AI ability". Anti-cheating AI design.
- **Ключевые навыки:**
  - Psychometrics
  - Item response theory
  - AI detection (для cheating prevention)
  - Authentic assessment design
  - Fairness evaluation
- **Demand:** ⭐⭐⭐ (College Board, ETS, edTech, universities)
- **Как стать:**
  1. Education research foundation
  2. Psychometrics specialty
  3. AI/cheating literacy
- **Образ:** Дизайнер испытаний на которых "списать невозможно". Не потому что блокируешь — а потому что нечего списывать.

---

#### 84. AI Learning Analytics Engineer

- **Что делает:** Строит data pipelines + dashboards для learning analytics. School/university level.
- **Ключевые навыки:**
  - Data engineering
  - LMS APIs (Canvas, Moodle, Blackboard)
  - Privacy-preserving analytics (FERPA compliance)
  - Visualization
  - Predictive modeling (at-risk students)
- **Demand:** ⭐⭐⭐ (universities, EdTech vendors)
- **Как стать:**
  1. Data engineer foundation
  2. Education sector placement
  3. Privacy compliance certification
- **Образ:** Радар прогресса. Раньше учитель видел студента 2 раза в неделю — сейчас видим траекторию каждого по минутам.

---

#### 85. AI Accessibility in Education Specialist

- **Что делает:** Использует AI чтобы делать образование доступным — for disabled students, non-native speakers, neurodiverse.
- **Ключевые навыки:**
  - Disability awareness
  - Accessibility standards (WCAG, ADA)
  - AI tools (speech-to-text, text-to-speech, summarization)
  - Curriculum adaptation
  - Advocacy + change management
- **Demand:** ⭐⭐⭐ (huge но underfunded)
- **Как стать:**
  1. Special education or accessibility background
  2. AI tool literacy
  3. School district or non-profit placement
- **Образ:** Мост между миром и студентом который раньше не мог дойти. AI — это пандус для учёбы.

---

### A10. AI Finance / Quant (5 профессий)

> Профессии ниже описывают работу специалистов. Это не инвестиционная рекомендация и не обещание дохода от торговли.

---

#### 86. AI Quant Researcher

- **Что делает:** Использует AI для alpha generation, factor research, trading strategies. Hedge funds.
- **Ключевые навыки:**
  - Stats + ML deep
  - Time-series prediction
  - Market microstructure
  - Backtesting frameworks
  - Risk management
- **Demand:** ⭐⭐⭐⭐⭐ (Renaissance, Two Sigma, DE Shaw, Citadel — все hire)
- **Как стать:**
  1. PhD math/physics/CS
  2. Internship в quant fund
  3. Full-time после strong performance
- **Образ:** Игрок в покер с триллионом партий в день. AI видит patterns которые человек никогда.

---

#### 87. AI Fraud Detection Engineer

- **Что делает:** Строит anti-fraud системы — payment fraud, identity theft, money laundering.
- **Ключевые навыки:**
  - Anomaly detection
  - Graph neural networks (transactions = graph)
  - Real-time inference
  - Regulatory compliance (KYC, AML)
  - Adversarial robustness
- **Demand:** ⭐⭐⭐⭐ (every bank, payment processor, fintech)
- **Как стать:**
  1. ML engineer foundation
  2. Fintech placement
  3. Compliance certifications (CFE)
- **Образ:** Охрана банка XXI века. Раньше — глазами. Сейчас — миллион глаз AI ловят аномалии за milliseconds.

---

#### 88. AI Underwriter (insurance/lending)

- **Что делает:** AI-augmented underwriting — life, health, auto, home insurance, lending decisions.
- **Ключевые навыки:**
  - Actuarial basics or underwriting experience
  - ML models (XGBoost, neural nets)
  - Fairness + bias auditing
  - Regulatory compliance (state-level, ECOA)
  - Explainability tools
- **Demand:** ⭐⭐⭐⭐ (insurtech + lending fintech)
- **Как стать:**
  1. Underwriting or actuarial foundation
  2. ML certification
  3. Insurtech (Lemonade, Root) placement
- **Образ:** Risk-калькулятор который видит 1000 факторов одновременно. Решение за секунды, не за дни.

---

#### 89. AI Compliance Engineer (banking)

- **Что делает:** Строит compliance automation для banks/fintechs — KYC, AML, transaction monitoring, reporting.
- **Ключевые навыки:**
  - Banking regulations (BSA, OFAC, FATCA)
  - NLP для regulatory text
  - Workflow automation
  - Audit trails
  - Cross-jurisdictional compliance
- **Demand:** ⭐⭐⭐⭐ (compliance bottleneck во всех banks)
- **Как стать:**
  1. Compliance background or law
  2. Engineering certification
  3. RegTech placement (Hummingbird, ComplyAdvantage)
- **Образ:** Юрист-робот для банка. Никогда не пропускает regulatory update.

---

#### 90. AI Trading Systems Architect

- **Что делает:** Проектирует архитектуру high-frequency / algo trading systems с AI components.
- **Ключевые навыки:**
  - Low-latency systems (C++, Rust)
  - Network engineering (microseconds matter)
  - Risk systems
  - Exchange protocols (FIX, ITCH)
  - ML inference at scale
- **Demand:** ⭐⭐⭐ (узко — HFT shops + prop trading)
- **Как стать:**
  1. Systems engineering deep
  2. Quant exposure
  3. Industry placement (Jane Street, Jump Trading, HRT)
- **Образ:** Архитектор гонки на скорости света. Микросекунда = миллион долларов.

---

### A11. AI Specialty Emerging (10 профессий)

Это **узкие специалисты на стыке индустрий**.

---

#### 91. AI Climate / ESG Specialist

- **Что делает:** AI для ESG reporting, carbon accounting, climate risk assessment.
- **Ключевые навыки:**
  - Carbon accounting standards (GHG Protocol)
  - Satellite data analysis
  - Climate models
  - ESG regulatory frameworks (CSRD, SEC)
  - Data integration
- **Demand:** ⭐⭐⭐⭐ (CSRD enforcement 2026 → enterprise wave)
- **Как стать:**
  1. Sustainability background or environmental science
  2. AI/data science certification
  3. Industry placement (Watershed, Persefoni)
- **Образ:** Бухгалтер планетарного масштаба. Считает не доллары, а тонны CO2.

---

#### 92. AI Agriculture Engineer (precision farming)

- **Что делает:** AI для farming — yield prediction, pest detection, irrigation optimization, autonomous tractors.
- **Ключевые навыки:**
  - Agronomy basics
  - Computer vision (drone imagery)
  - IoT / edge compute
  - Geospatial analysis
  - Sustainability metrics
- **Demand:** ⭐⭐⭐ (John Deere, Climate Corp, Indigo Ag, FBN)
- **Как стать:**
  1. AgTech or agronomy background
  2. AI/data certification
  3. AgriTech placement
- **Образ:** Агроном с дроном-помощником. Видит поле глазами орла. Каждое растение учтено.

---

#### 93. AI Legal Tech Engineer

- **Что делает:** Строит legal AI tools — contract review, case law research, eDiscovery (Harvey, Casetext, Spellbook).
- **Ключевые навыки:**
  - NLP deep
  - Legal domain knowledge
  - Long-context handling
  - Citation accuracy
  - Privilege + confidentiality
- **Demand:** ⭐⭐⭐⭐⭐ (Harvey + thousands of legal tech startups)
- **Как стать:**
  1. ML engineer foundation
  2. Legal domain certification or partnership
  3. LegalTech placement
- **Образ:** Помощник юриста с памятью всего законодательства. Читает 1000 страниц за секунды.

---

#### 94. AI Real Estate Analyst

- **Что делает:** AI для real estate valuation, market prediction, property management automation, tenant matching.
- **Ключевые навыки:**
  - Real estate market knowledge
  - Geospatial ML
  - Computer vision (satellite + street view)
  - Time-series prediction
  - Regulatory awareness (zoning, fair housing)
- **Demand:** ⭐⭐⭐ (Zillow, Compass, Opendoor, Redfin + property managers)
- **Как стать:**
  1. Real estate or finance background
  2. ML certification
  3. PropTech placement
- **Образ:** Оценщик который видел все 100 миллионов транзакций мира. Цена за дом — за секунды.

---

#### 95. AI Sports Analytics Engineer

- **Что делает:** AI для sports — player performance, injury prediction, game strategy, fan engagement.
- **Ключевые навыки:**
  - Sports domain knowledge
  - Computer vision (tracking)
  - Biomechanics basics
  - Time-series ML
  - Visualization
- **Demand:** ⭐⭐⭐ (NBA, NFL, soccer clubs, F1 — все hire)
- **Как стать:**
  1. Data science foundation
  2. Sports analytics certification (SSAC)
  3. Team or sports media placement
- **Образ:** Тренер с микроскопом. Видит то что не видит человек: микро-паттерны движения, fatigue, opportunity.

---

#### 96. AI Cybersecurity Hunter

- **Что делает:** AI-augmented threat hunting — adversarial ML, anomaly detection, threat intel, incident response.
- **Ключевые навыки:**
  - Cybersecurity foundation
  - ML adversarial techniques
  - SIEM / SOAR platforms
  - Threat intelligence
  - Reverse engineering
- **Demand:** ⭐⭐⭐⭐⭐ (AI-powered attacks → need AI-powered defense)
- **Как стать:**
  1. Cybersecurity foundation (OSCP, etc.)
  2. ML specialty
  3. Industry placement (CrowdStrike, Mandiant, Palo Alto)
- **Образ:** Сафари-гид но охотится на хакеров. AI помогает увидеть следы в джунглях логов.

---

#### 97. AI Government / Civic Tech

- **Что делает:** AI для government services — benefits processing, citizen services, policy analysis. Often через 18F, USDS, Code for America.
- **Ключевые навыки:**
  - Government domain knowledge
  - Procurement awareness
  - Plain language design
  - Compliance (Section 508, FedRAMP)
  - Stakeholder management
- **Demand:** ⭐⭐⭐ (rising как AI Executive Order rollouts)
- **Как стать:**
  1. Tech career foundation
  2. Government placement (USDS, 18F, GovTech)
  3. Civic tech projects (Code for America)
- **Образ:** Реформатор бюрократии. AI разрушает очереди и сокращает паперки.

---

#### 98. AI Energy Grid Engineer

- **Что делает:** AI для smart grid — demand prediction, renewable integration, outage detection, EV charging optimization.
- **Ключевые навыки:**
  - Power systems engineering
  - Time-series forecasting
  - Optimization (linear/non-linear)
  - Edge compute
  - Regulatory awareness (FERC, ISO)
- **Demand:** ⭐⭐⭐⭐ (energy transition + EV wave)
- **Как стать:**
  1. Power engineering foundation
  2. ML certification
  3. Utility or grid software placement (Tesla Powerwall team, AutoGrid, GridX)
- **Образ:** Дирижёр энергетической сети. Каждую секунду балансирует millions of devices.

---

#### 99. AI Logistics Optimizer

- **Что делает:** AI для supply chain optimization — routing, inventory, demand forecasting, last-mile.
- **Ключевые навыки:**
  - Operations research deep
  - ML forecasting
  - Geospatial / routing algorithms
  - SAP/Oracle integration
  - Real-time systems
- **Demand:** ⭐⭐⭐⭐ (Amazon, FedEx, DHL, project44)
- **Как стать:**
  1. OR or industrial engineering foundation
  2. ML + supply chain specialty
  3. Industry placement
- **Образ:** Шахматист на доске в 1 миллион клеток. Каждая ходка — товар через мир.

---

#### 100. AI Supply Chain Architect

- **Что делает:** Strategy + architecture для AI-enabled supply chain — resilience, sustainability, transparency.
- **Ключевые навыки:**
  - Supply chain strategy
  - Multi-tier visibility (graph data)
  - Risk modeling
  - ESG integration
  - Vendor management
- **Demand:** ⭐⭐⭐⭐ (post-COVID resilience focus + China decoupling)
- **Как стать:**
  1. Supply chain career 7-10 лет
  2. AI/digital transformation specialty
  3. Senior consulting or industry role
- **Образ:** Архитектор кровеносной системы мировой торговли. AI = МРТ для каждого узла.

---

## <a id="b-v2"></a>🌳 Section B6-B10: ещё 50 ГИБРИДНЫХ профессий

---

### B6. Healthcare hybrids (10 профессий)

> AI помогает врачу, но не заменяет лицензированную работу и не даёт персональных медицинских рекомендаций.

---

#### 101. Surgeon + AI = AI-Augmented Surgeon

- **Что делает:** Хирург с Da Vinci + AI overlay для real-time guidance, anatomy recognition, complication prediction.
- **Ключевые навыки:**
  - Surgical residency (8-10 лет, base)
  - Robotic surgery certification
  - AI tool fluency
  - Real-time decision making
  - Multi-tasking (видеть и AI, и пациента)
- **Demand:** ⭐⭐⭐⭐ (every top hospital wants this)
- **Как стать:**
  1. MD + surgery residency + fellowship
  2. Robotic surgery certification
  3. AI augmentation training
- **Образ:** Пилот пассажирского лайнера с автопилотом + супер-радар. Управляет вместе с AI.

---

#### 102. Radiologist + AI = Diagnostic AI Specialist

- **Что делает:** Радиолог + AI triage (Aidoc, Rad AI). Видит 200 cases вместо 80, с lower miss rate.
- **Ключевые навыки:**
  - Radiology foundation (residency)
  - AI tool literacy
  - Quality assurance methodologies
  - Productivity workflow management
  - Patient communication
- **Demand:** ⭐⭐⭐⭐ (radiology shortage + AI solves throughput)
- **Как стать:**
  1. MD radiology residency
  2. AI tool certification (Aidoc, Annalise.ai)
  3. Hospital AI champion role
- **Образ:** Сокол + AI = радиолог. AI смотрит каждую тень — человек принимает решение.

---

#### 103. Pharmacist + AI = AI-Enabled Pharmacist

- **Что делает:** Фармацевт + AI tools для drug interaction checks, personalized dosing, medication therapy management.
- **Ключевые навыки:**
  - Pharm-D foundation
  - Clinical decision support tools
  - Pharmacogenomics basics
  - Patient education
  - EHR navigation
- **Demand:** ⭐⭐⭐⭐ (community pharmacy + hospital roles)
- **Как стать:**
  1. Pharm-D degree
  2. AI tool certification
  3. Specialty MTM training
- **Образ:** Контролёр взаимодействий миллиона лекарств. Раньше — в голове. Сейчас — AI помогает.

---

#### 104. Nurse + AI = AI-Augmented Practitioner

- **Что делает:** Медсестра + AI для triage, early warning systems, patient monitoring, documentation.
- **Ключевые навыки:**
  - RN/BSN/NP foundation
  - AI tool comfort
  - Critical thinking при AI false positives
  - Patient advocacy
  - Workflow integration
- **Demand:** ⭐⭐⭐⭐⭐ (nursing shortage + AI accelerates productivity)
- **Как стать:**
  1. Nursing degree
  2. AI clinical tool training
  3. Specialty certification (NP, CNS)
- **Образ:** Медсестра с третьим глазом. AI видит ухудшение пациента за 4 часа до crash.

---

#### 105. Dentist + AI = AI Diagnostic Dentist

- **Что делает:** Стоматолог + AI vision на X-rays (Pearl, VideaHealth) для cavity detection, treatment planning.
- **Ключевые навыки:**
  - DDS/DMD foundation
  - AI X-ray tool literacy
  - Treatment planning
  - Patient communication (explaining AI findings)
  - Insurance navigation
- **Demand:** ⭐⭐⭐⭐ (Pearl + VideaHealth + emerging)
- **Как стать:**
  1. DDS/DMD degree
  2. AI tool certification
  3. Practice management
- **Образ:** Стоматолог + рентгенолог в одном лице. AI находит то что глаз пропускает.

---

#### 106. Veterinarian + AI = AI Vet Assistant

- **Что делает:** Ветеринар + AI vision (cancer in scans), telemedicine triage, breed-specific dosing.
- **Ключевые навыки:**
  - DVM foundation
  - AI imaging tool literacy
  - Multi-species knowledge
  - Telemedicine workflow
  - Owner communication
- **Demand:** ⭐⭐⭐ (vet shortage + AI accelerates)
- **Как стать:**
  1. DVM degree
  2. AI tool certification
  3. Specialty practice
- **Образ:** Семейный врач для существ которые не говорят. AI помогает услышать.

---

#### 107. Physical Therapist + AI = AI Movement Coach

- **Что делает:** PT + AI motion analysis (Sword Health, Hinge Health) для personalized rehab + injury prevention.
- **Ключевые навыки:**
  - DPT foundation
  - Motion analysis tool literacy
  - Tele-rehab workflows
  - Patient engagement
  - Outcomes measurement
- **Demand:** ⭐⭐⭐⭐ (Sword Health \$3B valuation, Hinge IPO)
- **Как стать:**
  1. DPT degree
  2. Tele-PT platform training
  3. Specialty certification
- **Образ:** Тренер + анализ Олимпийского уровня для обычного пациента. AI видит как ты двигаешься.

---

#### 108. Psychiatrist + AI = AI-Augmented Mental Health Specialist

- **Что делает:** Психиатр + AI для symptom tracking, medication response prediction, between-visit support.
- **Ключевые навыки:**
  - MD psychiatry foundation
  - AI literacy + safety
  - Digital therapeutics integration
  - Privacy + ethics
  - Patient-AI relationship navigation
- **Demand:** ⭐⭐⭐⭐ (mental health crisis + telepsych explosion)
- **Как стать:**
  1. MD + psychiatry residency
  2. Digital health certification
  3. Hybrid practice setup
- **Образ:** Психиатр с AI-журналом каждого пациента. Видит паттерны за месяцы — не только в кабинете.

---

#### 109. Optometrist + AI = AI Vision Specialist

- **Что делает:** Оптометрист + AI retinal scans (Eyenuk, IDx-DR) для diabetic retinopathy, glaucoma, AMD detection.
- **Ключевые навыки:**
  - OD foundation
  - AI screening tool literacy
  - Patient education
  - Referral pathways
  - Telehealth integration
- **Demand:** ⭐⭐⭐ (FDA-approved tools growing, walmart/costco vision)
- **Как стать:**
  1. OD degree
  2. AI tool certification
  3. Practice integration
- **Образ:** Окулист + AI = детектор болезней глаз за минуту. Раньше — годы пропускали.

---

#### 110. Cardiologist + AI = AI Cardiology Specialist

- **Что делает:** Кардиолог + AI на ECG, echo, cardiac MRI (Ultromics, Caption Health). Predicts heart failure 5 years ahead.
- **Ключевые навыки:**
  - MD cardiology foundation
  - AI imaging tool literacy
  - Wearable data integration (Apple Watch, KardiaMobile)
  - Patient-facing AI tools
  - Quality assurance
- **Demand:** ⭐⭐⭐⭐⭐ (heart disease #1 killer + AI tools mature)
- **Как стать:**
  1. MD + cardiology fellowship
  2. AI imaging certification
  3. Research / clinical AI champion role
- **Образ:** Кардиолог + AI = детектор инфаркта за 5 лет. Профилактика вместо реанимации.

---

### B7. Government / Public Sector (10 профессий)

---

#### 111. Police Officer + AI = AI-Augmented Officer

- **Что делает:** Офицер + body cam AI + predictive analytics + report-writing AI (Axon Draft One).
- **Ключевые навыки:**
  - Police academy foundation
  - AI tool literacy
  - Bias awareness
  - Civil liberties knowledge
  - Community engagement
- **Demand:** ⭐⭐⭐ (Axon dominating, controversy ongoing)
- **Как стать:**
  1. Police academy
  2. AI body cam certification
  3. Community policing training
- **Образ:** Офицер с AI-партнёром. AI пишет отчёты — офицер работает с людьми.

---

#### 112. Judge + AI = AI-Assisted Judiciary

- **Что делает:** Судья + AI для legal research, case precedent search, sentencing recommendations (controversial).
- **Ключевые навыки:**
  - JD + judicial experience
  - AI tool literacy
  - Bias awareness in AI
  - Constitutional law
  - Ethics
- **Demand:** ⭐⭐⭐ (slow adoption due to ethical concerns)
- **Как стать:**
  1. JD + bar
  2. Legal AI training
  3. Judicial appointment / election
- **Образ:** Судья + библиотекарь всего права в одном. AI suggests — человек решает.

---

#### 113. Urban Planner + AI = Smart City Planner

- **Что делает:** Урбанист + AI simulation для traffic, zoning, public services, climate adaptation.
- **Ключевые навыки:**
  - Urban planning foundation
  - GIS + ML
  - Stakeholder engagement
  - Simulation tools
  - Equity analysis
- **Demand:** ⭐⭐⭐⭐ (smart cities investment wave)
- **Как стать:**
  1. MPA или urban planning degree
  2. GIS + data science certification
  3. Municipal placement
- **Образ:** Архитектор города-машины. Каждое решение проверено в симуляции 1000 раз.

---

#### 114. Social Worker + AI = AI-Enabled Caseworker

- **Что делает:** Social worker + AI для case prioritization, benefit eligibility check, risk assessment.
- **Ключевые навыки:**
  - MSW foundation
  - AI tool literacy
  - Bias + ethics awareness
  - Trauma-informed care
  - Resource navigation
- **Demand:** ⭐⭐⭐⭐ (caseload reduction = mission)
- **Как стать:**
  1. MSW degree
  2. AI tool training
  3. Agency placement
- **Образ:** Социальный работник с AI-помощником-документалистом. Больше времени с людьми — меньше с бумагами.

---

#### 115. Tax Auditor + AI = AI-Augmented Auditor

- **Что делает:** Auditor + AI для anomaly detection, fraud pattern recognition, audit selection.
- **Ключевые навыки:**
  - Accounting/audit foundation
  - AI tool literacy
  - Data analysis
  - Communication
  - Regulatory awareness
- **Demand:** ⭐⭐⭐⭐ (Big 4 + IRS modernization)
- **Как стать:**
  1. CPA foundation
  2. Data analytics specialization
  3. Big 4 or agency placement
- **Образ:** Аудитор с миллионом глаз AI на каждой транзакции. Аномалии видны за секунды.

---

#### 116. Customs Officer + AI = AI Border Specialist

- **Что делает:** Border agent + AI scanning (cargo, faces, behavior). Tradeoffs vs civil liberties.
- **Ключевые навыки:**
  - Customs/border training
  - AI scanning tool literacy
  - International trade knowledge
  - Bias awareness
  - Multilingual + cultural
- **Demand:** ⭐⭐⭐ (ICE, CBP modernization)
- **Как стать:**
  1. Federal LE training
  2. AI tool certification
  3. Specialty assignment
- **Образ:** Таможенник с рентгеном который видит на miles around. Спорно — но реально.

---

#### 117. Military Officer + AI = AI Strategy Officer

- **Что делает:** Военный офицер + AI для intelligence analysis, mission planning, battlefield awareness.
- **Ключевые навыки:**
  - Military training (academy + experience)
  - AI tool literacy
  - International law (LOAC)
  - Strategic thinking
  - Cybersecurity
- **Demand:** ⭐⭐⭐⭐ (Palantir, Anduril, traditional defense)
- **Как стать:**
  1. Military academy or commission
  2. AI defense certification
  3. Joint duty / specialty assignment
- **Образ:** Командир + AI = генерал с обзором всего поля одновременно. Решения за секунды, не дни.

---

#### 118. Diplomat + AI = AI Translation/Analysis Specialist

- **Что делает:** Дипломат + AI translation + sentiment analysis + cultural intelligence.
- **Ключевые навыки:**
  - International relations background
  - AI translation tool literacy (limits + risks)
  - Multilingual baseline
  - Cultural intelligence
  - Negotiation
- **Demand:** ⭐⭐⭐ (State Dept modernization, NGOs)
- **Как стать:**
  1. IR degree + foreign service exam
  2. AI tool training
  3. Foreign posting
- **Образ:** Дипломат с AI-помощником. Понимает not just words but contexts через cultures.

---

#### 119. Public Health Officer + AI = AI Epidemiologist

- **Что делает:** Public health + AI для epidemic forecasting, contact tracing, intervention planning.
- **Ключевые навыки:**
  - MPH foundation
  - Time-series ML
  - Geospatial analysis
  - Public communication
  - Crisis management
- **Demand:** ⭐⭐⭐⭐ (post-COVID investment + ongoing threats)
- **Как стать:**
  1. MPH degree
  2. Data science training
  3. CDC/WHO/state placement
- **Образ:** Часовой эпидемий. AI видит outbreak за дни до того как становится новостью.

---

#### 120. Election Officer + AI = AI Verification Specialist

- **Что делает:** Election admin + AI для signature verification, ballot processing, misinformation detection.
- **Ключевые навыки:**
  - Election administration
  - AI tool literacy
  - Security + audit trails
  - Public trust + transparency
  - Regulatory compliance
- **Demand:** ⭐⭐ (slow adoption, controversial)
- **Как стать:**
  1. Election admin career
  2. AI tool training
  3. State/county placement
- **Образ:** Хранитель честности голосования. AI ускоряет — человек гарантирует.

---

### B8. Religion / Philosophy / Coaching (5 профессий)

---

#### 121. Pastor / Priest + AI = AI-Augmented Spiritual Counselor

- **Что делает:** Священник + AI для sermon prep, biblical research, congregant follow-up (boundaries critical).
- **Ключевые навыки:**
  - Theological foundation
  - AI tool literacy
  - Boundaries + discernment
  - Pastoral care
  - Community building
- **Demand:** ⭐⭐ (slow adoption, but growing)
- **Как стать:**
  1. Seminary/ministry training
  2. AI tool training
  3. Community placement
- **Образ:** Священник + AI = расширенная библиотека. Человеческое сердце всегда первое.

---

#### 122. Philosophy Professor + AI = AI Ethics Educator

- **Что делает:** Профессор философии + AI ethics specialty. Учит students как мыслить о AI ethics critically.
- **Ключевые навыки:**
  - Philosophy PhD
  - AI ethics literature
  - Pedagogy
  - Engagement с industry
  - Public communication
- **Demand:** ⭐⭐⭐⭐ (every university needs AI ethics course)
- **Как стать:**
  1. Philosophy PhD
  2. AI ethics specialization
  3. Faculty + consulting
- **Образ:** Учитель мудрости в эру скорости. AI быстрый — мудрый медленный. Нужны оба.

---

#### 123. Life Coach + AI = AI Personal Development Coach

- **Что делает:** Coach + AI для goal tracking, habit reinforcement, between-session support (Replika-style done right).
- **Ключевые навыки:**
  - Coaching certification (ICF)
  - AI tool literacy
  - Boundaries
  - Marketing + sales
  - Privacy awareness
- **Demand:** ⭐⭐⭐ (coaching industry growing, AI fits)
- **Как стать:**
  1. ICF coaching certification
  2. AI tool training
  3. Build practice
- **Образ:** Коуч + AI-журнал клиента. Видит паттерны за месяцы — meeting раз в неделю.

---

#### 124. Career Counselor + AI = AI Career Navigator

- **Что делает:** Career counselor + AI для job market analysis, skill gap assessment, personalized career paths.
- **Ключевые навыки:**
  - Counseling foundation
  - AI tool literacy
  - Job market data analysis
  - Industry awareness
  - Empathy
- **Demand:** ⭐⭐⭐⭐ (career disruption = need for guides)
- **Как стать:**
  1. MS counseling or career development cert
  2. AI tool training
  3. University, non-profit, or private practice
- **Образ:** Навигатор в эпоху turbulence. AI видит карту — человек знает тебя.

---

#### 125. Meditation Teacher + AI = AI Mindfulness Guide

- **Что делает:** Учитель медитации + AI personalization (Headspace, Calm, Balance + AI).
- **Ключевые навыки:**
  - Meditation teaching certification
  - AI tool literacy
  - Personalization design
  - Boundaries
  - Cultural sensitivity
- **Demand:** ⭐⭐⭐ (mental health crisis + tech)
- **Как стать:**
  1. Meditation teacher training (MBSR, etc.)
  2. AI app collaboration
  3. Build audience
- **Образ:** Учитель + AI = персональная медитация для каждого. Не "one size fits all" — а "for you, now".

---

### B9. Sports / Athletics (10 профессий)

---

#### 126. Athlete + AI = AI-Trained Performer

- **Что делает:** Athlete + AI для biomechanics analysis, nutrition optimization, sleep, mental prep.
- **Ключевые навыки:**
  - Elite athletic foundation
  - AI tool comfort
  - Data interpretation
  - Self-discipline
  - Coach collaboration
- **Demand:** ⭐⭐⭐ (every elite athlete has data team)
- **Как стать:**
  1. Athletic excellence (one path)
  2. Data literacy
  3. Coach + tech partnership
- **Образ:** Олимпийский атлет + AI = 1% optimization daily. Через год — недостижимый уровень.

---

#### 127. Coach + AI = AI Performance Coach

- **Что делает:** Coach + AI на video analysis, opponent scouting, training plan optimization.
- **Ключевые навыки:**
  - Coaching foundation (years of experience)
  - AI video analysis tools (Hudl, Sportscode)
  - Data interpretation
  - Communication к athletes
  - Strategy
- **Demand:** ⭐⭐⭐⭐ (data + AI now table stakes)
- **Как стать:**
  1. Coaching career
  2. Sports analytics certification
  3. Higher levels through results
- **Образ:** Тренер + второй мозг. Видит patterns в каждой игре + предсказывает opponents.

---

#### 128. Referee + AI = AI-Augmented Official

- **Что делает:** Referee + VAR-style AI for in-game decision support.
- **Ключевые навыки:**
  - Refereeing foundation
  - AI tool literacy
  - Real-time decision making
  - Communication
  - Pressure tolerance
- **Demand:** ⭐⭐⭐ (controversy ongoing, but growing)
- **Как стать:**
  1. Officiating training + experience
  2. AI tool certification
  3. Level progression
- **Образ:** Судья + AI = меньше ошибок, больше доверия. (Если хорошо implemented.)

---

#### 129. Sports Scout + AI = AI Talent Scout

- **Что делает:** Scout + AI для player evaluation, draft prediction, prospect tracking.
- **Ключевые навыки:**
  - Sports knowledge deep
  - Data analytics
  - Travel + networking
  - Pattern recognition
  - Communication
- **Demand:** ⭐⭐⭐ (data-driven scouting wave)
- **Как стать:**
  1. Playing or coaching foundation
  2. Analytics specialty
  3. Team placement
- **Образ:** Скаут + AI = видеть будущую звезду в подростке. Раньше — интуиция. Сейчас — intuition + 1000 metrics.

---

#### 130. Sports Commentator + AI = AI Multilingual Caster

- **Что делает:** Каст + AI for real-time stats, multilingual translation, fact-checking.
- **Ключевые навыки:**
  - Broadcasting foundation
  - Sports knowledge deep
  - AI tool comfort
  - Live performance under pressure
  - Storytelling
- **Demand:** ⭐⭐⭐ (streaming + multilingual content)
- **Как стать:**
  1. Journalism / broadcasting foundation
  2. Sports specialty
  3. AI tool integration
- **Образ:** Комментатор + AI = stats в реальном времени. Каждый player, каждая игра.

---

#### 131. Trainer + AI = AI Conditioning Specialist

- **Что делает:** Strength + conditioning coach + AI for load management, injury prevention, peak performance timing.
- **Ключевые навыки:**
  - S&C certification (NSCA CSCS)
  - AI wearable data interpretation
  - Periodization
  - Sport-specific training
  - Athlete communication
- **Demand:** ⭐⭐⭐⭐ (every pro team)
- **Как стать:**
  1. Exercise science degree + CSCS
  2. AI tool training (Catapult, Whoop)
  3. Pro team placement
- **Образ:** Тренер + AI = тренировка под микроскопом. Знает когда давить, когда отдыхать.

---

#### 132. Sports Medicine + AI = AI Injury Prediction Specialist

- **Что делает:** Sports med doc + AI for injury risk prediction, return-to-play decisions, recovery optimization.
- **Ключевые навыки:**
  - MD/DO sports medicine
  - AI tool literacy
  - Biomechanics
  - Imaging interpretation
  - Player relationships
- **Demand:** ⭐⭐⭐⭐ (injury = millions lost, AI helps)
- **Как стать:**
  1. MD + sports med fellowship
  2. AI tool certification
  3. Team placement
- **Образ:** Врач команды + хрустальный шар. Предсказывает injury за недели.

---

#### 133. Sports Manager + AI = AI Team Strategist

- **Что делает:** GM + AI for player valuation, contract negotiation analytics, salary cap optimization.
- **Ключевые навыки:**
  - MBA or extensive sports business background
  - Advanced analytics
  - Negotiation
  - Salary cap mastery
  - Long-term planning
- **Demand:** ⭐⭐⭐ (top jobs few, but huge)
- **Как стать:**
  1. Sports business career
  2. Front office progression
  3. Analytics fluency
- **Образ:** GM + AI = шахматы на 50 ходов вперёд. Player + contracts + salary cap.

---

#### 134. E-sports Coach + AI = AI Gaming Performance Coach

- **Что делает:** E-sports coach + AI replay analysis + opponent prediction + mental game.
- **Ключевые навыки:**
  - Gaming expertise (specific titles)
  - AI replay tools
  - Mental performance
  - Communication к young players
  - Streaming awareness
- **Demand:** ⭐⭐⭐ (e-sports professionalization)
- **Как стать:**
  1. Gaming career or analyst path
  2. Coaching certifications
  3. Team placement
- **Образ:** Тренер для гейминга, где скорость рефлексов + AI analysis = чемпионство.

---

#### 135. Sports Journalism + AI = AI Sports Analyst

- **Что делает:** Журналист + AI для data-driven storytelling, real-time analysis, multi-platform content.
- **Ключевые навыки:**
  - Journalism foundation
  - Sports knowledge
  - AI tool literacy
  - Multi-platform content
  - Audience engagement
- **Demand:** ⭐⭐⭐ (Athletic + ESPN + emerging)
- **Как стать:**
  1. Journalism degree or path
  2. Sports beat
  3. AI tool integration
- **Образ:** Журналист + AI = data + story. Раньше факт. Сейчас факт + 1000 контекстов.

---

### B10. Manufacturing / Logistics (15 профессий)

---

#### 136. Assembly Worker + AI = AI-Augmented Operator

- **Что делает:** Factory worker + AR glasses + AI guidance for assembly, quality check.
- **Ключевые навыки:**
  - Manufacturing foundation
  - AR glasses comfort
  - AI tool literacy
  - Quality awareness
  - Adaptability
- **Demand:** ⭐⭐⭐ (Industry 4.0 adoption)
- **Как стать:**
  1. Manufacturing job
  2. AR/AI tool training
  3. Specialty upskilling
- **Образ:** Рабочий + умные очки = каждая деталь правильно. AI ловит ошибки до того как уйдут.

---

#### 137. Warehouse Worker + AI = AI-Picker Hybrid

- **Что делает:** Warehouse + AI picking guidance + robot collaboration (Amazon, GXO, Locus Robotics).
- **Ключевые навыки:**
  - Warehouse foundation
  - Robot collaboration
  - AI tool literacy
  - Physical fitness
  - Safety awareness
- **Demand:** ⭐⭐⭐⭐ (Amazon scale + everyone follows)
- **Как стать:**
  1. Warehouse hire
  2. Robot training
  3. Lead/specialist roles
- **Образ:** Picker + AI робот = команда. Робот таскает — человек думает.

---

#### 138. Truck Driver + AI = AI-Autonomy Supervisor

- **Что делает:** Truck driver + autonomous truck monitoring (Aurora, Kodiak, TuSimple).
- **Ключевые навыки:**
  - CDL foundation
  - AI supervision skills
  - Edge case decision making
  - Safety
  - Logistics awareness
- **Demand:** ⭐⭐⭐ (transition phase 2026-2030)
- **Как стать:**
  1. CDL training
  2. Autonomous truck certification
  3. Aurora/Kodiak/etc placement
- **Образ:** Капитан корабля + автопилот. Автопилот ведёт — капитан принимает edge cases.

---

#### 139. Pilot + AI = AI-Augmented Pilot

- **Что делает:** Commercial pilot + AI autopilot + AI flight planning + AI fatigue monitoring.
- **Ключевые навыки:**
  - ATPL or military pilot
  - AI tool literacy
  - Crisis management
  - CRM (crew resource management)
  - Continuous training
- **Demand:** ⭐⭐⭐ (pilot shortage + AI augments)
- **Как стать:**
  1. Flight training (long road)
  2. Airline progression
  3. AI augmentation training
- **Образ:** Пилот + AI = двойной cockpit. Один не заменяет другого — augments.

---

#### 140. Air Traffic Controller + AI = AI Traffic Optimizer

- **Что делает:** ATC + AI for traffic optimization, conflict prediction, weather routing.
- **Ключевые навыки:**
  - ATC certification (FAA / EASA)
  - AI tool literacy
  - Crisis management
  - Multi-tasking
  - Calm under pressure
- **Demand:** ⭐⭐⭐ (FAA modernization)
- **Как стать:**
  1. FAA Academy
  2. ATC certification
  3. AI tool training
- **Образ:** Дирижёр неба + AI. AI предупреждает о конфликтах за минуты.

---

#### 141. Ship Captain + AI = AI Marine Operator

- **Что делает:** Captain + autonomous ship monitoring (Yara Birkeland, ASKO autonomous vessels).
- **Ключевые навыки:**
  - Maritime training
  - AI tool literacy
  - Weather + navigation
  - Crisis management
  - Logistics
- **Demand:** ⭐⭐ (slow adoption, but growing)
- **Как стать:**
  1. Maritime academy
  2. Sea time + certifications
  3. AI vessel training
- **Образ:** Капитан + автономный корабль = меньше команды, больше технологии.

---

#### 142. Postal Worker + AI = AI-Augmented Delivery Specialist

- **Что делает:** Delivery + AI routing + drone integration + customer touchpoint optimization.
- **Ключевые навыки:**
  - Delivery foundation
  - AI routing tool literacy
  - Drone basics (where applicable)
  - Customer service
  - Physical fitness
- **Demand:** ⭐⭐⭐⭐ (Amazon, UPS, FedEx, USPS)
- **Как стать:**
  1. Delivery job
  2. AI tool training
  3. Specialty roles
- **Образ:** Почтальон + AI = маршрут оптимизирован каждый день. Customers — happy.

---

#### 143. Cleaner + AI = AI-Powered Facility Manager

- **Что делает:** Cleaner + AI robot fleet management (Avidbots, Whiz robots).
- **Ключевые навыки:**
  - Cleaning industry foundation
  - Robot fleet management
  - AI tool literacy
  - Quality assurance
  - Customer service
- **Demand:** ⭐⭐⭐ (commercial cleaning automation wave)
- **Как стать:**
  1. Cleaning industry experience
  2. Robot operation certification
  3. Management role
- **Образ:** Уборщик + флот роботов = чище, быстрее, дешевле. Управление, не швабра.

---

#### 144. Security Guard + AI = AI Surveillance Operator

- **Что делает:** Guard + AI cameras + behavior analysis + threat prediction.
- **Ключевые навыки:**
  - Security training
  - AI tool literacy
  - Bias awareness
  - Calm under pressure
  - Customer service
- **Demand:** ⭐⭐⭐ (Verkada, Rhombus, growing)
- **Как стать:**
  1. Security certification
  2. AI tool training
  3. Specialty placement
- **Образ:** Охранник + 1000 камер с AI = один человек видит то что раньше 10 не могли.

---

#### 145. Construction Worker + AI = AI-Augmented Builder

- **Что делает:** Construction + AI plan visualization + AR guidance + safety monitoring.
- **Ключевые навыки:**
  - Construction trade foundation
  - AR/AI tool literacy
  - Safety awareness
  - Plan reading
  - Team collaboration
- **Demand:** ⭐⭐⭐⭐ (construction tech wave)
- **Как стать:**
  1. Trade apprenticeship
  2. AI/AR tool training
  3. Specialty roles
- **Образ:** Строитель + AR очки = blueprint на месте. Меньше ошибок, быстрее.

---

#### 146. Quality Inspector + AI = AI Vision Inspector

- **Что делает:** QC + AI computer vision for defect detection в manufacturing.
- **Ключевые навыки:**
  - QC foundation
  - AI vision tool literacy
  - Statistical process control
  - Specification reading
  - Communication
- **Demand:** ⭐⭐⭐⭐ (every factory)
- **Как стать:**
  1. QC training
  2. AI tool certification
  3. Industry specialization
- **Образ:** QC + AI глаз = каждая деталь проверена. 100% sample size — раньше невозможно.

---

#### 147. Logistics Manager + AI = AI Supply Chain Coordinator

- **Что делает:** Logistics manager + AI for route optimization, exception management, vendor coordination.
- **Ключевые навыки:**
  - Supply chain foundation
  - AI tool literacy (TMS, WMS)
  - Vendor management
  - Exception handling
  - Data analysis
- **Demand:** ⭐⭐⭐⭐ (every shipper)
- **Как стать:**
  1. Logistics career
  2. AI tool training
  3. Mgmt progression
- **Образ:** Логистик + AI = меньше exceptions, лучше service.

---

#### 148. Procurement Specialist + AI = AI Buyer

- **Что делает:** Procurement + AI for vendor analysis, spend optimization, contract intelligence.
- **Ключевые навыки:**
  - Procurement foundation
  - AI tool literacy
  - Negotiation
  - Contract review
  - Spend analysis
- **Demand:** ⭐⭐⭐ (every Fortune 500)
- **Как стать:**
  1. Procurement career
  2. AI tool training
  3. Specialty (direct/indirect, services)
- **Образ:** Закупщик + AI = знает рынок лучше vendors. Экономит миллионы.

---

#### 149. Inventory Manager + AI = AI Stock Optimizer

- **Что делает:** Inventory manager + AI for demand forecasting, optimization, replenishment.
- **Ключевые навыки:**
  - Inventory management foundation
  - AI forecasting tools
  - ERP fluency
  - Statistical understanding
  - Communication
- **Demand:** ⭐⭐⭐⭐ (retail + e-commerce + manufacturing)
- **Как стать:**
  1. SCM degree or experience
  2. AI tool training
  3. Industry specialization
- **Образ:** Inventory + AI = right stock, right time. Не "сколько хочется" — "сколько нужно".

---

#### 150. Production Manager + AI = AI Manufacturing Engineer

- **Что делает:** Production mgr + AI for scheduling, capacity planning, OEE optimization.
- **Ключевые навыки:**
  - Manufacturing foundation
  - AI tool literacy
  - Lean / Six Sigma
  - Team management
  - Data interpretation
- **Demand:** ⭐⭐⭐⭐ (Industry 4.0)
- **Как стать:**
  1. Manufacturing/IE degree
  2. Plant experience
  3. AI tool training
- **Образ:** Производственник + AI = меньше downtime, больше output. Каждая минута считается.

---

## <a id="c-extended"></a>🔥 Section C-Extended: 25 исчезающих профессий

Расширяем с 10 до 25 — добавляем 15 more.

---

#### 11. Bookkeeper (basic)

- **Что заменяется:** AI bookkeeping (Pilot, Bench AI, QuickBooks autopilot).
- **Что выживет:** Senior accountants + CPAs + специалисты по сложным entities.
- **Образ:** Excel-ниндзя теряет работу. CPA с advisory mindset выигрывает.

---

#### 12. Court Stenographer

- **Что заменяется:** AI transcription + summarization (Verbit, Trint, Voicea).
- **Что выживет:** Realtime captioners для accessibility, specialty legal recording.
- **Образ:** Машинистка суда уходит. Сертифицированный court reporter для critical cases остаётся.

---

#### 13. Travel Agent (basic)

- **Что заменяется:** AI travel planning (ChatGPT + Booking.com + Kayak).
- **Что выживет:** Luxury/specialty travel agents (за личное знакомство, концирж-сервис).
- **Образ:** Базовый агент с 1990s уходит. Concierge с private contacts остаётся.

---

#### 14. Drive-Through Cashier

- **Что заменяется:** AI voice ordering (McDonald's, Chick-fil-A, Wendy's pilots).
- **Что выживет:** Friendly hosts для customer experience роли.
- **Образ:** Окошко без человека — голос AI принимает заказ.

---

#### 15. Telemarketer

- **Что заменяется:** AI voice agents (cheaper, never tired).
- **Что выживет:** High-value B2B SDRs для complex sales (relationship matters).
- **Образ:** Cold caller на рутинных звонках уходит. SDR с domain expertise остаётся.

---

#### 16. Library Cataloger

- **Что заменяется:** AI metadata extraction + classification.
- **Что выживет:** Librarians как research consultants, digital archivists.
- **Образ:** Каталогизатор уходит. Librarian-помощник по поиску информации остаётся.

---

#### 17. Toll Booth Operator

- **Что заменяется:** Electronic tolling + license plate readers (уже почти ушёл).
- **Что выживет:** Уже почти не существует.
- **Образ:** Будка с человеком — рудимент. Cashless всё.

---

#### 18. Bank Teller

- **Что заменяется:** Mobile banking + AI customer service.
- **Что выживет:** Wealth management advisors, complex transaction specialists.
- **Образ:** Базовое окно банка уходит. Personal banker для \$1M+ accounts остаётся.

---

#### 19. Newspaper Delivery

- **Что заменяется:** Digital subscriptions, dying print industry.
- **Что выживет:** Уже почти не существует (legacy для elderly).
- **Образ:** Велосипедист в 5 утра уходит. Push notification приходит.

---

#### 20. Movie Ticket Sales

- **Что заменяется:** Self-serve kiosks + mobile apps.
- **Что выживет:** Cinema experience hosts (specialty IMAX, premium).
- **Образ:** Касса в кино уходит. QR-код приходит.

---

#### 21. Encyclopedia Salesperson (уже исчез)

- **Что было:** Door-to-door + comprehensive set seller.
- **Что заменилось:** Wikipedia + Google + Claude.
- **Образ:** Уже история. Учиться на memento mori для других профессий.

---

#### 22. Print Magazine Editor (basic)

- **Что заменяется:** Digital-first + AI content generation.
- **Что выживет:** Specialty/luxury print (Monocle, Apartamento), digital editors-in-chief.
- **Образ:** Mass-market magazine уходит. Niche print + digital остаются.

---

#### 23. Phone Book Publisher (уже исчез)

- **Что было:** Yellow Pages + White Pages annually.
- **Что заменилось:** Google Maps + LinkedIn + Yelp.
- **Образ:** Mementо mori. Тяжёлая книга на пороге — archive только.

---

#### 24. Stockbroker (entry-level retail)

- **Что заменяется:** Robo-advisors (Wealthfront, Betterment) + commission-free trading.
- **Что выживет:** High-net-worth advisors, специалисты по options + alternatives.
- **Образ:** Retail broker за commission уходит. Wealth manager с holistic planning остаётся.

---

#### 25. Travel Typist

- **Что заменяется:** Self-service booking + AI assistants.
- **Что выживет:** Specialty corporate travel managers.
- **Образ:** Машинистка-туристический агент уходит. Corporate travel architect остаётся.

---

## <a id="d-extended"></a>🛠 Section D-Extended: 50 Skills для будущего

Расширяем с 25 до 50.

### AI-Specific Technical (25 new)

#### 26. AI Prompt Versioning

Системный подход к version control промптов как code — git, A/B test, rollback.

#### 27. LLM Cost Forecasting

Прогноз cost based on usage patterns. Capacity planning \$\$\$.

#### 28. Multi-Agent Debugging

Trace agent communication, find failure modes, root cause distributed bugs.

#### 29. Voice Agent Tuning

Optimization latency + naturalness + interruption handling.

#### 30. RAG Architecture Design

Chunking strategies, retrieval rerankers, multi-modal RAG.

#### 31. Local Model Fine-Tuning

LoRA, QLoRA, hardware-aware optimization на consumer GPUs.

#### 32. AI Safety Auditing

Red-teaming, adversarial probing, alignment evaluation.

#### 33. Constitutional AI Design

Designing principles → behaviors translation для AI systems.

#### 34. AI Ethics Judgment

Resolving conflicts between competing principles, contextual ethics.

#### 35. Cross-Cultural AI Deployment

Tuning AI behavior для разных cultures, language, value systems.

#### 36. AI Procurement

Vendor evaluation, contracts, SLA, data ownership.

#### 37. AI Vendor Negotiation

Pricing, commitments, data clauses, switching costs awareness.

#### 38. Tax/Legal AI Implications

Understanding AI usage tax implications, employment law impact.

#### 39. AI Insurance Literacy

Understanding insurance for AI deployments (errors, IP, liability).

#### 40. Hybrid Workflow Design

Designing human-AI workflows (handoffs, oversight, autonomy boundaries).

#### 41. AI-Human Team Management

Managing teams где люди + agents работают вместе.

#### 42. AI Cost Benchmarking

Comparing cost across providers + workloads.

#### 43. AI Evaluation Methodology

Building evals, golden datasets, regression testing.

#### 44. AI Red Teaming

Adversarial testing systems before deployment.

#### 45. AI Bias Testing

Fairness across demographics, edge cases discovery.

#### 46. Agent Capability Assessment

Evaluating what agent can vs cannot do reliably.

#### 47. AI Memory Architecture

Designing long-term, working, episodic memory for agents.

#### 48. Tool Use Design

When/how to give agents tools vs prompt-only.

#### 49. MCP Server Creation

Building Model Context Protocol servers.

#### 50. Local AI Ops

Running on-prem AI infrastructure (Ollama, LM Studio, vLLM).

---

## <a id="section-f"></a>📅 Section F: Year-by-Year Прогноз 2027-2030

> **Disclaimer:** Это сценарии автора, а не факты. Числа в этом разделе убраны, остались направления.

---

### 2027 — Year of Agents

**Главный shift:** Autonomous agents переходят из demos в production. Voice AI становится default UI для many use cases.

**Key technical shifts:**

- Reliable autonomous agents в production (mainstream adoption Fortune 500)
- Voice-first interfaces становятся привычными
- AI cost: ожидается заметное удешевление токенов (прогноз, не факт)
- Multi-agent systems с 5-20 agents в production routine

**Growing professions (top 10 by demand growth):**

| # | Profession |
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

**Declining professions (top 5):**

| # | Profession |
|---|---|
| 1 | Junior copywriter |
| 2 | Tier-1 support |
| 3 | Entry-level translator |
| 4 | Routine paralegal |
| 5 | Data entry |

---

### 2028 — Year of Specialization

**Главный shift:** AI commodity layer matures. Winners = vertical AI specialists (healthcare, legal, finance).

**Key technical shifts:**

- AI commodity layer matures (frontier model differences shrink for большинства сценариев)
- Vertical AI (healthcare, legal, finance) winners emerge — moats from domain data + compliance
- Local AI приближается по качеству к frontier-моделям (прогноз)
- Multi-modal default (text + voice + vision в каждом app)

**Growing professions:**

- Vertical AI specialists (industry deep) — Healthcare, Legal, Finance AI demand
- Local AI deployment engineers
- AI safety / red team
- AI compliance roles
- AI procurement managers

**Declining:**

- Generic "AI engineer" (commodity)
- Junior software engineers (replaced by senior+AI, hire less)
- Mid-level analysts (AI does the work, hire less)

**New emerging professions 2028:**

- **AI Litigation Specialist** — lawsuits AI vs humans (IP, harm, wrongful decision)
- **AI Insurance Adjuster** — handling AI-related claims (errors, accidents, liability)
- **AI Public Defender Tech** — using AI to provide legal services to underserved
- **AI Patent Specialist** — IP for AI-generated works
- **AI Restitution Counselor** — helping people displaced by AI find new paths

---

### 2029 — Pre-AGI Tension

**Главный shift:** Models approach near-unbounded reasoning. Some professions disrupted dramatically. Regulatory frameworks fully active.

**Key technical shifts:**

- Models approach unbounded reasoning (mathematical problem solving, original research)
- Some professions disrupted dramatically (research, complex code, even creative)
- Regulatory frameworks fully in place (EU AI Act + US AI Bill of Rights + China sovereign AI)
- AI Treaty discussions начинаются (geopolitical)
- AI mediated economic activity = significant % of GDP

**Growing:**

- AI Safety Researchers (редкая экспертиза)
- AI Alignment Engineers
- AI Constitutional Engineers (designing values systems)
- AI Governance Specialists (policy + technical)
- AI Insurance/Liability specialists

**Declining (sharply):**

- Many entry-level knowledge jobs (gap year crisis для grads)
- Mid-level managers (AI flatten hierarchies)
- Generic content creators (AI bar raised dramatically)

**Crisis points:**

- Universities struggle to define what to teach grads
- Generation gap (those born 2010+ never experienced pre-AI work)
- Some countries protectionist (job preservation laws)

---

### 2030 — New Equilibrium

**Главный shift:** AI universal в knowledge work (assuming no AGI breakthrough). Human-AI augmentation = норма.

**Key technical shifts:**

- AI universal в knowledge work (если не AGI yet)
- Human-AI augmentation = новая norm (как computers в 2000s)
- Появляются компании, где один-два основателя работают с большим числом AI-агентов (прогноз)
- Specialty B2B AI vertical winners dominate
- Personal AI ownership становится культурой (как owning a domain в 1990s)

**Long-term winners (стабильные через AI):**

- **AI Safety / Ethics / Compliance** — never goes away, paid premium
- **AI-Augmented Professionals** (doctors/lawyers/etc with deep domain) — increased productivity = increased earnings
- **AI Strategy Consultants** — helping companies adopt (every enterprise needs guides)
- **Creative directors** — taste matters (AI executes, human decides)
- **Sales / relationships** — humans buy from humans (high-trust transactions)

**Long-term losers:**

- Mid-skill routine work (commodity)
- Generic content production (deflated cost)
- Basic analyst work (AI did the work)
- Standardized education paths (need adaptive learners)


---

## <a id="section-g"></a>🌍 Section G: Geographic Shifts 2026-2030

| Region | Growing | Declining | Why |
|--------|---------|-----------|-----|
| **San Francisco / NYC** | AI Safety, frontier research, AI legal/finance | Generic engineering | Remote AI commoditizes |
| **London / Berlin** | Compliance, regulation, AI ethics | Less competitive в pure tech | EU AI Act compliance hub |
| **Singapore / Dubai** | AI finance, AI healthcare | Manufacturing | Regulatory friendly + capital |
| **Mumbai / Bangalore** | AI services / outsourcing, hybrid roles | Basic IT services | Hybrid roles dominate |
| **Eastern Europe / Latam** | AI freelance / contractors | Local IT support | Cost arbitrage + AI accelerates |
| **Russia / CIS** | Self-hosted AI / sovereignty AI | Western platform jobs | Sanctions + regulation |
| **Tokyo / Seoul** | AI hardware + robotics | Service jobs | Demographics + investment |
| **Tel Aviv** | AI security, defense AI | Generic startups | Specialty + geopolitical |
| **Mexico City / Bogotá** | Nearshore AI engineering для USA | Call centers | Time zone + cost advantage |
| **Lagos / Nairobi** | AI agriculture, AI fintech | Manual labor | Local solutions + leapfrog |

---

## <a id="section-h"></a>📚 Section H: Skills Evolution Year-by-Year

### 2026 critical skills (NOW)

- **Prompt engineering** (still high value, junior bar lower)
- **Python + LLM APIs**
- **MCP integration**
- **Cost engineering** (token budgets, model selection)
- **Basic AI safety** (prompt injection, jailbreak awareness)

### 2027 critical skills

- **Multi-agent orchestration** (5+ agents, coordination patterns)
- **Voice AI development** (Vapi, Bland, Retell)
- **Local AI deployment** (Ollama, vLLM, on-prem)
- **AI cost optimization deep** (caching, distillation, routing)
- **Regulation literacy** (EU AI Act Articles, US AI EO)

### 2028 critical skills

- **Vertical AI domain expertise** (healthcare/legal/finance/etc deep)
- **AI safety / red team** (adversarial testing, alignment)
- **Local AI fine-tuning** (LoRA на specific tasks)
- **AI procurement / vendor management**
- **Cross-cultural AI deployment** (multi-region, multi-lingual)

### 2029-2030 critical skills

- **AI alignment understanding** (not just safety — alignment)
- **AI governance navigation** (policy + technical)
- **Hybrid human-AI workflow design**
- **Tax / legal AI literacy**
- **AI Treaty navigation** (geopolitical)
- **AI economics** (jobs, displacement, transition)

---

## <a id="section-i"></a>🛡 Section I: Что НЕ сделает AI до 2030

10 things AI **definitely won't** replace by 2030:

### 1. Genuine empathy в crisis moments

AI имитирует empathy — но в moments of true loss, fear, joy — humans want humans. Hospice, grief counseling, post-tragedy support — стабильно human.

### 2. Physical childbirth / breastfeeding

Биология. Никакой AI не родит ребёнка. Сопровождение тоже остаётся humanly intimate.

### 3. Real-time martial arts / combat sports

Physical embodiment + millisecond reflexes + lived training. Roboticism далеко от Olympic level в 2030.

### 4. Authentic religious / spiritual leadership

Lived experience + community connection + sacred traditions. AI может assist — не lead.

### 5. Original scientific breakthroughs

AI находит patterns в existing data. Breakthroughs часто требуют intuition + serendipity + cross-domain leaps. Human + AI = breakthrough, not AI alone.

### 6. Political leadership requiring democratic legitimacy

Voters won't elect AI. Even if AI better at policy — legitimacy = human-only.

### 7. Top-tier negotiation involving high-stakes trust

\$100M+ deals, M&A, international treaties. AI prepares — humans close.

### 8. Live performance art

Theater, concert, sports — charisma + presence + risk = humans. AI can perform but audience experience differs.

### 9. Care work requiring sustained physical presence

Childcare, elder care, hospice care, intimate physical care. Even with robots — humans wanted.

### 10. Creative direction requiring taste + cultural understanding

AI выполняет большую часть исполнительной творческой работы. Вопрос "что делать и зачем" остаётся за человеком (вкус, культурный момент, видение).

---

## <a id="section-j"></a>👥 Section J: Гибридная Экономика — 3 Archetypes 2030

К 2030, большинство knowledge workers будут в одной из 3 archetypes:

---

### Archetype 1: AI-Native Specialist

**Pattern:**

- 60-70% времени с AI
- 100% specialty в domain (legal, medical, engineering, etc)
- High productivity через AI augmentation

**Examples:** AI-Augmented Surgeon, AI Cardiologist, AI Lawyer, AI Architect


**Lifestyle:**

- Deep work + occasional client/patient time
- Continuous learning (AI tools update quarterly)
- Higher productivity = higher earning (but burnout risk)
- Often urban-anchored (clients, hospitals, courts)

**Образ:** Олимпийский атлет своего domain. AI — coach + analytics + scoreboard.

---

### Archetype 2: Human-Centric Connector

**Pattern:**

- 20% AI / 80% relationships
- Sales, leadership, therapy, religion, hospitality
- Trust + presence = main value

**Examples:** Sales executive, CEO, therapist, pastor, concierge, executive coach


**Lifestyle:**

- Travel, meetings, network building
- Emotional intelligence as primary skill
- AI handles admin — human handles relationships
- Geographic flexibility (where the people are)

**Образ:** Дирижёр-человек. AI — оркестр инструментов, человек — chemistry в комнате.

---

### Archetype 3: Solo AI Empire

**Pattern:**

- 90% AI / 10% strategy
- Founder с 10 agents
- High autonomy, high risk

**Examples:** Solo SaaS founder, AI agency owner, content creator-entrepreneur, real estate investor with AI ops


**Lifestyle:**

- High autonomy, location-independent
- High variance income
- Loneliness risk (no team)
- Continuous experimentation

**Образ:** Капитан корабля где 10 матросов — AI. Решает курс и пожинает плоды. (Или тонет.)

---

### Дополнительно — 4 mini-archetypes:

- **Hands Worker + AI** (Archetype 4): trades + AR (электрик, сантехник). Защищён от disruption годами (physical).
- **Educator-Navigator** (Archetype 5): учит людей жить с AI. Demand growing.
- **Compliance Sentinel** (Archetype 6): regulation expert. Stable, защищённая роль.
- **Safety Researcher** (Archetype 7): premium top-tier. Узко, но высоко.

---

## <a id="top-30"></a>⭐ Top 30 Emerging Professions 2026-2030 (расширено с 10)

Порядок — оценка автора (спрос, перспективы, устойчивость на 5 лет), не измерение:

| # | Profession |
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

## <a id="salary-2030"></a>💰 Salary Benchmarks 2030 (Regional)

Прогноз зарплат по регионам убран: его нельзя проверить. Планируя карьеру, опирайся на актуальные данные по своей стране и на собственные разговоры с людьми из профессии.

---

## 🎬 Final Practical Advice — V2.0

После 200 профессий + прогноза:

### 5 mental models для navigation

1. **Не выбирай "будущую профессию" — выбирай долгосрочный skill set.** Section H показывает skills evolving year-by-year. Профессия = current applying. Skills = portable.

2. **Specialty > generality в 2030.** Generic "AI engineer" commoditizes. AI engineer + healthcare/legal/finance specialty = moat.

3. **Hybrid > pure.** Чистая профессия (doctor, lawyer, accountant) под давлением. Hybrid (doctor + AI, lawyer + AI) = productivity premium + защищённость.

4. **Trust scales slowly — relationships защищены.** AI не close \$10M deal. Не вылечит сложный mental case. Relationships остаются human.

5. **Geographic arbitrage существует, но ожидаемо сужается.** Оплата удалённой работы зависит от региона и заказчика; проверяй реальные ставки в своей стране.

### 90-day plan template (updated V2.0)

**Day 1-30: Map.**

- Read this document полностью
- Pick 5 profession candidates
- Identify domain + AI tool overlap
- Research salary в **твоём** регионе (по свежим вакансиям и обзорам)

**Day 31-60: Validate.**

- Connect с 5 people в каждой profession (LinkedIn)
- Build 1 portfolio project в top profession
- Learn 1 key skill (from Section H для twoего year horizon)

**Day 61-90: Commit.**

- Pick 1 profession + 1 fallback
- Plan 12-month learning path
- Schedule re-evaluation через 6 месяцев

---

## 📚 Sources V2.0 (дополнительно к v1.0)

- **WEF Future of Jobs Report** — https://www.weforum.org
- **McKinsey Global Institute — Future of Work** — https://www.mckinsey.com
- **Anthropic Economic Index** — https://www.anthropic.com/economic-index
- **OpenAI Economic Impacts** — https://openai.com/research
- **AI Now Institute** — https://ainowinstitute.org
- **Stanford AI Index** — https://aiindex.stanford.edu

Это стартовые точки для самостоятельной проверки. Цифры из них в справочник не переносились.

---

## 🔗 Cross-references V2.0

| Topic | Уроки курса |
|-------|-------------|
| AI Research / Science (A7), будущее профессий | [AI Roadmap 2027–2030](108-ai-roadmap-2027-2030.md) |
| Healthcare AI (A8, B6), AI Finance (A10) | [AI Ethics & Safety](61b-ai-ethics-safety.md), [AI Regulation & Compliance](61c-ai-regulation-compliance.md) |
| Future archetypes (Section J) | [Что такое AI](00-what-is-ai.md), [Кем стать: выбери свой путь](49b-choose-your-path.md) |

---

**Версия:** 2.0, актуализировано в октябре 2026

**200 профессий total** (100 NEW + 100 HYBRID)

**25 исчезающих** (расширено с 10)

**50 skills** (расширено с 25)

**Прогноз:** Year-by-year 2027-2030, сценарии без цифр

🔥 **V1.0 — карта леса сегодня. V2.0 — карта леса + прогноз погоды на 5 лет. Выбери своё место на новой карте.**
