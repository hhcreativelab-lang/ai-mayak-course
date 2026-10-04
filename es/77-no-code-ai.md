# IA sin código para quienes no programan: v0, Webflow, Framer

**Tiempo:** unos 25 min de lectura + 35 min de práctica

---

## Lo esencial

🎨 **Imagínalo así:** imagina trabajar con un arquitecto sin necesitar un dibujante. Describes con palabras lo que quieres, "una casa de tres recámaras con ventanales de piso a techo y cochera techada", y 30 segundos después tienes enfrente un diseño terminado. Nunca tomaste un lápiz, no conoces el reglamento de construcción, y aun así la casa queda con aspecto profesional. Así funcionan las herramientas de IA sin código: describes lo que quieres y ellas lo construyen. Claude Code, en esta imagen, es el contratista general al que llamas cuando necesitas una instalación eléctrica o una plomería a la medida que el plano estándar no contemplaba.

Esta lección trata de construir sitios web y apps para ti y para tus clientes sin escribir a mano una sola línea de código. También trata de cuándo basta con lo sin código, y cuándo es momento de traer a Claude.

---

## Conceptos clave

- **IA sin código (no-code)** (crear software sin escribir código): herramientas que generan la interfaz, el contenido y la lógica de una app a partir de una descripción en lenguaje común
- **v0** (v0.app, antes v0.dev): un servicio de Vercel que construye interfaces y apps en React a partir de un prompt (tu solicitud a la IA); puedes copiar el código que produce directo a Claude Code
- **Webflow AI**: la IA integrada en Webflow que genera textos, imágenes y contenido del CMS sin que salgas del editor
- **Framer AI**: crea una página de aterrizaje a partir de una sola oración, adaptada automáticamente a celulares y tabletas
- **El enfoque híbrido**: v0 o Framer generan la parte visual, y Claude Code agrega la lógica de negocio, las integraciones de API (una API, o interfaz de programación de aplicaciones, es la forma en que los programas hablan entre sí) y la base de datos
- **El nicho de "constructor por encargo"**: un servicio en el que tomas pedidos de sitios web, los construyes rápido con las herramientas de esta lección y se los entregas al cliente como producto terminado
- **Velocidad vs. flexibilidad**: lo sin código es más rápido para trabajos estándar; Claude Code es insustituible para la lógica a la medida y el crecimiento a largo plazo
- **Lovable y Bolt.new**: los competidores de Claude Code para quienes no programan. Generan apps completas (full-stack) a partir de una descripción, pero tienen un techo en cuanto puedes personalizarlas

---

## Teoría

### Por qué la IA sin código se volvió una herramienta profesional

Antes, "hacer un sitio sin código" significaba una plantilla de Squarespace o Wix con bloques fijos y animaciones limitadas. Hoy, las herramientas de IA sin código generan componentes de React listos para producción, hacen que el diseño se adapte a cualquier tamaño de pantalla, configuran los campos del CMS y publican en una CDN (red de distribución de contenido). La distancia entre "lo hice yo" y "contraté a un desarrollador" se achicó tanto que un dueño de negocio sin formación técnica puede armar rápido un sitio sencillo que antes le tomaba semanas a un equipo.

Eso abre una oportunidad de negocio concreta: volverte "constructor por encargo", alguien que conoce estas herramientas mejor que el cliente y al que le pagan por su criterio para elegir el conjunto de herramientas correcto y por la rapidez de entrega, no por escribir código.

---

### v0 (Vercel): del texto a una interfaz en React

