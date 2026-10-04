# Cómo escribir un buen prompt para Claude Code

**Tiempo:** unos 35 min de lectura + 20 min de práctica

---

## Lo esencial

Un prompt (la solicitud en texto que le das a una IA) es una orden de trabajo para un agente (un programa que realiza tareas por su cuenta). Una orden de trabajo vaga da un mal resultado, y no es culpa del contratista. Una orden de trabajo clara da un resultado preciso mucho antes, muchas veces al primer intento. Esta lección te enseña a escribir buenas órdenes de trabajo para Claude Code. Los mismos principios funcionan en cualquier asistente de IA (ChatGPT, Gemini, Claude en tu navegador): lo único que cambia es dónde pegas el texto.

---

## Conceptos clave

- Claude Code = un contratista brillante con acceso a tus herramientas
- Qué tan específico es tu prompt decide directamente la calidad del resultado
- La diferencia entre un prompt malo y uno bueno, con ejemplos reales
- Plan Mode (modo de planificación): úsalo cuando no tengas claro lo que quieres
- Cómo la calidad del resultado depende de qué tan bien entiendes el tema

---

## Teoría

### Claude Code es un contratista, no un mago

Es tentador pensar en Claude Code como una varita mágica: "digo lo que quiero y queda hecho". Una mejor forma de verlo:

**Claude Code es un contratista brillante** con muchísima experiencia, capaz de construir casi cualquier cosa. Pero solo tiene acceso a lo que tú le diste:

- Los archivos de la carpeta del proyecto que abriste
- Las herramientas que conectaste
- La información que describiste en la tarea

No conoce tu marca, a tus clientes ni tus preferencias de diseño a menos que se las expliques.

Justamente por eso **las solicitudes vagas dan resultados vagos**, y las solicitudes específicas dan resultados precisos.

🎨 **Imagínalo así:** un prompt es la orden de trabajo que le entregas a un maestro de obras. Si le dices "Construye algo bonito", va a construir algo. Tal vez te guste, tal vez no. Si le dices "Construye una casa de dos pisos, de unos 120 metros cuadrados, tres recámaras, cochera para un auto, fachada de ladrillo, techo de lámina metálica", sabe exactamente qué construir.

### Anatomía de un mal prompt

Veamos una solicitud mala típica:

```
Hazme un sitio web para un negocio de paseo de perros
```

Lo que el agente no puede saber con esta solicitud:

- ¿Qué estilo y colores? (¿Corporativo y serio? ¿Divertido y colorido?)
- ¿Qué secciones? (¿Solo una página de inicio? ¿Precios? ¿Reseñas? ¿Un formulario de reservación?)
- ¿Qué ciudad o zona? (¿Necesita un mapa?)
- ¿Una página o varias?
- ¿Necesita formulario de reservación? ¿Pago en línea?
- ¿En qué idioma? (¿Solo español, o también inglés?)
- ¿Hay logotipo?

El agente va a hacer algo. Pero ese "algo" va a estar basado en sus suposiciones, no en lo que de verdad necesitas. Como resultado vas a tener:

- 3 o 4 rondas de correcciones ("no, eso no es, hazlo así")
- Muchos tokens gastados (los tokens son los pedacitos de texto que una IA lee y escribe)
- Frustración

### Anatomía de un buen prompt

La misma solicitud, bien escrita:

```
Crea una landing page para un negocio de paseo de perros en Monterrey, Nuevo León.

Requisitos:
- Sección principal (hero): título "Paseo profesional de perros", subtítulo "Todos los días, con cualquier clima, paseadores con experiencia", botón "Reserva un paseo"
- Sección de servicios: 3 tarjetas: paseo individual (1 hora, $35 USD), paseo en grupo (1.5 horas, $25 USD), entrenamiento + paseo (2 horas, $55 USD)
- Sección de reseñas: 3 bloques con una cita y el nombre del cliente (invéntalos)
- Formulario de reservación: nombre, teléfono, raza del perro, elección de servicio, botón "Solicitar reservación"
- Pie de página: teléfono 81 5555 0123, correo hola@example.com, Instagram @paseoperros_mty

Estilo: combinación de colores azul #2563EB y blanco, fuente del sistema, tarjetas con esquinas redondeadas
Tecnología: solo HTML y CSS, sin frameworks, un solo archivo index.html
Adaptable: que funcione en celulares
```

