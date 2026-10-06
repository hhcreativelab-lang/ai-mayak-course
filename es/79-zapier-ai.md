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
- **AI by Zapier**: un paso integrado que llama a un modelo de lenguaje (puedes elegir modelos de OpenAI, Anthropic, Google y otros) directamente dentro de un Zap
- **Zapier Agents**: los agentes de Zapier, que deciden por su cuenta qué herramientas usar para una tarea. Zapier los está pasando ahora al paso AI by Zapier
- **Zapier Tables**: la base de datos integrada de Zapier, que también puede hacer análisis con IA
- **Webhook**: una forma universal de recibir datos de cualquier fuente, incluso de una que no tiene integración oficial (planes de pago)
- **Tarea (task)**: la unidad de cobro. Cada acción que un Zap completa con éxito gasta tareas; el disparador no (consulta el centro de ayuda de Zapier para ver exactamente cómo se cuentan)
- **Zap de varios pasos**: un Zap con más de dos pasos. Está disponible en los planes de pago y durante la prueba gratis, y es donde ocurre el trabajo de verdad

---

## Teoría

### Zapier vs Make vs n8n: cuál elegir y cuándo

En la automatización sin código hay tres jugadores principales. Cada uno tiene su nicho.

| Criterio | Zapier | Make | n8n |
|---|---|---|---|
| Integraciones | Más de 9,000 apps (según Zapier, octubre de 2026) | Más de 3,000 apps (según Make, octubre de 2026) | cientos de nodos listos + solicitudes HTTP a cualquier servicio |
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

- Necesitas ramificaciones complejas y mucho volumen: Make cobra en créditos y, con volúmenes altos, muchas veces sale más barato. Compara las dos páginas de precios con tus propios números
- Los datos no pueden pasar por servidores ajenos: n8n en tu propio servidor
- El presupuesto es muy chico y no hay muchas tareas: el plan de pago de entrada de Make cubre muchas necesidades

---

### AI by Zapier: el cerebro dentro de un Zap

"AI by Zapier" es un paso integrado en el editor de Zaps. Le manda a un modelo de lenguaje tu prompt y los datos de los pasos anteriores. Puedes elegir el modelo: hay modelos de OpenAI, Anthropic (Claude), Google y otras empresas.

**Qué puede hacer AI by Zapier:**

- Analizar texto (un correo, una solicitud, una reseña)
- Clasificar datos (cliente potencial caliente o frío, reseña positiva o negativa)
- Generar texto (un borrador de respuesta a un correo, la descripción de un producto)
- Extraer datos estructurados (sacar un nombre, una empresa y un presupuesto de un texto desordenado)
- Traducir y adaptar contenido

**Cómo se ve en el editor:**

El paso "AI by Zapier" tiene dos paneles:

- **Configure**: aquí escribes tu prompt (el campo Prompt), eliges el modelo y ajustas la configuración. Los datos de pasos anteriores se insertan en el prompt escribiendo "/"
- **Preview**: una prueba que muestra qué devuelve el paso con datos reales de ejemplo

La respuesta de la IA pasa a los siguientes pasos. Si hace falta, puedes dividirla en campos separados (la sección Output Fields). En los ejemplos de abajo, las llaves dobles `{{...}}` marcan el lugar donde insertas un campo de un paso anterior.

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

La IA procesa la solicitud y devuelve su respuesta en JSON (un formato para escribir datos que los programas pueden leer). El siguiente paso lo lee y manda una notificación al vendedor indicado.

🎨 **Imagínalo así:** antes, una solicitud nueva de tu sitio web caía en el CRM y se quedaba ahí hasta que un vendedor tuviera tiempo. Ahora la IA la lee en segundos, la marca como "caliente" y le manda al vendedor una notificación que dice "llama ahora mismo". Mientras antes alguien llame a un cliente potencial caliente, mejores son las probabilidades de cerrar la venta.

---

### Zapier Agents: una IA que elige sus propias herramientas

Zapier Agents va más allá de los Zaps clásicos. Un agente es una IA que:

