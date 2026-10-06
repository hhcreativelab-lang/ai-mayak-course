# El modelo de fábrica: plantillas para un trabajo con clientes que se repite

**Tiempo:** unos 25 min de lectura + 30 min de práctica

---

## Lo esencial

Tu primera casa tarda 3 meses en construirse. La décima tarda 3 semanas, porque para entonces ya tienes plantillas de muros, proveedores de confianza y una cuadrilla que sabe qué hacer. El modelo de fábrica significa que cada proyecto nuevo de un tipo parecido sale más rápido y más barato que el anterior. Y puedes cobrarle al cliente un poco más, porque un resultado más rápido vale más para él.

Si vendes servicios de IA como freelancer o como actividad extra, así es como tomas proyectos parecidos sin que las horas se acumulen cada vez.

Los ejemplos de esta lección vienen de proyectos hechos con código: esos se construyen en Claude Code, que se ve en el siguiente módulo del curso y en la biblioteca avanzada. No necesitas entender cada nombre de archivo. Si por ahora trabajas sin código, quédate con el principio: una plantilla puede ser un juego de prompts, la estructura de una propuesta o una lista de verificación para la entrega.

---

## Conceptos clave

- **Fábrica**: un sistema de plantillas para crecer: 80% estándar + 20% personalización
- **Repositorio plantilla**: el punto de partida de cada tipo de proyecto, para nunca empezar de cero (un repo, abreviatura de repositorio, es una carpeta de proyecto que se controla con Git)
- **SOP (procedimiento estándar de operación)**: un proceso documentado para cada tipo de proyecto
- **Tiempo de entrega**: baja de 2 semanas a 5 días hábiles gracias a las plantillas
- **Un equipo de agentes**: subagentes especializados de Claude (agentes auxiliares, cada uno con una sola tarea concreta) para cada plantilla
- **Sobreprecio**: más rápido = más caro (según el valor, no según el tiempo)

---

## Teoría

### El problema del trabajo de una sola vez

🎨 **Imagínalo así:** un cocinero que reinventa la receta del guiso todos los días. Cada vez busca las proporciones, olvida cuánta sal lleva y tarda una hora en lugar de quince minutos. Un chef escribe la receta una vez y después la repite a la perfección, para cualquier número de porciones.

Empezar de cero cada vez es caro y lento:

```
Proyecto 1: Newsletter Automation
- Configuración OAuth de Gmail API: 4 horas
- Estructura del Cloudflare Worker: 3 horas
- Configuración del bot de Slack: 2 horas
- Total de infraestructura: 9 horas (de ~40 en total)

Proyecto 2: Newsletter Automation (otro cliente)
- Configuración OAuth de Gmail API: 4 horas (¡otra vez!)
- Estructura del Cloudflare Worker: 3 horas (¡otra vez!)
- Configuración del bot de Slack: 2 horas (¡otra vez!)
- Total de infraestructura: 9 horas (22% de todo tu tiempo en cosas que ya hiciste)
```

Después de 5 proyectos parecidos podrías trabajar el doble de rápido, pero empiezas de nuevo cada vez.

🎨 **Imagínalo así:** tu primera casa tarda 3 meses. Todo es nuevo: dónde comprar los materiales, cómo colar los cimientos, con qué cuadrilla puedes contar. Tu décima casa tarda 3 semanas: los materiales se piden con anticipación a un proveedor de confianza, la cuadrilla conoce su papel y los muros estándar ya están en los planos. Por fuera las casas se ven distintas. El sistema de adentro es el mismo.

---

### Tres tipos de plantillas en una fábrica

🎨 **Imagínalo así:** los constructores trabajan con tres tipos de piezas ya hechas: planos de cimientos estándar (iguales en todas las casas), distribuciones estándar (unas cuantas opciones para elegir) y acabados que escoge el cliente (distintos cada vez). Tres niveles de plantillas, tres niveles de velocidad.

