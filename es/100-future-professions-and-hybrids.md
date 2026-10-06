# Profesiones del futuro: 100 profesiones nuevas e híbridas con IA

**Tiempo:** unas 2 horas para leerla completa (es una guía de consulta: lee las partes que necesites)

---

> **Una guía de consulta de este curso.**
> Si te has preguntado "¿la IA me va a quitar el trabajo?", esta es la respuesta larga: un mapa completo de las profesiones en la era de la IA. Qué es totalmente nuevo, qué está cambiando con la IA y qué está desapareciendo.
> Actualizado: octubre de 2026.

---

## 🔥 El panorama general: la IA como un incendio forestal

La IA no llegó al mundo del trabajo **como una mejora**. Llegó como un incendio forestal:

- **Algunos árboles (trabajos) se queman**: los rutinarios, los que siguen plantillas, los repetitivos
- **Brotan semillas nuevas**: trabajos que no existían hace tres años (Prompt Engineer, AI Agent Architect)
- **Los tocones viejos echan retoños nuevos (híbridos)**: médicos, abogados y diseñadores no desaparecen; se vuelven `profesión + IA = híbrido`

**Qué tener en cuenta:**

- El cambio ya está en marcha. Entender cómo funciona es la mejor forma de proteger tu propia carrera
- Los profesionales fuertes no "compiten con la IA". "Dirigen a la IA"
- El conjunto de habilidades más valioso en 2026 es **saber usar la IA + dominar tu campo**

---

## ⚠️ Aviso

Este es un mapa de consulta de profesiones y un pronóstico basado en escenarios, no datos de investigación.

- Se quitaron las estimaciones de salarios, los porcentajes de crecimiento y los tamaños de mercado: no se verificaron con fuentes primarias. Para cifras actuales de tu país y de tu puesto, revisa las estadísticas laborales oficiales de tu país (las publica el instituto nacional de estadística o el ministerio de trabajo), además de bolsas de trabajo y encuestas salariales
- Las estrellas de demanda (⭐) y los pronósticos para 2027–2030 son estimaciones y escenarios del autor, no mediciones, y pueden no cumplirse
- Sobre medicina, derecho y finanzas: la IA ayuda a un profesional, pero no reemplaza el trabajo que requiere licencia ni da asesoría personal
- Esto no es asesoría financiera ni de inversión, ni una promesa de ingresos

---

## 📑 Cómo está organizada esta guía

