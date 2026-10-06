# Cómo empaquetar tus servicios de IA en tres ofertas claras

**Tiempo:** unos 30 min de lectura + 30 min de práctica

Las cantidades en dólares de los ejemplos de abajo son inventadas. Muestran cómo se arman los paquetes, no precios de mercado ni un pronóstico de ingresos. Calcula tu propio precio en la siguiente lección, [Precios basados en valor](39-monetization-pricing.md).

---

## Lo esencial

Sin un menú, el cliente no sabe qué pedir ni cuánto cuesta. Te pregunta "¿Y tú qué sabes hacer?", tú te lanzas a una explicación larga y la conversación no llega a ningún lado. Los paquetes son tu menú: tres opciones claras, cada una con una lista clara de lo que incluye y un precio. El cliente elige solo, y tú no tienes que regatear en cada paso.

---

## Conceptos clave

- **Servicio frente a producto**: un servicio es distinto cada vez, un producto se repite. Los paquetes hacen que un servicio funcione más como un producto
- **3 paquetes**: la psicología de la elección. Normalmente es más fácil elegir entre tres opciones que entre una, o entre cinco o más (una hipótesis de trabajo, no una ley)
- **Alcance**: una lista clara de lo que está incluido y lo que NO. Sin ella, el crecimiento del alcance (scope creep: el proyecto que va creciendo sin que nadie lo diga, más allá de lo acordado) es inevitable
- **SLA**: un acuerdo de nivel de servicio (Service Level Agreement). Tiempo de respuesta, disponibilidad (qué tan confiable sigue funcionando el sistema), cómo funciona el soporte
- **Documentación de entrega**: lo que el cliente recibe además del sistema mismo: instrucciones, capacitación, usuarios y accesos
- **Niveles de precio**: niveles que reflejan la cantidad de trabajo, la rapidez y el nivel de soporte

---

## Teoría

### Servicio frente a producto: cuál es la diferencia

**Un servicio** (como suelen vender los freelancers):
- Cada proyecto se negocia desde cero
- El precio no se sabe hasta que estimas el trabajo
- El cliente no sabe qué va a recibir
- Difícil de escalar, porque cada trabajo es nuevo

**Un servicio convertido en producto** (paquetes):
- El cliente ve las opciones por adelantado
- El precio se conoce antes de la primera llamada
- Un alcance claro de lo que incluye
- Más fácil de entregar, porque reutilizas plantillas y lo que aprendiste en proyectos anteriores

🎨 **Imagínalo así:** el menú de un restaurante. El chef sabe cocinar cientos de platillos, pero el menú tiene 30, cada uno con su precio. El cliente elige uno. No se pregunta "¿qué se puede pedir aquí?" ni regatea el precio de cada ingrediente.

---

### La psicología de los tres paquetes

🎨 **Imagínalo así:** los tres tamaños de vaso en una cafetería: chico, mediano, grande. El chico se ve diminuto junto al grande. Mucha gente pide el mediano, porque se siente como "la opción sensata". Esa percepción la diseñas a propósito.

La economía del comportamiento describe varios efectos en los que se basan los precios por niveles (el efecto señuelo se explica en el libro de Dan Ariely *Las trampas del deseo*, en inglés *Predictably Irrational*). Aquí va una hipótesis de trabajo que vale la pena probar con tus propios clientes:

- Con **una opción**, el cliente piensa "¿compro esto o no?"
- Con **tres opciones**, el cliente piensa "¿cuál de las tres compro?"
- Con **cinco opciones o más**, puede aparecer la parálisis de la elección, y el cliente pospone la decisión

La gente muchas veces elige la opción de en medio (a esto se le llama efecto de compromiso). El paquete de arriba hace que el de en medio se vea "razonable", y el de abajo resalta el valor del de en medio. Qué tan bien funciona esto en tu mercado te lo van a mostrar tus propias ventas.

**Tus metas al diseñar los paquetes:**
- Paquete de abajo (Basic): útil de verdad, pero con límites evidentes
- Paquete de en medio (Pro): el que quieres vender más seguido
- Paquete de arriba (Enterprise): hace que Pro se vea razonable, y además le queda de verdad a clientes más grandes

---