**Tipo 1: Plantilla de infraestructura**

Código que se repite y es igual en todos los proyectos:

```
template-base/
├── cloudflare-worker/
│   ├── worker.js              ← Worker principal con el enrutamiento
│   ├── auth.js                ← funciones de apoyo OAuth para Google/Microsoft
│   ├── slack-bot.js           ← configuración básica del bot de Slack
│   └── kv-storage.js          ← funciones de apoyo para Cloudflare KV
├── triggers/
│   ├── cron-template.ts       ← plantilla de tarea cron de Trigger.dev
│   └── webhook-template.ts    ← plantilla de receptor de webhooks
├── utils/
│   ├── claude-client.js       ← envoltorio de la API de Anthropic con reintentos
│   ├── error-handler.js       ← manejo de errores estándar
│   └── logger.js              ← registro estructurado
├── .env.example               ← siempre la misma estructura
├── .gitignore                 ← estándar
└── README-template.md         ← plantilla de documentación
```

(Una tarea cron es una tarea que corre con un calendario. Un webhook es un mensaje que una app le manda a otra cuando pasa algo. Un archivo .env guarda la configuración y las claves secretas de un proyecto.)

Proyecto nuevo = `git clone template-base new-project-name` (un comando de Git que copia la plantilla a una carpeta nueva). La infraestructura queda lista en 30 minutos, no en 9 horas.

**Tipo 2: Plantilla de flujo de trabajo**

Una plantilla completa para un tipo específico de proyecto:

```
template-newsletter/           ← para Newsletter Automation
template-lead-gen/             ← para generación de prospectos
template-exec-assistant/       ← para el asistente ejecutivo
template-content-pipeline/     ← para creación de contenido
template-crm-integration/      ← para integraciones con CRM
```

Cada una contiene: la lógica central del flujo, las herramientas estándar, un CLAUDE.md con un prompt especializado (CLAUDE.md es el archivo de instrucciones que Claude Code lee cuando trabaja en ese proyecto) y un .env.example con la lista de claves de API que vas a necesitar.

**Tipo 3: Plantillas de CLAUDE.md**

Instrucciones especializadas para los agentes, un conjunto para cada tipo de tarea:

```markdown
# CLAUDE.md para el agente de Newsletter Automation

Eres un agente de automatización de boletines.
Tu trabajo: reunir noticias, generar contenido, coordinar el envío.

## Reglas de trabajo:
- SIEMPRE muestra una vista previa antes de enviar
- Usa brand_guidelines.md para el tono del correo
- Si una API devuelve un error, regístralo y sigue con los datos parciales
- No más de 5 noticias por edición, salvo que se indique otra cosa

## Formato de cada noticia: titular + 2 oraciones + enlace
...
```

---

### 80% plantilla + 20% personalización

🎨 **Imagínalo así:** un traje de sastre. El 80% son los patrones estándar que el sastre usa desde hace años: el corte del saco, el ancho de los hombros, el largo de la manga. El 20% es sobre ti: tus medidas, la tela que elegiste, el color de los botones. El cliente recibe un traje a la medida. El sastre no corta desde cero cada vez.

Esta es la proporción clave de la fábrica:

**80% estándar (de la plantilla):**
- Estructura de archivos
- Conexiones con los servicios de API
- Manejo de errores y registro
- Funciones básicas del bot de Slack
- Documentación de entrega (tomas README-template.md y lo llenas)

**20% personalización (para el cliente):**
- Las fuentes de datos específicas del cliente
- La voz de la marca y el estilo del contenido
- Las reglas del negocio (qué cuenta como un "prospecto caliente" en esta empresa)
- La integración con el CRM específico del cliente
- Avisos y umbrales específicos

Personalizas el 20% para el cliente, pero él recibe un producto al 100%. Para ti, el 80% ya está hecho.

---

### Cómo una fábrica reduce el tiempo de entrega