Ahora al agente le queda muy poco por adivinar, así que la primera versión suele quedar cerca de lo que querías, con muchas menos rondas de correcciones.

**Qué cambió:** diste detalles concretos en cada punto que el agente, si no, habría tenido que adivinar.

### Las cinco partes de un buen prompt

🎨 **Imagínalo así:** las cinco partes de un prompt son como las preguntas básicas de un reportero: ¿Quién? ¿Qué? ¿Dónde? ¿Cuándo? ¿Por qué? A una nota periodística que le falte aunque sea una pierde el sentido. Un buen prompt funciona igual.

**1. El resultado (qué obtienes al final)**

No "crea una automatización", sino "crea un script de Python (Python es un lenguaje de programación) que..."

**2. Contexto (para qué lo necesitas)**

El contexto es todo lo que la IA puede ver en la conversación, así que aquí le dices el propósito: "Este script va a correr todos los días a las 9:00 a. m. y va a enviar..."

**3. Restricciones (qué no hacer)**

"No uses bibliotecas externas excepto requests. No crees una base de datos, solo un archivo CSV."

**4. Ejemplos (cómo debería verse)**

"El formato del correo: el asunto es 'Reporte del [fecha]', y el cuerpo es una tabla con las columnas Nombre, Monto, Estado."

**5. Criterio de terminado (cómo comprobarlo)**

"Está terminado cuando el script corre sin errores, crea un archivo report.csv y envía un correo a test@example.com."

No siempre necesitas las cinco; a veces bastan dos o tres. Pero cuanto más compleja la tarea, más importa cada una.

### Plan Mode: cuando no tienes claro lo que quieres

🎨 **Imagínalo así:** Plan Mode es como reunirte con un arquitecto antes de empezar la obra. Le dices: "Quiero una casa acogedora para una familia con niños". El arquitecto hace preguntas: ¿Cuántos niños? ¿Necesitas cochera? ¿Cuál es el presupuesto? Después te trae un plano, no una cuadrilla de albañiles. Primero revisas el plano, y solo entonces das luz verde para empezar a construir.

A veces conoces el problema, pero no cómo resolverlo técnicamente. O sabes el resultado que quieres, pero no entiendes de qué partes debería estar hecho.

Para eso existe **Plan Mode** en Claude Code.

Cómo activarlo: escribe tu solicitud y agrega al final "Antes de empezar, hazme preguntas para aclarar", o activa Plan Mode en la interfaz. En la terminal cambias entre modos con Shift+Tab (o escribes el comando `/plan`); en la app de escritorio eliges el modo en la lista junto al botón de enviar.

Ejemplo:

```
Quiero automatizar un resumen diario por correo con noticias de bienes raíces para mis clientes.
Antes de empezar, hazme preguntas para aclarar, así entiendes exactamente qué construir.
```

El agente va a hacer preguntas como:

- "¿De dónde deberían salir las noticias: de sitios web específicos o de una API (Application Programming Interface: una forma de que un programa le pida datos a otro)?"
- "¿Cuántas noticias debería incluir cada correo?"
- "¿Debería personalizarse según la ciudad de cada cliente?"
- "¿Dónde guardas tu lista de clientes: Google Sheets, un CRM (Customer Relationship Management: un software para llevar el registro de tus clientes), un archivo CSV?"
- "¿A qué hora debería enviarse?"

Después de que respondes, el agente arma un plan, y solo entonces empieza a construir.

