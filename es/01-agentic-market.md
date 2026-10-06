# Qué es un agente de IA y por qué importa ahora

**Tiempo:** unos 25 min de lectura + 20 min de práctica

---

## Lo esencial

Piensa en la construcción en los tiempos en que un solo albañil ponía cada ladrillo con sus propias manos: lento, caro, limitado. Hoy existen cuadrillas de construcción a las que simplemente les dices "quiero una casa así", y la construyen. La IA agéntica es un cambio de ese tamaño para la automatización de los negocios.

**¿Qué es un agente de IA, en palabras simples?** Es un sistema de IA que no solo te responde, sino que realiza una tarea de varios pasos por su cuenta: busca datos, toma decisiones en el camino, llama a otros programas y servicios, y resuelve errores. Un chatbot es solo la ventana por la que hablas con él.

---

## Conceptos clave

- El mercado de la IA agéntica: dónde estamos ahora y hacia dónde va
- Por qué la mitad de la década de 2020 es un punto de entrada, ni "demasiado pronto" ni "demasiado tarde"
- Qué hizo posibles los sistemas agénticos en producción (uso real y cotidiano en los negocios, no una demostración)
- El papel de Claude Code como herramienta que puedes usar sin ser programador

---

## Teoría

### Las cifras del mercado: de nicho a corriente principal

🎨 **Imagínalo así:** el mercado de los teléfonos inteligentes en 2007, el momento en que salió el primer iPhone. Quienes empezaron a crear apps en 2008-2009 trabajaban en un mercado joven y en crecimiento; después se llenó de competencia. La IA agéntica de hoy se parece mucho a los primeros años de las apps para celular.

Las estimaciones del tamaño del mercado de la IA agéntica varían mucho de una firma de investigación a otra, así que esta lección no da cifras concretas en dólares. Si te encuentras una cifra en un artículo, revisa de quién es el informe y para qué año hace la proyección. Busca panoramas recientes de Gartner y McKinsey (al final de la lección hay sugerencias de búsqueda).

Para darte una idea de la dirección: en agosto de 2025, la firma de análisis Gartner pronosticó que para finales de 2026 hasta el 40% de las aplicaciones empresariales incluirían agentes de IA para tareas específicas, frente a menos del 5% en 2025 (comunicado de prensa de Gartner del 26 de agosto de 2025). Es un pronóstico, no un hecho. Pero muestra la escala: la tecnología ya está dentro de productos que la gente usa todos los días.

