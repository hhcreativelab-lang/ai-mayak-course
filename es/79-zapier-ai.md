# Zapier AI: miles de apps y Zaps inteligentes con IA

**Tiempo:** unos 20 min de lectura + 30 min de práctica

---

## Lo esencial

Imagina que tienes un intérprete universal que habla a la vez los idiomas de miles de programas distintos. Gmail habla su propio idioma, Notion habla otro, Stripe otro más. Zapier es ese intérprete: recibe una señal de una app y se la pasa a otra, cambiando de "idioma" en el camino. Los pasos de IA en Zapier son el cerebro del intérprete. En lugar de reenviar datos de forma mecánica, decide qué decir y cómo: analiza, clasifica, escribe una respuesta, toma una decisión.

🎨 **Imagínalo así:** Zapier sin IA es un cartero. Recoge un sobre aquí y lo deja allá. Zapier con IA es un asistente de oficina muy listo. Toma la carta, la lee, entiende de qué se trata, escribe una respuesta en el tono correcto y se la manda a la persona indicada. Esa es la diferencia entre mecánica e inteligencia.

En esta lección vas a conocer Zapier AI, una de las herramientas sin código (no-code) más conocidas. Vas a aprender a armar Zaps con pasos de IA, a ver cuándo Zapier les gana a sus competidores y a crear tu primer flujo de trabajo automático e inteligente sin escribir una sola línea de código.

---

## Conceptos clave

- **Zap**: una automatización con 2 o más pasos: un disparador (un evento) + una acción (qué hacer)
- **AI by Zapier**: un paso integrado que llama a Claude o a ChatGPT directamente dentro de un Zap
- **Zapier Agents**: agentes autónomos en Zapier que trabajan sin que nadie los dispare a mano
- **Zapier Tables**: la base de datos integrada de Zapier, que también puede hacer análisis con IA
- **Webhook**: una forma universal de recibir datos de cualquier fuente (incluso una que no tiene integración oficial)
- **Tarea (task)**: la unidad de cobro. Las acciones de un Zap gastan tareas cada vez que se ejecuta (consulta el centro de ayuda de Zapier para ver exactamente cómo se cuentan)
- **Zap de varios pasos**: un Zap con 3 o más pasos (solo en planes de pago), y donde ocurre el trabajo de verdad

---

## Teoría

### Zapier vs Make vs n8n: cuál elegir y cuándo

En la automatización sin código hay tres jugadores principales. Cada uno tiene su nicho.

| Criterio | Zapier | Make | n8n |
|---|---|---|---|
| Integraciones | Miles de apps (consulta el sitio de Zapier) | Miles de apps (consulta el sitio de Make) | cientos de nodos listos + HTTP |
| Curva de aprendizaje | Mínima | Media | Empinada |
| Plan gratis | 100 tareas/mes, solo Zaps de dos pasos | 1,000 créditos/mes | Community Edition en tu propio servidor |
| Planes de pago desde (a octubre de 2026) | $19.99/mes con pago anual (750 tareas) | Core desde $9/mes con pago mensual (10,000 créditos) | Cloud Starter €20/mes con pago anual (2,500 ejecuciones) |
| Pasos de IA | Integrados (AI by Zapier, Agents, Copilot) | Make AI Agents | Nodos AI Agent y LLM, MCP |
| Para quién es | Personas sin perfil técnico, pequeños negocios | Usuarios técnicos, escenarios complejos | Desarrolladores, equipos que priorizan la privacidad |
| Dónde corre | Nube | Nube | En tu propio servidor o en la nube |