**Cuándo usar Plan Mode:**

- La tarea es complicada y tiene muchas piezas
- No tienes claro cómo dividirla en partes
- Quieres asegurarte de que el agente te entendió antes de empezar
- Un error saldría caro (mucho tiempo o dinero)

### La calidad depende de qué tan bien entiendes el trabajo

Aquí va una verdad incómoda que conviene aceptar desde el principio:

**Cuanto mejor entiendas el tema, mejor será el resultado del agente.**

Si le pides a un agente que automatice un boletín por correo pero no entiendes cómo funcionan los boletines (SPF/DKIM, bajas de suscripción, manejo de rebotes), no vas a poder saber si el agente hizo un buen trabajo. Vas a tener algo que funciona en teoría, pero que puede tener problemas ocultos.

Si sí entiendes cómo funcionan los boletines, vas a dar las instrucciones correctas, vas a notar cuando el agente se salte algo importante y vas a poder revisar el resultado.

Esto no quiere decir que tengas que volverte desarrollador. Pero sí necesitas entender el **proceso de negocio** que estás automatizando:

- ¿Cómo funciona el proceso hoy (a mano)?
- ¿Qué casos especiales aparecen (las situaciones poco comunes que rompen la rutina normal)?
- ¿Qué significa "bien hecho" para este proceso?

Por eso los mejores creadores de sistemas con agentes son personas que primero entendieron un área (marketing, ventas, finanzas, logística) y después aprendieron las herramientas.

### Las correcciones son normales, no un fracaso

🎨 **Imagínalo así:** un pintor hace bocetos pequeños, después un borrador y luego la pintura detallada. Nadie espera un cuadro terminado desde la primera pincelada. Tu primer prompt es tu boceto. La meta no es "perfecto desde cero", sino "llegar al objetivo en la menor cantidad de pasos".

Incluso un prompt bien escrito rara vez da un resultado perfecto al primer intento. Y está bien.

El patrón para trabajar con un agente (los porcentajes de abajo son una guía aproximada, no una medición):

1. Escribes un buen prompt → obtienes el 70-80% de lo que necesitas
2. Ves qué no está bien → mandas un prompt de seguimiento con correcciones concretas
3. Llegas al 90-95% → una pasada más para los detalles pequeños
4. Listo

La meta de un buen prompt no es "perfecto a la primera", sino "lo más cerca posible del objetivo, con la menor cantidad posible de correcciones".

Un mal prompt te da un 30-40% al primer intento y necesita 5-7 correcciones.

Un buen prompt te da un 70-80% al primer intento y necesita 1-2 correcciones.

La diferencia son 3-4 correcciones. En tareas complejas, eso son horas de trabajo.

### Resumen rápido: mal prompt → buen prompt

| Mal prompt | Buen prompt | Por qué es mejor |
|---|---|---|
| "Haz un sitio web" | "Crea una landing page en HTML+CSS, una sola página, azul y blanco, secciones: hero, servicios, formulario" | Resultado, estilo y estructura concretos |
| "Escribe un script" | "Escribe un script de Python que lea un CSV, se quede con las filas donde el monto sea > 1000 y las guarde en un CSV nuevo" | Lenguaje, entrada, lógica, salida |
| "Automatiza el correo" | "Crea un flujo de trabajo (una secuencia de pasos que corre por su cuenta): cada lunes, junta 5 noticias de un RSS, genera un correo en HTML y envíalo por la API de Gmail a la lista que está en Google Sheets" | Horario, fuente, formato, canal, destinatarios |
| "Arregla el error" | "En main.py, línea 42: TypeError: expected str, got int. La función process_data recibe un número en lugar de un texto en la respuesta de la API" | Archivo, línea, tipo de error, contexto |
| "Hazlo bonito" | "Agrega: esquinas redondeadas de 8px, sombras en las tarjetas, 24px de espacio entre secciones, fuente Inter" | Ajustes de diseño concretos |