### Estructura de ejemplo para tres paquetes: automatización de un boletín

| | Basic | Pro | Enterprise |
|---|---|---|---|
| **Precio** | \$800 | \$2,200 | \$5,000 |
| **Qué construimos** | Boletín básico | Boletín + CRM (un sistema para llevar el registro de clientes) | Boletín + CRM + analítica + pruebas A/B (comparar dos versiones de un correo) |
| **Fuentes de noticias** | 1 (Perplexity) | 3 (Perplexity + RSS + a la medida) | Ilimitadas |
| **Destinatarios** | Hasta 500 | Hasta 5,000 | Ilimitados |
| **Infografías** | ❌ | ✅ (básicas) | ✅ (a la medida) |
| **Marca** | Plantilla | Adaptada a tu marca | Totalmente a la medida |
| **Documentación** | README | Video explicativo | SOP + capacitación del equipo |
| **Soporte** | 2 semanas por correo | 1 mes en Slack | 3 meses + SLA de 4 horas |
| **Plazo** | 5 días | 10 días | 3-4 semanas |

---

### Qué entra en el alcance: sé específico

🎨 **Imagínalo así:** un documento de alcance es como un menú con el precio junto a cada platillo. "Todo incluido" sin una lista significa que el cliente pide postre, luego otro postre, y luego dice "Pero dijiste que todo estaba incluido". Con un menú claro, sabe qué trae el combo y qué cuesta aparte.

El crecimiento del alcance es una razón frecuente por la que los proyectos terminan perdiendo dinero. En el camino, el cliente pide "cambios pequeños" que juntos duplican la cantidad de trabajo.

**Regla:** si el acuerdo no dice de forma explícita que algo está incluido, no está incluido.

**Plantilla de documento de alcance** (es una estructura, no un documento legal; pide a un abogado de tu país que revise tu contrato con el cliente):

```markdown
## Proyecto: Automatización del boletín, paquete Pro

### Incluido:
- Configuración y puesta en marcha del flujo principal
- Integración con Perplexity, canales RSS de noticias (hasta 3 fuentes) y tu dominio
- Plantilla de correo HTML adaptada a tu guía de marca
- Bot de Slack para aprobar cada número antes de que salga
- Registro en Google Sheets de cada envío
- Integración con tu CRM (Notion, HubSpot o Airtable, uno a tu elección)
- Video explicativo (Loom, ~20 min): cómo usar el sistema
- 30 días de soporte en Slack (respuesta en un día hábil)

### NO incluido en Pro (disponible como mejora aparte):
- Más de tres fuentes de noticias
- Pruebas A/B de los asuntos
- Panel de analítica
- Integración con plataformas de email marketing (Mailchimp, SendGrid); Pro envía solo por Gmail
- Traducción de los correos a varios idiomas
- Infografías a la medida (las básicas generadas con IA sí están incluidas)

### Condiciones:
- Pago: 50% por adelantado / 50% después de la demostración y la aprobación
- Plazo: 10 días hábiles a partir de recibir el anticipo y los accesos
- Revisiones: hasta 2 rondas incluidas
```

---

### SLA: que sea sencillo

🎨 **Imagínalo así:** un SLA es como tu acuerdo con un plomero. "Si se revienta un tubo en la noche, llego en menos de 4 horas. El mantenimiento de rutina se hace en horario de trabajo." El cliente sabe qué esperar. Tú sabes a qué te comprometiste. Sin sorpresas desagradables.

Un SLA no tiene que ser un documento legal. Para un pequeño negocio, bastan tres parámetros:

**1. Tiempo de respuesta a preguntas:**
- Basic: respuesta en 2 días hábiles por correo
- Pro: respuesta en un día hábil en Slack
- Enterprise: respuesta en 4 horas, incluidos los fines de semana

**2. Disponibilidad (para sistemas que funcionan solos):**
- Si el sistema deja de funcionar, te aviso en menos de 2 horas (en horario de trabajo)
- Arreglo: en un día hábil para problemas críticos

**3. Qué no está cubierto:**
- Caídas de servicios de terceros (API de Anthropic, API de Gmail, etcétera)
- Cambios en las API de terceros que rompan la integración (eso es un trabajo aparte)