**Qué es.** v0 (en v0.app, antes v0.dev) es un servicio de Vercel, la empresa detrás de Next.js. Ahora es un agente que construye interfaces y apps completas. Escribes un prompt ("haz una tarjeta de producto con imagen, precio, un botón de agregar al carrito y una etiqueta de descuento") y obtienes código de React listo, con Tailwind CSS y shadcn/ui. Hay un plan gratis; los planes de pago funcionan con créditos según el uso de tokens (condiciones en [v0.app/pricing](https://v0.app/pricing)).

**Cómo funciona.** v0 no solo entiende "un botón", sino "un botón al estilo de Stripe con efecto al pasar el cursor y un estado de carga". El resultado es código normal de React/Next.js que copias a tu proyecto; normalmente necesita algún ajuste fino para encajar.

**La función estrella para el enfoque híbrido.** Pegas el código generado en Claude Code y le dices: "conecta este componente a mi API /products/:id, agrega una carga con esqueleto (skeleton) y manejo de errores". Claude Code escribe la lógica sobre la parte visual de v0.

**Un flujo de trabajo práctico:**

1. Describe en v0 la pantalla o el componente que necesitas
2. Itera con prompts ("haz el título más grande", "agrega un modo oscuro")
3. Copia el código final
4. Pégalo en Claude Code y describe la lógica de negocio
5. Claude Code conecta los datos, agrega validación y publica

🎨 **Imagínalo así:** v0 es un diseñador que hace un boceto en 30 segundos. Claude Code es el desarrollador que toma el boceto y lo convierte en un producto que funciona. Tú eres el gerente que les da sus encargos a los dos.

---

### Webflow AI: contenido y CMS sin el trabajo pesado

**Qué es.** Webflow es un editor visual de sitios web con su propio hosting integrado. Webflow tiene funciones de IA: generar textos dentro del editor, ayuda con el contenido del CMS, traducir el sitio. Las funciones y los planes cambian, así que revisa los detalles vigentes en el sitio de Webflow.

**IA en el CMS.** Creas una colección del CMS llamada "Servicios" con tres campos: nombre, descripción, precio. Activas un campo de IA para "descripción", y Webflow escribe la descripción por sí mismo con base en el nombre y el contexto del sitio. Para una agencia con 50 servicios, eso le ahorra días de trabajo a un redactor.

**Localización en Webflow.** Traducción integrada del sitio a varios idiomas: haces clic en un botón y obtienes, por ejemplo, versiones en inglés y en portugués de tu sitio en español. Para clientes internacionales esto ahorra tiempo de traducción, pero la traducción automática igual necesita que una persona la lea.

**Limitaciones.** Webflow suele costar más que Framer: pagas tanto un plan del sitio como un plan del espacio de trabajo. Para clientes con un sitio sencillo, puede ser demasiado. Pero para negocios con blog, equipo y contenido que se actualiza seguido, encaja muy bien.

---

### Framer AI: una página de aterrizaje a partir de un prompt

**Qué es.** Framer es una herramienta de diseño que aprendió a generar páginas de aterrizaje completas a partir de una descripción en texto. Escribes: "Una página de aterrizaje para un estudio de yoga en Bogotá. Estilo minimalista moderno, tonos cálidos, secciones: portada, quiénes somos, horario de clases, reseñas, reserva una clase de prueba", y poco después tienes una página terminada con textos, imágenes y un diseño que se adapta a cualquier pantalla.

**Fortalezas.** Framer es conocido desde hace tiempo por animaciones bonitas que son difíciles de recrear en Webflow sin saber código. La IA mantiene ese nivel de calidad visual. Con el plan gratis, tu sitio se publica en un subdominio de Framer; conectar tu propio dominio requiere un plan de pago (condiciones en el sitio de Framer).

**Framer vs. Webflow.** Framer suele ser más rápido para generar páginas y se ve mejor de entrada. Webflow gana en funciones de CMS y en crecer hacia sitios grandes. Para la página de aterrizaje de un solo producto, usa Framer. Para el sitio de una empresa con catálogo, usa Webflow.

**Limitación.** Framer es ante todo una herramienta para sitios web y páginas de marketing, no para apps web complejas. Si el cliente quiere un área de cuenta para sus clientes o una integración con un CRM, necesitas Webflow o un híbrido con Claude Code.

---

### Bubble.io + plugins de IA: apps web completas

**Qué es.** Bubble es una de las herramientas sin código más capaces para construir apps web completas: con base de datos, cuentas de usuario, lógica e integraciones de pago. Agrega funciones de IA o conecta modelos por API (OpenAI, Claude), y la app puede leer, resumir y escribir por su cuenta.

**Proyectos típicos en Bubble.** Mercados en línea (como Airbnb, sin código), paneles de SaaS, plataformas de cursos en línea, CRM para pequeños negocios. Todo sin escribir código de servidor.

**Bubble + la API de Claude.** Con un plugin o con llamadas directas a la API, conectas Claude (un LLM, un modelo de lenguaje grande). Por ejemplo: un usuario sube un documento → Bubble manda el texto a la API de Claude → Claude devuelve un resumen → Bubble lo guarda en la base de datos y se lo muestra al usuario. Eso es un producto de IA que funciona sin una sola línea de código de servidor.

**La desventaja de Bubble.** Una curva de aprendizaje empinada: no vas a dominar lo básico en una tarde. Necesitas un plan de pago para lanzar, y el precio depende de cuánta carga le pone tu app a la plataforma (planes en el sitio de Bubble). El rendimiento es menor que con código escrito a mano. Es excelente para un MVP y poco tráfico; una startup que crece tarde o temprano va a necesitar migrar a código.

---

### Lovable: el competidor de Claude Code para quienes no programan

**Qué es.** Lovable (antes GPT Engineer) es una herramienta que genera una app a partir de una descripción. Se parece a Claude Code, pero funciona desde una interfaz web, sin terminal. Describes la app en un chat, Lovable construye la interfaz y la lógica, y trae un backend integrado, Lovable Cloud (base de datos, registro e inicio de sesión), además de la publicación.

**Sobre los datos de los clientes.** En algunos planes de Lovable, los datos de tu proyecto pueden usarse para entrenar modelos a menos que actives la opción de exclusión ("Data collection opt out", es decir, no participar en la recolección de datos). Revisa las condiciones vigentes en el sitio de Lovable y, para proyectos de clientes, activa la exclusión desde el principio.

**Lovable vs. Claude Code.** Con Lovable es más fácil empezar: no hay nada que instalar. Claude Code es más flexible y más capaz: funciona con cualquier conjunto de tecnologías y cualquier nube, y te da control total del código. Para un principiante que necesita un MVP rápido, Lovable. Para un producto serio que va a durar, Claude Code.

**Híbrido.** Algunos desarrolladores usan Lovable para un prototipo rápido, luego exportan el código y lo siguen afinando con Claude Code. Ese enfoque funciona bien.

---

### Bolt.new: la IA de StackBlitz en el navegador

**Qué es.** Bolt.new, de StackBlitz, es un generador de apps que funciona directo en tu navegador. No necesitas instalar nada: todo corre en la nube. Escribes un prompt y obtienes un proyecto funcionando con frontend y backend. El hosting y los dominios son parte del propio servicio (Bolt Cloud): una dirección gratis en bolt.host, tu propio dominio en los planes de pago.

**Fortalezas.** Bolt es muy rápido para trabajos sencillos: una página de aterrizaje, un formulario de contacto, un panel sencillo. Como está construido sobre StackBlitz, el código corre directo en el navegador, así que le puedes mostrar el resultado al cliente de inmediato, sin una publicación aparte.

**Limitaciones.** La lógica de negocio compleja, las integraciones a la medida, el trabajo con bases de datos: todo eso exige pasar a Claude Code o muchas correcciones a mano.

---

### Cuándo usar lo sin código vs. Claude Code

| Criterio | Sin código (v0/Framer/Webflow) | Claude Code |
|---|---|---|
| **Tiempo para lanzar** | horas | días |
| **Personalización** | Media | Total |
| **Costo de las herramientas** | depende de los planes de cada servicio | una suscripción de Claude (Pro o superior) o pago por token con la API |
| **Hosting** | Incluido en el plan o pagado aparte | Te encargas tú (Cloudflare, Vercel) |
| **Trabajos estándar** | ✅ Excelente | Demasiado |
| **Lógica a la medida** | ❌ Difícil o imposible | ✅ Control total |
| **Crecimiento** | Limitado por el plan | Sin límite |
| **Mantenimiento a largo plazo** | Dependes de la plataforma | Control total |
| **Integraciones de API** | Con plugins o Zapier (una plataforma que conecta distintas apps entre sí) | Cualquiera, de forma nativa |
| **Ideal para** | Páginas de aterrizaje, MVP, pequeños negocios | SaaS, productos complejos |

**Regla práctica:** si el proyecto es estándar (una página de aterrizaje, un sitio de negocio sencillo, un catálogo básico) y no necesita lógica a la medida, usa lo sin código. Si tiene un área de cuenta para clientes, integraciones o requisitos poco comunes, usa un híbrido o Claude Code puro. Precios y versiones vigentes: [Lo vigente](https://aimayak.com/es/now/).

---

### El enfoque híbrido: una interfaz sin código + un backend con Claude Code

🎨 **Imagínalo así:** los restaurantes muchas veces compran preparaciones básicas como masas y salsas, pero el toque final le toca al chef. Las herramientas sin código son las preparaciones básicas de la interfaz. Claude Code es el chef que lleva el platillo a calidad de restaurante.

**El flujo de un proyecto híbrido:**

```
[ETAPA 1: Diseño (v0 / Framer)]
Prompt → componentes de interfaz / página de aterrizaje
Iterar → diseño final aprobado
↓
[ETAPA 2: Personalización (Claude Code)]
Pegar el código de v0
Conectar API (Stripe, Slack, un CRM)
Agregar el inicio de sesión de usuarios
Agregar la validación de formularios
Configurar la lógica de negocio
↓
[ETAPA 3: Publicación (Cloudflare / Vercel)]
Un solo comando con Claude Code
CDN, SSL, dominio propio: se configuran automáticamente
↓
[ENTREGA AL CLIENTE]
Capacitación (15 min): cómo editar el contenido
Soporte: 1 mes, según el contrato
```

---

### El modelo de negocio del "constructor por encargo"

Este es un nicho concreto para quienes, entre los que toman este curso, tienen más alma de negocio. No eres desarrollador ni diseñador: eres experto en armar cosas. Sabes qué herramienta sirve para qué trabajo, puedes armar un resultado rápido y cobras por la rapidez y el criterio.

**Lo que puedes ofrecer:**

- Una página de aterrizaje (Framer + personalización)
- Un sitio de empresa con CMS (Webflow)
- El MVP de una app (Bubble, o un híbrido con Claude Code)
- El rediseño de un sitio existente (componentes de v0 + Claude Code)

**Por qué pagan los clientes.** Podrían intentar Framer ellos mismos, pero pasarían una semana aprendiéndolo y otra semana en correcciones. Tú lo haces más rápido. La diferencia de precio es su tiempo multiplicado por su tarifa por hora. Los precios los pone el mercado y tus propios costos; los ingresos no están garantizados. Para calcular tu precio, revisa la lección [Cómo ponerle precio a tus servicios de IA](39-monetization-pricing.md).

**Cómo encontrar clientes.** Los pequeños negocios sin sitio web, o con uno anticuado, están en todas partes: restaurantes locales, estéticas, despachos de abogados, consultorios médicos, sastrerías, agencias de viajes. No necesitan un producto complejo. Necesitan un sitio web decente con un formulario de contacto a un precio razonable.

---

## Práctica

### Ejercicio: arma una página de aterrizaje en 35 minutos con v0 + Claude Code

**Escenario:** un cliente te pide armar una página de aterrizaje para una escuela de inglés en línea para adultos. Necesita una portada, los beneficios, los planes de precios y un formulario de inscripción que mande cada solicitud al canal de Slack de la escuela.

---

**Paso 1: Genera el diseño en v0 (10 minutos)**

Entra a [v0.app](https://v0.app) y escribe este prompt:

```
Crea una página de aterrizaje para una escuela de inglés en línea para adultos. Estilo: moderno,
profesional, paleta de colores azul. Secciones:
1. Portada: el título "Empieza a hablar inglés en 3 meses", un subtítulo
   y un botón "Reserva una clase de prueba"
2. Tres beneficios: clases en vivo, horario flexible, un certificado
3. Precios: Básico ($49/mes), Estándar ($89/mes), Premium ($149/mes),
   mostrados como tarjetas con características y un botón
4. Formulario de inscripción: nombre, correo, teléfono, horario preferido, un botón de enviar
Usa Tailwind CSS; el componente debe estar en React. Todo el texto de la página en español.
```

Itera si hace falta ("haz más alta la portada", "muestra los precios lado a lado", "agrega íconos a los beneficios"). Cuando estés contento con la versión final, copia todo el código.

---

**Paso 2: Prepara el proyecto en Claude Code (5 minutos)**

```bash
# En la terminal:
mkdir english-school-landing
cd english-school-landing
```

Abre Claude Code en esta carpeta y escribe:

```
Crea un proyecto nuevo de Next.js con Tailwind CSS.
Estructura: app/page.tsx para la página de inicio.
Instala las dependencias y revisa que todo funcione.
```

---

**Paso 3: Pega el código de v0 (5 minutos)**

Dile a Claude Code:

```
Aquí está un componente de React que generé en v0.
Ponlo en app/page.tsx y asegúrate de que todos los imports estén bien,
Tailwind funcione y el componente se muestre sin errores.

[pega aquí el código de v0]
```

Claude Code va a ordenar los imports, corregir cualquier conflicto y arrancar el proyecto.

---

**Paso 4: Manda las inscripciones a Slack (10 minutos)**

Un webhook entrante (incoming webhook) es un enlace privado que publica en un canal de Slack lo que se le mande; las páginas de ayuda de Slack muestran cómo crear uno.

```
Agrega el manejo del formulario de inscripción. Cuando un visitante haga clic en "Reserva una clase de prueba",
los datos deben mandarse a nuestro canal de Slack con un webhook entrante.

La URL de mi webhook entrante de Slack: [la URL de tu webhook]

Formato del mensaje en Slack:
🎓 Nueva solicitud de clase de prueba
Nombre: {name}
Correo: {email}
Teléfono: {phone}
Horario preferido: {time}

Agrega:
1. Una ruta de API app/api/contact/route.ts para manejar el formulario
2. Validación de campos (nombre de al menos 2 letras, un correo válido, un número de teléfono)
3. Un estado de carga en el botón
4. Un mensaje de éxito / error para el visitante
5. Una variable de entorno para la URL del webhook
```

---

**Paso 5: Publica en Vercel (5 minutos)**

```
Prepara el proyecto para publicarlo en Vercel:
1. Crea un .env.example con las variables necesarias
2. Agrega un vercel.json si hace falta alguna configuración especial
3. Asegúrate de que .gitignore ignore .env
4. Inicializa git y haz el primer commit

Luego publícalo con el comando: npx vercel --prod
```

Después de publicar, Claude Code te va a mostrar la URL. Mándasela al cliente para que la apruebe.

**Sobre los planes gratis.** El plan Hobby de Vercel es solo para proyectos personales, no comerciales. Para el sitio de un cliente (comercial) necesitas un plan de pago de Vercel (Pro, desde $20/mes por desarrollador a octubre de 2026; consulta [Lo vigente](https://aimayak.com/es/now/)) u otro hosting, como Cloudflare Pages.

---

## Herramientas y recursos

| Herramienta | Para qué sirve | Precio | Enlace |
|---|---|---|---|
| **v0** | Interfaces y apps en React a partir de un prompt | Hay plan gratis; los planes de pago funcionan con créditos | v0.app |
| **Webflow** | Editor visual de sitios con contenido de IA | Planes de pago del sitio y del espacio de trabajo; precios en el sitio | webflow.com |
| **Framer** | Páginas de aterrizaje y animaciones a partir de un prompt | Hay plan gratis; dominio propio con plan de pago | framer.com |
| **Bubble.io** | Apps web completas sin código | Plan gratis para construir; planes de pago para lanzar | bubble.io |
| **Lovable** | Construir apps con IA para quienes no programan | Plan gratis con límite de créditos | lovable.dev |
| **Bolt.new** | Apps en el navegador, de StackBlitz | Plan gratis con límites | bolt.new |
| **Vercel** | Publicar Next.js, dominios propios | Hobby (no comercial) es gratis; Pro para negocios | vercel.com |
| **Zapier / Make** | Conectar herramientas sin código entre sí | Planes gratis con límites | zapier.com / make.com |

**Un kit de inicio de bajo costo para un constructor por encargo:**

- v0 (plan gratis) + Claude Code (incluido en una suscripción de pago de Claude, no disponible en el plan gratis) + Cloudflare Pages o Vercel + Framer (plan gratis)
- Para proyectos de clientes (comerciales), los planes gratis muchas veces no sirven: lee las condiciones de cada servicio

---

## Ideas clave

> "La IA sin código no se trata de engañar al cliente. Se trata de darle un resultado en 2 días en lugar de 3 semanas. La herramienta no importa; importan el resultado y la rapidez."

> "El híbrido v0 + Claude Code es lo mejor de dos mundos: una interfaz que se ve bien sin el trabajo pesado, más libertad total en la lógica, sin los límites de una plataforma."

> "Tu primer proyecto real te va a enseñar más que 10 lecciones de teoría. Busca un pequeño negocio cerca de ti, ofrécele armarle una página de aterrizaje y empieza cuando estés listo."

---

## Siguiente lección

→ [n8n + IA](78-n8n-ai-workflows.md): flujos inteligentes con nodos de LLM

Vamos a ver cómo n8n (una alternativa a Zapier que puedes correr en tu propio servidor) se vuelve un orquestador de IA capaz: vamos a conectar la API de Claude a procesos de negocio reales y a construir cadenas "disparador → IA → acción" sin una sola línea de código de servidor.
