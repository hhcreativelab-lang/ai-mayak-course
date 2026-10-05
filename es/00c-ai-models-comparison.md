# Claude vs ChatGPT vs Gemini: comparación de modelos de IA

**Tiempo:** unos 30 min de lectura + 25 min de práctica

> *Imagina que eliges un vehículo para distintos trabajos. Un Ferrari para la pista de carreras, una Land Rover para el campo, un Toyota Corolla para moverte todos los días por la ciudad. No existe "el mejor auto y punto", solo el mejor auto para un camino concreto. Los modelos de IA funcionan exactamente igual. Esta lección es tu mapa de los caminos y los autos del mercado de la IA. Los modelos y precios concretos son a octubre de 2026. Cambian rápido, así que revisa la lista actual en la página [Lo vigente](https://aimayak.com/now/).*

---

## Lo esencial

Al terminar esta lección vas a entender:
- Qué grandes modelos de IA existen y quién los hace
- En qué es fuerte cada modelo y en qué se queda corto
- Cuándo elegir Claude, ChatGPT, Gemini, un modelo abierto o Mistral
- Por qué este curso usa Claude Code en las lecciones donde construimos, y por qué es una elección pensada, no fanatismo

---

## Conceptos clave

**LLM** (Large Language Model, modelo de lenguaje grande): un sistema de IA entrenado con una cantidad enorme de texto. Puede entender el lenguaje y generar (crear) respuestas.

**Benchmark** (una prueba de rendimiento): una prueba estandarizada para comparar modelos. Piénsalo como el examen de admisión de la IA: MMLU, HumanEval, MATH, GSM8K.

**Ventana de contexto**: la cantidad máxima de texto que una IA puede ver y tener presente a la vez. Más o menos: si la ventana es de 200K tokens, el modelo puede tener en memoria un libro de 150,000 palabras.

**Token** (la unidad de texto más pequeña para una IA): más o menos 0.75 de una palabra en inglés. "Hello" = 1 token, "Hello world" = 2 tokens. En español y en otros idiomas una palabra suele gastar más tokens, y cada modelo cuenta un poco distinto. Cada token cuesta dinero cuando trabajas a través de la API (Application Programming Interface: el canal que usan los programas para comunicarse con el modelo).

**Open source / pesos abiertos**: un modelo cuyos pesos están publicados, así que puedes descargarlo y correrlo en tu propia máquina. Los términos de la licencia cambian de un modelo a otro.

**Multimodal** (trabaja con varios tipos de datos): un modelo que maneja no solo texto, sino también imágenes, sonido y video.

**Inferencia**: el momento en que el modelo genera una respuesta a tu pregunta. El proveedor gasta poder de cómputo; tú pagas los tokens.

**Parámetros** (también llamados "pesos" del modelo): los números dentro de la red neuronal del modelo. Por regla general, cuantos más hay, más capaz es el modelo, pero también más pesado de correr. Se cuentan en miles de millones (en inglés, billions, de ahí la B): 8B, 70B, 405B.

---

## Teoría

### 1. ¿Para qué comparar modelos?

Mucha gente empieza con la IA así: oye hablar de ChatGPT y usa solo eso. O abre Claude y nunca mira nada más. Es como usar solo un desarmador y nunca tomar el martillo, solo porque el desarmador fue la primera herramienta que agarraste.

Tres razones para conocer todo el mercado:

**Tareas distintas, fortalezas distintas.** Trabajar con un documento legal enorme de 500 páginas pide un modelo con una ventana de contexto grande (a octubre de 2026, hay una ventana de alrededor de 1 millón de tokens en Claude Fable 5.1, Opus 5.5 y Sonnet 5.5, en varios modelos de Gemini y en los modelos GPT-6; revisa la documentación de cada proveedor para las cifras exactas). Escribir código de calidad: Claude y otros agentes de programación. Trabajar con imágenes y voz en una sola solicitud: ChatGPT o Gemini. Privacidad total sin nube: un modelo abierto que corre de forma local en tu propia computadora.

**Los precios varían de 10 a 100 veces.** A octubre de 2026, un millón de tokens de entrada (el texto que le envías al modelo) cuesta $0.10 USD en GPT-6 Luna y $10 USD en GPT-6 Astra. Entre los modelos de Claude, un millón de tokens de entrada va de $1 USD en Haiku 4.5 a $10 USD en Fable 5.1. Para tareas rutinarias, eso es una diferencia enorme en el presupuesto.

**El mercado cambia rápido.** El modelo que era el mejor hace seis meses puede haber perdido su lugar frente a uno nuevo. Cuando entiendes el panorama (el mapa general del mercado), eliges con información en lugar de solo seguir la moda.

🎨 **Imagínalo así:** conocer todo el mercado de modelos de IA es como tener un mapa de tu ciudad. Quizá siempre manejes por la misma ruta. Pero el mapa te muestra el desvío para evitar el tráfico, la vía hecha para camiones, la ciclovía.

---

### 2. Las principales empresas y sus modelos, a octubre de 2026

| Empresa | Qué ofrecen ahora (octubre de 2026) | Tipo | Fundación |
|----------|--------------------------------|-----|----------|
| Anthropic (EE. UU.) | Claude Fable 5.1, Opus 5.5, Sonnet 5.5, Haiku 4.5 | Cerrado | 2021 |
| OpenAI (EE. UU.) | La familia GPT-6 (Astra, Sol, Luna); el chat normal de ChatGPT funciona con modelos de la familia GPT-5.6 | Cerrado | 2015 |
| Google / DeepMind (EE. UU./Reino Unido) | Gemini 3.x (Flash, Pro, Deep Think); Gemini 4 se anunció el 30 de septiembre de 2026 y todavía no está disponible al público | Cerrado | 1998 / 2010 |
| Meta (EE. UU.) | Muse Spark (desde abril de 2026, es la base del asistente Meta AI); los modelos Llama publicados antes siguen disponibles | Muse Spark es cerrado, Llama tiene pesos abiertos | 2004 |
| Mistral AI (Francia) | El asistente Mistral Vibe (antes Le Chat) y modelos a través de la API | Algunos modelos tienen pesos abiertos | 2023 |
| SpaceXAI (antes xAI, EE. UU.) | Grok 4.x | Cerrado | 2023 |
| Alibaba (China) | La familia Qwen | Algunos modelos tienen pesos abiertos | 1999 |
| DeepSeek (China) | DeepSeek V4 (V4.1-Flash salió en septiembre de 2026) | Pesos abiertos (licencia MIT) | 2023 |

La diferencia entre "cerrado" y "abierto":

- **Modelo cerrado**: lo usas a través de una API o una app (chatgpt.com, claude.ai). Pagas por el uso. El modelo en sí nunca está en tu máquina; corre en los servidores de la empresa.
- **Modelo abierto** (pesos abiertos): lo descargas y lo corres tú, en tu propia computadora o servidor. El modelo en sí es gratis. Tus datos no van a ningún lado. Pero necesitas el equipo.

---

### 3. Claude (Anthropic): una mirada más de cerca

Anthropic la fundaron en 2021 exempleados de OpenAI, entre ellos Dario Amodei y Daniela Amodei. La empresa se enfoca en la seguridad de la IA; es uno de sus principios centrales.

**La línea de Claude (a octubre de 2026):**

| Modelo | Velocidad | Potencia | Precio por 1M de tokens, entrada / salida (API) | Cuándo usarlo |
|--------|----------|----------|-------------------------------------------|--------------------|
| Claude Haiku 4.5 | La más rápida | Básica | $1 / $5 USD | Tareas sencillas, respuestas cortas, procesamiento de grandes volúmenes |
| Claude Sonnet 5.5 | Rápida | Alta | $2 / $10 USD | Tareas diarias, ediciones, documentos, hojas de cálculo |
| Claude Opus 5.5 | Media | Muy alta | $4 / $20 USD | El modelo potente principal: trabajo largo con código y documentos; el predeterminado en Claude Code |
| Claude Fable 5.1 | Más lenta | Máxima | $10 / $50 USD | Las tareas de varios pasos más difíciles; en el plan Pro se paga aparte, con créditos de uso (usage credits, créditos adicionales a tu plan), y en Max entra en el límite del plan |

Los precios vigentes y la lista de modelos están en la página [Lo vigente](https://aimayak.com/now/). También hay un modelo solo por invitación (Mythos 5.1, Project Glasswing); no está disponible para usuarios comunes.

**Ventana de contexto:** a octubre de 2026, Fable 5.1, Opus 5.5 y Sonnet 5.5 tienen 1 millón de tokens (unas 555,000 palabras en inglés según la estimación de Anthropic, más o menos toda la trilogía de El Señor de los Anillos y algo más); Haiku 4.5 tiene 200K tokens.

**Fortalezas de Claude** (así las describe la propia Anthropic; pruébalas con tus tareas):

- Seguir instrucciones: está hecho para tareas complejas de varios pasos con requisitos precisos
- Código: una de sus áreas más fuertes. Revisa los benchmarks independientes actuales (por ejemplo, SWE-bench), porque las posiciones cambian cada pocos meses
- Documentos largos: analiza, resume y encuentra contradicciones en contratos e informes
- Honestidad: Anthropic le da mucho peso. El modelo intenta admitir cuando no sabe algo, pero las alucinaciones (la IA inventando cosas con seguridad) siguen pasando, así que revisa dos veces todo lo importante
- Constitutional AI: el enfoque de seguridad de Anthropic. El modelo se entrena con una "constitución" de principios, no solo con retroalimentación humana

**Debilidades:**

- Sin búsqueda ni herramientas conectadas, no tiene datos en tiempo real: el modelo tiene una fecha de corte y no sabe nada posterior a esa fecha (en el chat hay búsqueda web)
- Generar imágenes no es el fuerte de Claude: para imágenes, la gente suele usar servicios aparte, como ChatGPT Images o Nano Banana en Gemini
- Multimodalidad limitada: a través de la API recibe texto e imágenes; no procesa audio ni video directamente

**Claude Code** es el agente de Anthropic para quienes construyen software y automatizaciones. En este curso aparece casi al final: en el módulo de la primera creación sin código y en la biblioteca. No es solo Claude en un navegador. Es un agente que puede leer archivos, escribir código, ejecutar comandos en la terminal (la ventana de texto donde escribes órdenes al sistema operativo de tu computadora) y manejar proyectos. Está incluido en los planes de pago (Pro y superiores).

🎨 **Imagínalo así:** Claude es como un colega con experiencia, muy inteligente y reflexivo. No se apura, piensa antes de responder, intenta admitir cuando no sabe algo. También se equivoca, así que lo importante se revisa, y a veces es más lento de lo que quisieras.

---

### 4. ChatGPT y los modelos de OpenAI

OpenAI hace ChatGPT, una de las apps de IA más usadas del mundo.

**Modelos de OpenAI a octubre de 2026:**

| Qué | Qué tiene de especial | Cuándo usarlo |
|-----|-------------|-------------------|
| GPT-6 Astra | El modelo de más alto nivel (anunciado el 3 de septiembre de 2026) | Las tareas más difíciles |
| GPT-6.1 Sol, GPT-6 Sol | Los modelos principales de los modos Work y Codex | Tareas de trabajo, código, documentos |
| GPT-6 Luna | Rápido y barato | Preguntas diarias, procesamiento de grandes volúmenes |
| La familia GPT-5.6 (Sol, Terra, Luna) | Los modelos del chat normal de ChatGPT | Conversaciones diarias |

Los nombres y la línea cambian cada pocos meses: por ejemplo, GPT-5.5 sale de ChatGPT el 14 de octubre de 2026. La lista actual está en la página [Lo vigente](https://aimayak.com/now/).

**Qué cambió respecto a generaciones anteriores.** Los modelos de "razonamiento" separados de la serie o, que antes tenías que elegir a mano, ahora están integrados en la línea principal: las preguntas difíciles las maneja un modo de razonamiento. Ese modo "piensa en voz alta" antes de responder. Toma más tiempo y es más preciso en problemas de lógica difíciles, pero para preguntas sencillas es demasiado y cuesta más.

**El ecosistema de OpenAI:**
- ChatGPT: la app para el público general, con los planes Free, Go ($8 USD), Plus ($20 USD), Pro (desde $100 USD) y Business; precios mensuales a octubre de 2026
- Work: un modo de agente para tareas largas (documentos, hojas de cálculo, presentaciones); comparte límites con Codex
- Codex: el producto para desarrollo de software: agentes en segundo plano, revisión de cambios
- La generación de imágenes está integrada en ChatGPT (ChatGPT Images); los modelos anteriores DALL-E 2 y 3 se apagaron en la API el 12 de mayo de 2026
- Whisper: voz a texto de código abierto
- Cerrados: la app Sora (26 de abril de 2026), la API de Sora (24 de septiembre de 2026), la Assistants API (26 de agosto de 2026)

**Navegación:** ChatGPT puede buscar en la web, lo cual sirve cuando necesitas información reciente.

**Fortalezas de ChatGPT:**
- Un amplio ecosistema de funciones e integraciones
- Generación de imágenes integrada, sin necesidad de un servicio aparte
- Voz nativa: conversaciones habladas de verdad
- Búsqueda web dentro del chat
- Una base de usuarios enorme: muchos tutoriales, casos de estudio y ayuda de la comunidad

**Debilidades:**
- Las funciones dependen de tu plan y de tu región, y los nombres de los modelos cambian seguido
- Los modelos de más alto nivel cuestan mucho más que los ligeros (hasta 100 veces más a través de la API)
- El modo de razonamiento es más lento, así que hay que esperar

🎨 **Imagínalo así:** ChatGPT es como un smartphone de gama alta con mil apps. Hace de todo y tiene un ecosistema enorme, pero una herramienta especializada a veces le gana en su propio nicho.

---

### 5. Gemini (Google / DeepMind): una mirada más de cerca

Google invierte muchísimo en IA: tiene el laboratorio Google DeepMind (los creadores de AlphaGo y AlphaFold; en 2023 se le unió el equipo de Google Brain) y sus propios chips para IA, las TPU (Tensor Processing Units).

**La línea de Gemini a octubre de 2026:**

| Qué | Qué tiene de especial |
|-----|-------------|
| Gemini 3.6 Flash | Un modelo rápido para las tareas diarias, disponible gratis (salió el 21 de julio de 2026) |
| Gemini 3.1 Pro | El modelo de más alto nivel; limitado en Free |
| Deep Think | Un modo de razonamiento profundo, en el plan Ultra |
| Gemini 4 (Argon) | Anunciado el 30 de septiembre de 2026; todavía no está disponible al público |

Planes en Estados Unidos (a octubre de 2026): Free, Google AI Plus ($4.99 USD), Google AI Pro ($19.99 USD), Google AI Ultra ($99.99 o $199.99 USD al mes). Fuera de Estados Unidos, los precios se fijan en moneda local. Los precios y versiones vigentes están en la página [Lo vigente](https://aimayak.com/now/).

**Ventana de contexto.** Varios modelos de Gemini tienen una ventana de 1 millón de tokens (revisa la documentación del modelo para las cifras exactas). Antes eso distinguía a Gemini, pero a octubre de 2026, Claude Fable 5.1, Opus 5.5 y Sonnet 5.5 y los modelos GPT-6 también tienen una ventana de alrededor de 1M. Para darte una idea: 1 millón de tokens son más o menos de 555,000 a 750,000 palabras en inglés, o de 5 a 10 libros de largo promedio. Puedes cargar todo el código fuente de un proyecto grande y analizarlo completo.

**La multimodalidad de Gemini:**
- Texto: sí
- Imágenes: sí
- Video: sí (por la API, Claude y GPT-6 solo reciben texto e imágenes)
- Audio: sí
- Código: sí

En amplitud de multimodalidad, Gemini es de los más fuertes (recibir video como entrada es lo que lo distingue).

**Integración con Google Workspace:** Gemini está integrado en Gmail, Google Docs, Google Sheets y Google Meet. Si tu empresa trabaja con Google Workspace, es una ventaja real.

**Integración con la Búsqueda de Google:** a través de Google AI Studio y dentro de los productos de Google, Gemini tiene acceso a datos recientes de la búsqueda.

**Un poco de historia:** el asistente de Google primero se llamó Bard; en febrero de 2024 pasó a llamarse Gemini. Para comparar su calidad con Claude y GPT, mira las clasificaciones independientes actuales y prueba con tus propias tareas: las posiciones cambian con cada lanzamiento.

**Los cambios de nombre de 2026:** desde el 16 de julio de 2026, NotebookLM se llama Gemini Notebook. Y el 30 de septiembre de 2026 Google anunció que las Skills van a reemplazar a los Gems (conjuntos de instrucciones guardados); los Gems personales deberían pasarse de forma automática en noviembre de 2026.

**Fortalezas de Gemini:**
- Una ventana de contexto grande, de hasta 1 millón de tokens
- Recibe texto, imágenes, video, audio y PDF como entrada
- Integración con Google Workspace
- Acceso a la Búsqueda de Google
- Modelos Flash de bajo costo y un nivel gratuito en la API

**Debilidades:**
- Los precios y las funciones dependen de tu país: algunas funciones no están disponibles en todos lados
- El modelo de más alto nivel está limitado en el plan gratuito, y Deep Think solo está en Ultra
- Los nombres de productos y planes cambian seguido, así que revisa las condiciones vigentes

🎨 **Imagínalo así:** Gemini es como un empleado de Google que se sabe de memoria todos los productos de la empresa y trabaja con texto, imágenes, video y sonido. Le sirve más a quien ya vive en los servicios de Google.

---

### 6. Modelos abiertos: Llama (Meta) y otros

Meta es la empresa dueña de Facebook, Instagram y WhatsApp. En 2023-2024 publicó los modelos Llama con pesos abiertos, y con eso se volvió posible correr modelos potentes en tu propio equipo.

**¿Por qué Meta publicó modelos abiertos?**

Mark Zuckerberg lo explicó en una carta abierta en julio de 2024. Meta no vende acceso a modelos de IA, así que publicarlos de forma abierta no le quita ingresos. A un modelo abierto lo mejora toda la comunidad, y se vuelve un estándar compartido. Y la propia Meta no quiere depender de las plataformas cerradas de sus competidores.

**Una actualización importante de 2026.** En abril de 2026, Meta presentó un modelo llamado Muse Spark, y el asistente Meta AI ahora funciona con él y no con Llama. Los pesos de Muse Spark no están publicados: se usa a través de los productos de Meta, algunos socios lo reciben por una API, y sobre las versiones futuras Meta solo dice que espera publicarlas de forma abierta. Los modelos Llama publicados antes todavía se pueden descargar. Hoy otras empresas también publican pesos abiertos: DeepSeek (V4 con licencia MIT), Alibaba (los modelos Qwen), Mistral (algunos modelos). Los principios de abajo sirven para cualquier modelo abierto; en la tabla, Llama es solo un ejemplo de tamaños de modelo.

**Ejemplos de tamaño (la familia Llama 3.x):**

| Modelo | Parámetros | Tamaño del archivo en Ollama | Dónde corre |
|--------|-----------|--------------------------|---------|
| Llama 3.1 8B | 8 mil millones | 4.9 GB | Una computadora moderna común |
| Llama 3.3 70B | 70 mil millones | 43 GB | Una estación de trabajo potente, con mucha memoria |
| Llama 3.1 405B | 405 mil millones | 243 GB | Un servidor. Cuando salió, en julio de 2024, Meta lo llamó el primer modelo abierto al nivel de los mejores cerrados |

El modelo completo se carga en la memoria, así que tu computadora necesita más memoria libre que lo que pesa el archivo.

**Qué significa "pesos abiertos":**
- Descargas los pesos del modelo (sus parámetros numéricos): un archivo grande, desde un par de gigabytes en los modelos pequeños hasta más de 240 GB en los más grandes
- Lo corres de forma local con un software especial
- Tus datos no van a ningún lado; todo se queda en tu computadora
- Puedes hacerle fine-tuning (ajuste fino, seguir entrenándolo) con tus propios datos
- El modelo en sí es gratis, pero la licencia puede traer restricciones: lee los términos

**Ollama** es una de las herramientas más populares para correr modelos abiertos. Correr modelos en tu propia computadora es gratis (los planes de pago son solo para funciones en la nube). Funciona en Mac, Windows y Linux. La instalación toma unos minutos.

**Cuándo elegir un modelo abierto (Llama u otro):**

- Datos que no pueden ir a la nube (expedientes médicos, documentos legales, información financiera de clientes)
- Quieres cero costos de API con grandes volúmenes
- Quieres hacerle fine-tuning a un modelo con datos especializados (por ejemplo, los documentos de tu empresa)
- Necesitas trabajar sin conexión (sin internet)

💡 Si trabajas en salud, derecho o finanzas, primero van las reglas de tu empleador o de tu consultorio o despacho para los datos de clientes, y la ley de protección de datos de tu país (en Estados Unidos, por ejemplo, los expedientes de pacientes están cubiertos por HIPAA). Pregunta antes de poner ese tipo de datos en cualquier herramienta de IA, local o no.

**Fortalezas de los modelos abiertos:**
- Gratis cuando los corres tú
- Privacidad total: tus datos nunca salen de tu computadora
- Puedes hacerles fine-tuning
- No dependes de una API externa

**Debilidades:**
- Necesitas memoria: más memoria libre que el tamaño del archivo del modelo (unos 5 GB para la versión 8B, 43 GB para la 70B)
- Un modelo que puedes correr en una computadora de casa suele quedarse atrás de los mejores modelos cerrados en tareas que exigen precisión
- Muchos modelos abiertos trabajan solo con texto; solo algunas versiones entienden imágenes
- Requiere configuración técnica

🎨 **Imagínalo así:** un modelo abierto es como Linux: gratis, potente, control total, pero necesitas conocimientos técnicos. Claude, ChatGPT y Gemini son como macOS: pagas por comodidad, velocidad y calidad listas desde el principio.

---

### 7. Mistral (Mistral AI): la alternativa europea

Mistral AI se fundó en 2023 en Francia, por tres investigadores de Google DeepMind y Meta AI. La empresa levantó una de las primeras rondas de inversión más grandes de Europa: 105 millones de euros.

**Lo que ofrece Mistral a octubre de 2026:**

- **Mistral Vibe** (antes Le Chat; cambió de nombre el 12 de agosto de 2026, con la misma dirección y cuenta): un asistente con tres modos: Vibe Chat (chat normal), Vibe Work (investigación, documentos, correos) y Vibe Code (código). Planes: Free, Pro ($14.99 USD al mes), Team ($24.99 USD por usuario), precios a octubre de 2026.
- **Modelos a través de la API** para desarrolladores, algunos con pesos abiertos. Mistral no dice en sus páginas de precios qué modelos corren dentro de Vibe; mira el sitio de la empresa para la lista de modelos y licencias.
- Históricamente conocida por los modelos Mistral Large, Mixtral y Codestral (Codestral se especializa en código).

**Mixture of Experts** (mezcla de expertos): una arquitectura que Mistral popularizó con su modelo Mixtral 8x7B. En lugar de una sola red neuronal grande, hay varios "expertos" especializados. Para cada solicitud, solo se activan algunos (en Mixtral, 2 de 8). La idea: una calidad más cercana a la de un modelo grande con un gasto de recursos más cercano al de uno pequeño. Hoy muchos fabricantes de modelos usan esta idea.

**Por qué importa Mistral:**

**Cumplimiento del GDPR** (Reglamento General de Protección de Datos, la ley de protección de datos de la UE): la norma limita pasar datos personales fuera de la UE sin las garantías adecuadas. Mistral, una empresa francesa, guarda los datos en la UE de forma predeterminada, así que si trabajas con grandes empresas europeas, muchas veces es más fácil que Mistral pase su revisión. Pero "compatible con el GDPR" no quiere decir "seguro de entrada": lee las condiciones de procesamiento de datos. Por ejemplo, en el plan gratuito de Vibe tus datos se usan para entrenar modelos de forma predeterminada; puedes desactivarlo en la configuración de privacidad.

**Fortalezas de Mistral:**
- Precio: el plan Pro cuesta $14.99 USD al mes, frente a $20 USD de Claude Pro y ChatGPT Plus (octubre de 2026)
- Una empresa europea: los datos se guardan en la UE de forma predeterminada
- Algunos modelos tienen pesos abiertos, así que puedes correrlos de forma local
- Idiomas europeos: la empresa describe su modelo principal como fluido de forma nativa en inglés, francés, español, alemán e italiano
- Un modo para programar (Vibe Code)

**Debilidades:**
- En el plan gratuito, los mensajes y las búsquedas web están limitados
- En la clasificación independiente LMArena, los modelos de Mistral no están entre los diez primeros a octubre de 2026: pruébalos con tus propios ejemplos

🎨 **Imagínalo así:** Mistral es como Airbus: la opción europea junto a los fabricantes estadounidenses. Se elige cuando importa que el proveedor y los datos estén en Europa.

---

### 8. Otros jugadores que vale la pena conocer

**Grok (SpaceXAI, antes xAI):** en febrero de 2026, SpaceX compró xAI, y la empresa ahora se llama SpaceXAI. La línea actual es Grok 4.x. Busca en la web y en X en tiempo real, maneja voz y crea imágenes y video. Puedes empezar gratis en grok.com; los precios de los planes de pago están en la página [Lo vigente](https://aimayak.com/now/).

**Qwen (Alibaba Cloud):** la familia de modelos de Alibaba. Las versiones abiertas se publican con la licencia libre Apache 2.0 y, según sus desarrolladores, admiten más de cien idiomas. Los modelos se hacen en China, así que mucha gente los considera para trabajar en chino y para los mercados de Asia. Salen versiones nuevas varias veces al año; revisa el sitio para la actual.

**DeepSeek (China):** se hizo muy conocida en enero de 2025, cuando publicó su modelo de razonamiento R1 con pesos abiertos. La línea actual es DeepSeek V4 (V4.1-Flash salió en septiembre de 2026), con pesos publicados bajo licencia MIT. La privacidad de los datos sigue siendo una cuestión importante: según la política de privacidad del servicio, los datos se guardan y procesan en la República Popular China, así que no pegues datos de clientes en el chat. Para excluirte del entrenamiento con tus datos, envía una solicitud a privacy@deepseek.com.

**Meta AI** funciona con el modelo Muse Spark y está integrado en las apps de Meta (WhatsApp, Instagram y otras). **Perplexity** es un buscador que da respuestas con enlaces a sus fuentes; usa modelos de distintas empresas. **Microsoft Copilot** es el asistente de Microsoft: el Copilot Pro de pago ya no se vende, y lo reemplazó el plan Microsoft 365 Premium ($19.99 USD al mes a octubre de 2026). Los detalles de cada uno están en las páginas de la sección [Herramientas](https://aimayak.com/tools/).

---

### 9. Tabla comparativa, a octubre de 2026

| Modelo | Empresa | Precio de API* | Ventana de contexto | Qué recibe como entrada | Pesos abiertos |
|--------|----------|-----------|----------------|-------------------|---------------|
| Claude Haiku 4.5 | Anthropic | $ | 200K | Texto + imágenes | No |
| Claude Sonnet 5.5 | Anthropic | $$ | 1M | Texto + imágenes | No |
| Claude Opus 5.5 | Anthropic | $$$ | 1M | Texto + imágenes | No |
| Claude Fable 5.1 | Anthropic | $$$$ | 1M | Texto + imágenes | No |
| GPT-6 Luna | OpenAI | $ | ver documentación | Texto + imágenes | No |
| GPT-6.1 Sol | OpenAI | $$ | ver documentación | Texto + imágenes | No |
| GPT-6 Astra | OpenAI | $$$$ | ver documentación | Texto + imágenes | No |
| Gemini 3.x Flash | Google | $ | hasta 1M (ver documentación) | Texto + imágenes + video + audio | No |
| Gemini 3.1 Pro | Google | $$ | hasta 1M (ver documentación) | Texto + imágenes + video + audio | No |
| DeepSeek V4.1-Flash | DeepSeek | $ | ver documentación | Texto + imágenes | Sí (MIT) |
| Llama 3.3 70B | Meta | Gratis\*\* | 128K | Solo texto | Sí |

\*Los precios son aproximados y se refieren a la API: $ = hasta $1 USD por millón de tokens de entrada, $$ = unos $2 USD, $$$ = unos $4 USD, $$$$ = $10 USD o más. Precios y versiones exactos: [Lo vigente](https://aimayak.com/now/).

\*\*Gratis = pesos abiertos, pero necesitas tu propio equipo para correr el modelo. A través de servicios que corren modelos abiertos en sus servidores y te dan acceso (Together.ai, Groq, Fireworks), pagas.

La tabla deja fuera a propósito las columnas "Código" y "Documentos" con calificaciones: las clasificaciones de calidad cambian con cada lanzamiento. Prueba un modelo con tus propias tareas y revisa benchmarks independientes.

---

### 10. Un árbol de decisión práctico: qué elegir y cuándo

Úsalo cada vez que surja la pregunta: "¿Qué modelo uso para esta tarea?"

```
TAREA → CONDICIÓN → BUENA OPCIÓN (a octubre de 2026)

Escribir código / construir un sistema → lo más importante es seguir instrucciones con precisión
  → Claude (Sonnet 5.5 u Opus 5.5) + Claude Code

Analizar un documento muy largo (más de 100 páginas, un libro, todo el código de un proyecto)
  → un modelo con ventana de alrededor de 1M de tokens: Claude Sonnet / Opus / Fable, Gemini o GPT-6

Trabajar con imágenes + voz + video en una sola solicitud
  → ChatGPT o Gemini

Los datos no pueden ir a la nube (médicos, legales, finanzas de clientes)
  → un modelo abierto (Llama, DeepSeek, Qwen, Mistral) corriendo localmente con Ollama

Necesitas velocidad + el menor costo para tareas rutinarias
  → Claude Haiku 4.5, los modelos rápidos Gemini Flash o GPT-6 Luna

Tu empresa opera en la UE, GDPR estricto
  → Mistral (revisa las condiciones de procesamiento de datos) o cualquier servicio que guarde los datos en la UE

Problemas difíciles de matemáticas / lógica / algoritmos
  → el modo de razonamiento de Claude o ChatGPT, o Gemini Deep Think

Empiezas desde cero y quieres probar gratis
  → claude.ai, chatgpt.com o gemini.google.com: los tres tienen plan gratuito

Quieres IA local sin depender de internet
  → Ollama + cualquier modelo abierto que quepa en tu computadora

Trabajas con datos de X/Twitter, necesitas información en tiempo real
  → Grok

Analizar el mercado chino / trabajar en chino
  → Qwen o DeepSeek
```

---

### 11. Un detalle importante: los precios cambian rápido

En los últimos años, el costo de las API de IA para modelos del mismo nivel de calidad bajó de forma notable. Las razones:

- La competencia entre empresas
- Más eficiencia en chips y algoritmos
- Los modelos abiertos empujan hacia abajo los precios de los cerrados

La conclusión: no memorices cifras concretas; van a quedar desactualizadas. Recuerda mejor el principio: revisa siempre los precios vigentes antes de lanzar un proyecto, en la página [Lo vigente](https://aimayak.com/now/) y en los sitios de los propios proveedores: Anthropic (claude.com/pricing), OpenAI, Google AI Studio.

---

### 12. Por qué este curso eligió Claude Code

En las lecciones donde construimos algo (el módulo de la primera creación sin código y la biblioteca), este curso usa Claude Code. Es una elección pensada, no fanatismo. Para los primeros módulos no lo necesitas: ahí basta con un chat normal.

**Razón 1: Calidad del código.** Claude está entre los modelos más fuertes para programar. Revisa los benchmarks independientes actuales (SWE-bench es una prueba en la que el modelo corrige errores reales de proyectos abiertos en GitHub); las posiciones cambian con cada lanzamiento.

**Razón 2: Una ventana de contexto grande.** Hasta 1M de tokens (a octubre de 2026) te permite cargar todo un proyecto en el contexto y trabajarlo como un todo. Eso es clave para construir sistemas reales.

**Razón 3: Claude Code como herramienta especializada.** No es solo un chat sobre una API. Es un agente conectado a la terminal, al sistema de archivos y a git (un sistema de control de versiones que guarda el historial de tus cambios). Otras empresas tienen sus propios agentes de programación (por ejemplo, Codex de OpenAI, Cursor, Devin Desktop), y las ideas de este curso se pueden llevar a ellos. Se eligió Claude Code porque es una herramienta cómoda para mostrar la práctica.

**Razón 4: Seguir instrucciones.** Los flujos de trabajo complejos (con agentes, reglas automáticas y habilidades guardadas) necesitan un modelo que realice instrucciones de varios pasos con precisión, sin desviarse. Claude lo hace bien.

**Lo que esto NO significa:**

- Claude no es el mejor en todo; ya lo viste en la tabla y en el árbol de decisión
- En el trabajo profesional real, vas a usar varios modelos
- Una estrategia con varios modelos es lo normal en proyectos serios: Claude para el código, Gemini para el video y el mundo de Google, ChatGPT para la voz y las imágenes, un modelo abierto para los datos privados

Entiende todo el panorama y conoce una herramienta a fondo: ese es el enfoque correcto.

---

## Práctica

### Ejercicio 1. Una prueba lado a lado (20 min)

1. Abre **claude.ai** (gratis). Si todavía no te registraste, vas a necesitar un correo y un número de teléfono para recibir un código de verificación por SMS
2. Abre **chatgpt.com** (gratis; para registrarte necesitas un correo), o usa Gemini u otro asistente de la sección [Herramientas](https://aimayak.com/tools/)
3. Dales a los dos el mismo prompt:

```
Explícame cómo funciona el interés compuesto con palabras sencillas,
con un ejemplo de $1,000 al 10% anual durante 10 años.
Sin fórmulas; usa una comparación de la vida diaria.
```

4. Compara las respuestas: ¿cuál es más clara? ¿Cuál está mejor organizada? Y revisa la exactitud: a los 10 años el total debería ser de unos $2,594 (multiplica $1,000 por 1.1 diez veces seguidas)

Para "cuál es más clara" no hay una respuesta correcta; es tu propia comparación práctica. El monto final, en cambio, sí se puede revisar, y es una buena costumbre.

---

### Ejercicio 2. Prueba la IA local (30 min, opcional)

1. Para este ejercicio necesitas una computadora; desde el celular no se puede. Entra a **ollama.com**, descarga e instala Ollama (correr modelos en tu propia computadora es gratis; funciona en Mac, Windows y Linux)
2. En Mac y Windows, después de instalar se abre una ventana de chat, y ahí mismo puedes elegir y descargar un modelo. La otra forma es abrir la terminal (una ventana para escribir comandos de texto) y ejecutar:

   ```bash
   ollama pull llama3.2
   ollama run llama3.2
   ```

3. Conversa con el modelo. Corre por completo en tu computadora: una vez descargado, no necesita internet ni clave de API (una clave de acceso)
4. Fíjate en la diferencia de velocidad y calidad comparado con claude.ai

llama3.2 es un modelo pequeño de Llama 3.2, con 3 mil millones de parámetros; el archivo ocupa unos 2 GB. Si ese modelo ya no está en el catálogo de Ollama, elige cualquier modelo pequeño del catálogo.

---

### Ejercicio 3. Reflexión (5 min)

Escribe tu respuesta a esto (en un cuaderno, o directamente en claude.ai):

> "Para el trabajo que hago como [tu puesto / área], ¿qué modelo de IA parece más útil, y por qué?"

Guarda tu respuesta. Al final del curso, va a ser interesante volver a leerla y ver si cambió tu punto de vista.

---

## Ideas clave

**No existe "la mejor IA", solo la mejor para una tarea concreta.** Igual que no existe el mejor auto y punto, solo el mejor para tu camino.

**Claude es una opción fuerte para código, documentos largos y seguir instrucciones con precisión.** Por eso el curso usa Claude Code en las lecciones donde construimos.

**Gemini es una opción fuerte para tareas multimodales y el mundo de Google.** Video y audio como entrada, integración con Workspace.

**ChatGPT es una opción fuerte para voz, imágenes y un ecosistema amplio.** Texto + imágenes + voz, de forma nativa.

**Un modelo abierto es la opción cuando los datos no deben salir de tu computadora.** Pesos abiertos, privacidad total, pero necesitas el equipo.

**Mistral le conviene a empresas europeas con requisitos del GDPR**, pero revisa de todos modos sus condiciones de procesamiento de datos.

**Los precios bajan rápido.** Revisa los precios vigentes antes de cada proyecto importante.

**Una estrategia con varios modelos es lo normal entre profesionales.** Conoce las herramientas y usa la mejor para cada trabajo.

---

## Glosario de la lección

| Término | Qué significa |
|--------|---------|
| LLM | Large Language Model (modelo de lenguaje grande) |
| API | Application Programming Interface: una forma de que los programas accedan a un servicio |
| Token | La unidad de texto más pequeña para una IA, más o menos 0.75 de una palabra en inglés |
| Ventana de contexto | La cantidad máxima de texto que un modelo puede ver a la vez |
| Benchmark | Una prueba de rendimiento estandarizada |
| Multimodal | Trabaja con varios tipos de datos (texto, fotos, audio, video) |
| Open source | Código fuente abierto y disponible gratis |
| Fine-tuning | Seguir entrenando un modelo con datos especializados |
| Inferencia | El proceso en el que un modelo genera una respuesta |
| Parámetros | Los números dentro de una red neuronal, contados en miles de millones (B) |
| Razonamiento | La capacidad de resolver un problema en varios pasos lógicos |
| GDPR | La ley europea que protege los datos personales |
| RAG | Retrieval-Augmented Generation: búsqueda + generación basada en una base de conocimiento |
| Constitutional AI | El enfoque de Anthropic: entrenar un modelo con un conjunto de principios (una "constitución") |
| Codebase | El conjunto completo del código fuente de un proyecto |
| Pesos | Los parámetros numéricos de una red neuronal entrenada |

---

## Próxima lección

**→ [Escribir con IA](67-ai-copywriting.md): la primera lección del módulo "IA para el trabajo diario: textos, correo, reuniones y traducción".**

Ya elegiste tus modelos. Ahora los ponemos a trabajar en tareas de todos los días: textos, correos, reuniones, presentaciones, traducción. Al presupuesto para suscripciones volvemos en la lección [Cuánto gastar en IA](00e-investment-roadmap.md), y a los agentes, en la lección [Qué es un agente de IA y por qué importa ahora](01-agentic-market.md), casi al final del curso.

---

*Comparación de modelos de IA | AI Mayak, actualizado en octubre de 2026*