---

### Documentación de entrega: qué recibe el cliente

🎨 **Imagínalo así:** la documentación es como el manual de una lavadora. El dueño no tiene idea de qué hay dentro del motor. Pero si el manual dice "presiona el botón 2 cuando veas el error E3", lo puede resolver solo. Tu meta: que el cliente pueda operar el sistema sin llamarte.

Una buena entrega es lo que separa a un profesional del freelancer promedio. Hay tres niveles:

**Basic: README.md (instrucciones por escrito)**

```markdown
# Automatización del boletín: instrucciones

## Cómo enviar el boletín
1. Abre Slack y escríbele al bot: "Enviar boletín"
2. Escribe el tema de esta semana
3. Espera la vista previa (normalmente 2-3 minutos)
4. Revisa el correo y haz clic en "Enviar" o "Editar"

## Dónde ver las estadísticas
Abre Google Sheets: [enlace]
Columnas: Fecha, Tema, Destinatarios, Estado

## Qué hacer si algo no funciona
1. Revisa que las claves de API en Cloudflare no hayan vencido (cada 90 días)
2. Escríbeme: [contacto]. Respondo en un día hábil
```

**Pro: video explicativo (Loom, 15-20 minutos; el plan gratis de Loom limita la duración de los videos, así que revisa las condiciones)**

Una grabación de pantalla donde muestras:
- Cómo ejecutar el flujo
- Cómo agregar un destinatario nuevo
- Dónde encontrar los registros y las estadísticas
- Cómo actualizar la guía de marca
- Qué hacer si algo se rompe

**Enterprise: SOP (procedimiento operativo estándar)**

Un documento completo de operación para el equipo del cliente. Incluye instrucciones para cada puesto, procedimientos para escalar problemas, un runbook (un manual paso a paso) para situaciones fuera de lo común y los contactos de soporte.

---

### Vender más a través de los paquetes: el camino natural

🎨 **Imagínalo así:** vender más a través de los paquetes funciona como un taller mecánico. Llegaste por un cambio de aceite, y el mecánico te muestra que pronto vas a tener que cambiar también las pastillas de freno. Ya estás ahí y ya le tienes confianza, así que tiene sentido. La lista de pendientes de un cliente es tu lista de "pastillas de freno casi gastadas" que notaste mientras hacías el trabajo.

Los paquetes crean puntos naturales de crecimiento:

```
Cliente Basic, 2 meses después:
"El sistema funciona muy bien. ¿Podemos agregar pruebas A/B para los asuntos?"
→ Sube a Pro, o un complemento aparte con su propio precio

Cliente Pro, 3 meses después:
"Necesitamos un panel para nuestra directora de marketing"
→ Sube a Enterprise, o un proyecto de analítica aparte
```

Para cada cliente, lleva una lista de pendientes (en inglés, backlog) con todo lo que mencionó como "estaría bien tener". Esa es tu lista de posibles ventas adicionales.

---

## Práctica

**Ejercicio: crea paquetes para tu propio servicio**

Toma un servicio que quieras ofrecer a clientes (por ejemplo, la idea que elegiste en las lecciones sobre el nicho) o un proyecto que ya hayas hecho.

1. Llena la tabla de tres paquetes:

| Parámetro | Basic (\$___) | Pro (\$___) | Enterprise (\$___) |
|---|---|---|---|
| Funciones principales | | | |
| Límites | | | |
| Documentación | | | |
| Soporte | | | |
| Plazo | | | |

2. Escribe un documento de alcance para el paquete Pro:
   - Una lista de "incluido" (al menos 5 puntos)
   - Una lista de "NO incluido" (al menos 3 puntos)
   - Condiciones de pago y de revisiones

3. Crea un SLA para Pro (3 parámetros: tiempo de respuesta, disponibilidad, qué no está cubierto)

4. Escribe una plantilla de README para el paquete Basic: cómo va a usar el cliente el sistema sin ti

**Meta:** un menú listo de tres paquetes que puedas mandarle a un cliente posible antes de la primera llamada.

---

## Referencia rápida: matriz de paquetes (una plantilla universal, cantidades inventadas)