**Lo que está pasando ahora mismo:**
- Las funciones agénticas ya vienen integradas en productos cotidianos: Claude tiene Claude Code y Cowork, ChatGPT tiene un modo Work para tareas, y la mayoría de los asistentes grandes ya tienen modos de "agente". Qué está disponible en cada plan lo encuentras en la página [Lo vigente](https://aimayak.com/now/).
- Empresas de banca, comercio, logística, medios y otros sectores están lanzando agentes. Los resultados varían: en algunos lugares la mejora se nota de inmediato, y en otros los sistemas tienen que volver a quedar bajo supervisión humana (mira el ejemplo de Klarna más abajo).

La conclusión prudente: muchas empresas intentan poner agentes en marcha, y no todas lo logran. Quienes saben construir sistemas agénticos y revisar qué tan bien funcionan tienen una ventaja, sobre todo donde no hay una persona técnica en el equipo.

### Por qué ahora: se juntaron tres factores

**Factor 1: los LLM (modelos de lenguaje grandes, la IA detrás de asistentes como Claude y ChatGPT) se volvieron lo bastante confiables**

🎨 **Imagínalo así:** los primeros LLM eran como un practicante de primer año: listo, con mucha energía, pero de vez en cuando decía tonterías con total seguridad. Los modelos de hoy se parecen más a un empleado con 5 años en el puesto: todavía se equivocan a veces, pero con una persona revisando los resultados, son lo bastante confiables para trabajo real.

Todavía en 2023, los modelos de lenguaje "alucinaban" con frecuencia (una alucinación es cuando la IA inventa un dato con toda seguridad) y daban respuestas seguras pero falsas. En producción, eso es un problema serio: si un sistema envía correos a clientes de forma automática con datos falsos, eso no es automatización, es un desastre.

Desde mediados de 2024, los modelos insignia (Claude 3.5 Sonnet, GPT-4o y Gemini 1.5 Pro; las líneas de modelos han cambiado varias veces desde entonces, y la lista actual está en la página [Lo vigente](https://aimayak.com/now/)) alcanzaron un nivel de confiabilidad con el que se pueden usar para tareas repetitivas de negocio. No son perfectos, pero sí lo bastante buenos para construir sistemas de producción con una revisión humana razonable.

**Factor 2: apareció la infraestructura**

🎨 **Imagínalo así:** construir un sistema agéntico antes de 2024 era como tener que extraer el mineral, fundir el acero y soldar la estructura tú mismo antes de siquiera empezar la casa. Ahora es como comprar materiales listos en una tienda de materiales: tomas lo que necesitas y lo armas siguiendo las instrucciones.

Antes, para construir un sistema agéntico tenías que resolver por tu cuenta decenas de problemas de infraestructura: cómo ejecutar tareas en un horario, cómo guardar el estado entre un paso y otro, cómo manejar errores, cómo publicar (poner tu sistema en línea para que funcione de verdad).

Ahora hay herramientas listas que se encargan de esos problemas:
- **trigger.dev**: ejecuta tareas en segundo plano y flujos de trabajo, con manejo de errores incluido
- **Modal**: ejecuta código en Python (Python es un lenguaje de programación) en la nube sin configurar servidores
- **Vercel**: publicación con un clic
- **MCP (Model Context Protocol)**: una forma estándar de conectar herramientas a un LLM
- **Skills (instrucciones reutilizables en Claude Code)**: patrones listos para tareas comunes

**Factor 3: Claude Code lo hizo posible sin saber programar**

Históricamente, solo un programador podía montar una automatización. Ahora Claude Code te deja describir una tarea con palabras comunes, y el agente (un programa que realiza tareas por su cuenta) escribe el código, crea los archivos y arma la estructura él mismo.

Eso no quiere decir que ya no hagan falta programadores; los sistemas complejos todavía los necesitan. Pero la barrera para construir automatizaciones que de verdad funcionen bajó muchísimo.

### La cuadrilla de construcción contra tú y un montón de ladrillos

**Automatización tradicional** (sin IA agéntica):
Pones cada ladrillo tú mismo. Configuras cada paso a mano en Zapier o n8n. Cuando surge algo fuera de lo normal, la automatización se rompe y vuelves a hacerlo a mano.

Es como construir una casa tú solo: se puede, pero es lento, caro y limitado en escala.

**Flujos de trabajo agénticos** (con Claude Code):
Contratas una cuadrilla de construcción. Explicas qué quieres obtener al final. La cuadrilla decide cómo construirlo, se adapta a las sorpresas en el camino y hace preguntas para aclarar solo cuando de verdad no sabe algo.

Pasas del papel de "albañil" al papel de "arquitecto".

### Quién ya lo hace: ejemplos reales

**Morgan Stanley**: desde 2023, el banco les da a sus asesores financieros un asistente de IA construido sobre modelos de OpenAI. Encuentra lo que hace falta en una gran biblioteca interna de estudios y documentos y ayuda a los asesores a responder más rápido a los clientes. Otra herramienta toma notas durante las reuniones (con el consentimiento del cliente) y redacta los correos de seguimiento, que el asesor edita antes de enviarlos.

**Klarna** (una empresa de pagos en línea): en febrero de 2024, la empresa dijo que su asistente de IA de atención al cliente hacía un trabajo comparable al de 700 agentes de tiempo completo (comunicado de prensa de Klarna). En mayo de 2025, su director general le dijo a Bloomberg que fijarse demasiado en el costo había bajado la calidad del servicio, y prometió que los clientes siempre podrían hablar con una persona real. La lección: el agente se encarga de las solicitudes rutinarias, y los casos complejos tienen que llegar a una persona.

**Notion**: integró un agente de IA en su producto. Cuando un usuario se lo pide, crea páginas, llena bases de datos y arma reportes (la lista completa de lo que puede hacer está en la documentación de Notion).

No son ejemplos futuristas. Ya están funcionando, con todo y sus limitaciones.

### Dónde entras tú

🎨 **Imagínalo así:** no tienes que ser Nike para vender tenis. Millones de tiendas pequeñas venden zapatos a clientes de todos los días. Los sistemas agénticos para pequeños negocios son tus "tiendas de barrio" en el mundo de la IA. Morgan Stanley es el centro comercial. Pero los centros comerciales son pocos, y las tiendas de barrio están en todas partes.

No eres Morgan Stanley. No tienes un equipo de 50 programadores. Pero tienes Claude Code, y eso es lo que cambia la ecuación.

Las pequeñas automatizaciones agénticas para pequeñas y medianas empresas (pymes) son un punto de entrada claro. Un pequeño negocio no puede contratar su propio equipo de IA, pero sí puede encargar una solución lista a alguien que sabe construirla.

Ese es uno de los caminos que muestra este curso: aprender a construir, convertirlo en un servicio y ofrecerlo a clientes. El curso es gratis, y los ingresos de este tipo de trabajo dependen de tu nicho, de tu mercado y de tu esfuerzo. Nadie puede garantizarlos.

---

🎨 **Imagínalo así:** el mercado de la IA agéntica es como el primer mercado de sitios web de 1998-2002. Todos los negocios iban a querer "una página web". En ese entonces, el oficio se llamaba "desarrollador web". Ahora se llama "constructor de sistemas agénticos". La diferencia: en aquel tiempo tenías que pasar mucho tiempo aprendiendo HTML/CSS/PHP. Hoy lo básico se arma bastante más rápido con Claude Code, pero la calidad, la seguridad y la revisión de los resultados todavía requieren aprender de verdad.

---

## Práctica

**Ejercicio:** Investiga 3 empresas que ya usan sistemas de IA agéntica en producción.

1. Encuentra tres casos de estudio de industrias distintas (puedes buscar "AI agents case study 2026" o "casos de uso de agentes de IA 2026")
2. Para cada uno, anota:
   - Qué tarea resuelve el sistema agéntico
   - Qué resultado obtuvo la empresa (con números, si los hay) y quién lo dice: la propia empresa, el vendedor de la solución o una fuente independiente
   - Cómo era antes (cómo lo hacían sin un agente)
3. Escribe una frase: "En mi negocio, o para mis clientes, la automatización agéntica podría ayudar con ___"

**Tiempo que debes reservar:** 20 minutos.

---

## Errores comunes

❌ **Error:** Pensar que la IA agéntica son solo chatbots como ChatGPT.
✅ **Mejor:** La IA agéntica son sistemas que realizan tareas de varios pasos por su cuenta: buscan datos, toman decisiones, llaman a API (interfaces de programación de aplicaciones, la forma en que los programas se comunican entre sí) y manejan errores. Un chatbot es solo la interfaz.

❌ **Error:** Esperar a que la tecnología "madure" y se vuelva masiva.
✅ **Mejor:** Las funciones agénticas ya vienen integradas en productos que usa muchísima gente. Probarlas ahora en una tarea pequeña es la forma más fácil de ver qué pueden hacer y qué no.

❌ **Error:** Querer construir de entrada soluciones empresariales complejas como las de Morgan Stanley.
✅ **Mejor:** Empieza en pequeño, con automatizaciones para pequeñas y medianas empresas. Flujos de trabajo simples de 3 a 5 pasos que resuelvan un problema concreto de un cliente.

---

## Herramientas y recursos

- **[Claude.ai](https://claude.ai)**: para buscar casos de estudio y analizarlos
- **[Claude Code](https://code.claude.com/docs/en/overview)**: la documentación oficial del agente (en inglés)
- **[Anthropic Blog](https://www.anthropic.com/news)**: ejemplos de Claude usado en producción
- **Gartner: Agentic AI**: pronósticos oficiales del mercado (busca: "Gartner Agentic AI forecast 2030")
- **McKinsey: The state of AI**: un informe anual sobre el mercado de la IA (busca: "McKinsey Global Survey AI")
- **a16z AI Canon**: una colección de lecturas sobre la IA moderna, de 2023, del fondo de inversión Andreessen Horowitz (en inglés)

→ En la biblioteca, opcional: la lección [Flujos de trabajo agénticos frente a la automatización tradicional](02-why-agentic-beats-traditional.md) para una comparación detallada con Zapier y n8n
→ Mira la lección [Primeros clientes](38-monetization-clients.md) para ver cómo ofrecer tus habilidades agénticas a clientes

---

## Ideas clave

> La IA agéntica ya está integrada en productos de uso masivo. Las estimaciones del mercado varían, así que fíjate en la dirección, no en una sola cifra impresionante.

> Las grandes empresas están adoptando agentes; a los pequeños negocios también les pueden servir, y alguien tendrá que construírselos. Pero los resultados dependen de la tarea que elijas y del control de calidad.

> Se juntaron tres factores justo ahora: LLM confiables + infraestructura lista + Claude Code como una puerta de entrada que no exige saber programar.

---

## Próxima lección

→ [IA sin código para quienes no programan: v0, Webflow, Framer](77-no-code-ai.md): tu primera construcción con herramientas de IA que no requieren código