---

## Práctica

**Ejercicio:** escribe un prompt malo, reescríbelo bien y compara los resultados.

**Paso 1: El prompt malo (5 min):**

1. Abre Claude Code en una carpeta vacía
2. Escribe este prompt tal cual:
   ```
   Crea un formulario para recibir solicitudes de clientes
   ```

3. Mira lo que obtuviste. Anota: ¿qué falta? ¿Qué decidió el agente por ti?

**Paso 2: El prompt bueno (10 min):**

1. Escribe un prompt nuevo con las cinco partes:
   - **Resultado:** "Crea un formulario en HTML..."
   - **Contexto:** "...para que los clientes reserven una primera consulta sobre [tu tema]"
   - **Campos:** enumera los campos exactos que necesitas
   - **Estilo:** colores, fuentes, el aspecto general
   - **Criterio de terminado:** "El formulario tiene que funcionar sin frameworks de JavaScript" (JavaScript es un lenguaje de programación)
2. Ejecuta este prompt
3. Compara el resultado con el primero

**Paso 3: Revisión (5 min):**

Respóndete:

- ¿Cuántas correcciones necesitó el primer prompt?
- ¿Cuántas necesitó el segundo?
- ¿Qué tuviste que explicar por separado la primera vez?

---

## Errores comunes

❌ **Error:** Escribir un prompt enorme de 500 palabras desde el principio.

✅ **En su lugar:** Empieza con lo esencial (resultado + contexto), obtén una primera versión y luego ajústala paso a paso. Dos o tres prompts cortos son mejores que uno gigante.

❌ **Error:** No decir tus restricciones: "no uses frameworks", "solo Python", "sin base de datos".

✅ **En su lugar:** Sin restricciones, el agente elige su propio conjunto de tecnologías. Si te importa qué se usa, dilo de forma explícita. Las restricciones te ahorran correcciones.

❌ **Error:** No revisar el resultado y desplegarlo (desplegar es ponerlo en línea, publicarlo) "tal cual".

✅ **En su lugar:** Revisa siempre: ¿corre sin errores?, ¿hace lo que esperabas?, ¿maneja los casos especiales? Usa Plan Mode si no tienes claro cómo dividir la tarea.

---

## Herramientas y recursos

- **[Claude Code](https://code.claude.com/docs/en/overview)**: la herramienta principal de esta lección
- **[Anthropic Prompt Engineering Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)**: la guía oficial para escribir prompts (en inglés)
- **[Anthropic API docs](https://docs.anthropic.com/en/api/getting-started)**: documentación de la API (para entender cómo funciona el modelo)
- **[Claude Code docs: CLI usage](https://code.claude.com/docs/en/getting-started)**: cómo usar Claude Code con eficacia

→ Mira la lección [El cambio de enfoque](03-default-shift-mindset.md): la mentalidad de contratista detrás de los buenos prompts

→ Mira la lección [Instalar y configurar Claude Code](05-setup.md): si todavía no preparaste tu espacio de trabajo

→ Mira la lección [CLAUDE.md](07-claude-md.md): un prompt de sistema siempre activo (para no tener que repetir tu contexto)

→ Mira la lección [Manejo del contexto: técnicas avanzadas](29-context-management-advanced.md): cómo llevar tus prompts a sistemas complejos

---

## Ideas clave

> Un mal prompt = una mala orden de trabajo. El agente va a hacer algo, pero no lo que necesitas.

> Las cinco partes de un buen prompt: resultado, contexto, restricciones, ejemplos, criterio de terminado.

> Plan Mode: úsalo cuando no sepas cómo dividir una tarea en partes. El agente va a hacer las preguntas correctas.

> La calidad del resultado depende de qué tan bien entiendes el tema. El agente construye a partir de tus planos.

---

## Próxima lección

→ [CLAUDE.md: el prompt de sistema de tu proyecto](07-claude-md.md)