**Sin fábrica:**
```
Semana 1: configuración de la infraestructura + flujo principal
Semana 2: personalización + pruebas + documentación
Total: 2 semanas
```

**Con fábrica:**
```
Día 1: clonar la plantilla + configurar .env + primera ejecución
Días 2-3: personalización para el cliente (20% de la lógica)
Día 4: pruebas + correcciones
Día 5: entrega + demostración
Total: 5 días hábiles (1 semana)
```

El doble de rápido, con el mismo resultado para el cliente.

---

### Sobreprecio: más rápido = más caro

🎨 **Imagínalo así:** el envío exprés. El correo normal: 5 días, $5. Un mensajero que lo entrega hoy en la noche: $50. El producto es el mismo, un sobre con documentos. Pero la velocidad cuesta 10 veces más. El cliente no paga por los kilómetros. Paga por tener el problema resuelto hoy y no el viernes.

Suena al revés, pero muchas veces funciona. El cliente no paga tu tiempo; paga el resultado. Si el resultado llega antes, vale más.

**Posicionamiento:**

❌ "Lo puedo hacer en 1 semana en lugar de 2 porque tengo plantillas"

✅ "Como me especializo en este tipo de proyectos, pongo el sistema en marcha en 5 días. Para la mayoría de los clientes eso importa: entre antes funcione el sistema, antes empieza el ahorro."

**Precios con fábrica, en la práctica:**

| Tipo | Sin fábrica | Con fábrica | Tu ingreso por hora |
|---|---|---|---|
| Newsletter Automation | $2,000 por 2 semanas | $2,200 por 5 días | Sube unas 2.2 veces |
| Flujo de generación de prospectos | $3,000 por 3 semanas | $3,200 por 8 días | Sube unas 2 veces |
| Asistente ejecutivo | $4,500 por 3 semanas | $5,000 por 10 días | Sube unas 2.2 veces |

El cliente paga un poco más y recibe el resultado el doble de rápido. En este cálculo hipotético, el ingreso por hora de tu trabajo se duplica. Las cifras son ilustrativas: tus horas y tus precios van a ser distintos, y esto no es una promesa de ingresos.

---

### Un equipo de agentes para cada plantilla

Cada plantilla de flujo trae subagentes especializados. Claude Code los busca en la carpeta `.claude/agents/` dentro del proyecto:

**template-newsletter:**
```
.claude/agents/
├── researcher.md     ← encuentra y evalúa noticias
├── writer.md         ← escribe el contenido con la voz de la marca
├── assembler.md      ← arma el correo en HTML
└── coordinator.md    ← coordina todo el proceso
```

**template-lead-gen:**
```
.claude/agents/
├── prospector.md     ← encuentra clientes potenciales
├── personalizer.md   ← escribe correos personalizados
├── qualifier.md      ← califica la calidad de los prospectos
└── crm-updater.md    ← actualiza los datos en el CRM
```

Cuando empiezas un proyecto nuevo de boletín, tomas los agentes ya hechos de la plantilla y cambias solo el CLAUDE.md con los detalles específicos de ese cliente.

---

### Un SOP para cada tipo de proyecto

🎨 **Imagínalo así:** la lista de verificación de un piloto en la cabina. Antes de despegar, es la misma lista cada vez: flaps, presión, contacto con la torre. El piloto no improvisa. Eso no lo vuelve un robot; significa que no se le olvida revisar la presión de las llantas cuando está nervioso.

Un procedimiento estándar de operación es un documento para ti (no para el cliente): cómo arrancar un proyecto de este tipo, paso a paso:

