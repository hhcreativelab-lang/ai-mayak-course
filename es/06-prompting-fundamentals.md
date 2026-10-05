# Cómo escribir un buen prompt

**Tiempo:** unos 15 min de lectura + 20 min de práctica

---

## Lo esencial

Un prompt es la solicitud en texto que le das a una IA: la tarea que le encargas. Piénsalo como una orden de trabajo para un contratista. Una orden de trabajo vaga da un mal resultado, y no es culpa del contratista. Una orden de trabajo clara da un resultado preciso mucho antes, muchas veces al primer intento. Esta lección te enseña a escribir buenas órdenes de trabajo para cualquier asistente de IA: Claude, ChatGPT, Gemini. Los ejemplos salen del trabajo de todos los días: un correo, un resumen, un plan. Si más adelante quieres construir con Claude Code (es un agente, o sea, un programa que realiza tareas por su cuenta en tu computadora), los principios son los mismos, y en esta lección hay una nota corta para eso.

---

## Conceptos clave

- Un asistente de IA = un contratista capaz que solo sabe lo que tú le dijiste
- Qué tan específico es tu prompt decide directamente la calidad del resultado
- La diferencia entre un prompt malo y uno bueno, con ejemplos reales
- Primero preguntas y un plan: qué hacer cuando no tienes claro lo que quieres (en Claude Code esto se llama Plan Mode, modo de planificación)
- Cómo la calidad del resultado depende de qué tan bien entiendes el tema

---

## Teoría

### La IA es un contratista, no un mago

Es tentador pensar en la IA como una varita mágica: "digo lo que quiero y queda hecho". Una mejor forma de verlo:

**Un asistente de IA es un contratista capaz**, con conocimientos amplios, que sabe escribir, calcular, explicar y planear. Pero solo tiene lo que tú le diste:

- El texto de tu solicitud
- Los archivos y documentos que adjuntaste a la conversación
- Lo que ya se dijo en esta conversación (y, si el asistente tiene activada la memoria, algunas cosas de conversaciones anteriores)

No conoce tu empresa, a tus clientes ni el tono en que sueles escribir, a menos que se los expliques.

Justamente por eso **las solicitudes vagas dan resultados vagos**, y las solicitudes específicas dan resultados precisos.

🎨 **Imagínalo así:** un prompt es la orden de trabajo que le entregas a un maestro de obras. Si le dices "Construye algo bonito", va a construir algo. Tal vez te guste, tal vez no. Si le dices "Construye una casa de dos pisos, de unos 120 metros cuadrados, tres recámaras, cochera para un auto, fachada de ladrillo, techo de lámina metálica", sabe exactamente qué construir.

### Anatomía de un mal prompt

Veamos una solicitud mala típica:

```
Escribe un correo a un cliente por un pedido atrasado
```

Lo que el asistente no puede saber con esta solicitud:

- ¿Quién es el cliente y cómo le hablas: de "tú" o de "usted"?
- ¿Qué se atrasó exactamente, y cuánto tiempo?
- ¿Cuál es el motivo, y hay que mencionarlo?
- ¿Qué ofreces para compensar: un descuento, entrega gratis, nada?
- ¿Qué tono: formal o cálido?
- ¿De qué largo debe ser el correo?
- ¿Quién lo firma y qué datos de contacto van al final?

El asistente va a escribir algo. Pero ese "algo" va a estar basado en sus suposiciones, no en tu situación. Como resultado vas a tener:

- 3 o 4 rondas de correcciones ("no, eso no es, reescribe esta parte")
- Tiempo perdido y mensajes de más que se descuentan del límite de tu plan
- Frustración

### Anatomía de un buen prompt

La misma solicitud, bien escrita:

```
Escribe un correo a una clienta por un pedido atrasado.

Quién soy: el encargado de un pequeño taller de muebles a la medida.
Para quién: Marina, una clienta frecuente que nos encargó los muebles de su cocina. Le hablo de "usted".
Qué pasó: prometimos entregar el 15 de marzo, pero las puertas llegaron del proveedor con defectos. La nueva fecha es el 29 de marzo.
Qué ofrecemos: entrega e instalación gratis.
Tono: cálido y respetuoso, sin frases de oficina y sin excusas largas.
Largo: 120 palabras o menos.
Al final: deja un espacio para mi teléfono y firma como "Óscar, encargado del taller".
```