Precios y versiones actuales: [Lo vigente](https://aimayak.com/now/).

🎨 **Imagínalo así:** Zapier es como un iPhone. Cuesta más, pero funciona desde que lo sacas de la caja, se ve bien y hay una app para todo. Make es como Android: más barato, más flexible, y hay que entenderle un poco. n8n es como Linux: control total, pero te vas a tener que arremangar.

**Cuándo gana Zapier:**

- El cliente quiere "déjalo listo y ya, yo me encargo después": Zapier es el más intuitivo
- Necesitas una integración poco común (un CRM hecho a la medida, un servicio local): miles de integraciones listas te cubren
- Importan el soporte y las garantías de disponibilidad: revisa las condiciones del plan
- Un equipo sin formación técnica va a ajustar los Zaps por su cuenta

**Cuándo gana Make o n8n:**

- Necesitas ramificaciones complejas con cientos de miles de operaciones al mes: Make es más barato
- Los datos no pueden pasar por servidores ajenos: n8n en tu propio servidor
- El presupuesto es muy chico y no hay muchas tareas: el plan de pago de entrada de Make cubre muchas necesidades

---

### AI by Zapier: el cerebro dentro de un Zap

"AI by Zapier" es el paso oficial del editor de Zaps que llama a un modelo de lenguaje (uno de los disponibles en Zapier, como Claude o ChatGPT) con tu prompt y los datos de los pasos anteriores.

**Qué puede hacer AI by Zapier:**

- Analizar texto (un correo, una solicitud, una reseña)
- Clasificar datos (cliente potencial caliente o frío, reseña positiva o negativa)
- Generar texto (un borrador de respuesta a un correo, la descripción de un producto)
- Extraer datos estructurados (sacar un nombre, una empresa y un presupuesto de un texto desordenado)
- Traducir y adaptar contenido

**Cómo se ve en el editor:**

El paso "AI by Zapier" tiene dos campos:

- **Prompt**: tu solicitud a la IA (puedes insertar datos de pasos anteriores con `{{variable}}`)
- **Response**: la respuesta de la IA, que pasa a los siguientes pasos

Un ejemplo de prompt para clasificar a un cliente potencial:
```
Analiza esta solicitud que llegó desde nuestro sitio web:
Nombre: {{Name}}
Empresa: {{Company}}
Mensaje: {{Message}}

Determina:
1. Temperatura del cliente potencial: caliente / tibio / frío
2. Presupuesto: indicado / no indicado / grande (>$10k)
3. Siguiente paso: llamar hoy / mandar un correo / marcar como spam

Responde solo con JSON:
{"temperature": "...", "budget": "...", "next_step": "..."}
```

La IA procesa la solicitud y devuelve un JSON, que el siguiente paso lee para mandar una notificación al vendedor indicado.

🎨 **Imagínalo así:** antes, una solicitud nueva de tu sitio web caía en el CRM y se quedaba ahí hasta que un vendedor tuviera tiempo. Ahora la IA la lee en segundos, la marca como "caliente" y le manda al vendedor una notificación que dice "llama ahora mismo". Mientras antes alguien llame a un cliente potencial caliente, mejores son las probabilidades de cerrar la venta.

---

### Zapier Agents: trabajo autónomo sin disparadores

Zapier Agents es una función que va más allá de los Zaps clásicos. Un agente es una IA que:

- Funciona todo el tiempo, sin que nadie la ponga en marcha a mano
- Puede decidir por su cuenta qué herramientas usar (leer Gmail, publicar en Slack, agregar un contacto a un CRM)
- Recuerda lo que hizo antes
- Recibe instrucciones en lenguaje común

**Un ejemplo real de agente:**
"Eres mi asistente de ventas. Cada vez que llegue a Gmail un correo con la etiqueta 'de un cliente potencial', léelo, escribe un resumen corto, busca información sobre la empresa, agrega el contacto a HubSpot y mándame una notificación por Slack con un plan corto para la llamada."

Es un solo agente que reemplaza 4-5 Zaps manuales, y trabaja de forma más inteligente: entiende el contexto en lugar de solo mover datos de un lugar a otro.

**Limitaciones de los Agents:**

- Se cobran aparte de las tareas de los Zaps normales (revisa en la página de precios de Zapier cómo)
- Son menos predecibles (la IA toma sus propias decisiones)
- Encajan peor en procesos muy bien definidos

Para la mayoría de las tareas de negocio, los Zaps clásicos con pasos de IA son la mejor opción: son predecibles, transparentes y baratos.

---

### Zapier Tables + IA: una base de datos con cerebro

Zapier Tables es una base de datos integrada, con forma de hoja de cálculo, que se conecta de manera nativa con los Zaps. Agregas un registro → un Zap arranca solo. El Zap procesa los datos → el resultado regresa a la tabla.

**Caso: una base de clientes enriquecida con IA:**

1. Un cliente llena un formulario → un registro nuevo en Zapier Tables
2. Disparador: registro nuevo → el Zap arranca
3. Paso de IA: a partir del nombre y la empresa, genera una hipótesis de lo que necesita el cliente
4. Paso de enriquecimiento: un servicio de enriquecimiento de datos agrega información sobre la empresa
5. El resultado se escribe de vuelta en la tabla, en un campo "Análisis de IA"
6. Un vendedor abre la tabla, y cada cliente potencial ya tiene contexto

Sin una base de datos externa, sin código. Todo vive en una sola herramienta.

---

### Casos de uso principales

**1. Enriquecimiento del CRM y reparto de clientes potenciales**

Llega un cliente potencial por un formulario del sitio web → la IA lo clasifica por temperatura, presupuesto e industria → los calientes van al mejor vendedor por Slack, los fríos entran a una secuencia de correos en Mailchimp, y el spam se borra.

**2. Distribución de contenido**

Una publicación nueva en Notion (un borrador) → AI by Zapier la adapta para una página de Facebook (corta, con emoji) → otro paso de IA la adapta para LinkedIn (un tono profesional) → se publica en ambos canales de forma automática.

**3. Clasificación de correos**

Un correo nuevo en Gmail → la IA lo lee y lo clasifica: cliente / socio / spam / urgente → los correos urgentes de clientes disparan un mensaje de texto (SMS) a tu celular, y ya te espera un borrador de respuesta escrito por la IA, así que solo falta presionar "Enviar".

**4. Reseñas y reputación**

Una reseña nueva en Google Maps → la IA analiza el tono → negativa: una notificación al encargado + un borrador de respuesta → positiva: se publica en tu sitio web de forma automática a través del CMS.

**5. Monitoreo financiero**

Una transacción nueva en Stripe → la IA revisa si tiene algo raro (un monto poco común, una región nueva, una primera compra) → si algo no cuadra → una notificación por Slack con un análisis del riesgo.

---

### Cuánto cuesta de verdad

**Zapier Free:** 100 tareas/mes, solo Zaps de dos pasos. Bueno para aprender.

**Zapier Professional:** a octubre de 2026, desde $19.99/mes con pago anual ($29.99 con pago mensual), 750 tareas, Zaps de varios pasos, AI by Zapier. Es el mínimo para escenarios reales.

**Zapier Team:** a octubre de 2026, desde $69/mes con pago anual ($103.50 con pago mensual), más tareas, varios usuarios (hasta 25).

Precios y versiones actuales: [Lo vigente](https://aimayak.com/now/).

**Trampas del cobro:**

- Las acciones de un Zap gastan tareas en cada ejecución. Cuentas sencillas: un Zap de 5 pasos que se ejecuta 100 veces al día = 500 tareas al día = 15,000 tareas al mes. La cantidad inicial de los planes de pago no alcanza para eso.
- Los pasos de IA se cobran aparte: por paso y por cada llamada a una herramienta (condiciones en la página de precios)
- Vigila tu consumo en el panel de Zapier y pon límites a tus Zaps

**Una estimación realista para un pequeño negocio:**

- 5-10 Zaps
- Cada uno se ejecuta 20-50 veces al día
- Largo promedio de un Zap: 3-4 pasos
- Total: unas 3,000-6,000 tareas/mes. Es más que la cantidad inicial de los planes de pago, así que tendrás que elegir un volumen de tareas mayor y revisar su precio en la página de precios

---

### "Zapier como servicio": vender automatización

No todos los clientes necesitan código. Muchos solo necesitan automatizaciones que funcionen.

**Qué vender:**

*Paquete 1: "Inicial" (pago único):*

- Una revisión de los procesos manuales actuales del cliente
- 3-5 Zaps básicos (sin IA)
- Configuración y entrega de accesos
- 30 días de soporte

*Paquete 2: "Automatización con IA" (pago único):*

- Lo mismo, pero con AI by Zapier en los pasos clave
- Enriquecimiento del CRM o clasificación de correos
- Documentación y capacitación del equipo

*Paquete 3: "Iguala" (mensual):*

- 2-3 horas al mes para mejorar los Zaps
- Monitoreo de errores
- Nuevas automatizaciones a medida que el cliente crece

**Dónde encontrar clientes:**

- Pequeños negocios con un equipo de 3-15 personas: muchas veces están ahogados en tareas manuales
- Tiendas en línea en Shopify o WooCommerce: captación de clientes potenciales, carritos abandonados, reseñas
- Agencias y despachos (marketing, bienes raíces, abogados): mucho trabajo repetitivo con documentos

**El argumento de venta principal:**
"Le voy a ahorrar a tu encargado de oficina N horas a la semana. Multiplica N por lo que cuesta una hora de su tiempo y por cuatro semanas: ese es tu ahorro mensual. Compáralo con mi precio y con el costo del plan de Zapier." Haz las cuentas con honestidad usando los datos del propio cliente, y no prometas ahorros que no puedas respaldar. Para calcular tu precio, revisa las lecciones [Empaqueta tus servicios de IA](42-packaging.md) y [Cómo ponerle precio a los servicios de IA](39-monetization-pricing.md).

---

### Webhooks: recibir datos de cualquier fuente

Un webhook en Zapier es una URL única a la que cualquier programa puede mandar cualquier dato. Si tu app no tiene una integración oficial con Zapier, no hay problema.

**Cómo funciona:**

1. Creas un Zap con el disparador "Webhooks by Zapier"
2. Zapier te da una URL única como `https://hooks.zapier.com/hooks/catch/1234567/abc123`
3. Cualquier app que pueda hacer una solicitud HTTP POST puede mandar datos a esa URL
4. Los datos llegan al Zap y siguen por los siguientes pasos

**Un ejemplo práctico:**
Un cliente tiene un CRM hecho a la medida sobre WordPress, sin integración con Zapier. Un desarrollador agrega una línea de PHP: cuando llega un cliente potencial nuevo, se manda un HTTP POST con los datos del contacto al webhook de Zapier. A partir de ahí, Zapier pasa los datos por la IA y manda notificaciones a Slack o por mensaje de texto. Treinta minutos de trabajo para el desarrollador. Una automatización funcionando para el cliente.

---

### Zapier vs Claude Code: cuándo usar cuál

No es una competencia. Son dos herramientas para trabajos distintos.

| Escenario | Herramienta |
|---|---|
| Conectar 2 apps SaaS populares sin lógica a la medida | Zapier |
| El presupuesto del cliente es justo y tiene que ser rápido | Zapier |
| El cliente quiere editar las automatizaciones por su cuenta | Zapier |
| Lógica compleja a la medida, datos poco comunes | Claude Code |
| Necesitas control total y tu propio servidor | Claude Code |
| El trabajo necesita una interfaz compleja o un panel | Claude Code |
| Un volumen muy alto de operaciones (caro en Zapier) | Claude Code |
| Necesitas integrarte con una API poco común | Claude Code + Webhook |

**La regla de oro:** empieza con Zapier. Si te topas con los límites o la complejidad se sale de control, pásate al código. Mientras el escenario sea sencillo, pagar un plan de Zapier suele salirle al cliente más barato que un desarrollo a la medida desde cero.

---

### Un Zap real: Correo → CRM → Slack

**La tarea:** los correos nuevos de clientes potenciales entran solos al CRM con un análisis de IA, y el vendedor recibe una notificación.

**Configuración:**

```
DISPARADOR: Gmail → New Email (Matching Search: "label:potential-client")
↓
PASO 2: Formatter by Zapier → Extract from Text
  → Extraer: Nombre, Empresa, Teléfono
↓
PASO 3: AI by Zapier → "Analiza este correo y califica la calidad del cliente potencial"
  Prompt:
  """
  Correo de: {{Sender}}
  Asunto: {{Subject}}
  Cuerpo: {{Body}}
  
  Califica a este cliente potencial en una escala del 1 al 10 y explica por qué.
  Devuelve JSON: {"score": N, "reason": "...", "next_action": "call/email/ignore"}
  """
↓
PASO 4: HubSpot → Create/Update Contact
  → Name: {{Step 2 - Name}}
  → Company: {{Step 2 - Company}}
  → Note: {{Step 3 - AI Response}}
  → Tag: "Puntuación de IA: {{score}}"
↓
PASO 5 (condición): Filter by Zapier → Solo si score >= 7
↓
PASO 6: Slack → Send Message to #sales
  → "Cliente potencial caliente: {{Name}} de {{Company}}
     Puntuación: {{score}}/10
     Motivo: {{reason}}
     Acción: {{next_action}}
     Correo: {{Gmail Link}}"
```

Tiempo de configuración: alrededor de una hora la primera vez. Cuánto tiempo le ahorra a tu vendedor depende de cuántos correos lleguen, así que calcúlalo con tus propios números.

---

## Práctica

### Paso 1: Crea una cuenta y tu primer Zap

1. Entra a [zapier.com](https://zapier.com) → Sign up (una cuenta gratis)
2. En el panel, haz clic en **"+ Create"** → **"Zap"**
3. Ya estás en el editor de Zaps. Los pasos están a la izquierda y la configuración a la derecha

### Paso 2: Configura el disparador

1. Haz clic en el primer paso (Trigger)
2. Elige **Gmail** (o cualquier app que uses)
3. Evento: **New Email**
4. Conecta tu cuenta de Gmail (haz clic en "Sign in")
5. Configura el filtro: Label = "Inbox"; puedes dejar From vacío
6. Haz clic en **"Test trigger"**: Zapier muestra tu correo más reciente como dato de ejemplo

### Paso 3: Agrega un paso de IA

1. Haz clic en **"+"** después del disparador
2. Busca **"AI by Zapier"**
3. Acción: **Analyze or generate text**
4. En el campo **Prompt**, escribe:
   ```
   Eres un asistente de ventas. Analiza este correo:
   
   De: {{From Name}}
   Asunto: {{Subject}}
   Cuerpo: {{Body Plain}}
   
   Escribe un resumen corto (2-3 oraciones) y decide: ¿vale la pena responderlo?
   Respuesta: [resumen] | Prioridad: Alta/Media/Baja
   ```
5. Haz clic en **"Test action"** y mira lo que generó la IA

### Paso 4: Manda el resultado a Slack (o recíbelo por correo o mensaje de texto)

1. Agrega un paso más con **"+"**
2. Elige **Slack** (para recibir un correo o un mensaje de texto, elige Gmail o una app de SMS; los campos serán un poco distintos)
3. Acción: **Send Channel Message**
4. Channel: elige el que quieras
5. Message Text:
   ```
   📧 Correo nuevo de {{From Name}}
   
   {{AI by Zapier - Response}}
   
   Original: {{Message URL}}
   ```
6. Haz clic en **"Test action"**: el mensaje aparecerá en Slack

### Paso 5: Enciende el Zap y pruébalo

1. Arriba a la derecha, cambia **"Zap is Off"** → **"Zap is On"**
2. Mándate un correo de prueba desde otra dirección de correo
3. Espera unos minutos (Zapier revisa los disparadores según un horario; la frecuencia depende de tu plan)
4. Recibe la notificación en Slack con el análisis de la IA

Felicidades: tu primer Zap inteligente con IA ya está funcionando.

**Qué probar después:**

- Agrega un filtro: procesa solo los correos que contengan ciertas palabras clave
- Conecta Google Sheets: registra en una hoja de cálculo cada correo analizado
- Agrega un segundo paso de IA: genera de forma automática un borrador de respuesta

---

## Herramientas y recursos

- **[Zapier](https://zapier.com)**: la herramienta principal de esta lección. Plan gratis: 100 tareas/mes; planes de pago desde $19.99/mes con pago anual, a octubre de 2026.
- **[Make.com](https://make.com)**: una alternativa para escenarios complejos. Tiene plan gratis: 1,000 créditos al mes.
- **[n8n.io](https://n8n.io)**: una alternativa que puedes correr en tu propio servidor. Nube desde €20 al mes con pago anual; la Community Edition para tu propio servidor es gratis (con la Sustainable Use License).
- **[Precios de Zapier](https://zapier.com/pricing)**: planes actuales y una calculadora de tareas.
- **[Zapier University](https://university.zapier.com)**: cursos gratis sobre Zapier.
- **[Documentación de AI by Zapier](https://help.zapier.com/hc/en-us/articles/16587495501453-Use-AI-by-Zapier)**: la documentación oficial del paso de IA.

---

## Ideas clave

> "Zapier no es solo automatización. Es una forma de darle funciones de IA a cualquier negocio sin una sola línea de código. Tu valor como especialista está en saber qué flujo de trabajo necesita el cliente y armarlo en horas, no en semanas."

> "AI by Zapier convierte un Zap de cartero en un asistente listo. No solo 'llegó un correo → lo reenvié', sino 'llegó un correo → lo entendí → tomé una decisión → actué'. Esa es la diferencia entre automatización e inteligencia."

> "Los servicios de automatización con Zapier no requieren programar. Necesitas entender los procesos del negocio del cliente y saber cómo automatizarlos. Lo que ganes depende de tu mercado y de tus clientes; nada está garantizado."

---

## Siguiente lección

→ [Entornos aislados para IA: E2B](80-ai-sandboxes-e2b.md): E2B y Modal para que los agentes ejecuten código de forma segura
