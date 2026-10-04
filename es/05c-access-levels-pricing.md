# Precios de Claude Code: ¿Free, Pro, Max, Team o API?

**Tiempo:** unos 25 min de lectura + 10 min para elegir un plan

---

## Lo esencial

Anthropic ofrece **5 niveles de acceso a Claude** (más la API, que va aparte). Cada nivel trae su propio conjunto de funciones, su propio precio y sus propios límites. Si eliges el equivocado, o pagas de más o chocas con el tope cada par de horas.

Lo más importante que debes entender desde el principio: **Claude Code no funciona con una cuenta gratuita.** Así que si te preguntas si Claude Code es gratis, la respuesta corta es no. Una cuenta gratuita te da el chat en claude.ai, en la app de escritorio y en tu celular. Para usar Claude en la terminal o en VS Code necesitas un plan de pago (como mínimo Pro) o una clave de API con cobro por token.

Esta lección es un mapa a octubre de 2026. Los precios y los límites cambian, así que siempre revisa las cifras vigentes en la página [Lo vigente](https://aimayak.com/es/now/) y en la página oficial de precios. Abajo: quién recibe qué por su dinero, qué plan le conviene a quién y cómo funcionan los pagos.

🎨 **Imagínalo así:** el acceso a la IA funciona como un plan de celular. Free es el plan básico para la llamada ocasional. Pro es el plan de todos los días con el que de verdad trabajas. Max es el plan premium para quienes lo usan mucho. Team es el plan familiar para un grupo. La API es un taxi con el taxímetro corriendo: pagas cada segundo del viaje. Enterprise es un jet privado con piloto bajo contrato.

---

## 🎯 Árbol de decisión: qué plan necesito

La pregunta clave no es "cuál plan es el más impresionante". Es "¿cuántas horas al día voy a trabajar de verdad con Claude?"

```
Quiero probar la IA por primera vez
  → Free ($0)

La uso todos los días de 1 a 3 horas y necesito Claude Code en la terminal
  → Pro ($20/mes con pago mensual, o $17/mes con pago anual = $200/año)

La uso de 6 a 8 horas al día (desarrollador / constructor)
  → Max 5x (desde $100/mes)

La uso intensamente más de 8 horas al día (tiempo completo en Claude Code)
  → Max 20x ($200/mes)

Tengo un equipo de 5 o más personas y necesitamos proyectos compartidos
  → Team Standard ($25/puesto con pago mensual, $20/puesto con pago anual)
  → Team Premium ($125/puesto con pago mensual, $100/puesto con pago anual; 5 veces el uso de Standard)

Industria regulada (salud/finanzas) o más de 100 usuarios
  → Enterprise ($20/puesto + uso de la API, a través de una llamada con ventas)

Estoy creando un programa, chatbot o Worker que llama a Claude desde código
  → API (una cuenta aparte y un cobro aparte, no Pro/Max)
```

**La opción por defecto para la mayoría de los constructores:** Pro ($20). Cubre la mayoría de las tareas. Pasa a Max cuando de verdad choques con el límite varias veces por semana.

🎨 **Imagínalo así:** una bici vs. una camioneta 4x4. Para ir a la tienda a unas cuadras, toma la bici. Para caminos de terracería, toma la camioneta. No compres una Land Cruiser para ir por un litro de leche.

---

## Conceptos clave

- **Plan (también llamado tier o nivel):** el nivel de tu suscripción a Claude. Decide qué modelos puedes usar, tu límite de mensajes y qué funciones tienes
- **Límite de uso:** cuánto puedes usar Claude en un periodo determinado. No es un número fijo de mensajes: las conversaciones largas, los archivos grandes y los modelos más pesados lo consumen más rápido
- **Claude Code:** un agente de IA para programar que funciona en la terminal, en VS Code, en la app de escritorio o en el navegador. Requiere un plan de pago (Pro, Max, Team, Enterprise) o una clave de API
- **Fable / Opus / Sonnet / Haiku:** cuatro familias de modelos. Haiku es rápido y barato, Sonnet es el equilibrio, Opus es más inteligente y es el predeterminado en las suscripciones, y Fable es el más potente y el más caro
- **Token:** una unidad de texto. Aproximadamente 4 caracteres, o 0.75 de una palabra, de texto en inglés. Un texto en inglés de 1,500 palabras ≈ 2,000 tokens
- **Prompt caching (caché de prompts):** Anthropic guarda en caché el contexto que se repite; leer de la caché cuesta el 10% del precio de entrada (todavía menos en algunos modelos)
- **Batch API:** un modo asíncrono. Envías solicitudes, Claude las procesa en un plazo de 24 horas y obtienes un 50% de descuento
- **Computer Use:** una función en research preview (versión de prueba temprana) en la que Claude controla tu computadora (mueve el cursor, escribe). En la app está disponible en Pro y Max
- **Console:** un panel de cuenta aparte en platform.claude.com (antes console.claude.com) donde administras las claves de API y el cobro de la API (no Pro/Max)

---

## Los planes en detalle

### Nivel 1: Claude Free ($0/mes)

**Qué obtienes:**

- claude.ai en el navegador, más las apps de escritorio y de celular
- Un límite de mensajes pequeño que depende de la demanda (el número exacto no es fijo)
- Los modelos Sonnet y Haiku (Opus no está incluido en Free)
- Artifacts, Skills, búsqueda web, creación de archivos, memoria
- Projects (proyectos): hasta 5
- **SIN Claude Code**
- La API es una cuenta aparte en la Console y no tiene nada que ver con Free

**Para quién es:**

- Un estudiante de bachillerato o universidad que prueba la IA por primera vez
- Un periodista que escribe un artículo a la semana con ayuda de la IA
- Cualquiera que quiera ver "cómo funciona esto" antes de pagar por algo

**Cuándo subir de plan:**

- Chocas seguido con el límite diario y quieres seguir trabajando
- Te das cuenta de que quieres trabajar en la terminal o en VS Code
- Necesitas más de cinco Projects o más uso

**Enlace:** [claude.ai](https://claude.ai) (el registro es gratis)

🎨 **Imagínalo así:** el camión urbano. El viaje es gratis, pero en hora pico vas de pie. Sirve para llegar a clases; no para ir al trabajo todos los días.

---

### Nivel 2: Claude Pro ($20/mes con pago mensual, o $17/mes con pago anual = $200/año)

Este es **el plan básico de trabajo**. La mayoría de la gente empieza aquí.

**Qué obtienes:**

- Más uso que en Free (según la página de precios: 5 veces más por sesión de 5 horas, más límites semanales)
- Opus 5.5 (el modelo predeterminado en Claude Code), Sonnet 5.5, Haiku 4.5; Fable 5.1 mediante créditos de uso
- **Claude Code** en la terminal, en VS Code, en la app de escritorio y en el navegador: la diferencia principal con Free
- Subir archivos en el chat (PDF, imágenes, documentos)
- Projects: carpetas con contexto persistente (conectas tu código y Claude lo recuerda)
- Artifacts: una vista previa de HTML/código directamente en el chat
- Claude Cowork, Research, Claude Design / Slides / Docs
- Computer Use (research preview, se activa en la configuración de la app)

**Ahorro:** el plan anual de $200/año sale en $17/mes (vs. $20 con pago mensual), cerca de 15% menos.

**Límites de Claude Code:**

- Los límites se cuentan por sesión de 5 horas y por semana; los números exactos dependen del modelo y de la demanda
- Para ver cuánto te queda: el comando `/usage` en Claude Code, o la página Usage en la configuración
- Los modelos más potentes (Opus, Fable) consumen el límite más rápido que Sonnet y Haiku. En las suscripciones, Fable funciona con créditos de uso

**⚠️ Nota importante sobre el tokenizador:** los modelos 4.7 y posteriores (incluidos Opus 5.5, Sonnet 5.5 y Fable 5.1) usan un tokenizador nuevo: el mismo texto ocupa cerca de 30% más tokens que en Sonnet 4.6 y anteriores. Vas a gastar tu límite más rápido de lo que sugiere la cantidad de texto.

**Para quién es:**

- Un desarrollador que escribe código de 2 a 4 horas al día
- Alguien de marketing de contenidos que escribe artículos y publicaciones
- Un fundador que trabaja solo y lleva sus proyectos
- Cualquiera que trabaje con IA de 1 a 3 horas al día

**Cuándo subir de plan:**

- Chocas con el límite de Opus varias veces por semana
- Trabajas en Claude Code más de 6 horas al día
- Ves el mensaje "Approaching limit" (te acercas al límite) más de una vez al día

**Enlace:** [claude.com/pricing](https://claude.com/pricing) o [claude.ai/upgrade](https://claude.ai/upgrade)

🎨 **Imagínalo así:** un sedán normal. Manejas cuando quieres, el pago mensual es fijo y un tanque de gasolina cubre tus rutas de todos los días. No está hecho para transporte de carga de larga distancia, pero resuelve el 95% de los viajes que vas a hacer.

---

### Nivel 3: Claude Max (desde $100/mes, dos niveles)

Max es para quienes trabajan con Claude **mucho**. Hay dos niveles: 5x y 20x el límite de Pro (precios a octubre de 2026).

#### Max 5x (desde $100/mes)

- 5 veces el límite de Pro por sesión de 5 horas
- Las mismas funciones que Pro
- Acceso anticipado a funciones nuevas
- Acceso prioritario en horas pico
- Límites de salida más altos

#### Max 20x ($200/mes)

- 20 veces el límite de Pro
- Las mismas funciones que Max 5x
- El límite de uso más alto de todos los planes individuales

**Para quién es:**

- Un desarrollador que pasa de 6 a 8 horas al día en Claude Code (Max 5x)
- Una agencia de IA que atiende a 5 o más clientes a la vez (Max 5x o 20x)
- Un constructor que trabaja intensamente más de 8 horas al día (Max 20x)
- Un fundador que trabaja solo y produce mucho contenido y código cada día

**La trampa (¿vale la pena Max?):**

- Es fácil cambiarse a Max solo "porque se ve genial y puedo"
- Sin unas 6 horas reales al día, el dinero no se recupera
- Max tiene sentido cuando chocas con el límite de Pro de forma regular
- Revisa tu uso real en Pro antes de subir de plan

**Enlace:** [claude.com/pricing](https://claude.com/pricing) o [claude.ai/upgrade](https://claude.ai/upgrade), el mismo lugar que Pro

🎨 **Imagínalo así:** un Tesla Plaid. Rápido, con mucha autonomía, te lleva a donde quieras cuando quieras. Pero si solo lo usas para ir al súper, estás pagando de más. Si lo compras para un trabajo real, se paga solo.

---

### Nivel 4: Claude Team (dos niveles: Standard y Premium)

Este es **el plan de equipo** para pequeñas empresas. En 2026, Anthropic dividió Team en dos niveles:

#### Team Standard

- **Mensual:** $25/puesto/mes
- **Anual:** $20/puesto/mes, un ahorro del 20%
- Todas las funciones de Claude, SSO, facturación centralizada

#### Team Premium

- **Mensual:** $125/puesto/mes
- **Anual:** $100/puesto/mes
- **5 veces más uso** que los puestos Standard
- Límites más altos en los modelos pesados

**Qué obtienes (en ambos):**

- Todo lo de Pro para cada usuario, incluido Claude Code
- **Proyectos compartidos:** varias personas trabajan con el mismo contexto
- Facturación centralizada: una sola factura para todo el equipo
- Controles de administrador: quién puede hacer qué
- Integración con SSO (inicio de sesión único)
- Analítica de uso del equipo: ves quién usó cuánto
- Espacios de trabajo separados para los miembros del equipo

**Lo que Team NO te da (eso ya es terreno de Enterprise):**

- Aprovisionamiento SCIM y registros de auditoría completos
- La Compliance API y periodos personalizados de retención de datos
- Preparación para HIPAA (la ley de privacidad de datos de salud de EE. UU.)

**Cuentas de ejemplo (Standard, con pago anual):**

- 5 puestos = $100/mes
- 10 puestos = $200/mes
- 50 puestos = $1,000/mes

**Para quién es:**

- Una startup de 5 a 50 personas (Standard para uso moderado, Premium si dependen mucho de Opus)
- Una pequeña agencia de IA con equipo
- Un negocio familiar donde 3 a 5 personas usan IA todos los días

**Enlace:** [claude.com/pricing](https://claude.com/pricing)

🎨 **Imagínalo así:** el estacionamiento de una oficina. Todos se estacionan ahí, hay una sola pluma de entrada y la cuenta es compartida. Práctico, pero se queda chico para una empresa grande (eso es Enterprise, con su propio edificio de estacionamiento).

---

### Nivel 5: Claude Enterprise (precio personalizado)

**Qué obtienes:**

- Aprovisionamiento SCIM
- Registros de auditoría completos
- Preparado para HIPAA (para el sector salud)
- Un DPA (Data Processing Agreement, acuerdo de procesamiento de datos) para el GDPR (el reglamento europeo de protección de datos)
- Lista de IP permitidas (IP allowlisting)
- Claude Security (beta)
- SSO avanzado + controles de administrador
- Límites de uso y acceso a modelos personalizados
- Un gerente de soporte dedicado

**Precio (a octubre de 2026):**

- **$20/puesto al mes, con pago anual, + uso de la API:** un híbrido de "puesto + consumo"
- El uso de la API se cobra aparte, con las tarifas oficiales de los modelos
- Lo típico son contratos anuales
- El precio final se negocia con el equipo de ventas

**Para quién es:**

- Empresas de más de 100 personas
- Industrias reguladas (salud, finanzas, legal)
- Empresas SaaS empresariales que integran Claude en su producto
- Contratos de gobierno y cuasi gubernamentales

**Cómo se compra:** a través del equipo de ventas de Anthropic (Contact Sales), no en el sitio de autoservicio

**Enlace:** [claude.com/pricing](https://claude.com/pricing) → Contact Sales

🎨 **Imagínalo así:** un jet privado con tripulación. Caro, totalmente a la medida, hecho para trabajos específicos. Comprarlo "por si acaso" no tiene sentido. Comprarlo cuando de verdad vuelas al extranjero por trabajo cada semana sí lo tiene.

---

### Nivel 6: Anthropic API (pagas lo que usas)

La API es **otra historia**. No es una suscripción mensual; es pago por uso.

**Qué es:**

- Acceso programático a los modelos mediante solicitudes HTTP
- No es una interfaz de chat sino **material de construcción** para tus propios programas
- La usas en código: Python, TypeScript, Go, cualquier lenguaje
- Pagas cada token que se procesa

**Importante:**

- La API **NO depende** de una suscripción Pro/Max. Es una cuenta aparte
- Puedes tener Pro para el chat y la API para tus propios programas al mismo tiempo
- La API se paga a través de la Console en platform.claude.com (un panel de cuenta aparte)

**Precios a octubre de 2026** (por millón de tokens, según la página oficial de precios de Anthropic; las cifras vigentes siempre están en la página [Lo vigente](https://aimayak.com/es/now/)):

#### Claude (Anthropic)

| Modelo | Entrada | Salida | Cuándo usarlo |
|---|---|---|---|
| Haiku 4.5 | $1.00 | $5.00 | Tareas simples: clasificación, traducción, respuestas cortas |
| Sonnet 5.5 | $2.00 | $10.00 | El equilibrio precio/calidad para la mayoría de las tareas, contexto de 1M |
| Opus 5.5 | $4.00 | $20.00 | Razonamiento complejo, arquitectura, análisis profundo, contexto de 1M |
| Fable 5.1 | $10.00 | $50.00 | Las tareas más largas y difíciles, contexto de 1M |

Los precios de los modelos cambian de una generación a otra: una nueva generación de Opus puede costar bastante menos que la anterior. Así que no te aprendas las cifras de memoria; revisa la tabla antes de hacer cualquier cálculo.

**⚠️ Tokenizador:** los modelos 4.7 y posteriores (en esta tabla, Opus 5.5, Sonnet 5.5 y Fable 5.1) usan un tokenizador más nuevo: el mismo texto ocupa cerca de 30% más tokens que en Sonnet 4.6 y anteriores. El aumento exacto depende del texto. Tu cuenta real puede salir más alta que tu estimación, así que agrega un margen de 30% cuando traslades cálculos de modelos anteriores.

**Mythos:** Claude Mythos 5.1 está disponible solo por invitación (Project Glasswing); un usuario normal no puede obtenerlo.

**Modelos que se retiran de la API:** los modelos antiguos se dan de baja. Claude Opus 4, Opus 4.1, Sonnet 4 y Haiku 3.5 ya se retiraron de la API de Claude (algunos siguen disponibles en Amazon Bedrock y Google Cloud). Claude Haiku 4.5 podría retirarse no antes del 15 de octubre de 2026. Si tienes un modelo desactualizado en producción, vigila la página de [model deprecations](https://platform.claude.com/docs/en/about-claude/model-deprecations) (retiro de modelos) y migra con anticipación.

#### OpenAI (para comparar, a octubre de 2026)

| Modelo | Entrada | Salida | Cuándo |
|---|---|---|---|
| gpt-6-luna | $0.10 | $0.50 | El más barato y rápido |
| gpt-6.1-sol | $2.00 | $10.00 | El equilibrio |
| gpt-6-astra | $10.00 | $50.00 | El más potente |

Los nombres y precios de los modelos de OpenAI cambian seguido; revisa las cifras vigentes en la página oficial de precios de la API de OpenAI.

**Qué significa un token en la práctica:**

- Cerca de 4 caracteres de texto en inglés, o cerca de 0.75 de una palabra, = 1 token
- Para los modelos 4.7 y posteriores, agrega cerca de **+30%** por el tokenizador nuevo
- Un prompt como "escribe una publicación para LinkedIn" con 10K tokens de contexto de entrada + 2K de salida ≈ $0.04 en Sonnet 5.5

**Cuentas de ejemplo (Sonnet 5.5):**

- 1,000 solicitudes con 500 tokens de entrada + 500 de salida (nominales) cada una
- Con el margen de +30% del tokenizador: ~650 de entrada + ~650 de salida
- Entrada: 650 × 1,000 / 1,000,000 × $2 = $1.30
- Salida: 650 × 1,000 / 1,000,000 × $10 = $6.50
- Total: **~$7.80** por 1,000 solicitudes

**Cuentas de ejemplo (Opus 5.5):**

- Las mismas 1,000 solicitudes, ~650 de entrada + ~650 de salida con el margen del tokenizador
- Entrada: 650 × 1,000 / 1,000,000 × $4 = $2.60
- Salida: 650 × 1,000 / 1,000,000 × $20 = $13.00
- Total: **~$15.60** por 1,000 solicitudes (el doble que Sonnet 5.5 para la misma tarea)

**Formas de ahorrar:**

- **Prompt caching:** leer de la caché cuesta el 10% del precio de entrada (detalles abajo y en la lección [Prompt caching y la Batch API](34-prompt-caching-batch-api.md))
- **Batch API:** 50% de descuento si estás dispuesto a esperar hasta 24 horas por el procesamiento. Los detalles están en la misma lección
- **Haiku 4.5 en lugar de Sonnet 5.5:** la mitad del costo en tareas simples
- **Menos tokens de salida:** mantén la salida corta, porque la salida cuesta 5 veces más que la entrada

#### Prompt caching: el desglose detallado (a octubre de 2026)

| Operación | Multiplicador sobre el precio base | TTL (cuánto dura) |
|---|---|---|
| Escritura en caché, 5 min | **1.25x** (25% más que el precio base de entrada) | 5 minutos |
| Escritura en caché, 1 hora | **2.0x** (el doble del precio) | 1 hora |
| Lectura de caché (acierto) | **0.1x, un 90% de descuento** (0.05x en Opus 5.5; para otros modelos, consulta la página oficial de precios) | mientras la caché siga activa |

**Ejemplos en Sonnet 5.5 ($2/MTok de entrada):**

- Escritura en caché, 5 min: $2.50/MTok
- Escritura en caché, 1 hora: $4.00/MTok
- Lectura de caché (acierto): $0.20/MTok

**Cuándo conviene:** la caché se paga sola después de 1 lectura (con una escritura de 5 minutos) o de 2 lecturas (con una escritura de 1 hora).

#### Herramientas de pago de la API (a octubre de 2026)

- **Web Search:** $10 por cada 1,000 búsquedas (+ tokens estándar)
- **Web Fetch:** gratis (solo tokens)
- **Code Execution:** se cobra por tiempo de contenedor, con una cantidad gratuita; las condiciones vigentes están en la [página oficial de precios](https://platform.claude.com/docs/en/about-claude/pricing)
- **Managed Agents (Claude Managed Agents):** se cobra por hora de sesión en ejecución; consulta la tarifa en la [página oficial de precios](https://platform.claude.com/docs/en/about-claude/pricing)

#### Novedades de Anthropic (a octubre de 2026)

- **Fable 5.1** (1 de septiembre de 2026): el más potente de los modelos disponibles para todos
- **Opus 5.5** (22 de septiembre de 2026) y **Sonnet 5.5** (28 de septiembre de 2026): los principales modelos de trabajo
- **Claude Mythos 5.1**: solo por invitación (Project Glasswing); no se ha lanzado al público
- **Ventana de contexto de 1M:** incluida al precio estándar, sin recargo, en Fable 5.1, Opus 5.5 y Sonnet 5.5; Haiku 4.5 tiene una ventana de 200K

**Para quién es:**

- Un desarrollador que crea un Cloudflare Worker, un chatbot o una automatización
- Una empresa SaaS que integra Claude en su producto
- Cualquier programa que llame a Claude desde código más de 100 veces al día

**Cuándo pasar de Pro a la API:**

- Quieres automatizar el procesamiento (un bot, un cron job programado, procesamiento por lotes)
- Necesitas integrar Claude en tu propio producto
- Tu volumen de llamadas supera lo que Pro te da a través del chat

**Enlace:** [platform.claude.com](https://platform.claude.com) (Console) → Billing → Add credit

**El monto mínimo de recarga y los métodos de pago** aparecen en Console → Billing.

🎨 **Imagínalo así:** un taxi con taxímetro. Pagas solo cuando viajas. Eso es práctico si viajas poco o de forma impredecible. Es un mal negocio si viajas 8 horas al día; en ese punto una suscripción Pro/Max sale más barata.

---

### Tabla comparativa (octubre de 2026)

| Función | Free | Pro | Max 5x | Max 20x | Team Standard | Team Premium | Enterprise | API |
|---|---|---|---|---|---|---|---|---|
| **Precio mensual** | $0 | $20/mes | desde $100/mes | $200/mes | $25/puesto | $125/puesto | $20/puesto + API | pago por uso |
| **Precio anual** | — | $17/mes ($200/año) | — | — | $20/puesto | $100/puesto | $20/puesto (pago anual) | — |
| **Claude Code** | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | con tu propio código |
| **Uso** | límite pequeño | 5x Free por sesión | 5x Pro | 20x Pro | más que Pro | 5x Standard | personalizado | niveles Start / Build / Scale |
| **Modelos** | Sonnet, Haiku | Opus, Sonnet, Haiku; Fable con créditos de uso | todos los disponibles | todos los disponibles | todos los disponibles | todos los disponibles | todos los disponibles | todos (precios arriba) |
| **Projects** | hasta 5 | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | a través de la API |
| **Espacio de trabajo compartido** | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | — |
| **SSO** | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ + SCIM | claves de API |
| **Preparado para HIPAA** | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | — |
| **Computer Use** (en la app) | ❌ | research preview | research preview | research preview | ❌ | ❌ | ❌ | a través de la API |
| **Prompt caching** | — | — | — | — | — | — | — | ✅ (lecturas de caché con 90% de descuento o más) |
| **Batch API** | — | — | — | — | — | — | — | ✅ (50% de descuento) |

---

### Mitos y errores comunes

**❌ "Me voy a comprar Max de una vez porque se ve genial"**

Sin unas 6 a 8 horas reales de trabajo al día, Max no se paga. Pro ya te da bastante más uso que Free. Empieza con Pro y sube de plan cuando choques seguido con el límite.

**❌ "La API es más barata que Pro para platicar con Claude"**

Para el chat interactivo, la API suele ser **más cara** que Pro: con cada respuesta, todo el historial de la conversación va en la solicitud. Un ejemplo en Sonnet 5.5 (precios a octubre de 2026): 100 solicitudes al día, cada una con 20K tokens de entrada y 1K tokens de salida = 2M de entrada × $2 + 0.1M de salida × $10 = $5 al día, o cerca de $150 al mes. Pro cuesta un fijo de $20 (o $17 con pago anual).

La API es más barata solo para la **automatización en código**: un Worker hace 5K llamadas al día, cada una con 500 tokens de entrada y 100 tokens de salida = 2.5M × $2 + 0.5M × $10 = $10 al día. Nunca llegarías a ese volumen platicando.

**❌ "Pro + API reemplaza a Team"**

Solo en parte. Pro + API te da acceso personal más automatización. Pero NO te da:

- Proyectos compartidos entre los miembros del equipo
- Facturación centralizada
- Controles de administrador
- Analítica de uso del equipo

Si 3 personas trabajan juntas, Pro × 3 = $60 (o $51 con pago anual). Con 5 o más personas, Team Standard tiene más sentido ($100/mes con pago anual por 5 puestos).

**❌ "Free alcanza para todo"**

Para el chat, tal vez. Para Claude Code, **no**: simplemente no está disponible en Free. Si quieres escribir código en la terminal, necesitas un plan de pago (como mínimo Pro) o una clave de API.

**❌ "Compré Pro, así que Claude Code funciona de inmediato"**

No de inmediato. Pro te da el **derecho** a usar Claude Code, pero todavía necesitas una terminal o VS Code, y Claude Code se instala aparte. Mira la lección [Cómo instalar y configurar Claude Code](05-setup.md).

**❌ "Puedo pausar mi suscripción"**

No cuentes con una pausa. Revisa en Settings → Billing qué opciones ofrece tu plan: cancelar, cambiar de plan u otra cosa. Antes de cancelar, guarda tus Projects y conversaciones importantes, y consulta las condiciones de retención de datos en el centro de ayuda oficial.

---

### Cómo pagar tu plan

Anthropic ofrece acceso y recibe pagos solo en los países admitidos. EE. UU. está en la lista; si vives en otro país o viajas fuera de EE. UU., revisa la página oficial antes de comprar: [anthropic.com/supported-countries](https://www.anthropic.com/supported-countries). La lista cambia.

**Métodos de pago:**

- Una tarjeta de crédito o débito es el método principal para las suscripciones y la API
- A los clientes Enterprise se les puede facturar bajo contrato
- Otros métodos dependen de la plataforma y de tu país; mira Settings → Billing

**Una tarjeta de respaldo:**

Un pago puede fallar por razones cotidianas: la protección contra fraudes de tu banco marca el cargo por error, o cambia tu dirección IP. Agrega a tu cuenta una segunda tarjeta de otro banco y asegúrate de que tenga fondos o crédito disponible suficientes.

**Si falla un pago:**

1. No te preocupes. Primero revisa la razón en Settings → Billing (un mensaje de "card declined by issuer", tarjeta rechazada por el emisor, normalmente significa que toca llamar a tu banco)
2. Actualiza tu tarjeta o agrega una de respaldo
3. Si nada funciona, contacta al soporte de Anthropic desde tu cuenta e incluye los datos de la transacción

**Reembolsos:** las condiciones de reembolso dependen del plan y de la región. Consulta las reglas vigentes en el centro de ayuda de Anthropic ([support.claude.com](https://support.claude.com)); para Team y Enterprise, revisa tu contrato.

**Renovación automática:**

- Viene activada por defecto
- Puedes desactivarla en Settings → Billing
- Conservas el acceso hasta el final del periodo que ya pagaste

---

### Cómo combinar planes: qué combinaciones funcionan

Un constructor muchas veces necesita más de un plan a la vez. Es normal:

**Pro + API** (la combinación más común para un desarrollador que trabaja solo)

- Pro a $20 (o $17 con pago anual) para el chat y Claude Code
- La API a $20-50/mes para tus propios Workers y automatizaciones
- Total: $37-70/mes, que cubre bien la mayoría de las tareas

**Max 5x + API** (para un constructor serio)

- Max desde $100/mes para trabajo intensivo en Claude Code
- La API a $50-200/mes para sistemas en producción
- Total: $150-300/mes. Vale la pena si chocas seguido con el límite y tus sistemas en producción de verdad están funcionando

**Team Standard + API** (para una agencia)

- Team Standard con pago anual = $100/mes por 5 puestos (un equipo puede empezar con 2 personas)
- La API para automatizaciones compartidas, $100-500/mes
- Una base práctica para una agencia con varios clientes

**Free + API** (para un desarrollador minimalista)

- Free a $0 para preguntas ocasionales
- La API para tus propios programas
- Solo si **no necesitas** Claude Code en la terminal

**Lo que no se combina:**

- ❌ Varias suscripciones de pago en una sola cuenta: una cuenta tiene un solo plan, y lo cambias subiendo o bajando de plan

---

### ¿Vale la pena? Cómo encontrar el plan correcto

No adivines. Revisa tu propio uso durante un par de semanas.

**Paso 1: Empieza con Pro ($20)**

No es caro, incluye Claude Code y puedes cancelar cuando quieras.

**Paso 2: Después de 2 semanas, revisa Settings → Usage:**

- ¿Cuántas veces chocaste con el límite? (0-2 = Pro es suficiente, 5 o más = es momento de Max)
- ¿Cuántas horas al día pasas en Claude Code? (1-3 = Pro, 6 o más = Max)
- ¿Usaste Opus, y chocaste con su límite?

**Paso 3: Decide con base en los datos:**

- Nunca chocaste con un límite → quédate en Pro
- Chocaste 2-3 veces → prueba Max 5x durante un mes
- Chocaste 10 o más veces → Max 20x se justifica
- Quieres automatización aparte → agrega la API a $20-50

**Paso 4: Vuelve a revisar cada trimestre**

Tu uso cambia. Si tu trabajo cambió, a veces conviene bajar a Pro.

---

## Lista de verificación (✅)

Antes de comprar una suscripción:

- [ ] Entiendes la diferencia entre Free / Pro / Max 5x / Max 20x
- [ ] Sabes cuándo necesitas Team y cuándo Enterprise
- [ ] Entiendes que la API es una cuenta aparte con cobro aparte a través de la Console (platform.claude.com)
- [ ] Decidiste qué plan vas a usar el próximo mes (Pro por defecto)
- [ ] Sabes cómo desactivar la renovación automática si lo necesitas
- [ ] Sabes que Claude Code requiere un plan de pago (como mínimo Pro) o una clave de API

---

## Herramientas y recursos

- **[Claude pricing overview](https://claude.com/pricing)** (resumen de precios de Claude): la página oficial con todos los planes
- **[Claude.ai upgrade](https://claude.ai/upgrade)**: sube de Free a Pro/Max
- **[Claude Team](https://claude.com/pricing)**: los planes de equipo Standard y Premium
- **[Claude Enterprise](https://claude.com/pricing)**: una llamada con ventas para empresas grandes
- **[Anthropic Console](https://platform.claude.com)**: tu panel de la API para claves, cobros y uso
- **[Precios de la API en detalle](https://platform.claude.com/docs/en/about-claude/pricing)**: un desglose detallado de precios por modelo
- **[Token counting](https://platform.claude.com/docs/en/build-with-claude/token-counting)** (conteo de tokens): cuenta cuántos tokens tiene tu prompt
- **[Status page](https://status.anthropic.com)** (página de estado): el estado de la API y los servicios en tiempo real
- **[Supported countries](https://www.anthropic.com/supported-countries)** (países admitidos): dónde está disponible Claude, si vives o viajas fuera de EE. UU.

---

## Ideas clave

> No elijas un plan "porque se ve genial". Elígelo según tu uso real. Empieza con Pro ($20 con pago mensual, o $17/mes con pago anual = $200/año) y sube de plan cuando de verdad choques con el límite varias veces por semana.

> Los precios de los modelos cambian de una generación a otra. A octubre de 2026, Opus 5.5 cuesta $4/$20 por millón de tokens y Sonnet 5.5 cuesta $2/$10, mientras que las generaciones anteriores de Opus costaban bastante más. Los modelos 4.7 y posteriores usan un tokenizador nuevo: cerca de 30% más tokens para el mismo texto, así que incluye un margen en tus cuentas.

> Los modelos antiguos se retiran de la API. Si tienes un modelo desactualizado en producción, vigila la página de retiro de modelos y migra con anticipación, o tus llamadas van a empezar a fallar.

> La API y Pro son **cosas distintas**; no las confundas. Pro te da el chat y Claude Code. La API le da a tu programa acceso a los modelos, con cobro aparte por token a través de la Console. Un constructor normalmente necesita las dos, una al lado de la otra.

---

## Próxima lección

→ [Cómo instalar y configurar Claude Code](05-setup.md): instala Claude Code, configura la terminal y VS Code, y ejecuta tu primer comando