Ahora al asistente le queda muy poco por adivinar, así que la primera versión suele quedar cerca de lo que querías, con muchas menos rondas de correcciones.

**Qué cambió:** diste detalles concretos en cada punto que el asistente, si no, habría tenido que adivinar.

💡 No pongas en el prompt apellidos, teléfonos ni direcciones reales de tus clientes: agrégalos tú al correo ya terminado. La lección sobre seguridad en IA, más adelante en este módulo, explica por qué.

### Las cinco partes de un buen prompt

🎨 **Imagínalo así:** las cinco partes de un prompt son como las preguntas básicas de un reportero: ¿Quién? ¿Qué? ¿Dónde? ¿Cuándo? ¿Por qué? A una nota periodística que le falte aunque sea una pierde el sentido. Un buen prompt funciona igual.

**1. El resultado (qué obtienes al final)**

No "ayúdame con este informe", sino "convierte este informe en un resumen de media página".

**2. Contexto (para qué lo necesitas y para quién es)**

El contexto es todo lo que el asistente puede ver en la conversación, así que aquí le dices el propósito: "El resumen lo va a leer mi director antes de una reunión con el banco, y va a tener cinco minutos".

**3. Restricciones (qué no hacer)**

"No agregues cifras que no estén en mi texto. Sin frases de relleno. No más de 150 palabras."

**4. Ejemplos (cómo debería verse)**

"Usa este formato: un título, tres conclusiones con cifras y una línea sobre el riesgo principal." Todavía mejor, pega una muestra: "Este es mi resumen anterior; hazlo con el mismo estilo".

**5. Criterio de terminado (cómo comprobarlo)**

"Está terminado cuando el resumen incluye ingresos, gastos y el riesgo principal, y cada cifra sale de mi informe."

No siempre necesitas las cinco; a veces bastan dos o tres. Pero cuanto más compleja la tarea, más importa cada una.

### Primero el plan (Plan Mode): cuando no tienes claro lo que quieres

🎨 **Imagínalo así:** es como reunirte con un arquitecto antes de empezar la obra. Le dices: "Quiero una casa acogedora para una familia con niños". El arquitecto hace preguntas: ¿Cuántos niños? ¿Necesitas cochera? ¿Cuál es el presupuesto? Después te trae un plano, no una cuadrilla de albañiles. Primero revisas el plano, y solo entonces das luz verde para empezar a construir.

A veces conoces el problema, pero no sabes por dónde empezar. O te imaginas el resultado, pero no entiendes de qué partes debería estar hecho.

Para eso hay una técnica sencilla: pídele al asistente que **primero te haga preguntas y te muestre un plan**, y que empiece el trabajo solo después de que le digas que sí. Basta con agregar al final de tu solicitud: "Antes de empezar, hazme preguntas para aclarar". Funciona en cualquier asistente.

Ejemplo:

```
Necesito organizar la mudanza de nuestra oficina a una nueva dirección en un mes.
Antes de armar el plan, hazme preguntas para aclarar la situación.
Después muéstrame un plan corto, y solo cuando yo diga que sí, detállalo día por día.
```

El asistente va a hacer preguntas como:

- "¿Cuántas personas trabajan en la oficina?"
- "¿Qué se va a mover: solo equipos y documentos, o también los muebles?"
- "¿Hay una fecha límite para desocupar el local anterior?"
- "¿Cuál es el presupuesto y quién está a cargo de la mudanza?"
- "¿Se puede parar el trabajo uno o dos días, o hay que mudarse sin dejar de operar?"

Después de que respondes, el asistente arma un plan, y solo entonces completa los detalles.

**Cuándo usar esta técnica:**

- La tarea es grande y tiene muchas piezas
- No tienes claro cómo dividirla en partes
- Quieres asegurarte de que el asistente te entendió antes de empezar
- Un error saldría caro (mucho tiempo o dinero)

💡 **Si más adelante construyes con Claude Code.** Ahí esta técnica tiene su propio modo, llamado Plan Mode (modo de planificación): Claude primero estudia el proyecto y propone un plan, y empieza a cambiar archivos solo después de que lo apruebas. En la terminal (una ventana para escribir comandos de texto) cambias entre modos con Shift+Tab o escribes el comando `/plan`; en la app de escritorio eliges el modo en la lista junto al botón de enviar. Las cinco partes del prompt son las mismas ahí: resultado, contexto, restricciones, un ejemplo y un criterio de terminado.