| Parámetro | Basic (\$500-\$1,500) | Pro (\$1,500-\$5,000) | Enterprise (\$5,000-\$15,000) |
|---|---|---|---|
| **Funciones** | Flujo básico, 1 integración | Flujo completo, 2-3 integraciones | Todo + módulos a la medida |
| **Personalización** | Diseño de plantilla | Adaptado a la marca del cliente | Totalmente a la medida |
| **Fuentes de datos** | 1 | 2-3 | Ilimitadas |
| **Documentación** | README por escrito | Video en Loom + README | SOP + capacitación del equipo |
| **Soporte** | 2 semanas por correo | 1 mes en Slack (respuesta en un día hábil) | 3 meses + SLA de 4 horas |
| **Revisiones** | 1 ronda | 2 rondas | 3 rondas + revisión |
| **Plazo** | 3-5 días | 7-10 días | 2-4 semanas |
| **Pago** | 100% por adelantado | 50/50 | 30/40/30 |

Copia esta tabla y adáptala a tu propio servicio. El paquete de en medio (Pro) es el que quieres vender más seguido.

---

## Errores comunes

- **Las mismas funciones en Basic y en Pro.** Si la única diferencia es "el soporte", el cliente se va a llevar Basic. Basic debe FUNCIONAR, pero con límites evidentes (1 fuente, diseño de plantilla, soporte mínimo).
- **No escribir lo que "NO está incluido".** La lista de "NO incluido" te protege del crecimiento del alcance. Sin ella, el cliente da por hecho que "todo está incluido".
- **Saltos de precio demasiado grandes.** Basic \$500 → Enterprise \$15,000, y el cliente no ve la lógica. Basic \$800 → Pro \$2,200 → Enterprise \$5,000 es una progresión que tiene sentido.

---

## Lecciones relacionadas

- **→ [Precios basados en valor](39-monetization-pricing.md)**: la siguiente lección, sobre cómo calcular la base de los precios de tus paquetes a partir del valor para el cliente
- **→ [El modelo de fábrica](48-factory-model.md)**: las plantillas aceleran la entrega de los paquetes y suben tu margen (lo que te queda después de los costos); lección que viene más adelante
- **→ [Entrega y retención](46-delivery-retention.md)**: cómo entregarle un paquete al cliente de forma profesional; lección que viene más adelante

---

## Herramientas y recursos

- **Notion**: [notion.com/templates](https://www.notion.com/templates). Para una página pública con tus paquetes (la puedes insertar en tu portafolio)
- **Google Docs**: para documentos de alcance (fácil de compartir con el cliente para que lo revise)
- **Loom**: [loom.com](https://www.loom.com/). Para grabar el video explicativo del paquete Pro (el plan gratis tiene límites; mira el sitio web)
- **PandaDoc / Docusign**: para firmar electrónicamente el documento de alcance (cuando crezca tu volumen)
- **Stripe**: [stripe.com](https://stripe.com/). Recibe pagos; puedes crear un Payment Link (enlace de pago) para cada paquete. No está disponible en todos los países: a octubre de 2026, en América Latina solo abre cuentas en Brasil y México; la lista completa está en su sitio
- **Tally**: [tally.so](https://tally.so/). Formularios iniciales, con un plan gratis (el cliente llena un cuestionario antes de empezar el proyecto)
- **Calendly**: [calendly.com](https://calendly.com/). Un enlace para agendar una llamada, directo en tu página de paquetes

---

## Ideas clave

> Tres paquetes no son algo arbitrario. Muchas veces a la gente le resulta más fácil elegir entre tres opciones que entre una o cinco. Muchos se van a llevar la de en medio.

> Un documento de alcance protege a las dos partes. El cliente sabe qué va a recibir. Tú sabes qué construir. Sin decepciones.

> Un SLA no tiene que ser un documento legal. Tres parámetros sencillos (tiempo de respuesta, disponibilidad, qué no está cubierto) son suficientes para un pequeño negocio.

> Lleva una lista de pendientes de cada cliente. Cada "estaría bien tener" puede ser tu siguiente contrato. Anótalo.

---

## Siguiente lección

→ [Cómo ponerle precio a tus servicios de IA: precios basados en valor](39-monetization-pricing.md)