- Arranca sola, por un evento o según un horario
- Puede decidir por su cuenta qué herramientas usar (leer Gmail, publicar en Slack, agregar un contacto a un CRM)
- Puede buscar respuestas en las fuentes de conocimiento que conectes y en la web
- Recibe instrucciones en lenguaje común

**Lo que está cambiando (a octubre de 2026):** Zapier está pasando el producto independiente Agents (agents.zapier.com) al paso AI by Zapier. Ahora puedes darle herramientas a ese paso (apps y fuentes de conocimiento), y actúa como agente directamente dentro de un Zap. Zapier no ha fijado una fecha para apagar el Agents independiente y dice que avisará a los usuarios por correo con tiempo.

**Un ejemplo real de agente:**
"Eres mi asistente de ventas. Cada vez que llegue a Gmail un correo con la etiqueta 'de un cliente potencial', léelo, escribe un resumen corto, busca información sobre la empresa, agrega el contacto a HubSpot y mándame una notificación por Slack con un plan corto para la llamada."

Es un solo agente que reemplaza 4-5 Zaps manuales, y trabaja de forma más inteligente: entiende el contexto en lugar de solo mover datos de un lugar a otro.

**Limitaciones de los Agents (a octubre de 2026):**

- El producto independiente Agents se cobra aparte, en "actividades" y no en tareas. Un paso de IA con herramientas dentro de un Zap gasta tareas normales
- Son menos predecibles (la IA toma sus propias decisiones)
- Encajan peor en procesos muy bien definidos

Para la mayoría de las tareas de negocio, los Zaps clásicos con pasos de IA son la mejor opción: son más predecibles y puedes ver qué pasó en cada paso.

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

Una transacción nueva en Stripe → la IA revisa si tiene algo raro (un monto poco común, una región nueva, una primera compra) → si algo no cuadra → una notificación por Slack con una explicación. Aquí la IA solo avisa; qué hacer con el pago lo decide una persona.

---

### Cuánto cuesta de verdad

**Zapier Free:** 100 tareas/mes, solo Zaps de dos pasos. En este plan, el paso de IA solo se puede probar en un Zap sin publicar. Bueno para conocer la herramienta.

**Zapier Professional:** a octubre de 2026, desde $19.99/mes con pago anual ($29.99 con pago mensual), 750 tareas, Zaps de varios pasos, webhooks, AI by Zapier. Es el mínimo para escenarios reales.

**Zapier Team:** a octubre de 2026, desde $69/mes con pago anual ($103.50 con pago mensual), más tareas, varios usuarios (hasta 25).