```markdown
# SOP: Proyecto Newsletter Automation

## Día 1: Configuración (2-3 horas)
□ git clone template-newsletter [project-name]
□ Crear .env a partir de .env.example, conseguir las claves de API del cliente
□ Correr una prueba básica: python test_connections.py
□ Configurar el Cloudflare Worker (wrangler deploy)
□ Primera ejecución de prueba del flujo con datos simulados

## Días 2-3: Personalización (4-6 horas)
□ Cargar las brand_guidelines del cliente
□ Configurar las fuentes de noticias (consulta de Perplexity, feeds RSS)
□ Ajustar la plantilla HTML a la marca del cliente
□ Configurar la lista de destinatarios (modo de prueba)
□ Bot de Slack: agregar al cliente como administrador

## Día 4: Pruebas (3-4 horas)
□ Ejecución completa con datos reales
□ Mandar un correo de prueba a tu propia dirección
□ Revisar el registro en Google Sheets
□ Corregir todos los problemas

## Día 5: Entrega (2-3 horas)
□ Grabar un recorrido en Loom (20 min)
□ Actualizar README-template.md para este proyecto
□ Demostración final con el cliente
□ Entregar los accesos con la lista de verificación
□ Mandar el correo final de cierre del proyecto
```

Escribir un SOP toma 30 minutos, y te ahorra horas en cada proyecto que sigue.

---

### Cuándo vale la pena una fábrica

🎨 **Imagínalo así:** afilar la sierra antes de empezar a cortar. Los primeros 20 minutos se van en afilar y parece tiempo perdido. Pero con una sierra sin filo, un árbol toma una hora. Con una afilada, 15 minutos. Entre más árboles tengas por delante, más rinden esos 20 minutos.

Una estimación honesta:

- **1-2 proyectos de un tipo:** construir la plantilla todavía no se paga
- **3er proyecto:** la plantilla empieza a ahorrarte tiempo
- **5º proyecto:** eres 2-3 veces más rápido que un principiante que lo hace desde cero
- **10º proyecto:** tu fábrica está completa; dominas este tipo de proyecto

Empieza a construir la plantilla después de tu segundo proyecto del mismo tipo. Ese es el momento correcto. Antes es optimización prematura.

---

## Práctica

**Ejercicio: crea tu primera plantilla**

1. Toma un trabajo que ya hayas hecho al menos una vez: un servicio de tus paquetes, o una automatización si ya construiste alguna (el ejemplo de abajo usa la automatización de boletines de la biblioteca avanzada)

2. Crea una carpeta `templates/newsletter-automation-template/` (cambia newsletter-automation por el nombre de tu propio trabajo):
   - Copia ahí todos los archivos del proyecto: documentos, prompts, hojas de cálculo y el código, si lo hay
   - Reemplaza todos los datos propios del cliente con marcadores (`[CLIENT_NAME]`, `[BRAND_COLOR]`, `[API_KEY]`)
   - Haz una lista de lo que hay que reemplazar al personalizar

3. Escribe un SOP para este tipo de proyecto (5 días, como en el ejemplo de arriba):
   - Día 1: ¿qué haces?
   - Días 2-3: personalización: ¿qué archivos concretos cambias?
   - Día 4: pruebas: ¿qué revisiones corres?
   - Día 5: entrega: ¿qué documentos creas?

4. Estima: si hubieras tenido esta plantilla desde el inicio, ¿cuántos días antes habrías terminado el proyecto?

5. Calcula el sobreprecio: si sin plantilla un proyecto te toma 10 días y cobras $2,000, ¿cuántos días te toma con plantilla y cuál es el nuevo precio? Compara con el ejemplo de esta lección: el doble de rápido y un poco más caro, es decir, unos 5 días y unos $2,200. Tu ingreso por día pasa entonces de $200 a $440.

**Meta:** una plantilla funcionando en la carpeta `templates/`. Ese es el primer ladrillo de tu fábrica.

---

## Referencia rápida: métricas de eficiencia de la fábrica