### La calidad depende de qué tan bien entiendes el trabajo

Aquí va una verdad incómoda que conviene aceptar desde el principio:

**Cuanto mejor entiendas el tema, mejor será el resultado.**

Supón que le pides a un asistente que arme un presupuesto para remodelar una cocina, pero no sabes qué lleva un presupuesto así: materiales, mano de obra, permisos, flete, retiro de escombro, un colchón para imprevistos. Entonces no vas a poder saber si hizo un buen trabajo. Vas a tener una tabla ordenada que se ve convincente, pero a la que le puede faltar la mitad de los conceptos.

Si sí entiendes cómo se arma un presupuesto de obra, vas a dar las instrucciones correctas, vas a notar cuando el asistente se salte algo y vas a poder revisar el resultado.

Esto no quiere decir que tengas que volverte experto en todo. Pero sí necesitas entender la **tarea que estás encargando**:

- ¿Cómo se hace hoy (a mano)?
- ¿Qué casos poco comunes aparecen?
- ¿Qué significa "bien hecho" para esta tarea?

Por eso, quienes suelen sacarle más provecho a la IA son las personas que conocen bien su área (marketing, ventas, finanzas, logística) y después aprenden la herramienta.

### Las correcciones son normales, no un fracaso

🎨 **Imagínalo así:** un pintor hace bocetos pequeños, después un borrador y luego la pintura detallada. Nadie espera un cuadro terminado desde la primera pincelada. Tu primer prompt es tu boceto. La meta no es "perfecto desde cero", sino "llegar al objetivo en la menor cantidad de pasos".

Una corrección es una pasada más: miras la respuesta y pides un ajuste. Incluso un prompt bien escrito rara vez da un resultado perfecto al primer intento. Y está bien.

Así suele ir el trabajo con un asistente (los porcentajes de abajo son una guía aproximada, no una medición):

1. Escribes un buen prompt → obtienes el 70-80% de lo que necesitas
2. Ves qué no está bien → pides correcciones concretas en el mismo chat
3. Llegas al 90-95% → una pasada más para los detalles pequeños
4. Listo

La meta de un buen prompt no es "perfecto a la primera", sino "lo más cerca posible del objetivo, con la menor cantidad posible de correcciones".

Un mal prompt te da un 30-40% al primer intento y necesita 5-7 correcciones.

Un buen prompt te da un 70-80% al primer intento y necesita 1-2 correcciones.

La diferencia son varias rondas de más en cada tarea. En tareas grandes, eso son horas de trabajo.

### Resumen rápido: mal prompt → buen prompt

| Mal prompt | Buen prompt | Por qué es mejor |
|---|---|---|
| "Escribe un correo" | "Escribe un correo a un cliente para mover nuestra reunión del 10 al 12 de junio: amable, de 80 palabras o menos, y ofrece dos horarios" | Para quién, sobre qué, tono, largo |
| "Haz un resumen" | "Resume este informe en media página para mi director: las tres conclusiones principales y un riesgo, solo con datos del texto" | Largo, lector, estructura, prohibido inventar |
| "Haz un plan" | "Haz un plan de dos semanas para preparar mis vacaciones: una lista de pendientes día por día y, aparte, lo que tengo que dejarle a un compañero" | Plazo, formato, qué importa |
| "Corrige el texto" | "Corrige los errores y las faltas de ortografía de este texto. No cambies el sentido ni el estilo. Al final, enumera los cambios" | Qué corregir, qué no tocar, cómo reportar |
| "Hazlo bonito" | "Dale otro formato a este texto: párrafos cortos, subtítulos y una lista en lugar de la enumeración larga" | Ajustes concretos en lugar de "bonito" |

---

## Práctica

**Ejercicio:** escribe un prompt malo, reescríbelo bien y compara los resultados.

**Paso 1: El prompt malo (5 min):**

1. Abre tu asistente (Claude, ChatGPT o Gemini) y empieza un chat nuevo
2. Escribe este prompt tal cual:
   ```
   Escribe un anuncio para una vacante en nuestra empresa
   ```

3. Mira lo que obtuviste. Anota: ¿qué falta? ¿Qué decidió el asistente por ti?