Precios y versiones actuales: [Lo vigente](https://aimayak.com/now/).

**Trampas del cobro:**

- Cada acción completada gasta tareas; el disparador no. Un ejemplo: un Zap con un disparador y 4 acciones que se ejecuta 100 veces al día = 400 tareas al día = 12,000 tareas al mes. La cantidad inicial de los planes de pago no alcanza para eso.
- Un paso de IA gasta tareas con un multiplicador: depende del nivel del modelo (Standard, Advanced, Premium), y cada llamada a una herramienta se cuenta aparte. En un plan de pago, un paso de IA nuevo viene por defecto en Premium, el nivel más caro, así que revísalo y elige el nivel tú mismo. Los multiplicadores están en el artículo de ayuda de Zapier "AI by Zapier model tier pricing"
- Vigila tu consumo en tu cuenta de Zapier. Un paso de IA tiene un límite de tareas por ejecución: si una ejecución lo supera, el paso se pausa y espera tu aprobación

**Una estimación realista para un pequeño negocio:**

- 5-10 Zaps
- Cada uno se ejecuta 20-50 veces al día
- Cada Zap tiene 3-4 pasos: un disparador y 2-3 acciones
- Total: desde 6,000 tareas al mes (5 Zaps × 20 ejecuciones × 2 acciones × 30 días) hasta 45,000 (10 × 50 × 3 × 30). Es más que la cantidad inicial de los planes de pago, así que tendrás que elegir un volumen de tareas mayor y revisar su precio en la página de precios

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

Un webhook en Zapier es una URL única a la que cualquier programa puede mandar datos. Si tu app no tiene una integración oficial con Zapier, no hay problema. Los webhooks están disponibles en los planes de pago.

**Cómo funciona:**

1. Creas un Zap con el disparador "Webhooks by Zapier" y el evento Catch Hook
2. Zapier te da una URL única como `https://hooks.zapier.com/hooks/catch/1234567/abc123`
3. Cualquier app que pueda hacer una solicitud HTTP POST puede mandar datos a esa URL
4. Los datos llegan al Zap y siguen por los siguientes pasos

**Un ejemplo práctico:**
Un cliente tiene un CRM hecho a la medida sobre WordPress, sin integración con Zapier. Un desarrollador agrega unas cuantas líneas de código: cuando llega un cliente potencial nuevo, los datos del contacto se mandan a la URL del webhook de Zapier. A partir de ahí, Zapier pasa los datos por la IA y manda notificaciones a Slack o por mensaje de texto. Poco trabajo para el desarrollador, y una automatización funcionando para el cliente.

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
DISPARADOR: Gmail → New Email Matching Search (búsqueda: "label:potential-client")
↓
PASO 2: Formatter by Zapier → Text → Extract Phone Number
  → Saca el número de teléfono del texto del correo
↓
PASO 3: AI by Zapier (campos de salida: name, company, score, reason, next_action)
  Prompt:
  """
  Correo de: {{Sender}}
  Asunto: {{Subject}}
  Cuerpo: {{Body}}
  
  Encuentra en el correo el nombre del remitente y su empresa.
  Califica a este cliente potencial en una escala del 1 al 10 y explica por qué.
  Siguiente acción: llamar / escribir / no responder.
  """
↓
PASO 4: HubSpot → Create or Update Contact
  → Name: {{Step 3 - name}}
  → Company: {{Step 3 - company}}
  → Phone: {{Step 2 - Output}}
  → Note: {{Step 3 - reason}}
  → Tu propio campo de contacto "Puntuación de IA": {{score}}
↓
PASO 5 (condición): Filter by Zapier → Solo si score >= 7
↓
PASO 6: Slack → Send Channel Message, canal #sales
  → "Cliente potencial caliente: {{name}} de {{company}}
     Puntuación: {{score}}/10
     Motivo: {{reason}}
     Acción: {{next_action}}
     Correo: {{Gmail Link}}"
```

Tiempo de configuración: alrededor de una hora la primera vez. Cuánto tiempo le ahorra a tu vendedor depende de cuántos correos lleguen, así que calcúlalo con tus propios números.

---

## Práctica

### Paso 1: Crea una cuenta y tu primer Zap

Cuando creas una cuenta nueva, Zapier activa automáticamente una prueba gratis de 14 días del plan Professional, sin tarjeta. Durante la prueba funcionan tanto un Zap de tres pasos como AI by Zapier. Cuando termina la prueba, un Zap como este se apaga hasta que pases a un plan de pago.

1. Entra a [zapier.com](https://zapier.com) → Sign up (registrarse es gratis)
2. En el menú de la izquierda, haz clic en **+ Create** → **Zap workflows** (en algunas versiones el botón se llama **Create a Zap**)
3. Ya estás en el editor de Zaps. Los pasos están a la izquierda y la configuración del paso elegido a la derecha

### Paso 2: Configura el disparador

Para esta práctica, conecta un buzón personal o de prueba. Los correos van a pasar por Zapier y por un modelo de IA, así que no conectes un buzón de trabajo con datos de otras personas sin permiso.

1. Haz clic en el primer paso (Trigger)
2. Elige **Gmail** (u otra app que uses)
3. En el campo **Trigger event**, elige **New Email**
4. En el campo **Account**, conecta tu Gmail (**+ Connect a new account**)
5. En la pestaña **Configure**, elige de qué carpeta tomar los correos (Inbox)
6. En la pestaña **Test**, haz clic en **Test trigger**: Zapier muestra un correo reciente como dato de ejemplo. Selecciónalo y haz clic en **Continue with selected record**

### Paso 3: Agrega un paso de IA

1. Haz clic en **+** después del disparador
2. Busca y elige **AI by Zapier**: el paso se abre en el editor
3. Junto al campo Prompt, abre la lista de modelos y elige el nivel Standard: alcanza para una tarea así y gasta menos tareas
4. En el campo **Prompt**, escribe el texto de abajo. Donde veas llaves, inserta un campo del correo: escribe "/" y elígelo de la lista
   ```
   Eres un asistente de ventas. Analiza este correo:
   
   De: {{From Name}}
   Asunto: {{Subject}}
   Cuerpo: {{Body Plain}}
   
   Escribe un resumen corto (2-3 oraciones) y decide: ¿vale la pena responderlo?
   Respuesta: [resumen] | Prioridad: Alta/Media/Baja
   ```
5. Haz clic en **Preview**, mira lo que escribió la IA y luego haz clic en **Finish**

### Paso 4: Manda el resultado a Slack (o recíbelo por correo o mensaje de texto)

Necesitas un espacio de Slack donde puedas publicar en un canal. Si no usas Slack, elige una de las otras opciones de abajo.

1. Agrega un paso más con **+**
2. Elige **Slack** (para recibir un correo o un mensaje de texto, elige Gmail o una app de SMS; los campos serán un poco distintos)
3. En el campo **Action event**, elige **Send Channel Message**
4. Channel: elige el que quieras
5. Message Text: escribe el texto de abajo. Las palabras entre llaves son campos de pasos anteriores: haz clic en el ícono de más (+) del campo y elige el que necesitas de la lista
   ```
   📧 Correo nuevo de {{From Name}}
   
   {{AI by Zapier - Response}}
   
   Original: {{Message URL}}
   ```
6. Haz clic en **Test step**: el mensaje aparecerá en Slack

### Paso 5: Enciende el Zap y pruébalo

1. Arriba a la derecha, haz clic en **Publish**: eso enciende el Zap
2. Mándate un correo de prueba desde otra dirección de correo (el Zap solo procesa los correos que llegan después de publicarlo)
3. Espera unos minutos (Zapier revisa si hay correos nuevos según un horario; la frecuencia depende de tu plan)
4. Revisa el resultado: en Slack debe aparecer un mensaje con el análisis del correo hecho por la IA

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
- **[Precios de Zapier](https://zapier.com/pricing)**: planes actuales y volúmenes de tareas.
- **[Zapier Learn](https://learn.zapier.com)**: cursos gratis sobre Zapier (en inglés).
- **[Documentación de AI by Zapier](https://help.zapier.com/hc/en-us/articles/8496342944013-Use-AI-by-Zapier-to-analyze-and-return-data)**: el artículo de ayuda oficial del paso de IA (en inglés).

---

## Ideas clave

> "Zapier no es solo automatización. Es una forma de darle funciones de IA a un negocio pequeño sin una sola línea de código. Tu valor como especialista está en entender qué flujo de trabajo necesita el cliente y armarlo rápido."

> "AI by Zapier convierte un Zap de cartero en un asistente listo. No solo 'llegó un correo → lo reenvié', sino 'llegó un correo → lo entendí → tomé una decisión → actué'. Esa es la diferencia entre automatización e inteligencia."

> "Los servicios de automatización con Zapier no requieren programar. Necesitas entender los procesos del negocio del cliente y saber cómo automatizarlos. Lo que ganes depende de tu mercado y de tus clientes; nada está garantizado."

---

## Siguiente lección

→ [Precios de Claude Code: ¿Free, Pro, Max, Team o API?](05c-access-levels-pricing.md): qué comprar, y cuándo, para abrir Claude Code

En la biblioteca, opcional: [Entornos aislados para IA: E2B](80-ai-sandboxes-e2b.md): E2B y Modal para que los agentes ejecuten código de forma segura