| Tipo de proyecto | Sin fábrica | Con fábrica | Ahorro | Tarifa efectiva |
|---|---|---|---|---|
| Newsletter Automation | 40 horas / 2 sem | 20 horas / 5 días | 50% del tiempo | $2,200 por 20 h = $110/hora |
| Flujo de prospectos | 60 horas / 3 sem | 30 horas / 8 días | 50% del tiempo | $3,200 por 30 h = $107/hora |
| Asistente ejecutivo | 80 horas / 3 sem | 40 horas / 10 días | 50% del tiempo | $5,000 por 40 h = $125/hora |
| Flujo de contenido | 45 horas / 2 sem | 22 horas / 5 días | 51% del tiempo | $2,400 por 22 h = $109/hora |
| Integración con CRM | 70 horas / 3 sem | 35 horas / 8 días | 50% del tiempo | $4,200 por 35 h = $120/hora |

**En resumen:** en este ejemplo, una fábrica duplica tu tarifa efectiva: $50-60/hora sin plantillas → $107-125/hora con plantillas, con casi el mismo precio para el cliente. Es un cálculo de práctica, no un pronóstico de ganancias.

---

## Errores comunes

- **Crecer antes de tener un SOP.** Sin un proceso documentado, lo que haces crecer es el caos. Primero un SOP para un tipo de proyecto → luego un segundo → luego un asistente.
- **Optimizar demasiado pronto.** Una plantilla después de tu primer proyecto es optimización prematura. Después de tu segundo proyecto DEL MISMO TIPO es el momento correcto.
- **Plantilla = copia de tu último proyecto.** No copies a ciegas. Quita los datos propios del cliente, pon marcadores, agrega una lista de "qué reemplazar". Si no, el siguiente cliente recibe los datos del anterior.
- **Nunca actualizar tus plantillas.** Las API cambian y las buenas prácticas evolucionan. Después de cada 3er proyecto, revisa la plantilla: ¿qué podría estar mejor?

---

## Lecciones relacionadas

- **→ [Empaquetado](42-packaging.md)**: los paquetes Básico/Pro/Empresarial = configuraciones ya hechas para tu fábrica
- **→ [Entrega y conservación de clientes](46-delivery-retention.md)**: el paquete de entrega de esa lección = parte del SOP de tu siguiente proyecto
- **→ [Casos de monetización](47-monetization-cases.md)**: los patrones de los 5 casos = la base para 5 tipos de plantillas

---

## Herramientas y recursos

- **GitHub**: un repositorio privado para guardar tus plantillas (para que no se pierdan entre computadoras)
- **Cookiecutter** (Python): una herramienta para crear proyectos a partir de plantillas desde la línea de comandos
- **Notion**: [notion.com/templates](https://www.notion.com/templates), para guardar los documentos SOP (fáciles de buscar y organizar)
- **GitHub Actions**: pruebas automáticas de tus plantillas cada vez que cambian
- **Loom**: [loom.com](https://www.loom.com/), para grabar videos de los SOP y poder pasarle el trabajo a un asistente
- **Upwork**: [upwork.com](https://www.upwork.com/), para contratar a un asistente para tareas operativas cuando tu fábrica ya funcione
- **Fiverr**: [fiverr.com](https://www.fiverr.com/), para contrataciones rápidas de tareas puntuales (diseño, pruebas)
- **Contra**: [contra.com](https://contra.com/), una plataforma para freelancers; a octubre de 2026 dice que los freelancers no pagan comisión

---

## Ideas clave

> 80% estándar + 20% personalización: esa es la fórmula de la fábrica. No 100% a la medida cada vez.

> Más rápido = más caro. La paradoja de la fábrica: entre menos tiempo dedicas, más puedes pedir muchas veces. Los clientes valoran el resultado, no el proceso.

> Un SOP es para ti, no para el cliente. Documenta el proceso para que el siguiente proyecto de este tipo salga casi en piloto automático.

> Empieza a construir una plantilla después de tu segundo proyecto. Antes es optimización prematura; después es tiempo perdido.

---

## Siguiente lección

→ [Graduación](49-graduation.md): tu plan de negocio con IA a 30-60-90 días