1. [Sección A: 50 profesiones NUEVAS (nacidas de la IA)](#section-a)
   - A1: Ingeniería de IA / Construcción (15)
   - A2: Contenido / Creatividad con IA (10)
   - A3: Negocios / Estrategia de IA (10)
   - A4: Operaciones de IA (8)
   - A5: IA especializada (7)
2. [Sección B: 50 profesiones HÍBRIDAS (un trabajo existente + IA)](#section-b)
   - B1: Trabajo del conocimiento (15)
   - B2: Trabajo creativo (10)
   - B3: Negocios / Ventas (10)
   - B4: Oficios + Servicios (10)
   - B5: Educación + Bienestar (5)
3. [Sección C: Lo que está desapareciendo (10 trabajos en riesgo)](#section-c)
4. [Sección D: Habilidades para el futuro (25 habilidades)](#section-d)
5. [Sección E: Árbol de decisión: qué profesión elegir](#section-e)
6. [Referencias salariales 2026](#salary-benchmarks)
7. [Las 10 profesiones emergentes principales 2026-2030](#top-10)
8. [Lista de verificación y próximos pasos](#next-steps)
9. [Fuentes](#sources)

---

## <a id="section-a"></a>🌱 Sección A: 50 profesiones NUEVAS

Profesiones **construidas alrededor de la propia IA**. Algunas aparecieron recién cuando despegó la IA generativa en 2022; otras ya existían, pero crecieron rápido desde entonces.

---

### A1. Ingeniería de IA / Construcción (15 profesiones)

Son **los constructores de la era de la IA**. La categoría de la que más se habla en 2026.

---

#### 1. Ingeniero de prompts (Prompt Engineer)

- **Qué hace:** Diseña y ajusta prompts para LLM (modelos de lenguaje grandes como Claude, GPT, Gemini y otros). Saca el máximo de un modelo al menor costo.
- **Habilidades clave:**
  - Entender cómo funcionan los LLM (tokens, contexto, atención)
  - Pruebas A/B de prompts
  - Optimización de costos (cuándo conviene Sonnet y cuándo Opus)
  - Chain-of-thought (razonamiento paso a paso), few-shot (con ejemplos), salidas estructuradas
  - Diseño de evals (cómo medir un "buen prompt")
  - Conocer las particularidades de cada modelo
- **Demanda:** ⭐⭐⭐⭐ (el nivel junior se está llenando; todavía faltan personas de nivel senior)
- **Cómo llegar:**
  1. Completa el tutorial interactivo gratuito de ingeniería de prompts de Anthropic (está en GitHub, en inglés)
  2. Arma 5 prompts de portafolio con impacto medido
  3. Contribuye a bibliotecas abiertas de prompts (PromptHub)
- **Imagínalo así:** un enólogo. Las mismas uvas se convierten en un gran vino o en un vino malísimo, según en qué manos caigan.

---

#### 2. Ingeniero de aplicaciones de IA (AI Application Engineer)

- **Qué hace:** Construye aplicaciones listas para producción sobre las API de los LLM. Backend + frontend + integración de IA.
- **Habilidades clave:**
  - Full-stack con Python/TypeScript
  - API de LLM (Anthropic SDK, OpenAI, etc.)
  - Bases de datos vectoriales (Pinecone, Weaviate, Qdrant)
  - Respuestas en streaming, patrones asíncronos
  - Manejo de errores, reintentos, alternativas de respaldo (fallbacks)
  - Monitoreo del costo por solicitud
- **Demanda:** ⭐⭐⭐⭐⭐ (la principal profesión nueva de 2026)
- **Cómo llegar:**
  1. Aprende a fondo un SDK de LLM (se recomienda el de Anthropic)
  2. Construye 3 proyectos en producción (publicados, no proyectos "de práctica")
  3. Una app de IA de código abierto en GitHub (1,000+ estrellas)
- **Imagínalo así:** un arquitecto que construye casas con un material nuevo. Los ladrillos (los LLM) son conocidos, pero el edificio que resulta es completamente nuevo.

---

#### 3. Ingeniero de operaciones de LLM (LLMOps Engineer)

- **Qué hace:** Publica, monitorea y escala aplicaciones de LLM en producción. DevOps, pero para IA.
- **Habilidades clave:**
  - Kubernetes, Docker
  - Observabilidad (Datadog, New Relic, soluciones propias)
  - Seguimiento de costos a nivel de token
  - Límites de solicitudes (rate limiting), colas
  - Conmutación por error entre regiones (multi-region failover)
  - Control de versiones del modelo + reversión (rollback)
- **Demanda:** ⭐⭐⭐⭐⭐ (crece a medida que más empresas usan IA en producción)
- **Cómo llegar:**
  1. Una base en DevOps (1-2 años de experiencia)
  2. Suma lo específico de los LLM (costo, latencia, evals)
  3. Una certificación de IA/ML de AWS/GCP
- **Imagínalo así:** el maquinista de un tren de carga. La locomotora (el modelo) ya existe; tu trabajo es llevar la carga a su destino sin descarrilar.

---

#### 4. Arquitecto de agentes de IA (AI Agent Architect)

- **Qué hace:** Diseña sistemas de varios agentes. Decide quién delega a quién, cómo se coordinan los agentes y cómo funciona la orquestación.
- **Habilidades clave:**
  - Patrones de diseño de agentes (orquestador, supervisor, enjambre)
  - LangGraph, Microsoft Agent Framework (el sucesor de AutoGen), Claude Agent SDK
  - Manejo del estado entre agentes
  - Propagación de errores
  - Presupuesto de costos a nivel de agente
  - Diseño de herramientas (cuándo darle al modelo una llamada a función y cuándo resolverlo dentro del prompt)
- **Demanda:** ⭐⭐⭐⭐⭐ (uno de los 3 roles emergentes principales)
- **Cómo llegar:**
  1. Una base como ingeniero senior
  2. Construye 2-3 sistemas de agentes en producción
  3. Da una charla en una conferencia de AI Engineer (World's Fair, Code Summit)
- **Imagínalo así:** un director de orquesta. Cada agente es un músico. El director no toca, pero sin él solo hay ruido.

---

#### 5. Ingeniero de pipelines RAG (RAG Pipeline Engineer)

- **Qué hace:** Construye sistemas de generación aumentada por recuperación (RAG), que permiten que un modelo responda a partir de los documentos propios de una empresa. Conecta datos privados → embeddings → base de datos vectorial → LLM.
- **Habilidades clave:**
  - Embeddings (OpenAI, Voyage, Cohere)
  - Bases de datos vectoriales
  - Estrategias de fragmentación (chunking)
  - Reordenamiento de resultados (re-ranking)
  - Búsqueda híbrida (semántica + por palabras clave)
  - Evaluar la calidad de un RAG
- **Demanda:** ⭐⭐⭐⭐ (la adopción en grandes empresas es muy alta)
- **Cómo llegar:**
  1. Aprende a fondo una base de datos vectorial
  2. Construye RAG para 3 campos distintos
  3. Publica una comparación de estrategias de fragmentación
- **Imagínalo así:** un bibliotecario que además es intérprete. Encuentra el libro correcto y lo traduce al idioma del cliente.

---

#### 6. Ingeniero de integración de IA (AI Integration Engineer)

- **Qué hace:** Lleva la IA a los sistemas empresariales que ya existen (Salesforce, SAP, ERP, CRM).
- **Habilidades clave:**
  - Patrones de integración empresarial
  - API REST/GraphQL
  - SSO, autenticación, cumplimiento normativo
  - Gestión del cambio
  - Evaluación de proveedores de IA
- **Demanda:** ⭐⭐⭐⭐ (la ola de adopción de IA en las empresas)
- **Cómo llegar:**
  1. Una base como ingeniero de backend
  2. Experiencia con software empresarial
  3. Una certificación de IA/LLM
- **Imagínalo así:** un plomero que mete tubería nueva (la IA) en una casa vieja (el software empresarial).

---

#### 7. Ingeniero de calidad de IA (AI Quality Engineer / Eval Engineer)

- **Qué hace:** Diseña evals (pruebas sistemáticas) para aplicaciones de LLM. Lanzar algo sin evals es como volar sin instrumentos.
- **Habilidades clave:**
  - Frameworks de evaluación (LangSmith, Braintrust)
  - Patrones de LLM como juez (LLM-as-judge)
  - Curaduría de conjuntos de datos de referencia (golden datasets)
  - Pruebas de regresión para prompts
  - Equilibrio entre costo y calidad
  - Significancia estadística en las pruebas de LLM
- **Demanda:** ⭐⭐⭐⭐⭐ (uno de los mayores huecos de la industria)
- **Cómo llegar:**
  1. Una base como ingeniero de QA
  2. Estudia a fondo el comportamiento de los LLM
  3. Publica una metodología de evaluación
- **Imagínalo así:** un catador de vinos. No hace el vino, pero sin él la bodega no sabe qué mejorar.

---

#### 8. Orquestador multiagente (Multi-Agent Orchestrator)

- **Qué hace:** Un AI Agent Architect especializado, enfocado en coordinar entre 5 y 50 agentes a la vez.
- **Habilidades clave:**
  - Sistemas distribuidos
  - Arquitectura basada en eventos
  - Protocolos de comunicación entre agentes
  - Detección de bloqueos mutuos (deadlocks)
  - Optimización de costos entre agentes
- **Demanda:** ⭐⭐⭐⭐ (un nicho muy demandado dentro de Agent Architect)
- **Cómo llegar:**
  1. Agent Architect → especialízate en orquestación
- **Imagínalo así:** un controlador de tráfico aéreo. 50 aviones en el aire, y ninguno puede chocar.

---

#### 9. Ingeniero de seguridad de IA (AI Security Engineer)

- **Qué hace:** Protege las aplicaciones de LLM contra la inyección de prompts, los jailbreaks y las fugas de datos.
- **Habilidades clave:**
  - Patrones de inyección de prompts
  - Filtrado de respuestas
  - Barreras de seguridad (guardrails) para el uso de herramientas
  - Detección de PII (información de identificación personal)
  - Pruebas adversarias
  - OWASP Top 10 para LLM
- **Demanda:** ⭐⭐⭐⭐⭐ (industrias reguladas: banca, salud)
- **Cómo llegar:**
  1. Una base como ingeniero de seguridad
  2. Aprende la superficie de ataque de los LLM
  3. Participa en competencias CTF de seguridad de IA
- **Imagínalo así:** un agente de escolta presidencial. Conoce cada ángulo desde el que podría llegar una amenaza.

---

#### 10. Ingeniero de optimización de costos de IA (AI Cost Optimization Engineer)

- **Qué hace:** Reduce la factura de LLM con enrutamiento de modelos, caché y compresión de prompts.
- **Habilidades clave:**
  - Escalonar modelos (elegir el modelo según la tarea: Haiku / Sonnet / Opus / Fable; revisa los precios en la página [Lo vigente](https://aimayak.com/now/))
  - Caché de prompts (con Anthropic, leer desde la caché cuesta una pequeña fracción del precio normal de entrada, mientras que escribir en la caché cuesta un extra; las tarifas actuales están en la página [Lo vigente](https://aimayak.com/now/))
  - Batch API: un descuento del 50% por procesamiento asíncrono
  - Caché semántica
  - Agrupar solicitudes en lotes
  - Análisis a nivel de token (los modelos más nuevos pueden contar el mismo texto como un número distinto de tokens, así que mide con tus propios datos)
  - Tableros de costos
- **Demanda:** ⭐⭐⭐⭐ (crece cuando la factura de LLM de una empresa se vuelve un gasto importante)
- **Cómo llegar:**
  1. Un ingeniero con mentalidad de negocio
  2. Publica un caso de estudio de cómo ahorraste \$X
- **Imagínalo así:** un auditor de energía para casas. La casa está iluminada y funciona, pero gasta el doble de electricidad de la que necesita.

---

#### 11. Ingeniero de bases de datos vectoriales (Vector Database Engineer)

- **Qué hace:** Especialista en bases de datos vectoriales. Particionamiento (sharding), rendimiento, búsqueda híbrida.
- **Habilidades clave:**
  - Pinecone, Weaviate, Qdrant, Milvus a fondo
  - Algoritmos HNSW, IVF
  - Elección del modelo de embeddings
  - Equilibrio entre costo y rendimiento
- **Demanda:** ⭐⭐⭐ (especializada, un mercado más pequeño)
- **Cómo llegar:**
  1. Una base como ingeniero de bases de datos
  2. Especialízate en una base de datos vectorial
- **Imagínalo así:** un archivista con memoria fotográfica. Sabe dónde está cada uno de un millón de documentos y saca cualquiera en un milisegundo.

---

#### 12. Arquitecto de pipelines de IA (AI Pipeline Architect)

- **Qué hace:** Diseña pipelines de ML/IA de principio a fin (datos → entrenamiento → publicación → monitoreo).
- **Habilidades clave:**
  - Plataformas de MLOps (MLflow, SageMaker, Gemini Enterprise Agent Platform de Google Cloud, antes Vertex AI)
  - Ingeniería de datos
  - Control de versiones de modelos
  - CI/CD para modelos
  - Feature stores (almacenes de variables)
- **Demanda:** ⭐⭐⭐⭐ (alta de forma constante)
- **Cómo llegar:**
  1. 2-3 años como ingeniero de ML
  2. Diseño de sistemas a nivel de arquitecto
- **Imagínalo así:** el ingeniero jefe de una fábrica. Todas las líneas de ensamblaje (flujos de datos) dependen de él.

---

#### 13. Especialista en ajuste fino (Fine-tuning Specialist)

- **Qué hace:** Entrena más a fondo los modelos base con datos privados. RLHF, DPO, LoRA.
- **Habilidades clave:**
  - PyTorch, Hugging Face
  - Infraestructura de entrenamiento (clústeres de GPU)
  - Curaduría de conjuntos de datos
  - Metodología de evaluación
  - Costos (entrenar modelos puede ser muy caro)
- **Demanda:** ⭐⭐⭐ (se reduce a medida que mejoran los modelos base, pero la especialidad sigue viva)
- **Cómo llegar:**
  1. Experiencia en investigación de ML
  2. Práctica real entrenando modelos
- **Imagínalo así:** el entrenador de una selección nacional. El talento en bruto (el modelo base) ya está ahí; tu trabajo es llevarlo a nivel olímpico.

---

#### 14. Ingeniero de modelos a la medida (Custom Model Engineer)

- **Qué hace:** Construye modelos especializados desde cero (cuando los modelos base no sirven).
- **Habilidades clave:**
  - Fundamentos de deep learning (aprendizaje profundo)
  - Arquitectura Transformer a fondo
  - Entrenamiento distribuido
  - Kernels de CUDA propios (nivel avanzado)
- **Demanda:** ⭐⭐ (un nicho estrecho con una barrera de entrada muy alta)
- **Cómo llegar:**
  1. Un doctorado o experiencia equivalente en investigación
  2. Artículos publicados
- **Imagínalo así:** un relojero suizo. Hace lo que la producción en masa no puede hacer.

---

#### 15. Ingeniero de infraestructura de IA (AI Infrastructure Engineer, especialista en vLLM/SGLang)

- **Qué hace:** Infraestructura de inferencia. Hace que los modelos corran más rápido y más barato en clústeres de GPU.
- **Habilidades clave:**
  - vLLM y SGLang a fondo
  - Fundamentos de CUDA
  - Optimización de memoria de GPU
  - Estrategias de procesamiento por lotes
  - Optimización de la caché KV
- **Demanda:** ⭐⭐⭐⭐ (muy alta en los laboratorios de vanguardia)
- **Cómo llegar:**
  1. Una base como ingeniero de sistemas
  2. Contribuye a un motor de inferencia de código abierto
- **Imagínalo así:** un preparador de autos de carreras. El mismo auto corre 20% más rápido.

---

### A2. Contenido / Creatividad con IA (10 profesiones)

---

#### 16. Productor de contenido con IA (AI Content Producer)

- **Qué hace:** Crea contenido (texto, video, audio) con la IA como herramienta principal. No como asistente de edición: como productor principal.
- **Habilidades clave:**
  - Claude/GPT para textos largos
  - Midjourney/gpt-image-2/Flux para imágenes
  - Suno para música
  - Runway/Kling para video
  - Coherencia con la voz de la marca
  - Adaptar contenido a varias plataformas
- **Demanda:** ⭐⭐⭐⭐ (es fácil entrar, pero el listón para nivel senior es alto)
- **Cómo llegar:**
  1. Aprende a fondo 3-4 herramientas de contenido con IA
  2. Arma un portafolio (canales con alcance real)
  3. Especialízate en un nicho (SaaS B2B, comercio electrónico, etc.)
- **Imagínalo así:** un chef que cocina con ingredientes del súper. La habilidad no está en cultivar las zanahorias; está en cómo las combinas.

---

#### 17. Compositor musical con IA (AI Music Composer, especialista en Suno)

- **Qué hace:** Genera música con herramientas de IA para uso comercial (jingles, música ambiental, bandas sonoras).
- **Habilidades clave:**
  - Suno (versiones actuales del modelo: mira [Lo vigente](https://aimayak.com/now/)) y generadores parecidos, con prompts dominados a fondo
  - Fundamentos de teoría musical (para guiar a la IA)
  - Edición de audio (Logic, Ableton para la posproducción)
  - Conocimiento de derechos de autor
- **Demanda:** ⭐⭐⭐ (en crecimiento, pero las reglas cambian seguido: Udio, por ejemplo, desactivó la descarga de pistas tras su acuerdo de 2025 con Universal Music)
- **Cómo llegar:**
  1. Aprende Suno y un generador de música más
  2. Un curso intensivo de teoría musical
  3. Antes de vender, lee la licencia de tu plan y las reglas del sitio donde vas a vender: bibliotecas de stock como Pond5 y AudioJungle no aceptan pistas generadas con IA
- **Imagínalo así:** un escultor. El barro (lo que genera la IA) es el material. La forma (tu gusto) es el arte.

---

#### 18. Productor de video con IA (AI Video Producer, Runway/Kling)

- **Qué hace:** Crea video con IA (Runway, Kling y otros modelos de video). Marketing, anuncios, cortometrajes.
- **Habilidades clave:**
  - Prompts para modelos de video (Runway, Kling y otros)
  - Storyboard (guion gráfico)
  - Posproducción (DaVinci Resolve)
  - Fundamentos de cinematografía
- **Demanda:** ⭐⭐⭐⭐ (crece rápido en 2026)
- **Cómo llegar:**
  1. Domina 2 herramientas de video con IA
  2. Arma 10 piezas de portafolio
  3. Encuentra un nicho (bienes raíces, moda, tecnología)
- **Imagínalo así:** un director de cortometrajes que trabaja solo. Lo que antes requería un equipo de 20 personas, ahora lo haces tú.

---

#### 19. Director de voz con IA (AI Voice Director, ElevenLabs)

- **Qué hace:** Produce contenido de voz con clonación de voz por IA (audiolibros, podcasts, voces de personajes, doblaje).
- **Habilidades clave:**
  - ElevenLabs a fondo
  - La ética y las leyes de la clonación de voz
  - Producción en varios idiomas
  - Edición de audio
- **Demanda:** ⭐⭐⭐⭐ (sobre todo para contenido multilingüe)
- **Cómo llegar:**
  1. Domina ElevenLabs Pro
  2. Arma una biblioteca de voces (con consentimiento)
  3. Proyectos de producción de audiolibros
- **Imagínalo así:** un director de doblaje. Elige las voces para cada personaje, solo que ahora las voces son virtuales.

---

#### 20. Diseñador de videojuegos con IA (AI Game Designer, mundos procedurales)

- **Qué hace:** Usa la IA para generar mundos de juego, diálogos de personajes no jugables (NPC) y diseño de niveles.
- **Habilidades clave:**
  - Unity/Unreal con integración de IA
  - LLM para diálogos dinámicos
  - Generación procedural
  - Fundamentos de diseño de videojuegos
- **Demanda:** ⭐⭐⭐ (un nicho especializado)
- **Cómo llegar:**
  1. Una base en desarrollo de videojuegos
  2. Proyectos de integración de IA
- **Imagínalo así:** el arquitecto de una ciudad infinita. Cada casa es distinta, pero el estilo se reconoce.

---

#### 21. Animador con IA (AI Animator)

- **Qué hace:** Crea animación con IA (Runway, Kaiber, herramientas específicas de animación).
- **Habilidades clave:**
  - Herramientas de animación con IA a fondo
  - Principios de la animación tradicional (ritmo, peso)
  - Integración con After Effects
- **Demanda:** ⭐⭐⭐ (especializada)
- **Imagínalo así:** un titiritero que no jala los hilos, sino que describe lo que deben hacer los títeres.

---

#### 22. Fotógrafo con IA / Director de imagen (AI Photographer / Image Director)

- **Qué hace:** Crea fotografía comercial con Midjourney/Flux/gpt-image-2. Fotos de producto, estilo de vida, moda.
- **Habilidades clave:**
  - Midjourney y Flux (versiones actuales) a fondo
  - Fundamentos de fotografía (composición, iluminación)
  - Coherencia de marca mediante referencias de estilo
  - Posprocesamiento (Lightroom)
- **Demanda:** ⭐⭐⭐⭐ (las tiendas en línea necesitan muchas fotos de producto)
- **Imagínalo así:** un fotógrafo sin cámara. El mismo ojo, otra herramienta.

---

#### 23. Creador de cómics / manga con IA (AI Comic / Manga Creator)

- **Qué hace:** Produce cómics/manga con IA. Es un nicho, sobre todo en la autopublicación.
- **Habilidades clave:**
  - Coherencia de personajes (entrenamiento de LoRA)
  - Composición de viñetas
  - Narración
- **Demanda:** ⭐⭐ (en crecimiento, pero es un nicho pequeño)
- **Imagínalo así:** un dibujante de cómics independiente que antes terminaba un tomo al año y ahora termina seis.

---

#### 24. Diseñador narrativo con IA (AI Narrative Designer)

- **Qué hace:** Diseña narrativas ramificadas para ficción interactiva, videojuegos y simulaciones de capacitación.
- **Habilidades clave:**
  - Scripting en Twine, Ink
  - Generación dinámica con LLM
  - Estructura narrativa
- **Demanda:** ⭐⭐⭐ (los mercados de videojuegos y de capacitación)
- **Imagínalo así:** el guionista de una serie con un millón de episodios, donde cada espectador ve el suyo.

---

#### 25. Arquitecto de la voz de marca con IA (AI Brand Voice Architect)

- **Qué hace:** Crea y mantiene una voz de marca coherente en todos los flujos de trabajo con IA. Guías de estilo, ajustes finos de marca, evals de voz.
- **Habilidades clave:**
  - Fundamentos de estrategia de marca
  - Personalización de LLM (prompts de sistema, ajuste fino)
  - Metodología de evaluación de la voz
- **Demanda:** ⭐⭐⭐⭐ (las empresas se están dando cuenta de que la IA arruina la voz de una marca si nadie la configura)
- **Imagínalo así:** el director de programación de una estación de radio. Cada locutor tiene su propia voz; el trabajo es mantener el tono general de la estación.

---

### A3. Negocios / Estrategia de IA (10 profesiones)

---

#### 26. Consultor de estrategia de IA (AI Strategy Consultant)

- **Qué hace:** Ayuda a las empresas a diseñar una hoja de ruta de IA. No la implementación: la estrategia, del tipo "dónde poner el dinero para IA".
- **Habilidades clave:**
  - Fundamentos de estrategia de negocios
  - El panorama de la IA (proveedores, capacidades, límites)
  - Modelado del retorno de inversión (ROI)
  - Gestión del cambio
  - Comunicación con directivos
- **Demanda:** ⭐⭐⭐⭐⭐ (muchas empresas buscan orientación)
- **Cómo llegar:**
  1. Experiencia en consultoría O en ingeniería de IA
  2. 5+ años de experiencia en negocios
  3. Arma 3 casos de estudio
- **Imagínalo así:** el capitán de un barco que sabe dónde están los icebergs. No maneja el motor; conoce el rumbo.

---

#### 27. Gerente de producto de IA (AI Product Manager, AI-PM)

- **Qué hace:** Un gerente de producto especializado en productos de IA. Entiende lo que los LLM pueden y no pueden hacer; lleva una hoja de ruta guiada por evals.
- **Habilidades clave:**
  - Habilidades clásicas de gerente de producto
  - Capacidades + límites de los LLM
  - Desarrollo de producto guiado por evals
  - Priorizar funciones teniendo en cuenta el costo
  - Investigación de usuarios para funciones de IA
- **Demanda:** ⭐⭐⭐⭐⭐ (uno de los 5 roles emergentes principales)
- **Cómo llegar:**
  1. Una base de 3+ años como gerente de producto
  2. Lanza una función de IA a producción
  3. Da charlas en conferencias de AI Engineering / Product
- **Imagínalo así:** dirigir una orquesta donde la mitad de los músicos son robots. Sabes qué puede y qué no puede hacer un robot con el violín.

---

#### 28. Líder de transformación con IA (AI Transformation Lead)

- **Qué hace:** Dirige la transformación con IA en una empresa grande. Cambio organizacional + tecnología + cultura.
- **Habilidades clave:**
  - Liderazgo directivo
  - Diseño organizacional
  - Gestión del cambio
  - Saber usar la IA
  - Responsabilidad sobre pérdidas y ganancias (P&L)
- **Demanda:** ⭐⭐⭐⭐ (las empresas grandes están creando estos puestos)
- **Imagínalo así:** un general que reforma el ejército en plena guerra.

---

#### 29. Especialista en adopción de IA (AI Adoption Specialist)

- **Qué hace:** Ayuda a empresas medianas (50-500 empleados) a poner en marcha flujos de trabajo con IA. Trabajo práctico, no una presentación de estrategia.
- **Habilidades clave:**
  - Dominio práctico de herramientas de IA (10+ herramientas)
  - Dar capacitaciones
  - Diseño de flujos de trabajo
  - Manejo de las partes interesadas
- **Demanda:** ⭐⭐⭐⭐⭐ (en las empresas medianas está la mayor parte de este trabajo)
- **Imagínalo así:** un instructor de manejo para gente que siempre ha ido de copiloto.

---

#### 30. Responsable de ética de IA (AI Ethics Officer)

- **Qué hace:** Se asegura de que la IA se use de forma responsable. Auditorías de sesgo, transparencia, equidad.
- **Habilidades clave:**
  - Marcos de ética de IA (NIST, EU AI Act)
  - Metodología para detectar sesgos
  - Relación con las partes interesadas
  - Conocimiento legal
- **Demanda:** ⭐⭐⭐ (industrias reguladas, empresas que operan en la UE)
- **Imagínalo así:** un árbitro. No juega el partido; hace cumplir las reglas.

---

#### 31. Responsable de cumplimiento normativo de IA (AI Compliance Officer)

- **Qué hace:** La Ley de IA de la UE (EU AI Act), las órdenes ejecutivas de EE. UU., la norma ISO 42001. La regulación de la IA.
- **Habilidades clave:**
  - El panorama de la regulación de la IA
  - Marcos de cumplimiento
  - Documentación rigurosa
  - Preparación para auditorías
- **Demanda:** ⭐⭐⭐⭐ (la EU AI Act entra en aplicación por etapas hasta 2028)
- **Imagínalo así:** un auditor de la autoridad fiscal, pero para la IA. Aburrido, pero necesario.

---

#### 32. Analista de ROI de IA (AI ROI Analyst)

- **Qué hace:** Calcula el retorno de inversión real de las iniciativas de IA. Costo vs aumento de productividad vs impacto en los ingresos.
- **Habilidades clave:**
  - Modelado financiero
  - Estructuras de costos de la IA
  - Métricas de productividad
  - Pruebas A/B
- **Demanda:** ⭐⭐⭐ (el área del director financiero)
- **Imagínalo así:** un contador con acceso especial. No solo cuenta los números, también la "magia".

---

#### 33. Especialista en compras de IA (AI Procurement Specialist)

- **Qué hace:** Compra herramientas y servicios de IA para empresas grandes. Evaluación de proveedores, negociación de contratos.
- **Habilidades clave:**
  - Fundamentos de compras
  - El panorama de proveedores de IA
  - Negociación de contratos
  - Costo total de propiedad
- **Demanda:** ⭐⭐⭐ (estable)
- **Imagínalo así:** un comprador compulsivo con mentalidad de director financiero. Compra mucho, pero con un propósito.

---

#### 34. Gerente de proveedores de IA (AI Vendor Manager)

- **Qué hace:** Gestiona la relación con los proveedores de IA (Anthropic, OpenAI, proveedores de bases de datos vectoriales).
- **Habilidades clave:**
  - Gestión de proveedores
  - Monitoreo de acuerdos de nivel de servicio (SLA)
  - Estrategia con varios proveedores
  - Optimización de costos
- **Demanda:** ⭐⭐⭐
- **Imagínalo así:** un diplomático que sabe con quién hablar y de qué.

---

#### 35. Responsable de riesgos de IA (AI Risk Officer)

- **Qué hace:** Identifica y reduce los riesgos de la IA (técnicos, de negocio, regulatorios, de reputación).
- **Habilidades clave:**
  - Marcos de gestión de riesgos
  - Categorías de riesgo propias de la IA (la alucinación, es decir, cuando la IA inventa cosas con total seguridad; el sesgo; la deriva)
  - Comunicación en crisis
- **Demanda:** ⭐⭐⭐⭐ (banca, salud, seguros)
- **Imagínalo así:** un meteorólogo para el negocio. Predice la tormenta antes de que el barco salga del puerto.

---

### A4. Operaciones de IA (8 profesiones)

---

#### 36. Entrenador de IA (AI Trainer, especialista en RLHF)

- **Qué hace:** Clasifica las respuestas de la IA y da retroalimentación para el entrenamiento RLHF (aprendizaje por refuerzo a partir de retroalimentación humana). Trabajo con una persona dentro del ciclo (human-in-the-loop).
- **Habilidades clave:**
  - Dominio de un campo (en un área específica)
  - Pensamiento crítico
  - Un método de calificación consistente
- **Demanda:** ⭐⭐⭐⭐ (los laboratorios de IA y sus contratistas contratan para este trabajo)
- **Imagínalo así:** un maestro calificando una serie interminable de exámenes.

---

#### 37. Auditor de IA (AI Auditor, verificación independiente)

- **Qué hace:** Audita de forma independiente los sistemas de IA en cumplimiento, equidad y rendimiento.
- **Habilidades clave:**
  - Metodología de auditoría
  - Evaluación de IA
  - Informes rigurosos
- **Demanda:** ⭐⭐⭐ (la EU AI Act está creando este mercado)
- **Imagínalo así:** un auditor financiero de las Big Four, solo que para la IA.

---

#### 38. Especialista de red team de IA (AI Red Team Specialist)

- **Qué hace:** Intenta romper los sistemas de IA. Pruebas adversarias, jailbreaks, casos límite.
- **Habilidades clave:**
  - Diseño creativo de ataques
  - Mentalidad de seguridad
  - Documentación
  - Métodos de red teaming publicados por los laboratorios de IA
- **Demanda:** ⭐⭐⭐⭐⭐ (los laboratorios de vanguardia tienen equipos de red team propios)
- **Imagínalo así:** un ladrón de bancos profesional al que le pagan por encontrar los huecos.

---

#### 39. Investigador del comportamiento de la IA (AI Behavior Researcher)

- **Qué hace:** Estudia cómo se comporta la IA en casos límite. Muy cerca de la investigación de alineación.
- **Habilidades clave:**
  - Metodología de investigación
  - Análisis estadístico
  - Entender el funcionamiento interno de los LLM
- **Demanda:** ⭐⭐⭐ (un nicho estrecho)
- **Imagínalo así:** un zoólogo que estudia una especie nueva. Solo que la especie es la IA, y la creamos sin entenderla del todo.

---

#### 40. Ingeniero de datos sintéticos (Synthetic Data Engineer)

- **Qué hace:** Genera datos sintéticos de entrenamiento. Es clave en campos donde los datos reales son escasos o privados.
- **Habilidades clave:**
  - Técnicas de generación de datos
  - Validación de calidad
  - Métodos que protegen la privacidad
- **Demanda:** ⭐⭐⭐⭐ (salud, finanzas, robótica)
- **Imagínalo así:** un mentiroso útil. Crea datos que parecen reales.

---

#### 41. Curador de conocimiento para IA (AI Knowledge Curator)

- **Qué hace:** Organiza y cuida las bases de conocimiento de los sistemas RAG. Un rol editorial para la era de la IA.
- **Habilidades clave:**
  - Arquitectura de la información
  - Criterio editorial
  - Optimización de búsqueda
  - Dominio de un campo
- **Demanda:** ⭐⭐⭐ (la adopción de RAG en grandes empresas)
- **Imagínalo así:** el editor en jefe de una biblioteca que ayuda a la IA a encontrar la verdad.

---

#### 42. Diseñador de flujos de trabajo con IA (AI Workflow Designer)

- **Qué hace:** Diseña flujos de trabajo entre personas e IA. Dónde trabaja la IA, dónde aprueba una persona, cómo se pasa la estafeta.
- **Habilidades clave:**
  - Diseño de procesos
  - Principios de UX
  - Saber lo que la IA puede hacer
- **Demanda:** ⭐⭐⭐⭐
- **Imagínalo así:** el coreógrafo de un baile entre una persona y un robot.

---

#### 43. Diseñador de interfaces persona-IA (Human-AI Interface Designer)

- **Qué hace:** UX/UI para interfaces potenciadas con IA. Respuestas en streaming, citas, indicadores de confianza.
- **Habilidades clave:**
  - Fundamentos de diseño UX
  - Patrones de interacción con IA
  - Diseño de información
- **Demanda:** ⭐⭐⭐⭐ (crece rápido)
- **Imagínalo así:** el arquitecto de un puente entre una persona y un robot.

---

### A5. IA especializada (7 profesiones)

---

#### 44. Desarrollador de agentes de voz con IA (AI Voice Agent Developer, Vapi/Bland.ai)

- **Qué hace:** Construye agentes de IA que hacen y reciben llamadas telefónicas para ventas, soporte y agendar citas.
- **Habilidades clave:**
  - Vapi, Bland.ai, Retell a fondo
  - Diseño de UX de voz
  - Integración con telefonía (Twilio)
  - Optimización de la latencia en tiempo real
- **Demanda:** ⭐⭐⭐⭐⭐ (uno de los 5 roles emergentes principales de 2026)
- **Imagínalo así:** un titiritero que hace que un robot suene como una persona al teléfono.

---

#### 45. Operador de Computer Use (Computer Use Operator)

- **Qué hace:** Construye flujos de trabajo con IA que manejan una computadora o un navegador (computer use de Anthropic, las funciones de agente de OpenAI en ChatGPT).
- **Habilidades clave:**
  - La API de Computer Use
  - Automatización del navegador
  - Identificar elementos de la interfaz
  - Recuperación ante errores
- **Demanda:** ⭐⭐⭐⭐ (una categoría nueva en 2025-2026)
- **Imagínalo así:** un marionetista que mueve las manos del agente sobre el teclado.

---

#### 46. Ingeniero de despliegue local de IA (Local AI Deployment Engineer)

- **Qué hace:** Instala y corre la IA de forma local (por privacidad, costo o latencia). Ollama, llama.cpp, en el propio dispositivo.
- **Habilidades clave:**
  - Modelos de pesos abiertos (Llama, Mistral, Qwen)
  - Cuantización
  - Motores de inferencia locales
  - Despliegue en el borde (edge)
- **Demanda:** ⭐⭐⭐ (sectores sensibles a la privacidad)
- **Imagínalo así:** alguien que construye una cabaña en el bosque sin conexión a la red: todo es suyo, nada está conectado a la red.

---

#### 47. Investigador de IA terapéutica (AI Therapy Researcher, ética de la IA de compañía)

- **Qué hace:** Investiga y diseña acompañantes de IA y herramientas terapéuticas éticas. Las consecuencias de Replika y Character.ai.
- **Habilidades clave:**
  - Formación en psicología
  - Ética
  - Diseño de interacción con IA
  - Seguridad de los usuarios
- **Demanda:** ⭐⭐⭐ (en crecimiento tras la preocupación pública)
- **Imagínalo así:** un nuevo tipo de psicólogo que no estudia pacientes, sino las relaciones entre las personas y la IA.

---

#### 48. Ingeniero de integración de robótica + IA (Robotics + AI Integration Engineer)

- **Qué hace:** Conecta los LLM con robots físicos. El ecosistema de Figure, 1X y Tesla Optimus.
- **Habilidades clave:**
  - Fundamentos de robótica
  - LLM para la planificación
  - Fusión de sensores
  - Control en tiempo real
- **Demanda:** ⭐⭐⭐⭐ (la ola de los robots humanoides)
- **Imagínalo así:** la persona que enseña a los robots a pensar antes de dar un paso.

---

#### 49. Desarrollador de apps para lentes inteligentes (Smart Glasses App Developer: Ray-Ban Meta, Apple Vision Pro)

- **Qué hace:** Apps para lentes y visores de realidad aumentada con asistentes de IA (Ray-Ban Meta, Apple Vision Pro).
- **Habilidades clave:**
  - SDK de realidad aumentada (Meta, Apple)
  - Integración de LLM
  - UX de voz
  - Patrones de IA siempre activa
- **Demanda:** ⭐⭐⭐ (un mercado temprano que podría despegar en 2027+)
- **Imagínalo así:** un desarrollador de apps para iPhone en 2008. La plataforma es joven, y todavía nadie sabe qué apps van a importar.

---

#### 50. Especialista en accesibilidad con IA (AI Accessibility Specialist)

- **Qué hace:** Usa la IA para que la tecnología sea accesible para personas con discapacidad. Descripciones de imágenes, control por voz, apoyos cognitivos.
- **Habilidades clave:**
  - WCAG y estándares de accesibilidad
  - Herramientas de IA para apoyo visual, auditivo y cognitivo
  - Investigación de usuarios con comunidades de personas con discapacidad
- **Demanda:** ⭐⭐⭐⭐ (presión regulatoria y ética)
- **Imagínalo así:** la persona que construye rampas para sillas de ruedas en el mundo digital. Hace visible lo invisible y hace que se escuche a quien no se escuchaba.

---

## <a id="section-b"></a>🌳 Sección B: 50 profesiones HÍBRIDAS

Un trabajo existente + IA = una nueva versión de ese trabajo. No "la IA reemplaza", sino "la IA potencia".

---

### B1. Trabajo del conocimiento (15 híbridos)

---

#### 51. Abogado + IA = Abogado potenciado con IA (AI-Augmented Lawyer)

- **Qué cambia:** La IA investiga, redacta borradores de contratos y resume jurisprudencia. Desaparece buena parte de la rutina.
- **Dónde sigue la persona:** Estrategia, relación con los clientes, audiencias en tribunales, decisiones de criterio, negociación. La asesoría legal y la licencia siguen en manos del abogado.
- **Herramientas de IA:** Harvey, CoCounsel, Lexis+ with Protégé (antes Lexis+ AI), flujos de trabajo propios con Claude

---

#### 52. Médico + IA = Médico asistido por IA (AI-Assisted Physician)

- **Qué cambia:** La IA ayuda con el diagnóstico (radiología, patología), redacta notas y sugiere opciones de tratamiento.
- **Dónde sigue la persona:** La relación con el paciente, las decisiones de criterio, los procedimientos, las decisiones éticas. El diagnóstico y la decisión sobre el tratamiento siguen en manos del médico con licencia.
- **Herramientas de IA:** Abridge, Microsoft Dragon Copilot (absorbió a Nuance DAX), herramientas de radiología con IA (Aidoc), herramientas propias de cada especialidad

---

#### 53. Contador + IA = Contador potenciado con IA (AI-Enabled Accountant)

- **Qué cambia:** La contabilidad diaria se automatiza. Las auditorías se semiautomatizan. Los pronósticos mejoran.
- **Dónde sigue la persona:** Estrategia, planeación fiscal, asesoría a clientes, criterio en casos complejos.
- **Herramientas de IA:** Vic.ai, MindBridge, flujos de trabajo propios con IA

---

#### 54. Maestro + IA = Docente potenciado con IA (AI-Augmented Educator)

- **Qué cambia:** Planes de clase personalizados, calificación automatizada, un tutor de IA para cada estudiante.
- **Dónde sigue la persona:** Motivación, aprendizaje socioemocional, mentoría, manejo del grupo.
- **Herramientas de IA:** Khanmigo, MagicSchool, flujos de trabajo propios con Claude

---

#### 55. Traductor + IA = Especialista en traducción con IA (AI Translation Specialist)

- **Qué cambia:** La IA se encarga por completo de la traducción básica. El traductor ahora posedita y se ocupa de los matices.
- **Dónde sigue la persona:** Matices culturales, textos de marketing, trabajo legal/médico crítico, traducción literaria.
- **Herramientas de IA:** DeepL, GPT/Claude, memorias de traducción propias

---

#### 56. Investigador + IA = Investigador potenciado con IA (AI-Powered Researcher)

- **Qué cambia:** Una revisión de literatura toma horas en lugar de meses. El análisis de datos es más rápido.
- **Dónde sigue la persona:** Diseño de hipótesis, ideas originales, criterio en la revisión por pares.
- **Herramientas de IA:** Elicit, Consensus, Perplexity Pro, Claude con búsqueda web

---

#### 57. Periodista + IA = Reportero potenciado con IA (AI-Augmented Reporter)

- **Qué cambia:** La investigación, la transcripción y los primeros borradores se hacen con ayuda de la IA.
- **Dónde sigue la persona:** Relación con las fuentes, periodismo de investigación, criterio editorial, reportería en el lugar de los hechos.
- **Herramientas de IA:** Otter.ai (transcripción), Claude/GPT (borradores), Perplexity (investigación)

---

#### 58. Terapeuta + IA = Profesional híbrido de salud mental (Hybrid Mental Health Practitioner)

- **Qué cambia:** La toma de notas se automatiza. Seguimiento con IA entre sesiones. Detección de patrones.
- **Dónde sigue la persona:** La alianza terapéutica (el centro del trabajo), la intervención en crisis, los casos complejos. La terapia en sí sigue en manos del profesional con licencia.
- **Herramientas de IA:** Eleos Health, Lyssn, flujos de trabajo propios con Claude

---

#### 59. Arquitecto + IA = Arquitecto de diseño generativo (Generative Design Architect)

- **Qué cambia:** El diseño generativo produce 100 opciones. Las revisiones de permisos y de cumplimiento de reglamentos se automatizan.
- **Dónde sigue la persona:** La visión del cliente, el contexto del terreno, el criterio estético, la supervisión de la obra.
- **Herramientas de IA:** Autodesk Forma (antes Spacemaker), modelos de difusión propios

---

#### 60. Ingeniero + IA = Ingeniero asistido por IA (AI-Assisted Engineer)

- **Qué cambia:** Programar se vuelve notablemente más rápido (Claude Code, Copilot, Cursor). La depuración es más rápida.
- **Dónde sigue la persona:** Arquitectura, diseño de sistemas, decisiones de criterio, mentoría.
- **Herramientas de IA:** Claude Code, Cursor, Copilot, herramientas específicas de cada campo

---

#### 61. Gerente de proyectos + IA = Gerente de proyectos híbrido (AI-PM Hybrid)

- **Qué cambia:** Los reportes de avance se generan solos. La detección de riesgos se hace con ayuda de la IA. La planeación de recursos se vuelve más inteligente.
- **Dónde sigue la persona:** Manejo de las partes interesadas, decisiones de criterio, motivación, escalamiento.
- **Herramientas de IA:** Asana AI, ClickUp AI, flujos de trabajo propios con Claude

---

#### 62. Reclutador + IA = Reclutador potenciado con IA (AI-Augmented Recruiter)

- **Qué cambia:** La búsqueda de candidatos se automatiza. La IA hace el primer filtro. El emparejamiento se vuelve más inteligente.
- **Dónde sigue la persona:** Construir relaciones, cerrar con los candidatos, evaluar el encaje cultural.
- **Herramientas de IA:** Eightfold, Paradox (ahora parte de Workday), flujos de trabajo propios

---

#### 63. Consultor + IA = Consultor nativo de IA (AI-Native Consultant)

- **Qué cambia:** La investigación, el análisis y la preparación de presentaciones se hacen con ayuda de la IA. El mismo entregable en un tercio del tiempo.
- **Dónde sigue la persona:** Relación con los clientes, presencia ante directivos, criterio, estrategia.
- **Herramientas de IA:** Claude/GPT para el análisis, Gamma para las presentaciones, herramientas propias

---

#### 64. Coach + IA = Coach potenciado con IA (AI-Powered Coach)

- **Qué cambia:** Seguimiento con IA entre sesiones. El seguimiento de metas se automatiza. Detección de patrones.
- **Dónde sigue la persona:** Rendición de cuentas, escucha profunda, momentos de avance decisivo.
- **Herramientas de IA:** Coachvox, flujos de trabajo propios con Claude

---

#### 65. Asesor financiero + IA = Asesor potenciado con IA (AI-Augmented Advisor)

- **Qué cambia:** El análisis de portafolios se automatiza. Sugerencias de rebalanceo. Aprovechamiento fiscal de pérdidas (tax-loss harvesting) impulsado por IA.
- **Dónde sigue la persona:** Confianza, acompañamiento en el comportamiento financiero, planeación compleja, la relación. La asesoría financiera personal sigue en manos del asesor con licencia.
- **Herramientas de IA:** Wealthbox AI, integración propia con un robo-advisor (asesor automatizado)

---

### B2. Trabajo creativo (10 híbridos)

---

#### 66. Diseñador + IA = Diseñador nativo de IA (AI-Native Designer)

- **Qué cambia:** Los bocetos (mockups), las variaciones y las opciones para pruebas A/B se generan con IA. El mismo rol con 5 a 10 veces más producción.
- **Dónde sigue la persona:** Estrategia de marca, gusto, investigación de usuarios, criterio.
- **Herramientas de IA:** Figma AI, Google Stitch, Midjourney, Claude para los textos

---

#### 67. Redactor publicitario + IA = Redactor potenciado con IA (AI-Augmented Writer)

- **Qué cambia:** La IA escribe los primeros borradores. La IA se encarga del contenido en volumen. La IA genera variantes de titulares.
- **Dónde sigue la persona:** Voz, estrategia, edición, ganchos, gusto.
- **Herramientas de IA:** Claude, GPT, Jasper

---

#### 68. Fotógrafo + IA = Fotógrafo híbrido (AI-Hybrid Photographer)

- **Qué cambia:** El posprocesamiento es 10 veces más rápido. La IA rellena multitudes en fotos de paisaje. Las fotos de producto salen de la generación con IA.
- **Dónde sigue la persona:** Visión, trabajo en locación, relación con los clientes, los momentos clave.
- **Herramientas de IA:** Lightroom AI, Topaz, Midjourney para composiciones

---

#### 69. Cineasta + IA = Director potenciado con IA (AI-Enabled Director)

- **Qué cambia:** Los efectos visuales (VFX) se abaratan. El material de apoyo (B-roll) se genera. La edición se hace con ayuda. La localización se automatiza.
- **Dónde sigue la persona:** Visión, casting, dirección de actores, historia.
- **Herramientas de IA:** Runway, Kling, herramientas de edición con IA

---

#### 70. Músico + IA = Músico que colabora con IA (AI-Collaborative Musician)

- **Qué cambia:** La IA ayuda a componer. Generación de pistas separadas (stems). La mezcla se automatiza.
- **Dónde sigue la persona:** Interpretación, emoción, originalidad, marca personal.
- **Herramientas de IA:** Suno, Udio, Mubert, mezcla con IA

---

#### 71. Actor + IA = Talento de voz con IA / Intérprete digital (AI-Voice Talent / Digital Performer)

- **Qué cambia:** Licenciar una voz clonada. Dobles digitales. Doblajes internacionales sin volver a grabar.
- **Dónde sigue la persona:** Actuación en vivo, trabajo frente a cámara, rango emocional real.
- **Herramientas de IA:** licencias de ElevenLabs, servicios de dobles digitales
- **Nota:** Desde 2023, los contratos colectivos de SAG-AFTRA (el sindicato de actores de EE. UU.) incluyen reglas sobre el uso de la IA

---

#### 72. Ilustrador + IA = Ilustrador híbrido (AI-Hybrid Illustrator)

- **Qué cambia:** Generación de fondos. Variaciones de color. Los primeros conceptos se hacen con ayuda de la IA.
- **Dónde sigue la persona:** Estilo, diseño de personajes, narración, acabado final.
- **Herramientas de IA:** Midjourney, Krea, LoRAs propios

---

#### 73. Animador + IA = Animador potenciado con IA (AI-Powered Animator)

- **Qué cambia:** Los cuadros intermedios (in-betweens) se automatizan. Sincronización labial con IA. La animación de fondos se genera.
- **Dónde sigue la persona:** Poses clave, actuación, ritmo de la historia.
- **Herramientas de IA:** Cascadeur, Toon Boom, Runway

---

#### 74. Editor de video + IA = Editor potenciado con IA (AI-Enhanced Editor)

- **Qué cambia:** El primer corte se automatiza. Subtítulos instantáneos. Reencuadre automático para video vertical.
- **Dónde sigue la persona:** Ritmo de la historia, ritmo emocional, acabado final.
- **Herramientas de IA:** Descript, Adobe AI, CapCut AI

---

#### 75. Diseñador de producción + IA = Diseñador de producción virtual (Virtual Production Designer)

- **Qué cambia:** Arte conceptual con IA. Explorar diseños de escenografía con IA. Búsqueda virtual de locaciones.
- **Dónde sigue la persona:** Construcciones físicas, decisiones en el set, la visión del cliente.
- **Herramientas de IA:** Midjourney, Unreal Engine + plugins de IA

---

### B3. Negocios / Ventas (10 híbridos)

---

#### 76. Vendedor + IA = Representante de desarrollo de ventas con IA (AI-Enabled SDR)

- **Qué cambia:** La prospección se automatiza. La IA redacta los correos. Los resúmenes de llamadas son instantáneos.
- **Dónde sigue la persona:** El cierre, los tratos complejos, las relaciones, el criterio.
- **Herramientas de IA:** Apollo AI, Clay, Outreach AI, Gong

---

#### 77. Mercadólogo + IA = Mercadólogo nativo de IA (AI-Native Marketer)

- **Qué cambia:** 5 veces más producción de contenido. Las pruebas A/B se automatizan. Personalización a gran escala.
- **Dónde sigue la persona:** Estrategia, marca, dirección creativa, elección de canales.
- **Herramientas de IA:** Adobe AI, Jasper, Claude/GPT, HubSpot AI

---

#### 78. Atención al cliente + IA = Especialista híbrido en soporte (Hybrid Support Specialist)

- **Qué cambia:** El nivel 1 lo atiende por completo la IA. El nivel 2 se atiende con ayuda de la IA. La detección del sentimiento del cliente se automatiza.
- **Dónde sigue la persona:** Problemas complejos, momentos que requieren empatía, escalamientos.
- **Herramientas de IA:** Intercom Fin, Zendesk AI, Ada
- **Nota:** El número de puestos baja, pero los roles senior se mantienen

---

#### 79. Gerente de RR. HH. + IA = Líder de RR. HH. potenciado con IA (AI-Augmented HR Lead)

- **Qué cambia:** El reclutamiento se automatiza. La IA personaliza la incorporación de nuevos empleados. Se detectan tendencias en el desempeño.
- **Dónde sigue la persona:** Resolución de conflictos, cultura, conversaciones delicadas.
- **Herramientas de IA:** Workday AI, BambooHR AI, herramientas propias

---

#### 80. Gerente de operaciones + IA = Gerente de operaciones potenciado con IA (AI-Powered Ops Manager)

- **Qué cambia:** La IA monitorea los procesos. Detección de anomalías. Sugerencias de optimización.
- **Dónde sigue la persona:** Coordinación entre áreas, criterio, gestión del cambio.
- **Herramientas de IA:** herramientas de minería de procesos + IA, herramientas propias

---

#### 81. Gerente de cuentas + IA = Gerente de éxito del cliente con IA (AI-Enabled CSM)

- **Qué cambia:** Detección del riesgo de que un cliente se vaya (churn). La preparación de renovaciones se automatiza. La investigación de cuentas es instantánea.
- **Dónde sigue la persona:** Relaciones, conversaciones estratégicas, escalamientos.
- **Herramientas de IA:** Gainsight AI, Catalyst, herramientas propias

---

#### 82. Analista de negocios + IA = Analista potenciado con IA (AI-Augmented Analyst)

- **Qué cambia:** Consultas SQL en lenguaje cotidiano. Generación de reportes. Detección de hallazgos.
- **Dónde sigue la persona:** Hacer las preguntas correctas, el contexto del negocio, el manejo de las partes interesadas.
- **Herramientas de IA:** Hex (con su agente de IA integrado), análisis de datos con Claude

---

#### 83. Mercadólogo de producto + IA = PMM nativo de IA (AI-Native PMM)

- **Qué cambia:** La inteligencia competitiva se automatiza. La IA escribe el contenido de lanzamiento. Investigación de perfiles de cliente (personas) más profunda.
- **Dónde sigue la persona:** Posicionamiento, mensajes, estrategia de salida al mercado.
- **Herramientas de IA:** Claude/GPT, Crayon, herramientas propias

---

#### 84. Gerente de marca + IA = Estratega de marca híbrido (AI-Hybrid Brand Strategist)

- **Qué cambia:** El monitoreo de la marca se automatiza. La producción de contenido escala. Análisis del sentimiento en tiempo real.
- **Dónde sigue la persona:** Visión de marca, decisiones creativas clave, alianzas.
- **Herramientas de IA:** Brandwatch + IA, herramientas propias

---

#### 85. Agente inmobiliario + IA = Agente inmobiliario potenciado con IA (AI-Augmented Realtor)

- **Qué cambia:** La IA escribe las descripciones de las propiedades. La calificación de prospectos se automatiza. Recorridos virtuales mejorados con IA.
- **Dónde sigue la persona:** Negociación, conocimiento de la zona, confianza, llegar al cierre.
- **Herramientas de IA:** Restb.ai, herramientas de IA para anuncios de propiedades, herramientas propias

---

### B4. Oficios + Servicios (10 híbridos)

---

#### 86. Chef + IA = Chef híbrido (AI-Hybrid Chef)

- **Qué cambia:** Diseño de menús con ayuda de la IA. Optimización nutricional. Pronósticos de inventario.
- **Dónde sigue la persona:** Cocinar, el sabor, la creatividad, dirigir la cocina.
- **Herramientas de IA:** flujos de trabajo propios con Claude, funciones de IA en software para restaurantes (pedidos, inventario, punto de venta)

---

#### 87. Entrenador personal + IA = Entrenador híbrido (AI-Coach Hybrid)

- **Qué cambia:** La IA arma programas personalizados. Análisis de la técnica a partir de video. El seguimiento del progreso se automatiza.
- **Dónde sigue la persona:** Motivación, acompañamiento presencial, dinámica de grupo.
- **Herramientas de IA:** Tonal, apps de entrenamiento como Future, herramientas propias

---

#### 88. Nutriólogo + IA = Nutricionista potenciado con IA (AI-Enabled Dietitian)

- **Qué cambia:** La IA planea las comidas. El seguimiento se automatiza. Detección de patrones.
- **Dónde sigue la persona:** Cambio de hábitos, casos complejos, rendición de cuentas.
- **Herramientas de IA:** Lumen, herramientas propias

---

#### 89. Mecánico + IA = Técnico de diagnóstico con IA (AI-Diagnostic Technician)

- **Qué cambia:** El diagnóstico es 2 veces más rápido (la IA lee los códigos y los síntomas). Mantenimiento predictivo.
- **Dónde sigue la persona:** La reparación física, la confianza del cliente, los casos complejos.
- **Herramientas de IA:** software de diagnóstico de Bosch, herramientas propias de los concesionarios

---

#### 90. Electricista + IA = Especialista en casas inteligentes (Smart Home Specialist)

- **Qué cambia:** Diseño de casas inteligentes con ayuda de la IA. Optimización del consumo de energía. Mantenimiento predictivo.
- **Dónde sigue la persona:** Instalación, solución de fallas, cumplir con las normas eléctricas.
- **Herramientas de IA:** plataformas de integración propias

---

#### 91. Plomero + IA = Especialista en plomería con IoT (IoT-Enabled Plumbing Specialist)

- **Qué cambia:** Detección de fugas con sensores IoT (internet de las cosas) + IA. Diagnóstico del sistema más inteligente. Cotizaciones generadas con IA.
- **Dónde sigue la persona:** El trabajo físico, las llamadas de emergencia.
- **Herramientas de IA:** Moen Flo, plataformas de plomería inteligente

---

#### 92. Sastre + IA = Diseñador de patrones con IA (AI-Pattern Designer)

- **Qué cambia:** Generación de patrones con IA. Predicción del ajuste de la prenda. Escaneos corporales en 3D automatizados.
- **Dónde sigue la persona:** La confección, las pruebas de ropa, el trabajo fino a mano.
- **Herramientas de IA:** Browzwear, Clo3D + plugins de IA

---

#### 93. Carpintero + IA = Diseñador de muebles paramétricos (Parametric Furniture Designer)

- **Qué cambia:** Explorar diseños con IA. Optimización de materiales. La planeación del corte CNC se automatiza.
- **Dónde sigue la persona:** El oficio, los acabados, las construcciones complejas.
- **Herramientas de IA:** Autodesk Fusion, Rhino + Grasshopper

---

#### 94. Florista + IA = Diseñador floral potenciado con IA (AI-Augmented Floral Designer)

- **Qué cambia:** Automatización de pedidos. Sugerencias de diseño. Pronósticos de inventario.
- **Dónde sigue la persona:** El arte de hacer arreglos, los eventos de los clientes, el gusto.
- **Herramientas de IA:** software para florerías, herramientas propias

---

#### 95. Estilista + IA = Asesor de estilo con IA (AI Style Consultant)

- **Qué cambia:** Vistas previas de estilos con IA. Igualación de colores. Se registran las preferencias de los clientes.
- **Dónde sigue la persona:** El oficio de cortar y teñir, la relación con los clientes.
- **Herramientas de IA:** Modiface, apps propias

---

### B5. Educación + Bienestar (5 híbridos)

---

#### 96. Profesor universitario + IA = Académico potenciado con IA (AI-Augmented Academic)

- **Qué cambia:** La IA se encarga de la revisión de literatura de investigación. Calificación con ayuda de la IA. Preparación de clases más rápida.
- **Dónde sigue la persona:** Mentoría, investigación original, criterio.
- **Herramientas de IA:** Elicit, Consensus, Claude

---

#### 97. Tutor particular + IA = Tutor potenciado con IA (AI-Enabled Tutor, al estilo de Khanmigo)

- **Qué cambia:** Práctica personalizada con IA. Explicaciones de conceptos con IA. Seguimiento del progreso.
- **Dónde sigue la persona:** Motivación, estrategia de preparación para exámenes, rendición de cuentas.
- **Herramientas de IA:** Khanmigo, GPTs propios

---

#### 98. Instructor de yoga + IA = Coach de bienestar potenciado con IA (AI-Powered Wellness Coach)

- **Qué cambia:** Análisis de la postura a través de una cámara. Secuencias personalizadas con IA.
- **Dónde sigue la persona:** Energía, presencia, ajustes con las manos.
- **Herramientas de IA:** tapetes de yoga inteligentes y apps que siguen la postura, herramientas propias

---

#### 99. Cuidado infantil + IA = Coach de crianza potenciado con IA (AI-Augmented Parent Coach)

- **Qué cambia:** La IA da seguimiento al desarrollo del niño. Sugerencias de actividades. Preguntas y respuestas a cualquier hora.
- **Dónde sigue la persona:** El cuidado físico, el apego, el criterio.
- **Herramientas de IA:** apps propias

---

#### 100. Cuidado de adultos mayores + IA = Cuidador asistido por IA (AI-Assisted Caregiver)

- **Qué cambia:** Monitoreo con IA. Recordatorios de medicamentos. Detección de caídas. Compañía con IA (un tema polémico).
- **Dónde sigue la persona:** El cuidado físico, la conexión emocional, el criterio.
- **Herramientas de IA:** Care.coach, dispositivos propios

---

## <a id="section-c"></a>🔥 Sección C: Lo que está desapareciendo (10 trabajos en riesgo en 2026-2030)

Una lista honesta. No para asustarte: para darte una dirección práctica.

---

### 1. Traducción básica de nivel inicial

- **Con qué la reemplaza la IA:** DeepL, GPT, Claude (la calidad en los pares de idiomas más comunes ya es alta)
- **Qué pueden hacer los profesionales:** Pasar al híbrido #55, Especialista en traducción con IA (poseditar + una especialidad)
- **Plazo:** según la estimación del autor, la mayor presión llega en 2026-2027

### 2. Redacción de primeros borradores (contenido genérico)

- **Con qué la reemplaza la IA:** Claude, GPT, Jasper (suficientemente buenos para contenido SEO masivo)
- **Qué hacer:** El híbrido #67, Redactor potenciado con IA (un rol de estrategia + edición)
- **Plazo:** según la estimación del autor, la mayor presión llega en 2026

### 3. Atención al cliente de nivel 1 (por chat)

- **Con qué la reemplaza la IA:** Intercom Fin, Zendesk AI, Ada (resuelven una parte importante de las solicitudes rutinarias)
- **Qué hacer:** Pasar al nivel 2/nivel 3 (casos delicados, escalamientos)
- **Plazo:** según la estimación del autor, la mayor presión llega en 2026-2027

### 4. Captura de datos

- **Con qué la reemplaza la IA:** OCR + extracción con IA (Hyperscience, flujos de trabajo propios)
- **Qué hacer:** Especialista en calidad de datos, diseño de flujos de trabajo con IA
- **Plazo:** según la estimación del autor, la mayor presión llega en 2026 (ya se está reduciendo rápido)

### 5. Contabilidad básica

- **Con qué la reemplaza la IA:** Vic.ai, Botkeeper, QuickBooks AI
- **Qué hacer:** El híbrido #53, Contador potenciado con IA (asesoría, estrategia)
- **Plazo:** según la estimación del autor, la mayor presión llega en 2027-2028

### 6. Investigación legal rutinaria (asistente jurídico de nivel inicial)

- **Con qué la reemplaza la IA:** Harvey, CoCounsel, Lexis+ with Protégé
- **Qué hacer:** Pasar al entrenamiento de IA, a la ingeniería de prompts para despachos de abogados o a una especialidad
- **Plazo:** según la estimación del autor, la mayor presión llega en 2027

### 7. Fotografía de stock (genérica)

- **Con qué la reemplaza la IA:** Midjourney, Flux, gpt-image-2 (imágenes baratas y suficientemente buenas)
- **Qué hacer:** El híbrido #68, Fotógrafo híbrido (una especialidad, eventos, contenido exclusivo)
- **Plazo:** según la estimación del autor, la mayor presión llega en 2026

### 8. Locución comercial genérica

- **Con qué la reemplaza la IA:** ElevenLabs, voces propias
- **Qué hacer:** La profesión #19, Director de voz con IA, o actuación especializada (voces premium)
- **Plazo:** según la estimación del autor, la mayor presión llega en 2026-2027

### 9. Diseño gráfico básico (plantillas)

- **Con qué lo reemplaza la IA:** Canva AI, Figma AI, Midjourney
- **Qué hacer:** El híbrido #66, Diseñador nativo de IA (un rol de estrategia + marca)
- **Plazo:** según la estimación del autor, la mayor presión llega en 2027

### 10. Código rutinario (boilerplate)

- **Con qué lo reemplaza la IA:** Cursor, Copilot, Claude Code
- **Qué hacer:** El híbrido #60, Ingeniero asistido por IA (arquitectura + criterio de nivel senior)
- **Plazo:** según la estimación del autor, la mayor presión llega en 2026 (el mercado para desarrolladores junior ya cambió)

---

## <a id="section-d"></a>💪 Sección D: 25 habilidades para el futuro

Habilidades universales que vas a necesitar en **cualquier** profesión en 2026-2030.

---

### Las 10 universales principales

1. **Saber usar la IA**: saber qué puede y qué no puede hacer la IA (es probabilística, alucina, puede tener sesgos)
2. **Ingeniería de prompts / diseño de instrucciones**: incluso en roles no técnicos se sabe escribir prompts
3. **Pensamiento crítico**: la IA puede equivocarse con total seguridad; sin pensamiento crítico, eso es un desastre
4. **Habilidades de verificación**: cómo revisar lo que produce la IA (verificar datos, citar fuentes)
5. **Pensamiento sistémico**: ver la IA como una parte de un flujo de trabajo, no como magia
6. **Comunicación**: con la IA, y con las personas **sobre** la IA
7. **Aprendizaje continuo**: la IA cambia cada mes; no puedes aprenderla una vez y ya
8. **Dominio de un campo**: más profundo y más específico = tu foso de protección frente a la IA
9. **Conocimiento de ética**: entender los sesgos de la IA y sus implicaciones para la privacidad
10. **Adaptabilidad**: las profesiones van a cambiar más seguido

### Técnicas (10)

11. **Fundamentos de Python**: incluso para quienes no son ingenieros; lo necesitas para las integraciones
12. **Git / control de versiones**: indispensable para cualquiera que trabaje con código o con configuraciones de IA
13. **Usar API**: REST/GraphQL, leer la documentación de una API
14. **Fundamentos de análisis de datos**: lo básico de pandas, consultas SQL
15. **Fundamentos de SQL**: los datos están en todas partes, y muchas veces tienes que sacarlos tú
16. **Soltura con la línea de comandos**: la terminal no da miedo
17. **Markdown / documentación**: la documentación es el producto principal de la era de la IA
18. **Fundamentos de la nube**: al menos una noción práctica de Cloudflare/Vercel/AWS
19. **Conciencia de seguridad**: secretos, autenticación, amenazas básicas
20. **Pensar en costos / presupuesto**: cada llamada a la IA cuesta dinero, y alguien tiene que hacer las cuentas

### Blandas (5)

21. **Ventas / negociación**: sigue siendo muy humano; la IA no cierra tratos
22. **Construir relaciones**: la confianza crece despacio, y la IA no puede acelerarla
23. **Empatía**: la IA la imita, pero no la siente
24. **Dirigir equipos potenciados con IA**: coordinar personas + agentes
25. **Contar historias**: antes los datos eran escasos; ahora el valor está en el contexto + la historia

---

## <a id="section-e"></a>🧭 Sección E: Árbol de decisión: qué profesión elegir

```
INICIO

¿Me encanta el trabajo técnico / con código?
├─ Sí → Ingeniería de IA / Aplicaciones de IA / LLMOps (A1)
│        → Subperfil:
│           - ¿Sistemas a fondo? → A1.15 Infraestructura
│           - ¿Construir apps? → A1.2 Aplicaciones de IA
│           - ¿Multiagente? → A1.4 Agent Architect
│           - ¿Optimización? → A1.10 Optimización de costos
└─ No → sigue

¿Soy una persona creativa?
├─ Sí → Contenido / Creatividad con IA (A2)
│        → Subperfil:
│           - ¿Texto? → A2.16 Productor de contenido
│           - ¿Visual? → A2.22 Fotógrafo con IA
│           - ¿Audio? → A2.19 Director de voz con IA
│           - ¿Video? → A2.18 Productor de video con IA
│           - ¿Música? → A2.17 Compositor musical con IA
└─ No → sigue

¿Trabajo con personas / en ventas / en gestión?
├─ Sí → Negocios / Estrategia de IA (A3)
│        → Subperfil:
│           - ¿Estrategia? → A3.26 Consultor de estrategia de IA
│           - ¿Producto? → A3.27 Gerente de producto de IA
│           - ¿Adopción? → A3.29 Especialista en adopción de IA
│           - ¿Ética? → A3.30 Responsable de ética de IA
└─ No → sigue

¿Trabajo en un campo específico (medicina/derecho/finanzas/educación)?
├─ Sí → La versión híbrida de mi profesión (B1)
│        → B1.51 Abogado + IA
│        → B1.52 Médico + IA
│        → B1.53 Contador + IA
│        → B1.54 Maestro + IA
│        → etc.
└─ No → sigue

¿Estudio / enseño?
├─ Sí → Híbridos de educación con IA (B5)
│        → B5.96 Profesor + IA
│        → B5.97 Tutor + IA
└─ No → sigue

¿Trabajo en un oficio / en servicios?
├─ Sí → La versión híbrida con IA de mi oficio (B4)
│        → B4.86 Chef + IA
│        → B4.89 Mecánico + IA
│        → B4.90 Electricista + IA (casa inteligente)
│        → etc.
└─ No → Especialista en adopción de IA (A3.29): ayudas a otras personas
         o Entrenador de IA (A4.36): tu conocimiento del campo → entrenamiento de IA
```

---

## <a id="salary-benchmarks"></a>💰 Referencias salariales 2026 (panorama general)

Se quitaron las tablas de salarios y los multiplicadores regionales: no se verificaron con fuentes primarias, y las cifras dependen mucho del país y la ciudad, la empresa, el nivel de la persona y qué tan bien negocie. Para cifras actuales de tu puesto y tu zona, revisa las estadísticas laborales oficiales de tu país, bolsas de trabajo y encuestas salariales, no esta guía.

---

## <a id="top-10"></a>⭐ Las 10 profesiones emergentes principales 2026-2030 (estimación del autor)

1. **Ingeniero de aplicaciones de IA (AI Application Engineer)**: la principal profesión nueva de esta era
2. **Arquitecto de agentes de IA (AI Agent Architect)**: los sistemas multiagente se están extendiendo
3. **Seguridad de IA / Red Team (AI Safety / Red Team)**: los laboratorios de vanguardia tienen equipos dedicados
4. **Ingeniero de prompts (Prompt Engineer)**: es fácil entrar, aunque el nivel junior se está llenando
5. **Desarrollador de agentes de voz con IA (AI Voice Agent Developer)**: hay demanda de agentes telefónicos hechos con plataformas como Vapi y Bland
6. **Abogado potenciado con IA (AI-Augmented Lawyer)**: herramientas como Harvey están cambiando el trabajo del día a día
7. **Especialista en adopción de IA (AI Adoption Specialist)** (grandes empresas): las grandes empresas necesitan ayuda para poner la IA en marcha
8. **Productor de contenido con IA (AI Content Producer)**: una economía de contenido nativa de IA
9. **Ingeniero de optimización de costos de IA (AI Cost Optimization Engineer)**: las empresas ya vieron sus facturas
10. **Responsable de ética / cumplimiento de IA (AI Ethics / Compliance Officer)**: la EU AI Act entra en aplicación por etapas

---

## <a id="next-steps"></a>🎯 Lista de verificación y próximos pasos

Después de leer esta guía:

- [ ] Elegí 3 profesiones candidatas (de las 100)
- [ ] Identifiqué las habilidades que me faltan para cada una (¿qué me falta?)
- [ ] Busqué cuánto se paga en **mi propia** zona (los promedios nacionales y las cifras de las grandes ciudades pueden confundirte)
- [ ] Elegí 1 y escribí un plan de aprendizaje de 90 días
- [ ] Me conecté con 3+ personas de esa profesión (LinkedIn, X, conferencias)
- [ ] Empecé un portafolio en esa profesión (3 entregables en 30 días)
- [ ] Voy a volver a evaluar en 90 días: ¿sigue siendo mi camino?

**Imagínalo así:** una profesión no es un tatuaje. En la era de la IA puedes cambiar cada 2-3 años sin perder impulso, siempre que tus habilidades sean universales (Sección D).

---

## 🎬 Consejos prácticos de este curso

1. **No estudies "IA"; estudia a fondo una herramienta concreta.** Domina una herramienta (Claude, por ejemplo) → la segunda te cuesta menos → y la siguiente también.
2. **Construye, no solo aprendas.** Un proyecto en producción vale más que 10 cursos.
3. **Especialidad + IA.** Un ingeniero de IA genérico se vuelve intercambiable. Un ingeniero de IA que además sabe de salud, derecho o finanzas tiene un foso de protección.
4. **Haz contactos en la comunidad de IA.** X (antes Twitter), Hacker News, las conferencias de AI Engineer.
5. **No persigas el salario más alto.** Elige una profesión con demanda duradera para 5-10 años (Sección A1, A3.26, A3.27, B1).

---

## <a id="sources"></a>📚 Fuentes

- **Hacker News Jobs**: https://news.ycombinator.com/jobs (ofertas de empleo en IA actualizadas)
- **Anthropic Careers** (empleos en Anthropic): https://www.anthropic.com/careers
- **OpenAI Careers** (empleos en OpenAI): https://openai.com/careers
- **WEF Future of Jobs Report** (informe del Foro Económico Mundial sobre el futuro del empleo): https://www.weforum.org/reports
- **McKinsey Future of Work** (el futuro del trabajo, de McKinsey): https://www.mckinsey.com/featured-insights/future-of-work
- **Pew Research sobre la IA en el trabajo**: https://www.pewresearch.org

Estas fuentes son puntos de partida para que verifiques las cosas por tu cuenta. Ninguna cifra de ellas se trasladó a esta guía.

---

## 🔗 Lecciones relacionadas del curso

| Tema | Lecciones del curso |
|-------|-------------|
| Fundamentos de IA | [La historia de la IA](00-what-is-ai.md), [Cómo funciona un LLM](00b-how-llm-works.md), [Comparación de modelos de IA](00c-ai-models-comparison.md), [IA sin miedo](00d-ai-without-fear.md) |
| Configuración + Claude Code | [Instalación y configuración](05-setup.md), [Claude Code de escritorio](05b-claude-code-desktop.md), [Planes y acceso](05c-access-levels-pricing.md) |
| Prompts | [Cómo escribir un buen prompt](06-prompting-fundamentals.md) |
| CLAUDE.md / Memoria | [CLAUDE.md](07-claude-md.md) |
| Crear apps | [Sitios web y aplicaciones web](15-websites-webapps.md), [API e integraciones](16-apis-integration.md), [Publicar en Cloudflare](18-deployment-cloudflare.md) |
| Sistemas multiagente | [Equipos de agentes](26-agent-teams.md), [Orquestación multiagente](82-multiagent-orchestration.md) |
| RAG | [RAG](14-rag.md) |
| Evals | [Evals](22-evals-system.md) |
| Seguridad | [Permisos y seguridad](28-permissions-security.md), [Defensa contra la inyección de prompts](107b-prompt-injection-defense.md) |
| Optimización de costos | [Caché de prompts y la Batch API](34-prompt-caching-batch-api.md), [Ingeniería de costos](48b-cost-engineering.md) |

Para ver qué lecciones importan para una profesión específica, revisa la página de Profesiones del sitio: ahí están los enlaces entre profesiones y lecciones. Las lecciones que no forman parte del curso principal están en la biblioteca y son opcionales.

---

**Versión:** actualizada en octubre de 2026

🔥 **El bosque está cambiando. Algunos árboles caen, brotan semillas y salen retoños nuevos de los tocones viejos. Elige tu lugar en el nuevo bosque.**

---

## 🆕 AMPLIACIÓN V2.0: 200 profesiones + un pronóstico hasta 2030

> **Agregado:** 2026-05-11. Versión 2.0.
> Duplicamos el número de profesiones a 200, y sumamos un pronóstico año por año para 2027-2030 y la economía híbrida.
>
> **Imagínalo así:** si la v1.0 es un mapa del bosque hoy, la v2.0 es un mapa del bosque dentro de cinco años, más el pronóstico del clima para cada año.

---

## 📑 Cómo está organizada la V2.0

- [Sección A6-A11: + 50 profesiones NUEVAS = 100 NUEVAS en total](#a-v2)
- [Sección B6-B10: + 50 profesiones HÍBRIDAS = 100 HÍBRIDAS en total](#b-v2)
- [Sección C ampliada: 25 trabajos que desaparecen (antes eran 10)](#c-extended)
- [Sección D ampliada: 50 habilidades (antes eran 25)](#d-extended)
- [Sección F: Pronóstico año por año 2027-2030](#section-f)
- [Sección G: Cambios geográficos](#section-g)
- [Sección H: Cómo evolucionan las habilidades año por año](#section-h)
- [Sección I: Lo que la IA NO hará antes de 2030](#section-i)
- [Sección J: La economía híbrida: 3 arquetipos para 2030](#section-j)
- [Las 30 profesiones emergentes principales 2026-2030 (ampliado desde 10)](#top-30)
- [Proyecciones salariales 2030 (por región)](#salary-2030)

---

## <a id="a-v2"></a>🌱 Sección A6-A11: 50 profesiones NUEVAS más

---

### A6. Hardware de IA / Robótica (10 profesiones)

Son **las manos de la era de la IA**. El software se encuentra con el hardware.

---

#### 51. Operador de robots humanoides (Humanoid Robot Operator)

- **Qué hace:** Opera y entrena robots humanoides (Figure, Tesla Optimus, Unitree). Los entrena con teleoperación + RLHF.
- **Habilidades clave:**
  - Equipos de teleoperación (controles de VR, captura de movimiento)
  - Conjuntos de datos para clonación de comportamiento (behavioral cloning)
  - Protocolos de seguridad cerca de personas
  - ML básico (una intuición de cómo funciona el RLHF)
  - Solución de fallas en mecatrónica
- **Demanda:** ⭐⭐⭐⭐ (varios fabricantes anunciaron planes de un despliegue más amplio; toma las fechas como planes, no como hechos)
- **Cómo llegar:**
  1. Un puesto inicial de operador o técnico en una empresa de robótica (Figure, Agility y otras)
  2. Arma un equipo de teleoperación en tu garaje + graba un conjunto de datos
  3. Una contribución de código abierto al framework LeRobot
- **Imagínalo así:** un titiritero del siglo XXI. La marioneta aprende sola; tu trabajo es mostrarle los primeros 1,000 movimientos.

---

#### 52. Diseñador de chips de IA (AI Chip Designer, ingeniería TPU/NPU)

- **Qué hace:** Diseña chips ASIC optimizados para inferencia o entrenamiento. Compite con NVIDIA gracias a la especialización.
- **Habilidades clave:**
  - Verilog / SystemVerilog
  - Jerarquía de memoria para arquitecturas transformer
  - Eficiencia energética (rendimiento por watt)
  - Entender las operaciones con matrices detrás de la atención (attention)
  - Herramientas EDA (Cadence, Synopsys)
- **Demanda:** ⭐⭐⭐⭐⭐ (muchas grandes tecnológicas y startups están creando sus propios chips de IA)
- **Cómo llegar:**
  1. Una carrera en ingeniería eléctrica o computación + una especialización en diseño de chips
  2. 3-5 años en diseño tradicional de chips (Intel, AMD, Apple)
  3. Un giro hacia trabajo específico de IA (Tenstorrent, Groq, Cerebras)
- **Imagínalo así:** el arquitecto de un rascacielos donde cada piso es una capa del modelo de IA. Si lo diseñas bien, obtienes 10 veces más de los mismos cimientos.

---

#### 53. Desarrollador de apps para lentes inteligentes (Smart Glasses Application Developer)

- **Qué hace:** Crea apps para Ray-Ban Meta, Apple Vision Pro y Snap Specs, además de capas de IA en tiempo real sobre lo que ves.
- **Habilidades clave:**
  - SDK de AR/VR (Meta SDK, ARKit, WebXR)
  - Visión por computadora (detección de objetos, OCR)
  - UX centrada en la voz (no hay teclado)
  - Presupuestos de latencia (<100ms es crítico)
  - Diseño para la privacidad (la cámara siempre está lista)
- **Demanda:** ⭐⭐⭐ (un mercado temprano: varios fabricantes ya venden lentes con IA, y las plataformas de apps son jóvenes)
- **Cómo llegar:**
  1. Una base en desarrollo móvil (iOS/Android)
  2. Un portafolio de AR (3 apps en producción)
  3. Integración de IA (Claude + visión)
- **Imagínalo así:** el arquitecto de una capa invisible de la realidad. Ve el mundo dos veces: con sus ojos y a través de los datos.

---

#### 54. Ingeniero de wearables con IA (AI Wearable Engineer)

- **Qué hace:** Crea dispositivos vestibles con IA (pines y colgantes de IA como Friend, el Rabbit R1, anillos inteligentes).
- **Habilidades clave:**
  - Sistemas embebidos (Rust, C++)
  - Gestión de energía (la duración de la batería es crítica)
  - ML en el dispositivo (TinyML, cuantización)
  - Procesamiento de audio siempre activo
  - Fusión de sensores (micrófono + acelerómetro + GPS)
- **Demanda:** ⭐⭐⭐ (la categoría todavía se está formando: Humane, que hizo uno de los primeros pines de IA, vendió su tecnología a HP en 2025)
- **Cómo llegar:**
  1. Una base en sistemas embebidos
  2. Una certificación en ML en el dispositivo
  3. Arma un prototipo en tu garaje (Raspberry Pi + Whisper corriendo localmente)
- **Imagínalo así:** un relojero del siglo XXI. Construye un mecanismo diminuto que te conoce mejor que tú mismo.

---

#### 55. Ingeniero de IA para vehículos autónomos (Autonomous Vehicle AI Engineer)

- **Qué hace:** Construye el sistema de conducción autónoma (Waymo, Tesla FSD, Wayve). Percepción → planeación → control, más LLM para los casos límite.
- **Habilidades clave:**
  - Visión por computadora a fondo
  - SLAM (localización y mapeo simultáneos)
  - Aprendizaje por refuerzo
  - Simulación (CARLA, el Waymo Open Dataset)
  - Ingeniería de casos de seguridad (safety case)
- **Demanda:** ⭐⭐⭐⭐ (concentrada en unas pocas empresas con mucho financiamiento, como Waymo, Tesla y Wayve)
- **Cómo llegar:**
  1. Una carrera en computación + una especialización en ML
  2. Un doctorado en robótica (opcional, pero ayuda para puestos de investigación)
  3. Una pasantía en una de las 5 principales empresas de vehículos autónomos
- **Imagínalo así:** un instructor de manejo para un taxista que nunca se cansa. Lo entrenas durante 100 millones de kilómetros (unos 62 millones de millas) en un simulador.

---

#### 56. Coordinador de enjambres de drones (Drone Swarm Coordinator)

- **Qué hace:** Programa la coordinación de decenas o cientos de drones a la vez, para inspección, agricultura, seguridad y espectáculos de luces.
- **Habilidades clave:**
  - ROS2, firmware PX4
  - Sistemas distribuidos (algoritmos de consenso)
  - Redes en malla (mesh)
  - Cumplimiento normativo (FAA, EASA)
  - Visión por computadora en tiempo real
- **Demanda:** ⭐⭐⭐ (nicho, pero creciendo en agricultura + inspección)
- **Cómo llegar:**
  1. Una base en robótica o sistemas embebidos
  2. Dominio de un solo dron (DJI SDK)
  3. Pasar a patrones de enjambre (ROS2 + multiagente)
- **Imagínalo así:** un coreógrafo para un enjambre de abejas. Cada abeja es tonta; el enjambre es brillante.

---

#### 57. Arquitecto de redes de sensores con IA (AI Sensor Network Architect)

- **Qué hace:** Diseña redes de sensores distribuidas (ciudad inteligente, fábrica, granja) con inferencia de IA en el borde (edge).
- **Habilidades clave:**
  - LoRaWAN, 5G, IoT satelital
  - Cómputo en el borde (NVIDIA Jetson, Coral)
  - Bases de datos de series de tiempo (InfluxDB, TimescaleDB)
  - ML para detección de anomalías
  - Protocolos industriales (Modbus, OPC-UA)
- **Demanda:** ⭐⭐⭐ (un nicho B2B, pero estable)
- **Cómo llegar:**
  1. Una base como ingeniero de IoT
  2. Experiencia en automatización industrial
  3. Una especialización en IA/edge
- **Imagínalo así:** un neurólogo para el planeta. Cada sensor es un nervio. Sin ellos, el mundo no siente nada.

---

#### 58. Ingeniero de BCI (interfaz cerebro-computadora, Brain-Computer Interface Engineer)

- **Qué hace:** Construye sistemas BCI (Neuralink, Synchron, Precision Neuroscience). Decodifica señales neuronales y las convierte en acciones.
- **Habilidades clave:**
  - Bases de neurociencia (spike sorting, LFP)
  - Procesamiento de señales (filtros de Kalman, decodificadores)
  - ML con datos neuronales
  - Biocompatibilidad y regulación médica (FDA)
  - C/C++ para decodificadores en tiempo real
- **Demanda:** ⭐⭐ (estrecha: un puñado de empresas en todo el mundo, aunque el campo está creciendo)
- **Cómo llegar:**
  1. Un doctorado en neurociencia o ingeniería eléctrica
  2. Un posdoctorado en un laboratorio de BCI
  3. Un salto a la industria (Neuralink, Synchron)
- **Imagínalo así:** un intérprete entre el cerebro y la máquina. Antes los intérpretes trabajaban entre el inglés y el español; ahora es entre neuronas y bytes.

---

#### 59. Ingeniero de manufactura aumentada con IA (AI-Augmented Manufacturing Engineer)

- **Qué hace:** Lleva a las fábricas visión con IA, mantenimiento predictivo y diseño generativo.
- **Habilidades clave:**
  - Sistemas de visión industrial (Cognex, Keyence)
  - Programación de PLC
  - ML para mantenimiento predictivo
  - Diseño generativo (Autodesk Fusion)
  - Nociones de Lean / Six Sigma
- **Demanda:** ⭐⭐⭐⭐ (Industria 4.0 + la ola de relocalización de la producción)
- **Cómo llegar:**
  1. Una base en ingeniería mecánica o de manufactura
  2. Una certificación en IA (NVIDIA DLI, Coursera ML)
  3. Implementaciones de IA industrial en tu portafolio
- **Imagínalo así:** un médico para la fábrica. Antes trataba síntomas; ahora trabaja con una resonancia magnética continua de cada máquina.

---

#### 60. Especialista en hardware de IA en el borde (Edge AI Hardware Specialist)

- **Qué hace:** Optimiza modelos de IA para dispositivos en el borde (Jetson, Coral, NPU de celulares, microcontroladores).
- **Habilidades clave:**
  - Cuantización (INT8, INT4)
  - Destilación de modelos
  - Conversión a ONNX, TensorRT, CoreML
  - NAS consciente del hardware
  - Perfilado de consumo de energía
- **Demanda:** ⭐⭐⭐⭐ (la ola de la IA en el dispositivo)
- **Cómo llegar:**
  1. Una base como ingeniero de ML
  2. Experiencia en sistemas embebidos
  3. Especialízate en una plataforma objetivo (móvil o industrial)
- **Imagínalo así:** un joyero. Toma un diamante tallado de 7B parámetros y lo reduce a 100MB para que quepa en un colgante.

---

### A7. Investigación / Ciencia de IA (10 profesiones)

Son **los exploradores**. Justo en la frontera.

---

#### 61. Investigador de alineación de IA (AI Alignment Researcher)

- **Qué hace:** Estudia cómo hacer que la IA sea segura y esté alineada con los valores humanos. No se trata de "prohibirle" sino de "enseñarle a querer lo correcto".
- **Habilidades clave:**
  - RLHF, DPO, Constitutional AI
  - Bases de verificación formal
  - Teoría de juegos, teoría de la decisión
  - Filosofía (utilitarismo, deontología)
  - Metodología de investigación
- **Demanda:** ⭐⭐⭐⭐⭐ (una de las áreas de investigación centrales de la década)
- **Cómo llegar:**
  1. Un doctorado en ML o el programa MATS
  2. Anthropic Fellows, o postúlate directamente
  3. Publica en el Alignment Forum, en NeurIPS, ICML
- **Imagínalo así:** un domador que trabaja con un depredador. El león es más fuerte que tú, así que no puedes simplemente darle órdenes. Pero sí puedes entrenarlo para que coma solo lo que debe.

---

#### 62. Investigador de interpretabilidad mecanicista (Mechanistic Interpretability Researcher)

- **Qué hace:** Estudia lo que hay **dentro** de los modelos de IA. Qué neuronas se encargan de qué, cómo se forman los circuitos.
- **Habilidades clave:**
  - Álgebra lineal a fondo
  - Clasificadores de sondeo (probing classifiers)
  - Parcheo de activaciones (activation patching)
  - Autoencoders dispersos (sparse autoencoders)
  - Herramientas de visualización
- **Demanda:** ⭐⭐⭐⭐ (un campo pequeño, con equipos en unos pocos laboratorios)
- **Cómo llegar:**
  1. Un doctorado en ML enfocado en interpretabilidad
  2. Replica los artículos de punta de Anthropic
  3. Postúlate a Anthropic / Apollo Research / Redwood
- **Imagínalo así:** un neurocientífico para un cerebro artificial. Antes los estudiantes de biología disecaban ranas; ahora miramos dentro de los LLM con un "microscopio" de activaciones.

---

#### 63. Investigador de escalamiento de IA (AI Scaling Researcher)

- **Qué hace:** Estudia las leyes de escalamiento (cómputo, datos, tamaño del modelo). Averigua dónde está la próxima frontera.
- **Habilidades clave:**
  - Entrenamiento distribuido (DeepSpeed, Megatron)
  - Las matemáticas de las leyes de escalamiento (Chinchilla, etc.)
  - Presupuestos de cómputo para entrenamientos muy grandes
  - Análisis de modos de falla
  - Inferencia estadística
- **Demanda:** ⭐⭐⭐ (un puñado de lugares en todo el mundo, pero de importancia crítica)
- **Cómo llegar:**
  1. Un doctorado en ML con experiencia en modelos grandes
  2. Experiencia en la industria con entrenamientos grandes
  3. Postúlate a un laboratorio de frontera
- **Imagínalo así:** un cartógrafo en un continente inexplorado. Cada paso cuesta millones, así que más te vale saber a dónde vas.

---

#### 64. Ingeniero de IA para biología sintética (Synthetic Biology AI Engineer)

- **Qué hace:** Aplica la IA a la biología: diseño de proteínas, descubrimiento de fármacos, optimización de CRISPR.
- **Habilidades clave:**
  - Bases de biología molecular
  - Patrones de AlphaFold / RoseTTAFold
  - Modelos de secuencia a estructura
  - Bases de laboratorio húmedo (o una alianza con uno)
  - Optimización de cómputo en GPU
- **Demanda:** ⭐⭐⭐⭐ (Isomorphic Labs + Cradle Bio + muchas startups)
- **Cómo llegar:**
  1. Un cruce entre computación/ML + biología (o biología + ML)
  2. Crea un modelo de predicción con datos públicos de proteínas
  3. Un salto a la industria (Insitro, Recursion)
- **Imagínalo así:** el arquitecto de máquinas vivas. Antes los biólogos descubrían lo que existe. Ahora diseñan lo que nunca existió.

---

#### 65. Especialista en IA para descubrimiento de fármacos (Drug Discovery AI Specialist)

- **Qué hace:** Usa la IA para el cribado de moléculas, el reposicionamiento de fármacos y la optimización de ensayos clínicos.
- **Habilidades clave:**
  - Quimioinformática (RDKit, DeepChem)
  - Dinámica molecular
  - Diseño de ensayos clínicos
  - La ruta regulatoria de la FDA
  - Optimización bayesiana
- **Demanda:** ⭐⭐⭐⭐ (grandes farmacéuticas y startups de descubrimiento de fármacos con IA)
- **Cómo llegar:**
  1. Un título en farmacia (PharmD) o un doctorado en química
  2. Una certificación en ML
  3. Un puesto de investigación en la industria
- **Imagínalo así:** un chef que simula un millón de recetas al día. Diez de ellas resultan ser medicinas.

---

#### 66. Investigador de IA para el clima (Climate AI Researcher)

- **Qué hace:** IA para modelado climático, pronóstico del tiempo, optimización de la captura de carbono y la red eléctrica.
- **Habilidades clave:**
  - Bases de ciencias atmosféricas
  - Solucionadores de EDP (redes neuronales de grafos para el clima)
  - Procesamiento de datos satelitales
  - Modelos climáticos (CESM, etc.)
  - Visualización
- **Demanda:** ⭐⭐⭐⭐ (Google GraphCast, Microsoft Aurora: grandes inversiones)
- **Cómo llegar:**
  1. Un doctorado en ciencias del clima o en ML + ciencias de la Tierra
  2. Una contribución de código abierto a WeatherBench
  3. Postúlate al equipo de clima de Google DeepMind, a NVIDIA Earth-2, a Microsoft
- **Imagínalo así:** un pronosticador del tiempo para todo el planeta. Los modelos de IA del clima ya generan pronósticos mucho más rápido, y su alcance útil sigue creciendo.

---

#### 67. Científico de materiales con IA (AI Material Scientist)

- **Qué hace:** IA para descubrir nuevos materiales: baterías, semiconductores, compuestos sustentables.
- **Habilidades clave:**
  - Bases de física del estado sólido
  - DFT (teoría del funcional de la densidad)
  - Redes neuronales de grafos para cristales
  - La base de datos Materials Project
  - Experimentación de alto rendimiento
- **Demanda:** ⭐⭐⭐ (estrecha, pero existe GNoME de Google DeepMind + startups de baterías)
- **Cómo llegar:**
  1. Un doctorado en ciencia de materiales o física
  2. Una especialización en ML
  3. Un salto a la industria (Citrine, Kebotix, Google DeepMind)
- **Imagínalo así:** un alquimista del siglo XXI. Los alquimistas buscaban oro; ahora la IA encuentra el "oro" para los autos eléctricos y los paneles solares.

---

#### 68. Investigador de IA cuántica (Quantum-AI Researcher)

- **Qué hace:** La intersección entre la computación cuántica y la IA. Algoritmos híbridos, aprendizaje automático cuántico.
- **Habilidades clave:**
  - Bases de computación cuántica (Qiskit, Cirq)
  - Algoritmos cuánticos variacionales
  - ML clásico a fondo
  - Álgebra lineal avanzada
  - Optimización consciente del hardware (IBM, IonQ)
- **Demanda:** ⭐⭐ (estrecha: pocas empresas y laboratorios nacionales; una apuesta a largo plazo)
- **Cómo llegar:**
  1. Un doctorado en física con enfoque cuántico
  2. Un cruce hacia ML
  3. Un salto a la industria o a un laboratorio nacional
- **Imagínalo así:** un científico parado entre dos eras. Todavía no le conviene a la industria, pero en 10 años podría volverse lo principal.

---

#### 69. Astrónomo con IA (AI Astronomer)

- **Qué hace:** IA para analizar datos astronómicos: detección de exoplanetas, ondas gravitacionales, clasificación de galaxias.
- **Habilidades clave:**
  - Bases de astronomía
  - ML para series de tiempo
  - Procesamiento de imágenes (datos de Hubble, JWST)
  - Detección de anomalías
  - Flujos de big data (a la escala de LSST)
- **Demanda:** ⭐⭐ (estrecha: academia + NASA + algunas startups)
- **Cómo llegar:**
  1. Un doctorado en astronomía
  2. Una especialización en ML
  3. Posdoctorado → científico investigador
- **Imagínalo así:** un telescopio tarda segundos en tomar una imagen. Un astrónomo antes tardaba años con los datos. Ahora la IA tarda minutos.

---

#### 70. Investigador de neuro-IA (Neuro-AI Researcher)

- **Qué hace:** La intersección entre la neurociencia y la IA. Usa el cerebro como inspiración para arquitecturas, y la IA para entender el cerebro.
- **Habilidades clave:**
  - Neurociencia a fondo
  - Neurociencia computacional
  - Diseño de arquitecturas neuronales
  - Datos de fMRI / electrofisiología
  - Metodología de investigación entre disciplinas
- **Demanda:** ⭐⭐⭐ (Apical Intelligence, antes Numenta; BrainGate; laboratorios académicos)
- **Cómo llegar:**
  1. Un doctorado en neurociencia
  2. Una especialidad computacional
  3. Un cruce hacia la industria
- **Imagínalo así:** un arqueólogo de la mente biológica. Cada descubrimiento sobre el cerebro es una posible arquitectura para la IA.

---

### A8. IA en salud (10 profesiones)

> La IA ayuda a un profesional, pero no reemplaza el trabajo médico con licencia y no da consejos médicos personales.

Son **los médicos de la era de la IA**. Donde lo que está en juego es más alto.

---

#### 71. Asistente de radiología con IA (AI Radiologist Assistant)

- **Qué hace:** Usa IA (Aidoc, Viz.ai, Harrison.ai) para priorizar radiografías, tomografías y resonancias magnéticas. Un humano en el circuito para las decisiones críticas.
- **Habilidades clave:**
  - Bases de radiología (o ser radiólogo certificado)
  - Manejo de herramientas de IA
  - Manejo de datos DICOM
  - Integración en el flujo de trabajo clínico
  - Protocolos de seguridad del paciente
- **Demanda:** ⭐⭐⭐⭐ (la lista de dispositivos médicos con IA autorizados por la FDA sigue creciendo)
- **Cómo llegar:**
  1. Un título de médico + una residencia en radiología
  2. Alfabetización en IA + capacitación en las herramientas que usa tu hospital (Aidoc, Viz.ai)
  3. Un puesto liderando la adopción en un hospital
- **Imagínalo así:** radiólogo + IA = piloto + piloto automático. La IA revisa cada imagen; el humano toma la decisión. Trabajo más rápido, y se escapan menos cosas.

---

#### 72. Especialista en NLP médico (Medical NLP Specialist)

- **Qué hace:** Construye sistemas de NLP (procesamiento de lenguaje natural) para expedientes clínicos electrónicos (EHR): extrae datos estructurados, apoya decisiones clínicas, optimiza la facturación.
- **Habilidades clave:**
  - NLP a fondo
  - Terminología médica (SNOMED, ICD-10)
  - Cumplimiento de HIPAA
  - API de EHR (Epic, Oracle Health, antes Cerner)
  - ML que preserva la privacidad
- **Demanda:** ⭐⭐⭐⭐ (los hospitales quieren aprovechar los datos de sus EHR)
- **Cómo llegar:**
  1. Una base como ingeniero de NLP
  2. Una certificación en el dominio de la salud
  3. Arma un portafolio de proyectos con EHR
- **Imagínalo así:** un arqueólogo de expedientes médicos. Excava datos estructurados de millones de notas sin estructura.

---

#### 73. Ingeniero de diagnóstico con IA (AI Diagnostic Engineer)

- **Qué hace:** Construye sistemas de IA para diagnóstico (cáncer de piel, retinopatía, corazón).
- **Habilidades clave:**
  - Visión por computadora
  - Imagenología médica
  - Validación clínica
  - La ruta 510(k) de la FDA
  - Modelos multimodales
- **Demanda:** ⭐⭐⭐⭐ (hospitales y fabricantes de equipo médico están adoptando la IA)
- **Cómo llegar:**
  1. Una base como ingeniero de ML + una especialidad médica
  2. Un trabajo en la industria (Tempus, PathAI, Paige)
  3. Experiencia con una solicitud ante la FDA
- **Imagínalo así:** los ojos de miles de patólogos en un solo algoritmo. Nunca se cansa.

---

#### 74. Especialista en reposicionamiento de fármacos con IA (AI Drug Repurposing Specialist)

- **Qué hace:** Usa la IA para encontrar nuevos usos para fármacos existentes (a menudo es más barato que desarrollar un fármaco nuevo).
- **Habilidades clave:**
  - Bases de farmacología
  - Grafos de conocimiento (fármaco-enfermedad-gen)
  - Inferencia causal
  - Diseño de ensayos clínicos
  - Rutas regulatorias
- **Demanda:** ⭐⭐⭐ (BenevolentAI, Healx)
- **Cómo llegar:**
  1. Un título en farmacia (PharmD) o una base en investigación farmacéutica
  2. Una especialización en ML
  3. Un puesto de investigación en la industria
- **Imagínalo así:** un cerrajero probando llaves. Una llave hecha para una puerta puede abrir otra, y la IA encuentra cuál.

---

#### 75. Investigador de IA para salud mental (AI Mental Health Researcher)

- **Qué hace:** Desarrolla IA para apoyo en salud mental (apps como Wysa) que sea ética, segura y basada en evidencia.
- **Habilidades clave:**
  - Bases de psicología clínica
  - NLP a fondo
  - Seguridad + reducción de daños
  - Diseño para el uso a largo plazo
  - Privacidad + consentimiento
- **Demanda:** ⭐⭐⭐⭐ (la crisis de salud mental + la accesibilidad de la IA)
- **Cómo llegar:**
  1. Un doctorado en psicología, o un cruce entre ML + psicología
  2. Un trabajo en la industria (Wysa, Spring Health)
  3. Estudios de validación clínica
- **Imagínalo así:** un consejero de apoyo en cada bolsillo. No reemplaza a un psiquiatra ni a un terapeuta con licencia, pero es una primera línea disponible 24/7.

---

#### 76. Especialista en patología con IA (AI Pathology Specialist)

- **Qué hace:** IA para patología digital: detección de cáncer, pronóstico y elección de tratamiento a partir de biopsias.
- **Habilidades clave:**
  - Bases de patología
  - Imágenes de laminilla completa (whole slide imaging)
  - Visión por computadora (imágenes de gigapíxeles)
  - Aprendizaje de múltiples instancias (multi-instance learning)
  - Validación clínica
- **Demanda:** ⭐⭐⭐⭐ (Paige, PathAI, Roche Digital Pathology)
- **Cómo llegar:**
  1. Un médico patólogo + IA, o ML + una certificación en patología
  2. Un trabajo en la industria
  3. Experiencia con herramientas aprobadas por la FDA
- **Imagínalo así:** un microscopio con los ojos de 10,000 patólogos. Puede detectar lo que a un ojo cansado se le escaparía.

---

#### 77. Ingeniero de genómica con IA (AI Genomics Engineer)

- **Qué hace:** IA para la identificación de variantes (variant calling), puntajes de riesgo poligénico y medicina personalizada.
- **Habilidades clave:**
  - Bioinformática (BWA, GATK)
  - Genética de poblaciones
  - Interpretación de variantes (guías ACMG)
  - Aprendizaje profundo con datos de secuencias
  - Cómputo que preserva la privacidad
- **Demanda:** ⭐⭐⭐ (Tempus, Verily, Color Health)
- **Cómo llegar:**
  1. Un doctorado en bioinformática, o ML + genética
  2. Experiencia con datos de poblaciones
  3. Un salto a la industria
- **Imagínalo así:** un intérprete del lenguaje del genoma al lenguaje de los diagnósticos. Antes tomaba años. Ahora toma segundos.

---

#### 78. Operador de robótica quirúrgica con IA (AI Surgical Robotics Operator)

- **Qué hace:** Opera robots quirúrgicos aumentados con IA (da Vinci de nueva generación, Vicarious Surgical) e interpreta las sugerencias de la IA.
- **Habilidades clave:**
  - Formación quirúrgica (residencia o especialidad)
  - Dominio de la interfaz robótica
  - Toma de decisiones en tiempo real
  - Evaluación de las sugerencias de la IA
  - Manejo de crisis
- **Demanda:** ⭐⭐⭐⭐ (la adopción de Intuitive Surgical + nuevos competidores)
- **Cómo llegar:**
  1. Un título de médico + una residencia quirúrgica (8-10 años)
  2. Una certificación en cirugía robótica
  3. Experiencia con herramientas de IA
- **Imagínalo así:** cirujano + robot + IA = un equipo de tres especialistas en un solo cuerpo. Una precisión que ninguna persona sola puede alcanzar.

---

#### 79. Optimizador de ensayos clínicos con IA (AI Clinical Trial Optimizer)

- **Qué hace:** Optimiza ensayos clínicos con IA: selección de pacientes, diseño de protocolos, evidencia del mundo real.
- **Habilidades clave:**
  - Bases de investigación clínica
  - Extracción de datos de EHR
  - Inferencia estadística
  - Conocimiento regulatorio
  - Economía de la salud
- **Demanda:** ⭐⭐⭐ (Saama, Medable)
- **Cómo llegar:**
  1. Una base en la industria farmacéutica o en investigación clínica
  2. Una certificación en ML / ciencia de datos
  3. Un trabajo en una farmacéutica o en una CRO
- **Imagínalo así:** el director de casting de un ensayo clínico. Elige a los candidatos ideales entre millones de pacientes en minutos.

---

#### 80. Analista de salud pública con IA (AI Public Health Analyst)

- **Qué hace:** IA para epidemiología, predicción de brotes, vigilancia de salud pública y distribución de vacunas.
- **Habilidades clave:**
  - Bases de epidemiología
  - Pronóstico de series de tiempo
  - Análisis geoespacial
  - Integración de datos públicos
  - Comunicación con públicos no técnicos
- **Demanda:** ⭐⭐⭐ (CDC, OMS, BlueDot)
- **Cómo llegar:**
  1. Una maestría en salud pública (MPH) o una carrera en epidemiología
  2. Habilidades de ciencia de datos
  3. Un trabajo en el gobierno o en una organización sin fines de lucro
- **Imagínalo así:** un vigía en la muralla de la ciudad. Vigila las primeras señales de un brote.

---

### A9. IA en educación / Edtech (5 profesiones)

---

#### 81. Diseñador curricular con IA (AI Curriculum Designer)

- **Qué hace:** Diseña planes de estudio con la IA integrada: el estudiante como cocreador junto con la IA, no "la IA hace la tarea".
- **Habilidades clave:**
  - Pedagogía / ciencias del aprendizaje
  - Manejo de herramientas de IA
  - Diseño de evaluaciones
  - Mapeo curricular
  - Gestión del cambio en las escuelas
- **Demanda:** ⭐⭐⭐⭐ (muchos distritos escolares todavía están definiendo cómo manejar la IA)
- **Cómo llegar:**
  1. Una base como docente
  2. Una certificación en EdTech / alfabetización en IA
  3. Un puesto a nivel de distrito escolar
- **Imagínalo así:** un arquitecto del aprendizaje. Antes era "memoriza el dato". Ahora es "aprende a bailar con la IA y date cuenta cuando se equivoca".

---

#### 82. Arquitecto de sistemas de tutoría con IA (AI Tutor System Architect)

- **Qué hace:** Construye sistemas de tutoría con IA (Khanmigo, las alianzas educativas de Anthropic) que sean personalizados, seguros y pedagógicamente sólidos.
- **Habilidades clave:**
  - Ingeniería de aplicaciones con LLM
  - Psicología educativa
  - Seguridad + diseño de contenido seguro para niños
  - Métricas de uso a largo plazo
  - Aprendizaje multimodal (texto, voz, visual)
- **Demanda:** ⭐⭐⭐⭐ (Khan Academy, Speak, Carnegie Learning)
- **Cómo llegar:**
  1. Una base como ingeniero de aplicaciones de IA (AI Application Engineer)
  2. Experiencia en educación
  3. Un trabajo en la industria EdTech
- **Imagínalo así:** el constructor de un maestro personal. Cada niño tiene su propio ritmo, su propio estilo, sus propios ejemplos.

---

#### 83. Diseñador de evaluaciones con IA (AI Assessment Designer)

- **Qué hace:** Diseña evaluaciones que **miden el pensamiento**, no "la memoria o la habilidad con la IA". Un diseño de evaluación que resiste las trampas con IA.
- **Habilidades clave:**
  - Psicometría
  - Teoría de respuesta al ítem
  - Saber qué pueden y qué no pueden hacer los detectores de texto generado con IA (para prevenir trampas)
  - Diseño de evaluación auténtica
  - Evaluación de la equidad
- **Demanda:** ⭐⭐⭐ (College Board, ETS, edtech, universidades)
- **Cómo llegar:**
  1. Una base en investigación educativa
  2. Una especialidad en psicometría
  3. Conocimiento sobre la IA y las trampas
- **Imagínalo así:** un diseñador de exámenes donde "copiar es imposible". No porque lo bloquees, sino porque no hay nada que copiar.

---

#### 84. Ingeniero de analítica del aprendizaje con IA (AI Learning Analytics Engineer)

- **Qué hace:** Construye flujos de datos y tableros para la analítica del aprendizaje a nivel de escuela o universidad.
- **Habilidades clave:**
  - Ingeniería de datos
  - API de LMS (Canvas, Moodle, Blackboard)
  - Analítica que preserva la privacidad (cumplimiento de FERPA)
  - Visualización
  - Modelado predictivo (estudiantes en riesgo)
- **Demanda:** ⭐⭐⭐ (universidades, proveedores de EdTech)
- **Cómo llegar:**
  1. Una base como ingeniero de datos
  2. Un trabajo en el sector educativo
  3. Una certificación en cumplimiento de privacidad
- **Imagínalo así:** un radar del progreso. Antes un maestro veía a un estudiante dos veces por semana; ahora puedes ver el camino de cada estudiante minuto a minuto.

---

#### 85. Especialista en accesibilidad educativa con IA (AI Accessibility in Education Specialist)

- **Qué hace:** Usa la IA para hacer la educación accesible para estudiantes con discapacidad, estudiantes que están aprendiendo inglés y estudiantes neurodivergentes.
- **Habilidades clave:**
  - Conocimiento sobre discapacidad
  - Estándares de accesibilidad (WCAG, ADA)
  - Herramientas de IA (voz a texto, texto a voz, resúmenes)
  - Adaptación curricular
  - Defensa de derechos + gestión del cambio
- **Demanda:** ⭐⭐⭐ (una necesidad enorme, pero con poco financiamiento)
- **Cómo llegar:**
  1. Experiencia en educación especial o accesibilidad
  2. Manejo de herramientas de IA
  3. Un trabajo en un distrito escolar o en una organización sin fines de lucro
- **Imagínalo así:** un puente entre el mundo y un estudiante que antes no podía llegar. La IA es una rampa para silla de ruedas hacia el aprendizaje.

---

### A10. IA en finanzas / Quant (5 profesiones)

> Las profesiones de abajo describen lo que hacen los profesionales. Esto no es asesoría de inversión ni una promesa de ingresos por trading.

---

#### 86. Investigador cuantitativo con IA (AI Quant Researcher)

- **Qué hace:** Usa la IA para generar alfa, investigar factores y diseñar estrategias de trading. Fondos de cobertura (hedge funds).
- **Habilidades clave:**
  - Estadística + ML a fondo
  - Predicción de series de tiempo
  - Microestructura del mercado
  - Frameworks de backtesting
  - Gestión de riesgos
- **Demanda:** ⭐⭐⭐⭐⭐ (fondos cuantitativos como Renaissance, Two Sigma, D. E. Shaw y Citadel)
- **Cómo llegar:**
  1. Un doctorado en matemáticas, física o computación
  2. Una pasantía en un fondo cuantitativo
  3. Una oferta de tiempo completo tras un buen desempeño
- **Imagínalo así:** un jugador de póker que juega un billón de manos al día. La IA ve patrones que una persona nunca vería.

---

#### 87. Ingeniero de detección de fraude con IA (AI Fraud Detection Engineer)

- **Qué hace:** Construye sistemas antifraude: fraude en pagos, robo de identidad, lavado de dinero.
- **Habilidades clave:**
  - Detección de anomalías
  - Redes neuronales de grafos (transacciones = un grafo)
  - Inferencia en tiempo real
  - Cumplimiento normativo (KYC, AML)
  - Robustez ante ataques adversarios
- **Demanda:** ⭐⭐⭐⭐ (bancos, procesadores de pagos y fintechs)
- **Cómo llegar:**
  1. Una base como ingeniero de ML
  2. Un trabajo en una fintech
  3. Certificaciones de cumplimiento (CFE)
- **Imagínalo así:** la seguridad de un banco en el siglo XXI. Antes eran los ojos de un guardia. Ahora un millón de ojos de IA detectan anomalías en milisegundos.

---

#### 88. Suscriptor de riesgos con IA (AI Underwriter, seguros/préstamos)

- **Qué hace:** Suscripción de riesgos aumentada con IA: seguros de vida, salud, auto y hogar, decisiones de préstamos.
- **Habilidades clave:**
  - Bases actuariales o experiencia en suscripción
  - Modelos de ML (XGBoost, redes neuronales)
  - Equidad + auditoría de sesgos
  - Cumplimiento normativo (a nivel estatal, ECOA)
  - Herramientas de explicabilidad
- **Demanda:** ⭐⭐⭐⭐ (insurtech + fintech de préstamos)
- **Cómo llegar:**
  1. Una base en suscripción o en actuaría
  2. Una certificación en ML
  3. Un trabajo en una insurtech (Lemonade, Root)
- **Imagínalo así:** una calculadora de riesgos que ve 1,000 factores a la vez. Una decisión en segundos, no en días.

---

#### 89. Ingeniero de cumplimiento con IA (AI Compliance Engineer, banca)

- **Qué hace:** Construye automatización de cumplimiento para bancos y fintechs: KYC, AML, monitoreo de transacciones, reportes.
- **Habilidades clave:**
  - Regulaciones bancarias (BSA, OFAC, FATCA)
  - NLP para textos regulatorios
  - Automatización de flujos de trabajo
  - Registros de auditoría
  - Cumplimiento en varias jurisdicciones
- **Demanda:** ⭐⭐⭐⭐ (el cumplimiento es un cuello de botella en muchos bancos)
- **Cómo llegar:**
  1. Experiencia en cumplimiento o en el área legal
  2. Una certificación en ingeniería
  3. Un trabajo en una empresa RegTech (Hummingbird, ComplyAdvantage)
- **Imagínalo así:** un abogado robot de cumplimiento para el banco. Nunca se le pasa una actualización regulatoria.

---

#### 90. Arquitecto de sistemas de trading con IA (AI Trading Systems Architect)

- **Qué hace:** Diseña la arquitectura de sistemas de trading de alta frecuencia y algorítmico con componentes de IA.
- **Habilidades clave:**
  - Sistemas de baja latencia (C++, Rust)
  - Ingeniería de redes (los microsegundos importan)
  - Sistemas de riesgo
  - Protocolos de bolsa (FIX, ITCH)
  - Inferencia de ML a gran escala
- **Demanda:** ⭐⭐⭐ (estrecha: firmas de HFT + trading propietario)
- **Cómo llegar:**
  1. Ingeniería de sistemas a fondo
  2. Contacto con el trabajo cuantitativo
  3. Un trabajo en la industria (Jane Street, Jump Trading, HRT)
- **Imagínalo así:** el arquitecto de una carrera a la velocidad de la luz. Un microsegundo = un millón de dólares.

---

### A11. Especialidades emergentes de IA (10 profesiones)

Son **especialistas de nicho donde se cruzan las industrias**.

---

#### 91. Especialista en IA para clima / ESG (AI Climate / ESG Specialist)

- **Qué hace:** IA para reportes ESG, contabilidad de carbono y evaluación de riesgos climáticos.
- **Habilidades clave:**
  - Estándares de contabilidad de carbono (GHG Protocol)
  - Análisis de datos satelitales
  - Modelos climáticos
  - Marcos regulatorios ESG (la CSRD de la UE y las reglas de tu país)
  - Integración de datos
- **Demanda:** ⭐⭐⭐⭐ (las reglas de reportes de sustentabilidad de la UE como la CSRD, incluso con los retrasos recientes, más la presión de los inversionistas)
- **Cómo llegar:**
  1. Experiencia en sustentabilidad o ciencias ambientales
  2. Una certificación en IA / ciencia de datos
  3. Un trabajo en la industria (Watershed, Persefoni)
- **Imagínalo así:** un contador a escala planetaria. No cuenta dólares sino toneladas de CO2.

---

#### 92. Ingeniero de IA para agricultura (AI Agriculture Engineer, agricultura de precisión)

- **Qué hace:** IA para el campo: predicción de rendimiento, detección de plagas, optimización del riego, tractores autónomos.
- **Habilidades clave:**
  - Bases de agronomía
  - Visión por computadora (imágenes de drones)
  - IoT / cómputo en el borde
  - Análisis geoespacial
  - Métricas de sustentabilidad
- **Demanda:** ⭐⭐⭐ (John Deere, Climate FieldView, Indigo Ag, FBN)
- **Cómo llegar:**
  1. Experiencia en AgTech o agronomía
  2. Una certificación en IA / datos
  3. Un trabajo en una empresa AgriTech
- **Imagínalo así:** un asesor agrícola con un dron como compañero. Ve el campo con ojos de águila. Cada planta está contada.

---

#### 93. Ingeniero de tecnología legal con IA (AI Legal Tech Engineer)

- **Qué hace:** Construye herramientas legales con IA: revisión de contratos, investigación de jurisprudencia, eDiscovery (Harvey, CoCounsel, Spellbook).
- **Habilidades clave:**
  - NLP a fondo
  - Conocimiento del dominio legal
  - Manejo de contextos largos
  - Precisión en las citas
  - Secreto profesional + confidencialidad
- **Demanda:** ⭐⭐⭐⭐⭐ (Harvey + muchas startups de tecnología legal)
- **Cómo llegar:**
  1. Una base como ingeniero de ML
  2. Una certificación en el dominio legal o una alianza
  3. Un trabajo en una empresa LegalTech
- **Imagínalo así:** un asistente legal que recuerda todas las leyes vigentes. Lee 1,000 páginas en segundos.

---

#### 94. Analista inmobiliario con IA (AI Real Estate Analyst)

- **Qué hace:** IA para la valuación de inmuebles, la predicción del mercado, la automatización de la administración de propiedades y la búsqueda de inquilinos adecuados.
- **Habilidades clave:**
  - Conocimiento del mercado inmobiliario
  - ML geoespacial
  - Visión por computadora (satélite + street view)
  - Predicción de series de tiempo
  - Conocimiento regulatorio (zonificación, vivienda justa)
- **Demanda:** ⭐⭐⭐ (Zillow, Compass, Opendoor, Redfin + administradores de propiedades)
- **Cómo llegar:**
  1. Experiencia en bienes raíces o finanzas
  2. Una certificación en ML
  3. Un trabajo en una empresa PropTech
- **Imagínalo así:** un valuador que ha visto las 100 millones de transacciones del mundo. El precio de una casa en segundos.

---

#### 95. Ingeniero de analítica deportiva con IA (AI Sports Analytics Engineer)

- **Qué hace:** IA para el deporte: rendimiento de jugadores, predicción de lesiones, estrategia de juego, conexión con los aficionados.
- **Habilidades clave:**
  - Conocimiento del deporte
  - Visión por computadora (seguimiento)
  - Bases de biomecánica
  - ML para series de tiempo
  - Visualización
- **Demanda:** ⭐⭐⭐ (la NBA, la NFL, clubes de futbol, equipos de F1)
- **Cómo llegar:**
  1. Una base en ciencia de datos
  2. Un curso de analítica deportiva, o un proyecto que puedas presentar en una conferencia como la MIT Sloan Sports Analytics Conference (SSAC)
  3. Un trabajo con un equipo o en medios deportivos
- **Imagínalo así:** un entrenador con microscopio. Ve lo que una persona no puede: micropatrones en el movimiento, el cansancio, una oportunidad.

---

#### 96. Cazador de amenazas de ciberseguridad con IA (AI Cybersecurity Hunter)

- **Qué hace:** Búsqueda de amenazas aumentada con IA: ML adversario, detección de anomalías, inteligencia de amenazas, respuesta a incidentes.
- **Habilidades clave:**
  - Una base en ciberseguridad
  - Técnicas de ML adversario
  - Plataformas SIEM / SOAR
  - Inteligencia de amenazas
  - Ingeniería inversa
- **Demanda:** ⭐⭐⭐⭐⭐ (ataques impulsados por IA → necesidad de defensa impulsada por IA)
- **Cómo llegar:**
  1. Una base en ciberseguridad (OSCP, etc.)
  2. Una especialidad en ML
  3. Un trabajo en la industria (CrowdStrike, Mandiant, Palo Alto Networks)
- **Imagínalo así:** un guía de safari que rastrea hackers. La IA te ayuda a ver las huellas en una selva de logs.

---

#### 97. IA para gobierno / tecnología cívica (AI Government / Civic Tech)

- **Qué hace:** IA para servicios de gobierno: trámite de beneficios, servicios para el público, análisis de políticas públicas. A menudo a través de equipos de servicios digitales del gobierno y grupos como Code for America.
- **Habilidades clave:**
  - Conocimiento del funcionamiento del gobierno
  - Nociones de compras públicas
  - Diseño en lenguaje claro
  - Cumplimiento (Section 508, FedRAMP)
  - Gestión de actores involucrados
- **Demanda:** ⭐⭐⭐ (en aumento a medida que se aplican órdenes ejecutivas sobre IA)
- **Cómo llegar:**
  1. Una base en una carrera tecnológica
  2. Un trabajo en el gobierno (equipos de servicios digitales federales, estatales o municipales)
  3. Proyectos de tecnología cívica (Code for America)
- **Imagínalo así:** un reformador de la burocracia. La IA deshace las filas y recorta el papeleo, como una oficina de trámites sin sala de espera.

---

#### 98. Ingeniero de redes eléctricas con IA (AI Energy Grid Engineer)

- **Qué hace:** IA para la red eléctrica inteligente: predicción de la demanda, integración de renovables, detección de apagones, optimización de la carga de autos eléctricos.
- **Habilidades clave:**
  - Ingeniería de sistemas eléctricos de potencia
  - Pronóstico de series de tiempo
  - Optimización (lineal/no lineal)
  - Cómputo en el borde
  - Conocimiento regulatorio (FERC, ISO)
- **Demanda:** ⭐⭐⭐⭐ (la transición energética + la ola de autos eléctricos)
- **Cómo llegar:**
  1. Una base en ingeniería eléctrica de potencia
  2. Una certificación en ML
  3. Un trabajo en una empresa de servicios eléctricos o de software para redes (el equipo de Tesla Powerwall, Uplight, GridX)
- **Imagínalo así:** el director de orquesta de la red eléctrica. Equilibra millones de dispositivos cada segundo.

---

#### 99. Optimizador logístico con IA (AI Logistics Optimizer)

- **Qué hace:** IA para optimizar la cadena de suministro: rutas, inventario, pronóstico de demanda, última milla.
- **Habilidades clave:**
  - Investigación de operaciones a fondo
  - Pronósticos con ML
  - Algoritmos geoespaciales / de rutas
  - Integración con SAP/Oracle
  - Sistemas en tiempo real
- **Demanda:** ⭐⭐⭐⭐ (Amazon, FedEx, DHL, project44)
- **Cómo llegar:**
  1. Una base en investigación de operaciones o ingeniería industrial
  2. Una especialidad en ML + cadena de suministro
  3. Un trabajo en la industria
- **Imagínalo así:** un jugador de ajedrez en un tablero de un millón de casillas. Cada jugada es un envío que cruza el mundo.

---

#### 100. Arquitecto de cadena de suministro con IA (AI Supply Chain Architect)

- **Qué hace:** Estrategia y arquitectura para una cadena de suministro con IA: resiliencia, sustentabilidad, transparencia.
- **Habilidades clave:**
  - Estrategia de cadena de suministro
  - Visibilidad en varios niveles de proveedores (datos en grafo)
  - Modelado de riesgos
  - Integración de ESG
  - Gestión de proveedores
- **Demanda:** ⭐⭐⭐⭐ (el enfoque en la resiliencia después del COVID + el desacoplamiento de China)
- **Cómo llegar:**
  1. Una carrera de 7-10 años en cadena de suministro
  2. Una especialidad en IA / transformación digital
  3. Un puesto sénior en consultoría o en la industria
- **Imagínalo así:** el arquitecto del sistema circulatorio del comercio mundial. IA = una resonancia magnética de cada cruce.

---

## <a id="b-v2"></a>🌳 Sección B6-B10: 50 profesiones HÍBRIDAS más

---

### B6. Profesiones híbridas en salud (10 profesiones)

> La IA ayuda al profesional clínico, pero no reemplaza el trabajo que requiere licencia y no da consejos médicos personales.

---

#### 101. Cirujano + IA = Cirujano aumentado con IA (AI-Augmented Surgeon)

- **Qué hace:** Un cirujano que trabaja con da Vinci + una capa de IA para guía en tiempo real, reconocimiento de la anatomía y predicción de complicaciones.
- **Habilidades clave:**
  - Residencia quirúrgica (8-10 años, la base)
  - Certificación en cirugía robótica
  - Manejo fluido de herramientas de IA
  - Toma de decisiones en tiempo real
  - Multitarea (vigilar a la vez a la IA y al paciente)
- **Demanda:** ⭐⭐⭐⭐ (hay demanda en los hospitales grandes)
- **Cómo llegar:**
  1. Título de médico + residencia quirúrgica + subespecialidad (fellowship)
  2. Una certificación en cirugía robótica
  3. Formación en trabajo aumentado con IA
- **Imagínalo así:** un piloto de avión con piloto automático y un súper radar. Vuela el avión junto con la IA.

---

#### 102. Radiólogo + IA = Especialista en diagnóstico con IA (Diagnostic AI Specialist)

- **Qué hace:** Un radiólogo + triaje con IA (Aidoc, Rad AI). Revisa más casos por turno, con la IA como un segundo par de ojos.
- **Habilidades clave:**
  - Una base en radiología (residencia)
  - Dominio de herramientas de IA
  - Métodos de control de calidad
  - Manejo de un flujo de trabajo de alto volumen
  - Comunicación con pacientes
- **Demanda:** ⭐⭐⭐⭐ (faltan radiólogos, y la IA ayuda con la carga de trabajo)
- **Cómo llegar:**
  1. Título de médico + residencia en radiología
  2. Capacitación en herramientas de IA (Aidoc, Harrison.ai)
  3. Un rol como referente de IA del hospital
- **Imagínalo así:** ojo de halcón + IA = un radiólogo. La IA revisa cada sombra; la persona toma la decisión.

---

#### 103. Farmacéutico + IA = Farmacéutico con IA (AI-Enabled Pharmacist)

- **Qué hace:** Un farmacéutico + herramientas de IA para revisar interacciones entre medicamentos, ajustar dosis personalizadas y gestionar la terapia con medicamentos.
- **Habilidades clave:**
  - Una base en farmacia (PharmD)
  - Herramientas de apoyo a la decisión clínica
  - Nociones de farmacogenómica
  - Educación del paciente
  - Manejo del expediente clínico electrónico (EHR)
- **Demanda:** ⭐⭐⭐⭐ (farmacias comerciales + puestos en hospitales)
- **Cómo llegar:**
  1. Un título en farmacia (PharmD)
  2. Una certificación en herramientas de IA
  3. Formación especializada en MTM (gestión de la terapia con medicamentos)
- **Imagínalo así:** un guardián que vigila las interacciones de un millón de medicamentos. Antes todo estaba en la cabeza del farmacéutico. Ahora la IA ayuda.

---

#### 104. Enfermera + IA = Profesional de enfermería aumentada con IA (AI-Augmented Practitioner)

- **Qué hace:** Una enfermera + IA para triaje, sistemas de alerta temprana, monitoreo de pacientes y documentación.
- **Habilidades clave:**
  - Una base en enfermería (RN/BSN/NP)
  - Soltura con herramientas de IA
  - Pensamiento crítico cuando la IA da falsos positivos
  - Defensa del paciente
  - Integrar la IA al flujo de trabajo
- **Demanda:** ⭐⭐⭐⭐⭐ (faltan enfermeras + la IA aumenta la productividad)
- **Cómo llegar:**
  1. Un título en enfermería
  2. Formación en herramientas clínicas de IA
  3. Una certificación de especialidad (NP, CNS)
- **Imagínalo así:** una enfermera con un tercer ojo. La IA puede señalar a un paciente que empeora horas antes de una crisis.

---

#### 105. Dentista + IA = Dentista con diagnóstico por IA (AI Diagnostic Dentist)

- **Qué hace:** Un dentista + visión por IA en radiografías (Pearl, Videa) para detectar caries y planear tratamientos.
- **Habilidades clave:**
  - Una base en odontología (DDS/DMD)
  - Dominio de herramientas de IA para radiografías
  - Planeación de tratamientos
  - Comunicación con pacientes (explicar lo que encontró la IA)
  - Manejo de seguros
- **Demanda:** ⭐⭐⭐⭐ (Pearl + Videa + nuevos participantes)
- **Cómo llegar:**
  1. Un título en odontología (DDS/DMD)
  2. Una certificación en herramientas de IA
  3. Gestión de consultorio
- **Imagínalo así:** un dentista y un radiólogo en una sola persona. La IA puede señalar lo que al ojo se le podría escapar.

---

#### 106. Veterinario + IA = Veterinario asistido por IA (AI Vet Assistant)

- **Qué hace:** Un veterinario + visión por IA (cáncer en estudios de imagen), triaje por telemedicina, dosis según la raza.
- **Habilidades clave:**
  - Una base en veterinaria (DVM)
  - Dominio de herramientas de imagen con IA
  - Conocimiento de varias especies
  - Flujo de trabajo de telemedicina
  - Comunicación con los dueños
- **Demanda:** ⭐⭐⭐ (faltan veterinarios + la IA agiliza el trabajo)
- **Cómo llegar:**
  1. Un título en veterinaria (DVM)
  2. Una certificación en herramientas de IA
  3. Una práctica especializada
- **Imagínalo así:** un médico de cabecera para pacientes que no pueden hablar. La IA te ayuda a escucharlos.

---

#### 107. Fisioterapeuta + IA = Coach de movimiento con IA (AI Movement Coach)

- **Qué hace:** Un fisioterapeuta + análisis de movimiento con IA (Sword Health, Hinge Health) para rehabilitación personalizada y prevención de lesiones.
- **Habilidades clave:**
  - Una base en fisioterapia (DPT)
  - Dominio de herramientas de análisis de movimiento
  - Flujos de trabajo de telerrehabilitación
  - Compromiso del paciente
  - Medición de resultados
- **Demanda:** ⭐⭐⭐⭐ (plataformas como Sword Health y Hinge Health)
- **Cómo llegar:**
  1. Un título en fisioterapia (DPT)
  2. Formación en una plataforma de fisioterapia a distancia
  3. Una certificación de especialidad
- **Imagínalo así:** un entrenador y un análisis de nivel olímpico para un paciente común. La IA ve cómo te mueves.

---

#### 108. Psiquiatra + IA = Especialista en salud mental aumentado con IA (AI-Augmented Mental Health Specialist)

- **Qué hace:** Un psiquiatra + IA para dar seguimiento a síntomas, predecir la respuesta a medicamentos y dar apoyo entre consultas.
- **Habilidades clave:**
  - Una base de médico + psiquiatría
  - Dominio de la IA + seguridad
  - Integración de terapias digitales
  - Privacidad + ética
  - Manejo de la relación entre paciente e IA
- **Demanda:** ⭐⭐⭐⭐ (la crisis de salud mental + el crecimiento de la telepsiquiatría)
- **Cómo llegar:**
  1. Título de médico + residencia en psiquiatría
  2. Una certificación en salud digital
  3. Montar una práctica híbrida
- **Imagínalo así:** un psiquiatra con un diario de IA para cada paciente. Ve patrones a lo largo de meses, no solo durante la consulta.

---

#### 109. Optometrista + IA = Especialista en visión con IA (AI Vision Specialist)

- **Qué hace:** Un optometrista + escaneos de retina con IA (Eyenuk, LumineticsCore, antes IDx-DR) para detectar retinopatía diabética, glaucoma y degeneración macular (AMD).
- **Habilidades clave:**
  - Una base en optometría (OD)
  - Dominio de herramientas de detección con IA
  - Educación del paciente
  - Rutas de referencia a especialistas
  - Integración con telesalud
- **Demanda:** ⭐⭐⭐ (en EE. UU. ya se usan herramientas de detección con IA autorizadas por la FDA)
- **Cómo llegar:**
  1. Un título en optometría (OD)
  2. Una certificación en herramientas de IA
  3. Integrarlo en una práctica
- **Imagínalo así:** oculista + IA = un detector de enfermedades de los ojos en un minuto. Problemas que antes pasaban inadvertidos durante años.

---

#### 110. Cardiólogo + IA = Especialista en cardiología con IA (AI Cardiology Specialist)

- **Qué hace:** Un cardiólogo + IA en electrocardiograma, ecocardiograma y resonancia cardiaca (Ultromics y herramientas parecidas). Ayuda a detectar problemas del corazón antes.
- **Habilidades clave:**
  - Una base de médico + cardiología
  - Dominio de herramientas de imagen con IA
  - Integración de datos de dispositivos vestibles (Apple Watch, KardiaMobile)
  - Herramientas de IA para pacientes
  - Control de calidad
- **Demanda:** ⭐⭐⭐⭐⭐ (las enfermedades cardiovasculares son la principal causa de muerte en el mundo, y las herramientas de IA para ellas están relativamente maduras)
- **Cómo llegar:**
  1. Título de médico + subespecialidad en cardiología
  2. Una certificación en imagen con IA
  3. Un rol en investigación o como referente de IA de la clínica
- **Imagínalo así:** cardiólogo + IA = un sistema de alerta temprana para el corazón. Prevención en lugar de reanimación.

---

### B7. Gobierno / sector público (10 profesiones)

---

#### 111. Policía + IA = Policía aumentado con IA (AI-Augmented Officer)

- **Qué hace:** Un policía + IA en cámaras corporales + analítica predictiva + redacción de informes con IA (Axon Draft One).
- **Habilidades clave:**
  - Una base de academia de policía
  - Dominio de herramientas de IA
  - Conciencia de los sesgos
  - Conocimiento de las libertades civiles
  - Trabajo con la comunidad
- **Demanda:** ⭐⭐⭐ (Axon es el proveedor más conocido; el debate sobre estas herramientas sigue)
- **Cómo llegar:**
  1. La academia de policía
  2. Una certificación en cámaras corporales con IA
  3. Formación en policía de proximidad
- **Imagínalo así:** un policía con un compañero de IA. La IA redacta los informes; el policía trabaja con la gente.

---

#### 112. Juez + IA = Judicatura asistida por IA (AI-Assisted Judiciary)

- **Qué hace:** Un juez + IA para investigación jurídica, búsqueda de precedentes y recomendaciones de sentencia (controvertido).
- **Habilidades clave:**
  - Título en derecho + experiencia judicial
  - Dominio de herramientas de IA
  - Conciencia de los sesgos de la IA
  - Derecho constitucional
  - Ética
- **Demanda:** ⭐⭐⭐ (adopción lenta por preocupaciones éticas)
- **Cómo llegar:**
  1. Título en derecho + habilitación para ejercer
  2. Formación en IA jurídica
  3. Nombramiento o elección como juez
- **Imagínalo así:** un juez y un bibliotecario de todas las leyes en una sola persona. La IA sugiere; la persona decide.

---

#### 113. Urbanista + IA = Planificador de ciudades inteligentes (Smart City Planner)

- **Qué hace:** Un urbanista + simulación con IA para tráfico, uso de suelo, servicios públicos y adaptación al clima.
- **Habilidades clave:**
  - Una base en urbanismo
  - SIG (GIS) + aprendizaje automático (ML)
  - Trabajo con las partes interesadas
  - Herramientas de simulación
  - Análisis de equidad
- **Demanda:** ⭐⭐⭐⭐ (la ola de inversión en ciudades inteligentes)
- **Cómo llegar:**
  1. Una maestría en administración pública o un título en urbanismo
  2. Una certificación en SIG + ciencia de datos
  3. Un empleo en un municipio o gobierno local
- **Imagínalo así:** el arquitecto de una ciudad que funciona como una máquina. Cada decisión se prueba 1,000 veces en una simulación.

---

#### 114. Trabajador social + IA = Gestor de casos con IA (AI-Enabled Caseworker)

- **Qué hace:** Un trabajador social + IA para priorizar casos, revisar si alguien califica para apoyos y evaluar riesgos.
- **Habilidades clave:**
  - Una base en trabajo social (MSW)
  - Dominio de herramientas de IA
  - Conciencia de sesgos + ética
  - Atención informada sobre el trauma
  - Orientación sobre recursos disponibles
- **Demanda:** ⭐⭐⭐⭐ (reducir la carga de casos es la misión)
- **Cómo llegar:**
  1. Un título en trabajo social (MSW)
  2. Formación en herramientas de IA
  3. Un empleo en una dependencia pública
- **Imagínalo así:** un trabajador social con un asistente de IA que se encarga de la documentación. Más tiempo con las personas, menos con el papeleo.

---

#### 115. Auditor fiscal + IA = Auditor aumentado con IA (AI-Augmented Auditor)

- **Qué hace:** Un auditor + IA para detectar anomalías, reconocer patrones de fraude y elegir qué declaraciones auditar.
- **Habilidades clave:**
  - Una base en contabilidad/auditoría
  - Dominio de herramientas de IA
  - Análisis de datos
  - Comunicación
  - Conocimiento de la regulación
- **Demanda:** ⭐⭐⭐⭐ (las Big Four + la modernización de la autoridad fiscal, por ejemplo el IRS en EE. UU.)
- **Cómo llegar:**
  1. Una base de contador público (CPA)
  2. Una especialización en analítica de datos
  3. Un empleo en una firma Big Four o en una dependencia pública
- **Imagínalo así:** un auditor con un millón de ojos de IA sobre cada transacción. Las anomalías aparecen en segundos.

---

#### 116. Agente de aduanas + IA = Especialista fronterizo con IA (AI Border Specialist)

- **Qué hace:** Un agente fronterizo + escaneo con IA (carga, rostros, comportamiento). Implica tensiones con las libertades civiles.
- **Habilidades clave:**
  - Formación en aduanas/fronteras
  - Dominio de herramientas de escaneo con IA
  - Conocimiento del comercio internacional
  - Conciencia de los sesgos
  - Idiomas + conocimiento cultural
- **Demanda:** ⭐⭐⭐ (modernización de las agencias fronterizas de EE. UU., ICE y CBP)
- **Cómo llegar:**
  1. Formación como agente federal del orden
  2. Una certificación en herramientas de IA
  3. Una asignación especializada
- **Imagínalo así:** un agente de aduanas con rayos X que ven a kilómetros a la redonda. Controvertido, pero real.

---

#### 117. Oficial militar + IA = Oficial de estrategia con IA (AI Strategy Officer)

- **Qué hace:** Un oficial militar + IA para análisis de inteligencia, planeación de misiones y conocimiento del campo de batalla.
- **Habilidades clave:**
  - Formación militar (academia + experiencia)
  - Dominio de herramientas de IA
  - Derecho internacional (derecho de los conflictos armados, LOAC)
  - Pensamiento estratégico
  - Ciberseguridad
- **Demanda:** ⭐⭐⭐⭐ (Palantir, Anduril, la defensa tradicional)
- **Cómo llegar:**
  1. Una academia militar o un nombramiento como oficial
  2. Una certificación en IA para defensa
  3. Una asignación conjunta o especializada
- **Imagínalo así:** comandante + IA = un general que ve todo el campo a la vez. Decisiones en segundos, no en días.

---

#### 118. Diplomático + IA = Especialista en traducción y análisis con IA (AI Translation/Analysis Specialist)

- **Qué hace:** Un diplomático + traducción con IA + análisis de sentimiento + inteligencia cultural.
- **Habilidades clave:**
  - Una formación en relaciones internacionales
  - Dominio de herramientas de traducción con IA (sus límites + riesgos)
  - Una base multilingüe
  - Inteligencia cultural
  - Negociación
- **Demanda:** ⭐⭐⭐ (modernización del Departamento de Estado de EE. UU., ONG)
- **Cómo llegar:**
  1. Un título en relaciones internacionales + el examen del servicio exterior
  2. Formación en herramientas de IA
  3. Un destino en el extranjero
- **Imagínalo así:** un diplomático con un asistente de IA. Entiende no solo las palabras, sino el contexto entre culturas.

---

#### 119. Funcionario de salud pública + IA = Epidemiólogo con IA (AI Epidemiologist)

- **Qué hace:** Salud pública + IA para pronosticar epidemias, rastrear contactos y planear intervenciones.
- **Habilidades clave:**
  - Una base en salud pública (MPH)
  - Aprendizaje automático con series de tiempo
  - Análisis geoespacial
  - Comunicación pública
  - Manejo de crisis
- **Demanda:** ⭐⭐⭐⭐ (inversión pos-COVID + amenazas constantes)
- **Cómo llegar:**
  1. Una maestría en salud pública (MPH)
  2. Formación en ciencia de datos
  3. Un empleo en los CDC de EE. UU., la OMS o una secretaría de salud
- **Imagínalo así:** un vigía de epidemias. La IA puede captar las señales de un brote antes de que salga en las noticias.

---

#### 120. Funcionario electoral + IA = Especialista en verificación con IA (AI Verification Specialist)

- **Qué hace:** Un administrador electoral + IA para verificar firmas, procesar boletas y detectar desinformación.
- **Habilidades clave:**
  - Administración electoral
  - Dominio de herramientas de IA
  - Seguridad + registros de auditoría
  - Confianza pública + transparencia
  - Cumplimiento normativo
- **Demanda:** ⭐⭐ (adopción lenta, controvertida)
- **Cómo llegar:**
  1. Una carrera en administración electoral
  2. Formación en herramientas de IA
  3. Un empleo en un organismo electoral estatal o local
- **Imagínalo así:** el guardián de un voto honesto. La IA agiliza; una persona garantiza el resultado.

---

### B8. Religión / filosofía / coaching (5 profesiones)

---

#### 121. Pastor / sacerdote + IA = Consejero espiritual aumentado con IA (AI-Augmented Spiritual Counselor)

- **Qué hace:** Un ministro religioso + IA para preparar sermones, investigar la Biblia y dar seguimiento a los fieles (los límites son fundamentales).
- **Habilidades clave:**
  - Una base teológica
  - Dominio de herramientas de IA
  - Límites + discernimiento
  - Acompañamiento pastoral
  - Construcción de comunidad
- **Demanda:** ⭐⭐ (adopción lenta, pero en aumento)
- **Cómo llegar:**
  1. Formación en seminario/ministerio
  2. Formación en herramientas de IA
  3. Un rol en una congregación o comunidad
- **Imagínalo así:** pastor + IA = una biblioteca ampliada. El corazón humano siempre va primero.

---

#### 122. Profesor de filosofía + IA = Educador en ética de la IA (AI Ethics Educator)

- **Qué hace:** Un profesor de filosofía especializado en ética de la IA. Enseña a los estudiantes a pensar críticamente sobre la ética de la IA.
- **Habilidades clave:**
  - Un doctorado en filosofía
  - La literatura sobre ética de la IA
  - Pedagogía
  - Vinculación con la industria
  - Comunicación pública
- **Demanda:** ⭐⭐⭐⭐ (cada vez más universidades ofrecen cursos de ética de la IA)
- **Cómo llegar:**
  1. Un doctorado en filosofía
  2. Una especialización en ética de la IA
  3. Docencia universitaria + consultoría
- **Imagínalo así:** un maestro de sabiduría en la era de la velocidad. La IA es rápida; la sabiduría es lenta. Se necesitan las dos.

---

#### 123. Coach de vida + IA = Coach de desarrollo personal con IA (AI Personal Development Coach)

- **Qué hace:** Un coach + IA para dar seguimiento a metas, reforzar hábitos y dar apoyo entre sesiones (al estilo de Replika, pero bien hecho).
- **Habilidades clave:**
  - Una certificación de coaching (ICF)
  - Dominio de herramientas de IA
  - Límites
  - Marketing + ventas
  - Conciencia de la privacidad
- **Demanda:** ⭐⭐⭐ (la industria del coaching crece, y la IA encaja en ella)
- **Cómo llegar:**
  1. Una certificación de coaching ICF
  2. Formación en herramientas de IA
  3. Crear tu propia práctica
- **Imagínalo así:** un coach + el diario de IA del cliente. Ve patrones a lo largo de meses aunque se reúnan una vez por semana.

---

#### 124. Orientador vocacional + IA = Guía de carrera con IA (AI Career Navigator)

- **Qué hace:** Un orientador vocacional + IA para analizar el mercado laboral, evaluar brechas de habilidades y trazar rutas profesionales personalizadas.
- **Habilidades clave:**
  - Una base en orientación
  - Dominio de herramientas de IA
  - Análisis de datos del mercado laboral
  - Conocimiento de las industrias
  - Empatía
- **Demanda:** ⭐⭐⭐⭐ (cambios bruscos en las profesiones = se necesitan guías)
- **Cómo llegar:**
  1. Una maestría en orientación o un certificado en desarrollo profesional
  2. Formación en herramientas de IA
  3. Una universidad, una organización sin fines de lucro o una práctica privada
- **Imagínalo así:** un navegante en tiempos turbulentos. La IA ve el mapa; la persona te conoce a ti.

---

#### 125. Maestro de meditación + IA = Guía de mindfulness con IA (AI Mindfulness Guide)

- **Qué hace:** Un maestro de meditación + personalización con IA (Headspace, Calm, Balance + IA).
- **Habilidades clave:**
  - Una certificación como maestro de meditación
  - Dominio de herramientas de IA
  - Diseño de la personalización
  - Límites
  - Sensibilidad cultural
- **Demanda:** ⭐⭐⭐ (la crisis de salud mental + la tecnología)
- **Cómo llegar:**
  1. Formación como maestro de meditación (MBSR, etc.)
  2. Colaborar con apps de IA
  3. Construir una audiencia
- **Imagínalo así:** maestro + IA = una meditación personal para cada quien. No "una talla para todos", sino "para ti, ahora mismo".

---

### B9. Deportes / atletismo (10 profesiones)

---

#### 126. Atleta + IA = Deportista entrenado con IA (AI-Trained Performer)

- **Qué hace:** Un atleta + IA para analizar la biomecánica, optimizar la nutrición, el sueño y la preparación mental.
- **Habilidades clave:**
  - Una base como atleta de alto rendimiento
  - Soltura con herramientas de IA
  - Interpretación de datos
  - Autodisciplina
  - Trabajo con entrenadores
- **Demanda:** ⭐⭐⭐ (los atletas de élite trabajan cada vez más con equipos de datos)
- **Cómo llegar:**
  1. Excelencia deportiva (un camino)
  2. Dominio de los datos
  3. Una alianza entre entrenador + tecnología
- **Imagínalo así:** atleta olímpico + IA = una mejora de 1% cada día. Un año después, un nivel que nadie más alcanza.

---

#### 127. Entrenador + IA = Coach de rendimiento con IA (AI Performance Coach)

- **Qué hace:** Un entrenador + IA para análisis de video, estudio de rivales y optimización de planes de entrenamiento.
- **Habilidades clave:**
  - Una base como entrenador (años de experiencia)
  - Herramientas de análisis de video con IA (Hudl, Sportscode)
  - Interpretación de datos
  - Comunicación con los atletas
  - Estrategia
- **Demanda:** ⭐⭐⭐⭐ (los datos + la IA ya son lo mínimo indispensable)
- **Cómo llegar:**
  1. Una carrera como entrenador
  2. Una certificación en analítica deportiva
  3. Subir de nivel gracias a los resultados
- **Imagínalo así:** un entrenador con un segundo cerebro. Ve patrones en cada partido y predice lo que harán los rivales.

---

#### 128. Árbitro + IA = Árbitro aumentado con IA (AI-Augmented Official)

- **Qué hace:** Un árbitro + IA tipo VAR como apoyo para decidir durante el partido.
- **Habilidades clave:**
  - Una base en arbitraje
  - Dominio de herramientas de IA
  - Toma de decisiones en tiempo real
  - Comunicación
  - Manejo de la presión
- **Demanda:** ⭐⭐⭐ (la controversia sigue, pero va en aumento)
- **Cómo llegar:**
  1. Formación en arbitraje + experiencia
  2. Una certificación en herramientas de IA
  3. Subir de categoría
- **Imagínalo así:** árbitro + IA = menos errores, más confianza. (Si se implementa bien.)

---

#### 129. Visor deportivo + IA = Cazatalentos con IA (AI Talent Scout)

- **Qué hace:** Un visor (scout) + IA para evaluar jugadores, predecir el draft y dar seguimiento a promesas.
- **Habilidades clave:**
  - Conocimiento profundo del deporte
  - Analítica de datos
  - Viajes + red de contactos
  - Reconocimiento de patrones
  - Comunicación
- **Demanda:** ⭐⭐⭐ (la ola de visoría basada en datos)
- **Cómo llegar:**
  1. Una base como jugador o entrenador
  2. Una especialidad en analítica
  3. Un empleo en un equipo
- **Imagínalo así:** visor + IA = descubrir a una futura estrella en un chico de preparatoria. Antes era intuición. Ahora es intuición + 1,000 métricas.

---

#### 130. Comentarista deportivo + IA = Narrador multilingüe con IA (AI Multilingual Caster)

- **Qué hace:** Un comentarista + IA para estadísticas en tiempo real, traducción a varios idiomas y verificación de datos.
- **Habilidades clave:**
  - Una base en radio y televisión
  - Conocimiento profundo del deporte
  - Soltura con herramientas de IA
  - Trabajo en vivo bajo presión
  - Narración de historias
- **Demanda:** ⭐⭐⭐ (streaming + contenido en varios idiomas)
- **Cómo llegar:**
  1. Una base en periodismo / radio y televisión
  2. Una especialidad en deportes
  3. Integrar herramientas de IA
- **Imagínalo así:** comentarista + IA = estadísticas en tiempo real. Cada jugador, cada partido.

---

#### 131. Preparador físico + IA = Especialista en acondicionamiento con IA (AI Conditioning Specialist)

- **Qué hace:** Un preparador de fuerza y acondicionamiento + IA para manejar las cargas, prevenir lesiones y llegar al máximo rendimiento en el momento justo.
- **Habilidades clave:**
  - Una certificación en fuerza y acondicionamiento (NSCA CSCS)
  - Interpretación de datos de dispositivos vestibles con IA
  - Periodización
  - Entrenamiento específico del deporte
  - Comunicación con los atletas
- **Demanda:** ⭐⭐⭐⭐ (equipos profesionales)
- **Cómo llegar:**
  1. Un título en ciencias del ejercicio + CSCS
  2. Formación en herramientas de IA (Catapult, Whoop)
  3. Un empleo en un equipo profesional
- **Imagínalo así:** preparador + IA = entrenamiento bajo el microscopio. Sabe cuándo exigir y cuándo descansar.

---

#### 132. Medicina deportiva + IA = Especialista en predicción de lesiones con IA (AI Injury Prediction Specialist)

- **Qué hace:** Un médico deportivo + IA para predecir el riesgo de lesiones, decidir el regreso al juego y optimizar la recuperación.
- **Habilidades clave:**
  - Título de médico con especialidad en medicina deportiva
  - Dominio de herramientas de IA
  - Biomecánica
  - Interpretación de estudios de imagen
  - Relación con los jugadores
- **Demanda:** ⭐⭐⭐⭐ (las lesiones les cuestan caro a los equipos, y la IA ayuda a manejar el riesgo)
- **Cómo llegar:**
  1. Título de médico + subespecialidad en medicina deportiva
  2. Una certificación en herramientas de IA
  3. Un empleo en un equipo
- **Imagínalo así:** un médico de equipo con bola de cristal. Predice una lesión con semanas de anticipación.

---

#### 133. Directivo deportivo + IA = Estratega de equipo con IA (AI Team Strategist)

- **Qué hace:** Un gerente general + IA para valuar jugadores, analizar negociaciones de contratos y optimizar el tope salarial.
- **Habilidades clave:**
  - Un MBA o una amplia trayectoria en el negocio del deporte
  - Analítica avanzada
  - Negociación
  - Dominio del tope salarial
  - Planeación a largo plazo
- **Demanda:** ⭐⭐⭐ (pocos puestos de alto nivel, pero son grandes)
- **Cómo llegar:**
  1. Una carrera en el negocio del deporte
  2. Ir subiendo en la directiva del club
  3. Soltura con la analítica
- **Imagínalo así:** gerente general + IA = ajedrez con 50 jugadas de anticipación. Jugadores + contratos + tope salarial.

---

#### 134. Entrenador de e-sports + IA = Coach de rendimiento en videojuegos con IA (AI Gaming Performance Coach)

- **Qué hace:** Un entrenador de e-sports + análisis de repeticiones con IA + predicción de rivales + el juego mental.
- **Habilidades clave:**
  - Experiencia en videojuegos (títulos específicos)
  - Herramientas de IA para repeticiones
  - Rendimiento mental
  - Comunicación con jugadores jóvenes
  - Conocimiento del streaming
- **Demanda:** ⭐⭐⭐ (los e-sports se están profesionalizando)
- **Cómo llegar:**
  1. Una carrera como jugador o como analista
  2. Certificaciones de entrenador
  3. Un empleo en un equipo
- **Imagínalo así:** un entrenador de videojuegos, donde reflejos + análisis con IA = un campeonato.

---

#### 135. Periodismo deportivo + IA = Analista deportivo con IA (AI Sports Analyst)

- **Qué hace:** Un periodista + IA para contar historias con datos, análisis en tiempo real y contenido para varias plataformas.
- **Habilidades clave:**
  - Una base en periodismo
  - Conocimiento del deporte
  - Dominio de herramientas de IA
  - Contenido para varias plataformas
  - Interacción con la audiencia
- **Demanda:** ⭐⭐⭐ (The Athletic + ESPN + nuevos participantes)
- **Cómo llegar:**
  1. Un título o una trayectoria en periodismo
  2. Una fuente deportiva fija
  3. Integrar herramientas de IA
- **Imagínalo así:** periodista + IA = datos + historia. Antes era el hecho. Ahora es el hecho + 1,000 piezas de contexto.

---

### B10. Manufactura / logística (15 profesiones)

---

#### 136. Operario de ensamble + IA = Operador aumentado con IA (AI-Augmented Operator)

- **Qué hace:** Un trabajador de fábrica + lentes de realidad aumentada (AR) + guía con IA para ensamblar y revisar la calidad.
- **Habilidades clave:**
  - Una base en manufactura
  - Soltura con lentes de AR
  - Dominio de herramientas de IA
  - Conciencia de calidad
  - Adaptabilidad
- **Demanda:** ⭐⭐⭐ (adopción de la Industria 4.0)
- **Cómo llegar:**
  1. Un empleo en manufactura
  2. Formación en herramientas de AR/IA
  3. Capacitarte para una especialidad
- **Imagínalo así:** trabajador + lentes inteligentes = cada pieza bien hecha. La IA detecta errores antes de que salgan de la línea.

---

#### 137. Trabajador de almacén + IA = Surtidor híbrido con IA (AI-Picker Hybrid)

- **Qué hace:** Un trabajador de almacén + guía de surtido con IA + trabajo junto a robots (Amazon, GXO, Locus Robotics).
- **Habilidades clave:**
  - Una base en almacén
  - Trabajo junto a robots
  - Dominio de herramientas de IA
  - Buena condición física
  - Conciencia de seguridad
- **Demanda:** ⭐⭐⭐⭐ (los almacenes grandes se automatizan primero, y los demás los siguen)
- **Cómo llegar:**
  1. Conseguir empleo en un almacén
  2. Formación para trabajar con robots
  3. Puestos de líder/especialista
- **Imagínalo así:** surtidor + robot con IA = un equipo. El robot carga; la persona piensa.

---

#### 138. Conductor de camión + IA = Supervisor de autonomía con IA (AI-Autonomy Supervisor)

- **Qué hace:** Un conductor de camión + monitoreo de camiones autónomos (Aurora, Kodiak).
- **Habilidades clave:**
  - Una base con licencia de conducir comercial (CDL en EE. UU.)
  - Habilidades para supervisar a la IA
  - Toma de decisiones en casos límite
  - Seguridad
  - Conocimiento de logística
- **Demanda:** ⭐⭐⭐ (una fase de transición en 2026-2030)
- **Cómo llegar:**
  1. Formación para la licencia comercial (CDL)
  2. Una certificación en camiones autónomos
  3. Un empleo en Aurora, Kodiak o una empresa similar
- **Imagínalo así:** un capitán de barco + piloto automático. El piloto automático lleva el timón; el capitán se encarga de los casos límite.

---

#### 139. Piloto + IA = Piloto aumentado con IA (AI-Augmented Pilot)

- **Qué hace:** Un piloto comercial + piloto automático con IA + planeación de vuelo con IA + monitoreo de fatiga con IA.
- **Habilidades clave:**
  - Una licencia de piloto de transporte de línea aérea (ATP) o experiencia de vuelo militar
  - Dominio de herramientas de IA
  - Manejo de crisis
  - CRM (gestión de recursos de la tripulación)
  - Formación continua
- **Demanda:** ⭐⭐⭐ (faltan pilotos, y la IA los complementa)
- **Cómo llegar:**
  1. Formación de vuelo (un camino largo)
  2. Ir subiendo en una aerolínea
  3. Formación en trabajo aumentado con IA
- **Imagínalo así:** piloto + IA = una cabina doble. Ninguno reemplaza al otro; la IA complementa.

---

#### 140. Controlador aéreo + IA = Optimizador de tráfico con IA (AI Traffic Optimizer)

- **Qué hace:** Un controlador de tránsito aéreo + IA para optimizar el tráfico, predecir conflictos y trazar rutas según el clima.
- **Habilidades clave:**
  - Certificación de control de tránsito aéreo (FAA / EASA)
  - Dominio de herramientas de IA
  - Manejo de crisis
  - Multitarea
  - Mantener la calma bajo presión
- **Demanda:** ⭐⭐⭐ (modernización de la FAA en EE. UU.)
- **Cómo llegar:**
  1. La academia de la FAA (en EE. UU.) o la autoridad de aviación de tu país
  2. Certificación de control de tránsito aéreo
  3. Formación en herramientas de IA
- **Imagínalo así:** un director de orquesta del cielo + IA. La IA avisa de los conflictos con minutos de anticipación.

---

#### 141. Capitán de barco + IA = Operador marítimo con IA (AI Marine Operator)

- **Qué hace:** Un capitán + monitoreo de barcos autónomos (Yara Birkeland, buques autónomos de ASKO).
- **Habilidades clave:**
  - Formación marítima
  - Dominio de herramientas de IA
  - Clima + navegación
  - Manejo de crisis
  - Logística
- **Demanda:** ⭐⭐ (adopción lenta, pero en aumento)
- **Cómo llegar:**
  1. Una academia náutica
  2. Tiempo de navegación + certificaciones
  3. Formación en buques con IA
- **Imagínalo así:** capitán + barco autónomo = una tripulación más pequeña, más tecnología.

---

#### 142. Cartero + IA = Especialista en entregas aumentado con IA (AI-Augmented Delivery Specialist)

- **Qué hace:** Entregas + rutas con IA + integración de drones + optimizar cada punto de contacto con el cliente.
- **Habilidades clave:**
  - Una base en entregas
  - Dominio de herramientas de rutas con IA
  - Nociones de drones (donde aplique)
  - Atención al cliente
  - Buena condición física
- **Demanda:** ⭐⭐⭐⭐ (Amazon, UPS, FedEx, USPS)
- **Cómo llegar:**
  1. Un empleo de reparto
  2. Formación en herramientas de IA
  3. Puestos especializados
- **Imagínalo así:** cartero + IA = una ruta optimizada cada día. Clientes contentos.

---

#### 143. Personal de limpieza + IA = Administrador de instalaciones con IA (AI-Powered Facility Manager)

- **Qué hace:** Una persona de limpieza + gestión de una flota de robots con IA (Avidbots, robots Whiz).
- **Habilidades clave:**
  - Una base en la industria de la limpieza
  - Gestión de flotas de robots
  - Dominio de herramientas de IA
  - Control de calidad
  - Atención al cliente
- **Demanda:** ⭐⭐⭐ (la ola de automatización de la limpieza comercial)
- **Cómo llegar:**
  1. Experiencia en la industria de la limpieza
  2. Una certificación en operación de robots
  3. Un puesto de gestión
- **Imagínalo así:** limpieza + una flota de robots = más limpio, más rápido, más barato. Gestionar, no trapear.

---

#### 144. Guardia de seguridad + IA = Operador de vigilancia con IA (AI Surveillance Operator)

- **Qué hace:** Un guardia + cámaras con IA + análisis de comportamiento + predicción de amenazas.
- **Habilidades clave:**
  - Formación en seguridad
  - Dominio de herramientas de IA
  - Conciencia de los sesgos
  - Mantener la calma bajo presión
  - Atención al cliente
- **Demanda:** ⭐⭐⭐ (Verkada, Rhombus, en aumento)
- **Cómo llegar:**
  1. Una licencia o certificación como guardia de seguridad
  2. Formación en herramientas de IA
  3. Una asignación especializada
- **Imagínalo así:** un guardia + 1,000 cámaras con IA = una persona ve lo que antes no podían ver 10.

---

#### 145. Trabajador de la construcción + IA = Constructor aumentado con IA (AI-Augmented Builder)

- **Qué hace:** Construcción + visualización de planos con IA + guía con AR + monitoreo de seguridad.
- **Habilidades clave:**
  - Una base en un oficio de la construcción
  - Dominio de herramientas de AR/IA
  - Conciencia de seguridad
  - Lectura de planos
  - Trabajo en equipo
- **Demanda:** ⭐⭐⭐⭐ (la ola de tecnología en la construcción)
- **Cómo llegar:**
  1. Un aprendizaje en un oficio
  2. Formación en herramientas de IA/AR
  3. Puestos especializados
- **Imagínalo así:** constructor + lentes de AR = el plano ahí mismo, en la obra. Menos errores, trabajo más rápido.

---

#### 146. Inspector de calidad + IA = Inspector con visión por IA (AI Vision Inspector)

- **Qué hace:** Control de calidad + visión por computadora con IA para detectar defectos en manufactura.
- **Habilidades clave:**
  - Una base en control de calidad
  - Dominio de herramientas de visión con IA
  - Control estadístico de procesos
  - Lectura de especificaciones
  - Comunicación
- **Demanda:** ⭐⭐⭐⭐ (fábricas de todo tipo)
- **Cómo llegar:**
  1. Formación en control de calidad
  2. Una certificación en herramientas de IA
  3. Una especialización por industria
- **Imagínalo así:** control de calidad + un ojo de IA = cada pieza revisada. Una muestra del 100%, algo que antes era imposible.

---

#### 147. Gerente de logística + IA = Coordinador de cadena de suministro con IA (AI Supply Chain Coordinator)

- **Qué hace:** Un gerente de logística + IA para optimizar rutas, gestionar excepciones y coordinar proveedores.
- **Habilidades clave:**
  - Una base en cadena de suministro
  - Dominio de herramientas de IA (TMS, WMS)
  - Gestión de proveedores
  - Manejo de excepciones
  - Análisis de datos
- **Demanda:** ⭐⭐⭐⭐ (empresas que envían y transportan mercancía)
- **Cómo llegar:**
  1. Una carrera en logística
  2. Formación en herramientas de IA
  3. Subir a puestos de gestión
- **Imagínalo así:** logística + IA = menos excepciones, mejor servicio.

---

#### 148. Especialista en compras + IA = Comprador con IA (AI Buyer)

- **Qué hace:** Compras + IA para analizar proveedores, optimizar el gasto y entender a fondo los contratos.
- **Habilidades clave:**
  - Una base en compras
  - Dominio de herramientas de IA
  - Negociación
  - Revisión de contratos
  - Análisis del gasto
- **Demanda:** ⭐⭐⭐ (empresas grandes)
- **Cómo llegar:**
  1. Una carrera en compras
  2. Formación en herramientas de IA
  3. Una especialidad (directas/indirectas, servicios)
- **Imagínalo así:** comprador + IA = conoce el mercado tan bien como los propios proveedores. Menos pagos de más.

---

#### 149. Gerente de inventario + IA = Optimizador de inventario con IA (AI Stock Optimizer)

- **Qué hace:** Un gerente de inventario + IA para pronosticar la demanda, optimizar y reabastecer.
- **Habilidades clave:**
  - Una base en gestión de inventarios
  - Herramientas de pronóstico con IA
  - Soltura con el ERP
  - Comprensión de estadística
  - Comunicación
- **Demanda:** ⭐⭐⭐⭐ (comercio minorista + comercio electrónico + manufactura)
- **Cómo llegar:**
  1. Un título en gestión de la cadena de suministro (SCM) o experiencia
  2. Formación en herramientas de IA
  3. Una especialización por industria
- **Imagínalo así:** inventario + IA = el inventario justo en el momento justo. No "cuánto nos gustaría", sino "cuánto necesitamos".

---

#### 150. Gerente de producción + IA = Ingeniero de manufactura con IA (AI Manufacturing Engineer)

- **Qué hace:** Un gerente de producción + IA para programar la producción, planear la capacidad y optimizar la eficiencia general de los equipos (OEE).
- **Habilidades clave:**
  - Una base en manufactura
  - Dominio de herramientas de IA
  - Lean / Six Sigma
  - Gestión de equipos
  - Interpretación de datos
- **Demanda:** ⭐⭐⭐⭐ (Industria 4.0)
- **Cómo llegar:**
  1. Un título en manufactura o ingeniería industrial
  2. Experiencia en planta
  3. Formación en herramientas de IA
- **Imagínalo así:** gerente de producción + IA = menos tiempo muerto, más producción. Cada minuto cuenta.

---

## <a id="c-extended"></a>🔥 Sección C ampliada: 25 empleos que desaparecen

Ampliamos la lista de 10 a 25: aquí van 15 más.

---

#### 11. Tenedor de libros (nivel básico)

- **Qué se está reemplazando:** La contabilidad con IA (Pilot, la automatización de QuickBooks y herramientas similares).
- **Qué sobrevive:** Contadores sénior + contadores públicos certificados + especialistas en entidades complejas.
- **Imagínalo así:** el ninja de Excel pierde el trabajo. Gana el contador público con mentalidad de asesor.

---

#### 12. Taquígrafo judicial

- **Qué se está reemplazando:** La transcripción + resúmenes con IA (Verbit, Trint).
- **Qué sobrevive:** Subtituladores en tiempo real para accesibilidad, registro jurídico especializado.
- **Imagínalo así:** el mecanógrafo del juzgado va de salida. Se queda el estenógrafo judicial certificado para los casos críticos.

---

#### 13. Agente de viajes (nivel básico)

- **Qué se está reemplazando:** La planeación de viajes con IA (ChatGPT + Booking.com + Kayak).
- **Qué sobrevive:** Agentes de viajes de lujo o especializados (por las relaciones personales y el servicio de concierge).
- **Imagínalo así:** el agente básico al estilo de los años noventa va de salida. Se queda el concierge con contactos privados.

---

#### 14. Cajero de autoservicio en auto (drive-through)

- **Qué se está reemplazando:** Pedidos por voz con IA (pruebas piloto en varias cadenas de comida rápida, como Wendy's).
- **Qué sobrevive:** Anfitriones amables en puestos de experiencia del cliente.
- **Imagínalo así:** una ventanilla de autoservicio sin persona: una voz de IA toma tu pedido.

---

#### 15. Operador de telemarketing

- **Qué se está reemplazando:** Agentes de voz con IA (más baratos, nunca se cansan).
- **Qué sobrevive:** Representantes de desarrollo de ventas (SDR) B2B de alto valor para ventas complejas (donde la relación importa).
- **Imagínalo así:** el que hace llamadas en frío de rutina va de salida. Se queda el SDR con experiencia en el sector.

---

#### 16. Catalogador de biblioteca

- **Qué se está reemplazando:** Extracción de metadatos + clasificación con IA.
- **Qué sobrevive:** Bibliotecarios como asesores de investigación, archivistas digitales.
- **Imagínalo así:** el catalogador va de salida. Se queda el bibliotecario que ayuda a las personas a encontrar información.

---

#### 17. Cobrador de caseta de peaje

- **Qué se está reemplazando:** El cobro electrónico + lectores de placas (ya casi desapareció).
- **Qué sobrevive:** Ya casi no existe.
- **Imagínalo así:** una caseta con una persona adentro es un vestigio. Ahora todo es sin efectivo, como E-ZPass.

---

#### 18. Cajero de banco

- **Qué se está reemplazando:** La banca en el celular + atención al cliente con IA.
- **Qué sobrevive:** Asesores de gestión patrimonial, especialistas en operaciones complejas.
- **Imagínalo así:** la ventanilla básica va de salida. Se queda el banquero personal para cuentas de más de \$1M.

---

#### 19. Repartidor de periódicos

- **Qué se está reemplazando:** Suscripciones digitales, una industria impresa que se achica.
- **Qué sobrevive:** Un servicio mucho más pequeño (se mantiene sobre todo para suscriptores de muchos años).
- **Imagínalo así:** el chico en bicicleta a las 5 a. m. ya no está. En su lugar aparece una notificación push.

---

#### 20. Venta de boletos de cine

- **Qué se está reemplazando:** Quioscos de autoservicio + apps en el celular.
- **Qué sobrevive:** Anfitriones de la experiencia en el cine (salas especiales IMAX, pantallas premium).
- **Imagínalo así:** la taquilla va de salida. Llega el código QR.

---

#### 21. Vendedor de enciclopedias (ya desapareció)

- **Qué era:** Vender colecciones completas de puerta en puerta.
- **Qué lo reemplazó:** Wikipedia + Google + Claude.
- **Imagínalo así:** ya es historia. Un memento mori del que otras profesiones pueden aprender.

---

#### 22. Editor de revista impresa (nivel básico)

- **Qué se está reemplazando:** La publicación digital primero + generación de contenido con IA.
- **Qué sobrevive:** Impresos especializados o de lujo (Monocle, Apartamento), directores editoriales digitales.
- **Imagínalo así:** la revista masiva va de salida. Se quedan el impreso de nicho + lo digital.

---

#### 23. Editor de directorios telefónicos (ya desapareció)

- **Qué era:** La Sección Amarilla + la Sección Blanca, cada año.
- **Qué lo reemplazó:** Google Maps + LinkedIn + Yelp.
- **Imagínalo así:** memento mori. Un libro pesado en la puerta de la casa ya solo pertenece al archivo.

---

#### 24. Corredor de bolsa (minorista, nivel de entrada)

- **Qué se está reemplazando:** Asesores automatizados (robo-advisors como Wealthfront, Betterment) + operaciones sin comisión.
- **Qué sobrevive:** Asesores para clientes de alto patrimonio, especialistas en opciones + inversiones alternativas.
- **Imagínalo así:** el corredor minorista que vive de comisiones va de salida. Se queda el gestor patrimonial que hace una planeación integral.

---

#### 25. Capturista de reservaciones de viaje

- **Qué se está reemplazando:** Reservaciones de autoservicio + asistentes de IA.
- **Qué sobrevive:** Gerentes especializados en viajes corporativos.
- **Imagínalo así:** el capturista de la agencia de viajes va de salida. Se queda el arquitecto de viajes corporativos.

---

## <a id="d-extended"></a>🛠 Sección D ampliada: 50 habilidades para el futuro

Ampliamos de 25 a 50.

### Habilidades técnicas específicas de IA (25 nuevas)

#### 26. Control de versiones de prompts (AI Prompt Versioning)

Un enfoque sistemático para controlar las versiones de los prompts como si fueran código: git, pruebas A/B, volver a una versión anterior.

#### 27. Pronóstico de costos de LLM (LLM Cost Forecasting)

Pronosticar costos a partir de los patrones de uso. Planeación de capacidad en \$\$\$.

#### 28. Depuración de sistemas multiagente (Multi-Agent Debugging)

Rastrear cómo se comunican los agentes, encontrar los modos de falla y llegar a la causa raíz de errores distribuidos.

#### 29. Ajuste de agentes de voz (Voice Agent Tuning)

Optimizar la latencia + la naturalidad + cómo se manejan las interrupciones.

#### 30. Diseño de arquitectura RAG (RAG Architecture Design)

Estrategias de fragmentación (chunking), reordenadores de resultados (rerankers), RAG multimodal.

#### 31. Ajuste fino de modelos locales (Local Model Fine-Tuning)

LoRA, QLoRA, optimización según el hardware en GPU de consumo.

#### 32. Auditoría de seguridad de IA (AI Safety Auditing)

Red teaming, pruebas adversariales, evaluación de la alineación.

#### 33. Diseño de IA constitucional (Constitutional AI Design)

Traducir principios en comportamientos para sistemas de IA.

#### 34. Criterio ético en IA (AI Ethics Judgment)

Resolver conflictos entre principios que compiten; ética según el contexto.

#### 35. Implementación de IA entre culturas (Cross-Cultural AI Deployment)

Ajustar el comportamiento de la IA a distintas culturas, idiomas y sistemas de valores.

#### 36. Compras de IA (AI Procurement)

Evaluación de proveedores, contratos, acuerdos de nivel de servicio (SLA), propiedad de los datos.

#### 37. Negociación con proveedores de IA (AI Vendor Negotiation)

Precios, compromisos, cláusulas sobre datos, conciencia del costo de cambiar de proveedor.

#### 38. Implicaciones fiscales y legales de la IA (Tax/Legal AI Implications)

Entender las implicaciones fiscales de usar IA y su impacto en el derecho laboral (los detalles son una pregunta para tu contador o abogado).

#### 39. Conocimiento de seguros para IA (AI Insurance Literacy)

Entender los seguros para implementaciones de IA (errores, propiedad intelectual, responsabilidad civil).

#### 40. Diseño de flujos de trabajo híbridos (Hybrid Workflow Design)

Diseñar flujos de trabajo entre personas e IA (traspasos, supervisión, los límites de la autonomía).

#### 41. Gestión de equipos de IA y personas (AI-Human Team Management)

Gestionar equipos donde las personas y los agentes trabajan juntos.

#### 42. Comparación de costos de IA (AI Cost Benchmarking)

Comparar costos entre proveedores + cargas de trabajo.

#### 43. Metodología de evaluación de IA (AI Evaluation Methodology)

Crear evaluaciones (evals), conjuntos de datos de referencia (golden datasets), pruebas de regresión.

#### 44. Red teaming de IA (AI Red Teaming)

Pruebas adversariales de los sistemas antes de ponerlos en marcha.

#### 45. Pruebas de sesgo en IA (AI Bias Testing)

Equidad entre grupos demográficos; descubrir casos límite.

#### 46. Evaluación de capacidades de agentes (Agent Capability Assessment)

Evaluar qué puede y qué no puede hacer un agente de forma confiable.

#### 47. Arquitectura de memoria de IA (AI Memory Architecture)

Diseñar la memoria a largo plazo, de trabajo y episódica de los agentes.

#### 48. Diseño del uso de herramientas (Tool Use Design)

Cuándo y cómo dar herramientas a los agentes frente a dejarlos solo con prompts.

#### 49. Creación de servidores MCP (MCP Server Creation)

Crear servidores de Model Context Protocol.

#### 50. Operación de IA local (Local AI Ops)

Operar infraestructura de IA en las propias instalaciones (Ollama, LM Studio, vLLM).

---

## <a id="section-f"></a>📅 Sección F: Pronóstico año por año 2027-2030

> **Aviso:** Estos son escenarios del autor, no hechos. Los números de esta sección se eliminaron; solo quedan las tendencias.

---

### 2027: el año de los agentes

**El cambio principal:** Los agentes autónomos pasan de las demostraciones a la producción. La IA de voz se vuelve la interfaz predeterminada en muchos casos de uso.

**Cambios técnicos clave:**

- Agentes autónomos confiables en producción (adopción generalizada en las empresas Fortune 500)
- Las interfaces de voz primero se vuelven familiares
- Costo de la IA: se espera que los tokens bajen de precio notablemente (un pronóstico, no un hecho)
- Los sistemas multiagente con 5-20 agentes se vuelven algo rutinario en producción

**Profesiones en crecimiento (las 10 principales por crecimiento de la demanda):**

| # | Profesión |
|---|---|
| 1 | Arquitecto de agentes de IA (AI Agent Architect) |
| 2 | Desarrollador de IA de voz (Voice AI Developer) |
| 3 | Optimizador de costos de IA (AI Cost Optimizer) |
| 4 | Especialista en adopción de IA (AI Adoption Specialist) |
| 5 | Desarrollador de apps para lentes inteligentes (Smart Glasses App Developer) |
| 6 | Responsable de ética de IA (AI Ethics Officer) |
| 7 | Abogado/médico aumentado con IA (AI-Augmented Lawyer/Doctor) |
| 8 | Ingeniero de calidad de IA (AI Quality Engineer) |
| 9 | Auditor de IA (AI Auditor) |
| 10 | Diseñador educativo de IA (AI Education Designer) |

**Profesiones en declive (las 5 principales):**

| # | Profesión |
|---|---|
| 1 | Redactor publicitario junior |
| 2 | Soporte de primer nivel |
| 3 | Traductor de nivel inicial |
| 4 | Asistente jurídico de tareas rutinarias |
| 5 | Captura de datos |

---

### 2028: el año de la especialización

**El cambio principal:** La capa de IA genérica (commodity) madura. Ganan los especialistas en IA vertical (salud, derecho, finanzas).

**Cambios técnicos clave:**

- La capa de IA genérica madura (las diferencias entre los modelos de frontera se reducen para la mayoría de los casos de uso)
- Surgen ganadores de la IA vertical (salud, derecho, finanzas), con ventajas difíciles de copiar basadas en datos del sector + cumplimiento normativo
- La IA local se acerca en calidad a los modelos de frontera (un pronóstico)
- Lo multimodal se vuelve lo normal (texto + voz + visión en cada app)

**Profesiones en crecimiento:**

- Especialistas en IA vertical (conocimiento profundo de una industria): demanda de IA en salud, derecho, finanzas
- Ingenieros de implementación de IA local
- Seguridad de IA / red team
- Puestos de cumplimiento normativo en IA
- Gerentes de compras de IA

**En declive:**

- El "ingeniero de IA" genérico (se vuelve commodity)
- Ingenieros de software junior (los reemplazan personas sénior + IA; las empresas contratan menos)
- Analistas de nivel medio (la IA hace el trabajo; las empresas contratan menos)

**Nuevas profesiones que surgen en 2028:**

- **Especialista en litigios de IA (AI Litigation Specialist)**: demandas entre IA y personas (propiedad intelectual, daños, decisiones injustas)
- **Ajustador de seguros de IA (AI Insurance Adjuster)**: manejo de reclamaciones relacionadas con IA (errores, accidentes, responsabilidad)
- **Tecnólogo de defensoría pública con IA (AI Public Defender Tech)**: usar IA para dar servicios legales a personas con poco acceso a ellos
- **Especialista en patentes de IA (AI Patent Specialist)**: propiedad intelectual de obras generadas por IA
- **Consejero de reinserción ante la IA (AI Restitution Counselor)**: ayudar a las personas desplazadas por la IA a encontrar nuevos caminos

---

### 2029: tensión previa a la AGI

**El cambio principal:** Los modelos podrían volverse mucho más fuertes en razonamientos largos de varios pasos. Algunas profesiones podrían cambiar de forma drástica. Los marcos regulatorios están plenamente activos.

**Cambios técnicos clave:**

- Los modelos se vuelven mucho más fuertes en razonamientos largos (problemas matemáticos, tareas de investigación)
- Algunas profesiones sufren cambios drásticos (investigación, código complejo, incluso el trabajo creativo)
- Los marcos regulatorios están plenamente vigentes (la Ley de IA de la UE, las normas federales y estatales de EE. UU., las normas de IA de China)
- Comienzan las conversaciones sobre un tratado de IA (geopolítica)
- La actividad económica mediada por IA = un % importante del PIB

**En crecimiento:**

- Investigadores en seguridad de IA (AI Safety Researchers; experiencia escasa)
- Ingenieros de alineación de IA (AI Alignment Engineers)
- Ingenieros constitucionales de IA (AI Constitutional Engineers; diseñan sistemas de valores)
- Especialistas en gobernanza de IA (AI Governance Specialists; política + técnica)
- Especialistas en seguros y responsabilidad de IA

**En declive:**

- Muchos empleos de conocimiento de nivel inicial (a los recién egresados podría costarles encontrar su primer empleo)
- Mandos medios (la IA aplana las jerarquías)
- Creadores de contenido genérico (la IA subió muchísimo la vara)

**Posibles puntos de tensión:**

- A las universidades les cuesta definir qué enseñar a sus egresados
- Una brecha generacional (las personas nacidas desde 2010 nunca conocieron el trabajo antes de la IA)
- Algunos países se vuelven proteccionistas (leyes para preservar empleos)

---

### 2030: un nuevo equilibrio

**El cambio principal:** La IA está en todo el trabajo de conocimiento (suponiendo que no haya un salto a la AGI). Que las personas trabajen aumentadas con IA es la norma.

**Cambios técnicos clave:**

- La IA está en todo el trabajo de conocimiento (si todavía no hay AGI)
- Personas aumentadas con IA = la nueva norma (como las computadoras en los años 2000)
- Aparecen empresas donde uno o dos fundadores trabajan con muchos agentes de IA (un pronóstico)
- Dominan los ganadores especializados de la IA vertical B2B
- Tener una IA personal se vuelve parte de la cultura (como tener un dominio en los años noventa)

**Ganadores a largo plazo (estables durante el cambio hacia la IA):**

- **Seguridad / ética / cumplimiento en IA**: la necesidad no desaparece
- **Profesionales aumentados con IA** (médicos, abogados, etc. con conocimiento profundo de su área): más productividad, que puede traducirse en más ingresos
- **Consultores de estrategia de IA**: ayudan a las empresas a adoptar la IA (las grandes empresas necesitan guías)
- **Directores creativos**: el gusto importa (la IA ejecuta, una persona decide)
- **Ventas / relaciones**: la gente le compra a la gente (transacciones de alta confianza)

**Bajo más presión a largo plazo:**

- Trabajo rutinario de habilidad media (se vuelve commodity)
- Producción de contenido genérico (su precio se desplomó)
- Trabajo básico de analista (la IA hizo el trabajo)
- Rutas educativas estandarizadas (el mundo necesita personas que aprendan a adaptarse)


---

## <a id="section-g"></a>🌍 Sección G: Cambios geográficos 2026-2030

| Región | Probablemente crece | Probablemente decae | Por qué |
|--------|---------|-----------|-----|
| **San Francisco / Nueva York** | Seguridad de IA, investigación de frontera, IA en derecho/finanzas | Ingeniería genérica | El trabajo remoto con IA la vuelve commodity |
| **Londres / Berlín** | Cumplimiento, regulación, ética de la IA | Menos competitivas en tecnología pura | Un polo para el cumplimiento de la Ley de IA de la UE |
| **Singapur / Dubái** | IA en finanzas, IA en salud | Manufactura | Regulación favorable + capital |
| **Bombay / Bangalore** | Servicios de IA / outsourcing, puestos híbridos | Servicios básicos de TI | Dominan los puestos híbridos |
| **Europa del Este / América Latina** | Freelancers / contratistas de IA | Soporte local de TI | Arbitraje de costos + la IA agiliza el trabajo |
| **Mercados aislados por sanciones o por reglas de soberanía de datos** | IA autoalojada / IA "soberana" | Empleos ligados a plataformas occidentales | Sanciones + regulación |
| **Tokio / Seúl** | Hardware de IA + robótica | Empleos de servicios | Demografía + inversión |
| **Tel Aviv** | Seguridad de IA, IA para defensa | Startups genéricas | Especialización + geopolítica |
| **Ciudad de México / Bogotá** | Ingeniería de IA nearshore para EE. UU. | Centros de llamadas | Ventaja de zona horaria + costos |
| **Lagos / Nairobi** | IA para agricultura, fintech con IA | Trabajo manual | Soluciones locales + saltar etapas |

---

## <a id="section-h"></a>📚 Sección H: Cómo evolucionan las habilidades año por año

### Habilidades críticas de 2026 (AHORA)

- **Ingeniería de prompts** (todavía muy valiosa; la vara para los juniors es más baja)
- **Python + API de LLM**
- **Integración con MCP**
- **Ingeniería de costos** (presupuestos de tokens, elección de modelos)
- **Seguridad básica de IA** (conocer la inyección de prompts y los jailbreaks)

### Habilidades críticas de 2027

- **Orquestación multiagente** (5+ agentes, patrones de coordinación)
- **Desarrollo de IA de voz** (Vapi, Bland, Retell)
- **Implementación de IA local** (Ollama, vLLM, en las propias instalaciones)
- **Optimización profunda de costos de IA** (caché, destilación, enrutamiento)
- **Conocimiento de la regulación** (los artículos clave de la Ley de IA de la UE, las normas federales y estatales de IA de EE. UU.)

### Habilidades críticas de 2028

- **Experiencia profunda en un área de IA vertical** (salud/derecho/finanzas/etc.)
- **Seguridad de IA / red team** (pruebas adversariales, alineación)
- **Ajuste fino de IA local** (LoRA para tareas específicas)
- **Compras de IA / gestión de proveedores**
- **Implementación de IA entre culturas** (varias regiones, varios idiomas)

### Habilidades críticas de 2029-2030

- **Entender la alineación de la IA** (no solo la seguridad: la alineación)
- **Moverse en la gobernanza de la IA** (política + técnica)
- **Diseño de flujos de trabajo híbridos entre personas e IA**
- **Conocimiento fiscal / legal sobre IA**
- **Moverse entre tratados de IA** (geopolítica)
- **Economía de la IA** (empleos, desplazamiento, transición)

---

## <a id="section-i"></a>🛡 Sección I: Lo que la IA NO hará antes de 2030

10 cosas que es **muy poco probable** que la IA reemplace para 2030:

### 1. Empatía genuina en momentos de crisis

La IA imita la empatía, pero en momentos de pérdida real, miedo o alegría, la gente quiere a la gente. Los cuidados paliativos, el acompañamiento en el duelo, el apoyo después de una tragedia: todo eso sigue siendo humano.

### 2. El parto físico / la lactancia

Biología. Ninguna IA va a dar a luz a un bebé. Acompañar un parto también sigue siendo algo íntimamente humano.

### 3. Artes marciales / deportes de combate en tiempo real

Un cuerpo físico + reflejos de milisegundos + entrenamiento vivido. En 2030 la robótica está lejos del nivel olímpico.

### 4. Liderazgo religioso / espiritual auténtico

Experiencia vivida + conexión con la comunidad + tradiciones sagradas. La IA puede ayudar, no dirigir.

### 5. Avances científicos originales

La IA encuentra patrones en datos que ya existen. Los avances muchas veces requieren intuición + casualidad + saltos entre disciplinas. Persona + IA = un avance; la IA sola, no.

### 6. Liderazgo político que requiere legitimidad democrática

Los votantes no van a elegir a una IA. Aunque la IA fuera mejor para las políticas públicas, la legitimidad solo pertenece a las personas.

### 7. Negociaciones de primer nivel que dependen de una confianza con mucho en juego

Acuerdos de más de \$100M, fusiones y adquisiciones, tratados internacionales. La IA prepara; las personas cierran.

### 8. Artes escénicas en vivo

Teatro, conciertos, deportes: carisma + presencia + riesgo = personas. La IA puede actuar, pero la experiencia del público es distinta.

### 9. Trabajo de cuidados que requiere presencia física constante

Cuidado de niños, de personas mayores, cuidados paliativos, cuidados físicos íntimos. Incluso con robots, la gente quiere a la gente.

### 10. Dirección creativa que requiere gusto + comprensión cultural

La IA hace la mayor parte de la ejecución creativa práctica. La pregunta de "qué hacer y por qué" se queda con una persona (gusto, el momento cultural, visión).

---

## <a id="section-j"></a>👥 Sección J: La economía híbrida: 3 arquetipos para 2030

En el escenario del autor, para 2030 la mayoría de los trabajadores del conocimiento encajaría en uno de 3 arquetipos:

---

### Arquetipo 1: Especialista nativo de IA (AI-Native Specialist)

**Patrón:**

- 60-70% de su tiempo trabajando con IA
- 100% especializado en un área (derecho, medicina, ingeniería, etc.)
- Alta productividad gracias al trabajo aumentado con IA

**Ejemplos:** Cirujano aumentado con IA, cardiólogo con IA, abogado con IA, arquitecto con IA


**Estilo de vida:**

- Trabajo profundo + algo de tiempo con clientes o pacientes
- Aprendizaje continuo (las herramientas de IA se actualizan cada trimestre)
- Más productividad, que puede traducirse en más ingresos (pero con riesgo de agotamiento)
- Muchas veces ligado a una ciudad (clientes, hospitales, juzgados)

**Imagínalo así:** un atleta olímpico en su propio campo. La IA es el entrenador + la analítica + el marcador.

---

### Arquetipo 2: Conector centrado en las personas (Human-Centric Connector)

**Patrón:**

- 20% IA / 80% relaciones
- Ventas, liderazgo, terapia, religión, hospitalidad
- Confianza + presencia = el valor principal

**Ejemplos:** Ejecutivo de ventas, director general (CEO), terapeuta, pastor, concierge, coach ejecutivo


**Estilo de vida:**

- Viajes, reuniones, construir una red de contactos
- La inteligencia emocional como habilidad principal
- La IA se encarga de lo administrativo; la persona, de las relaciones
- Flexibilidad geográfica (ir a donde está la gente)

**Imagínalo así:** un director de orquesta humano. La IA es una orquesta de instrumentos; la persona es la química en la sala.

---

### Arquetipo 3: Imperio individual con IA (Solo AI Empire)

**Patrón:**

- 90% IA / 10% estrategia
- Un fundador con 10 agentes
- Mucha autonomía, mucho riesgo

**Ejemplos:** Un fundador de SaaS que trabaja solo, el dueño de una agencia de IA, un creador de contenido emprendedor, un inversionista inmobiliario con operaciones a cargo de IA


**Estilo de vida:**

- Mucha autonomía, sin depender de un lugar
- Ingresos que suben y bajan mucho
- Riesgo de soledad (sin equipo)
- Experimentación constante

**Imagínalo así:** un capitán de barco cuyos 10 marineros son todos IA. Marca el rumbo y cosecha las recompensas. (O se hunde.)

---

### Más 4 miniarquetipos:

- **Trabajador manual + IA (Hands Worker + AI)** (Arquetipo 4): los oficios + AR (electricista, plomero). Protegido de los cambios durante años (el trabajo es físico).
- **Educador-guía (Educator-Navigator)** (Arquetipo 5): enseña a las personas a vivir con la IA. La demanda está creciendo.
- **Centinela del cumplimiento (Compliance Sentinel)** (Arquetipo 6): un experto en regulación. Un puesto estable y protegido.
- **Investigador en seguridad (Safety Researcher)** (Arquetipo 7): un rol de investigación estrecho y de alto nivel.

---

## <a id="top-30"></a>⭐ Las 30 profesiones emergentes principales 2026-2030 (ampliado de 10)

El orden es una estimación del autor (demanda, perspectivas, estabilidad a 5 años), no una medición:

| # | Profesión |
|---|---|
| 1 | Investigador en seguridad / alineación de IA (AI Safety / Alignment Researcher) |
| 2 | Arquitecto de agentes de IA (AI Agent Architect) |
| 3 | Cirujano aumentado con IA (AI-Augmented Surgeon) |
| 4 | Ingeniero de aplicaciones de IA (AI Application Engineer) |
| 5 | Especialista en cardiología con IA (AI Cardiology Specialist) |
| 6 | Ingeniero de tecnología legal con IA (AI Legal Tech Engineer) |
| 7 | Cazador de amenazas de ciberseguridad con IA (AI Cybersecurity Hunter) |
| 8 | Investigador cuantitativo con IA (AI Quant Researcher) |
| 9 | Consultor de estrategia de IA (AI Strategy Consultant) |
| 10 | Ingeniero de calidad / evaluación de IA (AI Quality / Eval Engineer) |
| 11 | Interpretabilidad mecanicista de IA (AI Mechanistic Interpretability) |
| 12 | Diseñador de chips de IA (AI Chip Designer) |
| 13 | Descubrimiento de fármacos con IA (AI Drug Discovery) |
| 14 | Responsable de ética de IA (AI Ethics Officer) |
| 15 | Ingeniero de cumplimiento con IA (banca) (AI Compliance Engineer) |
| 16 | Desarrollador de IA de voz (Voice AI Developer) |
| 17 | IA para clima / ESG (AI Climate / ESG) |
| 18 | Operador de robots humanoides (Humanoid Robot Operator) |
| 19 | Diseñador educativo de IA (AI Education Designer) |
| 20 | Diagnóstico médico con IA (AI Healthcare Diagnostic) |
| 21 | Especialista en adopción de IA (AI Adoption Specialist) |
| 22 | Ingeniero de optimización de costos de IA (AI Cost Optimization Engineer) |
| 23 | Sistemas de trading con IA (AI Trading Systems) |
| 24 | Arquitecto de cadena de suministro con IA (AI Supply Chain Architect) |
| 25 | Desarrollador de apps para lentes inteligentes (Smart Glasses App Developer) |
| 26 | Arquitecto de sistemas de tutoría con IA (AI Tutor System Architect) |
| 27 | Especialista en patentes de IA (AI Patent Specialist) |
| 28 | Especialista en litigios de IA (AI Litigation Specialist) |
| 29 | Ajustador de seguros de IA (reclamaciones por IA) (AI Insurance Adjuster) |
| 30 | Ingeniero constitucional de IA (AI Constitutional Engineer) |

---

## <a id="salary-2030"></a>💰 Referencias salariales 2030 (por región)

El pronóstico salarial por región se eliminó: no hay forma de verificarlo. Cuando planees tu carrera, apóyate en datos actuales de tu país y tu ciudad (estadísticas laborales oficiales, vacantes), y en tus propias conversaciones con personas del sector.

---

## 🎬 Consejos prácticos finales (V2.0)

Después de 200 profesiones y un pronóstico:

### 5 modelos mentales para orientarte

1. **No elijas un "empleo del futuro"; elige un conjunto de habilidades a largo plazo.** La Sección H muestra cómo evolucionan las habilidades año por año. Un empleo es la forma en que aplicas tus habilidades ahora mismo. Las habilidades se llevan contigo.

2. **En 2030 la especialidad le gana a lo general.** El "ingeniero de IA" genérico se vuelve commodity. Un ingeniero de IA con especialidad en salud, derecho o finanzas tiene una ventaja difícil de copiar.

3. **Lo híbrido le gana a lo puro.** Una profesión pura (médico, abogado, contador) está bajo presión. Una híbrida (médico + IA, abogado + IA) = una prima por productividad + más protección.

4. **La confianza crece despacio, por eso las relaciones están protegidas.** La IA no va a cerrar un acuerdo de \$10M. No va a tratar un caso complejo de salud mental. Las relaciones siguen siendo humanas.

5. **El arbitraje geográfico existe, pero se espera que se reduzca.** El pago por trabajo remoto depende de la región y del cliente; revisa las tarifas reales donde vives.

### Plantilla de plan de 90 días (actualizada para V2.0)

**Días 1-30: Mapea.**

- Lee esta guía completa
- Elige 5 profesiones candidatas
- Encuentra dónde se cruzan tu área y las herramientas de IA
- Investiga los sueldos en **tu propia** zona (con estadísticas laborales oficiales, vacantes actuales y encuestas salariales)

**Días 31-60: Valida.**

- Conecta con 5 personas de cada profesión (LinkedIn)
- Haz 1 proyecto de portafolio en tu profesión principal
- Aprende 1 habilidad clave (de la Sección H, según tu horizonte de tiempo)

**Días 61-90: Comprométete.**

- Elige 1 profesión + 1 plan B
- Planea una ruta de aprendizaje de 12 meses
- Agenda una reevaluación en 6 meses

---

## 📚 Fuentes V2.0 (además de las de v1.0)

- **WEF Future of Jobs Report** (informe del Foro Económico Mundial sobre el futuro del empleo): https://www.weforum.org
- **McKinsey Global Institute, Future of Work** (el futuro del trabajo): https://www.mckinsey.com
- **Anthropic Economic Index** (índice económico de Anthropic): https://www.anthropic.com/economic-index
- **OpenAI Economic Impacts** (impactos económicos): https://openai.com/research
- **AI Now Institute**: https://ainowinstitute.org
- **Stanford AI Index**: https://aiindex.stanford.edu

Son puntos de partida para que verifiques por tu cuenta. Ningún número de estas fuentes se trasladó a esta guía.

---

## 🔗 Lecciones relacionadas (V2.0)

| Tema | Lecciones del curso |
|-------|-------------|
| Investigación / ciencia con IA (A7), el futuro del trabajo | [El futuro de la IA 2027–2030](108-ai-roadmap-2027-2030.md) |
| IA en salud (A8, B6), IA en finanzas (A10) | [Ética y seguridad en IA](61b-ai-ethics-safety.md), [Regulación y cumplimiento en IA](61c-ai-regulation-compliance.md) |
| Arquetipos del futuro (Sección J) | [La historia de la IA](00-what-is-ai.md), [Elige tu camino](49b-choose-your-path.md) |

---

**Versión:** 2.0, actualizada en octubre de 2026

**200 profesiones en total** (100 NUEVAS + 100 HÍBRIDAS)

**25 empleos que desaparecen** (ampliado de 10)

**50 habilidades** (ampliado de 25)

**Pronóstico:** año por año para 2027-2030, escenarios sin números

🔥 **La V1.0 es un mapa del bosque de hoy. La V2.0 es el mapa más el pronóstico del clima a 5 años. Elige tu lugar en el nuevo mapa.**