**Paso 2: El prompt bueno (10 min):**

1. Empieza otro chat nuevo, para que la primera respuesta no influya en la segunda, y escribe un prompt con las cinco partes:
   - **Resultado:** "Escribe un anuncio para una vacante de [puesto]..."
   - **Contexto:** "...en [tu empresa, o una inventada]. El anuncio se va a publicar en [sitio web o red social]. Buscamos a alguien que [el requisito principal]"
   - **Restricciones:** el largo y qué no poner, por ejemplo: "150 palabras o menos, sin frases como 'ambiente dinámico' o 'somos una gran familia'"
   - **Ejemplo:** describe el formato ("párrafos cortos y listas") o pega un anuncio que te guste
   - **Criterio de terminado:** "El anuncio incluye responsabilidades, requisitos, condiciones y cómo postularse"
2. Envía este prompt
3. Compara el resultado con el primero

**Paso 3: Revisión (5 min):**

Respóndete:

- ¿Cuántas rondas de correcciones habría necesitado el primer anuncio para poder publicarse?
- ¿Cuántas necesitaría el segundo?
- ¿Qué partes del segundo prompt habrías tenido que explicar por separado la primera vez?

Una forma fácil de comprobarlo: el segundo anuncio tiene los cuatro bloques de tu criterio de terminado, mientras que en el primero el asistente inventó algunos o se los saltó.

---

## Errores comunes

❌ **Error:** Escribir un prompt enorme de 500 palabras desde el principio.

✅ **En su lugar:** Empieza con lo esencial (resultado + contexto), obtén una primera versión y luego ajústala paso a paso. Dos o tres prompts cortos son mejores que uno gigante.

❌ **Error:** No decir tus restricciones: "no más de una página", "sin tecnicismos", "no inventes cifras".

✅ **En su lugar:** Sin restricciones, el asistente decide por su cuenta el largo y el tipo de lenguaje. Si te importa cómo debe quedar, dilo de forma explícita. Las restricciones te ahorran correcciones.

❌ **Error:** No revisar el resultado y mandarlo "tal cual".

✅ **En su lugar:** Revisa siempre: ¿los datos y las cifras son correctos (un asistente puede equivocarse e inventar)?, ¿el tono es el adecuado?, ¿sobra algo? Si no tienes claro cómo dividir la tarea, pide primero preguntas y un plan.

---

## Herramientas y recursos

- **[Claude Code](https://code.claude.com/docs/en/overview)**: el agente de Anthropic para quienes después quieran construir; no lo necesitas para esta lección (documentación en inglés; hay versión en español)
- **[Anthropic Prompt Engineering Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)**: la guía oficial de Anthropic para escribir prompts (en inglés; hay versión en español)
- **[Anthropic API docs](https://docs.anthropic.com/en/api/getting-started)**: documentación para desarrolladores que conectan Claude con sus propios programas (en inglés); si estás empezando, no la necesitas
- **[Claude Code docs: instalación](https://code.claude.com/docs/en/getting-started)**: cómo instalar y configurar Claude Code (en inglés)

→ Mira la lección [El Default Shift](03-default-shift-mindset.md): cómo darle tareas a un asistente igual que a un contratista (es la que sigue)

→ Opcional, de la biblioteca: [Instalar y configurar Claude Code](05-setup.md): si decides instalar Claude Code

→ Opcional, de la biblioteca: [CLAUDE.md](07-claude-md.md): instrucciones permanentes para Claude Code, para no repetir tu contexto en cada solicitud

→ Opcional, de la biblioteca: [Manejo del contexto: técnicas avanzadas](29-context-management-advanced.md): cómo trabajar con prompts en proyectos grandes

---

## Ideas clave

> Un mal prompt = una mala orden de trabajo. El asistente va a hacer algo, pero no lo que necesitas.

> Las cinco partes de un buen prompt: resultado, contexto, restricciones, ejemplos, criterio de terminado.

> ¿No sabes cómo dividir una tarea en partes? Pide primero preguntas y un plan. En Claude Code hay un Plan Mode para eso.

> La calidad del resultado depende de qué tan bien entiendes el tema. El asistente construye a partir de tus planos.

---

## Próxima lección

→ [El Default Shift](03-default-shift-mindset.md): cómo hacer de la IA tu primer ayudante en el trabajo
