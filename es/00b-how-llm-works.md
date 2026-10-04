# Cómo funciona un LLM por dentro, explicado sin matemáticas

**Tiempo:** unos 35 min de lectura + 15 min de práctica

> Hablas con Claude y te responde en un español claro, natural y bien organizado. Parece que te entiende. Pero ¿qué pasa realmente por dentro? No es magia, y tampoco es una "mente de verdad". Son matemáticas que trabajan con pequeños bloques de texto. Cuando lo entiendes, empiezas a usar la IA con más eficacia.

---

## Lo esencial

La mayoría de la gente usa un LLM (Large Language Model, modelo de lenguaje grande) como una caja negra: haces una pregunta y recibes una respuesta. Eso funciona. Pero saber cómo funciona la caja por dentro te da ventajas prácticas: ahorras dinero, obtienes mejores respuestas y entiendes por qué la IA a veces se equivoca y cómo evitarlo.

Esta lección es una radiografía de un modelo de lenguaje. Sin fórmulas. Solo imágenes.

---

## Conceptos clave

- Token: la unidad de texto más pequeña con la que trabaja la IA
- Preentrenamiento: cómo aprende un modelo a partir de enormes cantidades de texto
- Embedding: cómo la IA convierte las palabras en números y significado
- Transformer y atención: el diseño que lo cambió todo
- Ventana de contexto: la memoria de la IA dentro de una sola conversación
- Temperatura: la perilla de la "aleatoriedad creativa"
- Alucinación: por qué la IA a veces dice cosas falsas con total seguridad

---

## Teoría

---

### 1. Qué es un token: los átomos del lenguaje

Lo primero: la IA no lee palabras. Ve tokens, las unidades de texto más pequeñas con las que trabaja (piensa en las fichas de las maquinitas: piezas pequeñas y estándar que la máquina cuenta una por una).

Un token no es una palabra. Es un trozo de texto que el modelo de lenguaje trata como una pieza que ya no puede dividir. A veces un token es una palabra entera. A veces es parte de una palabra. A veces es un solo carácter.

**Ejemplos (con palabras en inglés):**
- La palabra `cat` ("gato") = 1 token (corta y común)
- La palabra `catastrophe` ("catástrofe") = 3 tokens: `cat` + `ast` + `rophe`
- Una palabra larga y poco común como `anthropomorphism` ("antropomorfismo") = varios tokens
- Las palabras de otros idiomas suelen dividirse en más pedazos que las del inglés

Un detalle importante: **el inglés es el idioma "más barato" en tokens.** Muchos otros idiomas necesitan más tokens para decir lo mismo, en algunos casos aproximadamente entre 1.5 y 2 veces más. Eso afecta directamente el costo, porque pagas por tokens.

Una regla práctica aproximada: **1,000 tokens ≈ 750 palabras** en inglés. El texto en otros idiomas suele ocupar más tokens para la misma cantidad de significado.

🎨 **Imagínalo así:** un token es una pieza de Lego. La IA no ve las palabras como objetos únicos. Ve piezas de distintos tamaños con las que se arman las palabras. La palabra "cat" es una pieza. La palabra "catastrophe" son tres: "cat", "ast" y "rophe". Cuando la IA escribe un texto, va colocando pieza tras pieza. De izquierda a derecha. Una a la vez. Cada pieza nueva depende de todas las anteriores.

**Por qué importa en la práctica:**
- Pagas por tokens, no por palabras: cuanto más corto y concreto sea tu prompt, más barato
- Los textos largos en otros idiomas pueden costar más que el mismo texto en inglés
- Un prompt compacto, sin relleno, puede bajar bastante los costos sin perder calidad

---

### 2. Cómo aprende la IA: el preentrenamiento

¿Cómo sabe Claude qué significa la palabra "gato"? ¿Cómo sabe que después de "El sol brilla en el" viene "cielo"? ¿Cómo sabe de historia, física, programación?

La respuesta: el preentrenamiento (la primera etapa del entrenamiento de un modelo de lenguaje).

Imagina que Anthropic reúne una biblioteca gigante de textos. No solo grande: inimaginablemente grande. Wikipedia en más de 100 idiomas, millones de libros, artículos científicos, código en GitHub, Reddit, Stack Overflow, noticias, foros, documentos legales. A esto se le llama corpus (del latín "cuerpo": una gran colección de textos que se usa para entrenar).

Después el modelo se entrena con ese corpus: billones de tokens, meses de cálculo en miles de chips especializados.

**La tarea del entrenamiento es casi absurdamente sencilla:** adivinar el siguiente token.

En concreto: el modelo ve el texto `"La Tierra gira alrededor del"` y tiene que predecir qué sigue. La respuesta correcta: `"Sol"`. El modelo predijo `"estrellas"`: incorrecto. Se ajustan los parámetros. Otra vez. Y otra. Billones de veces.

¿Suena primitivo? Pero todo nace de esta única tarea sencilla. Para adivinar bien la siguiente palabra en un artículo médico, hay que entender de medicina. Para adivinar bien en código, hay que entender la lógica de la programación. Para adivinar bien en poesía, hay que sentir el ritmo.

🎨 **Imagínalo así:** un niño que leyó absolutamente TODOS los libros del mundo. Cada periódico, cada libro de texto, cada novela, cada manual de refrigerador. No memorizó nada palabra por palabra; absorbió los patrones. Cómo se arma una oración. Cómo se conectan los hechos. Qué palabras suelen aparecer junto a cuáles. Claude pasó por ese mismo proceso, solo que no en 18 años de infancia, sino en unos pocos meses, con billones de tokens de texto.

---

### 3. Embeddings: cómo ve la IA el significado

Una computadora solo entiende números. Entonces, ¿cómo trabaja con texto?

La respuesta: cada token se convierte en un vector de números.

Un embedding (la posición de una palabra en un espacio hecho de números) es una forma de convertir cualquier palabra en una lista de números, de modo que las palabras con significados parecidos terminen con números parecidos.

Un vector (una lista ordenada de números) para la palabra "gato" podría verse así: `[0.32, -0.71, 0.15, 0.88, -0.03, ...]`: miles de números en una lista. La palabra "gatito" recibe una lista muy parecida. La palabra "plátano" recibe una completamente distinta.

Estos vectores viven en un espacio matemático con una cantidad enorme de dimensiones. Las palabras de significado parecido quedan cerca en ese espacio. Las de significado distinto quedan lejos.

**Una propiedad notable de los embeddings:** hacer cuentas con ellos realmente tiene sentido.

Hay un ejemplo famoso: vector("rey") - vector("hombre") + vector("mujer") ≈ vector("reina"). Hacer cuentas con texto dio la respuesta correcta sobre cómo se relacionan las ideas. No es casualidad; así está organizado el espacio del significado.

🎨 **Imagínalo así:** un mapa enorme, pero un mapa de significados, no de geografía. Cada palabra es una ciudad. "Monterrey" y "Guadalajara" quedan cerca: las dos son grandes ciudades mexicanas. "Monterrey" y "Tokio" quedan lejos. "Gato" y "gatito" son pueblos vecinos. "Gato" y "física cuántica" están en continentes distintos. Los embeddings son las coordenadas GPS de cada palabra en este mapa de significados. Cuando la IA procesa un texto, se mueve por este mapa y encuentra las relaciones entre las ideas.

---

### 4. El transformer y el mecanismo de atención

En 2017, Google publicó un artículo llamado "Attention Is All You Need" ("La atención es todo lo que necesitas"). Ese artículo cambió la historia de la IA.

El transformer (una arquitectura de red neuronal inventada en Google en 2017) es el tipo de diseño que se volvió la base de todos los modelos de lenguaje modernos: GPT, Claude, Gemini, Llama.

Antes de los transformers, la IA leía el texto como una persona lee un libro aburrido: de izquierda a derecha, palabra por palabra, olvidando el principio para cuando llegaba al final. Los textos largos le costaban.

El transformer resolvió esto de forma radical: ve TODO el texto a la vez.

**El mecanismo clave es la atención: la capacidad del modelo de tomar en cuenta cada parte del texto mientras procesa cada palabra.**

Cuando un transformer procesa la palabra "él" en una oración, el mecanismo de atención se pregunta: ¿a qué otras palabras de este texto tengo que prestarles atención para saber quién es "él"?

Ejemplo: `"El banco del parque estaba recién pintado"` vs `"El banco aprobó un préstamo al 12%"`.

La palabra "banco" es la misma. Pero en el primer caso, el mecanismo de atención nota la palabra "parque" y entiende: es un asiento. En el segundo, nota la palabra "préstamo" y entiende: es una institución financiera. Una palabra, dos significados distintos, diferenciados correctamente al prestar atención al contexto.

🎨 **Imagínalo así:** el director de una orquesta sinfónica. Frente a él hay 80 músicos. En cada momento del concierto, el director los escucha a todos a la vez. Pero según la obra y el compás, sube a unos (ahora importan más los violines) y baja a otros (los tambores pueden esperar). El mecanismo de atención es el director del texto. Escucha todas las palabras a la vez y decide, momento a momento, cuáles merecen más atención en ese instante.

---

### 5. La ventana de contexto: el escritorio de la IA

La ventana de contexto (la cantidad máxima de texto que la IA puede tener a la vista durante una conversación) probablemente es el ajuste más importante en la práctica cuando trabajas con IA.

Todo lo que está dentro de la ventana de contexto, la IA lo "ve" y lo toma en cuenta. Todo lo que queda fuera no existe para la IA en ese momento.

**Tamaños de la ventana de contexto (a octubre de 2026, para Claude en la API):**
- Claude Fable 5.1, Opus 5.5, Sonnet 5.5: **1,000,000 tokens** ≈ 555,000 palabras (en texto en inglés con el tokenizador actual) ≈ 1,800 páginas de libro
- Claude Haiku 4.5: 200,000 tokens ≈ 150,000 palabras ≈ 500 páginas

ChatGPT, Gemini y otros asistentes también tienen ventanas de cientos de miles o millones de tokens, pero las cifras exactas dependen del modelo y del plan: revisa la documentación del proveedor y la página [Lo vigente](https://aimayak.com/es/now/). En una app normal (por ejemplo, el chat de claude.ai), la cantidad disponible para ti puede ser distinta a la de la API.

Son números grandes. Pero en el trabajo real, el contexto se gasta más rápido de lo que crees: el prompt de sistema (las instrucciones de fondo que la app le da al modelo), el historial de la conversación, los documentos que subes y las propias respuestas de la IA ocupan espacio en la ventana de contexto.

**Qué pasa cuando el contexto se llena:**
Las partes anteriores de la conversación quedan "empujadas fuera", y la IA deja de tomarlas en cuenta. Lo vas a notar: la IA "olvida" lo que se dijo al principio de un chat largo. No es falta de inteligencia; es un límite físico de la arquitectura.

🎨 **Imagínalo así:** un escritorio. Todo lo que está sobre el escritorio lo puedes ver y tomar al instante. Esa es la ventana de contexto de la IA. Lo que está en el cajón tendrías que sacarlo (eso es la memoria a largo plazo, que la IA básica no tiene). Lo que dejaste en casa está completamente fuera de tu alcance. Cuando el escritorio se llena demasiado, los papeles viejos se resbalan al piso y desaparecen de tu vista. Una ventana de contexto de cientos de miles de tokens, o de un millón, es un escritorio muy grande. Pero igual tiene bordes.

**Conclusiones prácticas:**
- Un contexto grande es cómodo. Pero cuesta más (pagas por cada token de la solicitud)
- Para proyectos largos, usa `/compact` en Claude Code: comprime el historial sin perder lo esencial
- Organiza tus conversaciones: abre un chat nuevo para cada tarea nueva en lugar de meter todo en uno

---

### 6. Cómo genera la IA una respuesta, paso a paso

Escribiste: `"Explícame la mecánica cuántica con palabras sencillas"`. ¿Qué pasa después?

**Paso 1: Tokenización**
Tu texto se divide en tokens: "Explícame", "la", "mecánica", "cuántica" y así. Las palabras más largas o menos comunes se pueden dividir en varios tokens.

**Paso 2: Embeddings**
Cada token se convierte en un vector de números. Ahora tu solicitud existe como un conjunto de puntos en un espacio matemático.

**Paso 3: El transformer lo procesa**
El mecanismo de atención recorre todos los tokens, construye conexiones entre ellos y descifra el contexto. "Mecánica" + "cuántica" + "con palabras sencillas": tres partes, y cada una importa para entender la tarea.

**Paso 4: Calcular probabilidades**
El modelo mira todo lo que hay en el contexto y calcula: ¿cuál es el siguiente token más probable? No una sola opción, sino una distribución de probabilidades sobre todo su vocabulario (decenas de miles de tokens). "La": 12%, "Vamos": 8%, "Imagina": 15%...

**Paso 5: Muestreo (elegir el siguiente token a partir de la distribución de probabilidades)**
El modelo elige un token. Cómo elige exactamente depende de la temperatura (más sobre eso abajo).

**Paso 6: Repetir**
El token elegido se agrega al contexto. Los pasos 4 y 5 se repiten para el siguiente token. Y otra vez. Y otra, hasta que la respuesta está completa.

🎨 **Imagínalo así:** un músico de jazz improvisando en el escenario. Escucha todo lo que se ha tocado hasta ese momento: cada instrumento, todo el ritmo, todo el tema. Con base en eso, elige la siguiente nota. No al azar, pero tampoco siguiendo una partitura fija. Cada nota nace de todo lo anterior. Cada token de la respuesta de Claude es una "nota" que nace de todo el contexto. Por eso la IA no puede "regresar y corregir" el principio de su respuesta: solo toca hacia adelante, una nota a la vez.

---

### 7. Temperatura: la perilla de la aleatoriedad

La temperatura (un ajuste que controla cuánta "aleatoriedad" entra al elegir el siguiente token; el rango cambia según el servicio, casi siempre de 0 a 1 o de 0 a 2) es una idea importante para entender por qué las respuestas varían.

⚠️ **Una aclaración, a octubre de 2026.** En la API de los modelos de Claude más nuevos (Opus 4.7 y posteriores, incluido Opus 5.5), se quitó el control manual de la temperatura: cualquier valor distinto al predeterminado devuelve un error, y el comportamiento se guía con la forma en que redactas tu solicitud. Las apps de chat normales no tienen este ajuste. Algunos otros modelos y servicios todavía lo ofrecen, así que vale la pena conocer el principio de abajo, pero revisa la documentación de tu modelo.

Recuerda: en el paso de elegir el token, el modelo tiene una distribución de probabilidades. La temperatura decide cómo elegir dentro de ella.

**Temperatura = 0:**
El modelo siempre elige el token con la probabilidad más alta. Un modo totalmente determinista (determinista quiere decir predecible: la misma entrada da la misma salida). Haz la misma pregunta 10 veces y vas a obtener la misma respuesta. Predecible. Confiable. Aburrido. (Incluso con temperatura cero, no siempre está garantizada una respuesta idéntica.)

Sirve para: instrucciones precisas, sacar datos de documentos, tareas estructuradas, código.

**Temperatura = 1 (la predeterminada):**
Un equilibrio entre predictibilidad y variedad. Es el ajuste predeterminado de Claude. Las respuestas son coherentes, pero no mecánicas.

**Temperatura = 1.5 a 2:**
El modelo toma tokens de menor probabilidad: elecciones "inesperadas". Las respuestas se vuelven creativas, sorprendentes, a veces raras. Con temperaturas muy altas, se convierten en disparates.

🎨 **Imagínalo así:** la perilla de especias de un chef. Temperatura 0 es un platillo sin sal ni pimienta: predecible, siempre igual, seguro. Temperatura 1 es la receta de siempre: sabrosa y conocida. Temperatura 2 es el chef echando todo lo que hay en el especiero en cantidades al azar: a veces genial, muchas veces incomible. Para Claude, Anthropic eligió la "temperatura de la cocina" por su cuenta: en los modelos de Claude más nuevos de la API ya no puedes cambiarla, mientras que en varios otros modelos todavía sí.

**Guía práctica:**
- Escribir código / extraer datos → temperatura de 0 a 0.3
- Conversación normal / análisis → temperatura de 0.7 a 1.0
- Lluvia de ideas / escritura creativa → temperatura de 1.0 a 1.3
- Más de 1.5: solo para experimentos

---

### 8. Parámetros del modelo: qué son

Un parámetro (un valor numérico que el modelo aprendió durante el entrenamiento) es uno de los números dentro de una red neuronal que determinan cómo "piensa".

Dicho de forma sencilla: una red neuronal es una función matemática con miles de millones de variables. El entrenamiento es el proceso de encontrar los valores correctos para esas variables, de modo que la función se vuelva buena para predecir el siguiente token.

**Comparación de tamaños:**
- GPT-3 (2020): 175 mil millones de parámetros
- Los modelos insignia actuales de OpenAI, Anthropic y Google: las empresas no revelan su tamaño, y cualquier cifra que encuentres en internet es una suposición
- Llama 3.1 (Meta, de pesos abiertos, es decir, cualquiera puede descargar el modelo): versiones de 8, 70 y 405 mil millones

Más parámetros ≠ un mejor modelo. Es un error común. Lo que importa no es la cantidad, sino la calidad del entrenamiento, los datos y la arquitectura. Modelos más nuevos y más pequeños suelen superar a sus antecesores más grandes.

🎨 **Imagínalo así:** los parámetros son como las sinapsis del cerebro humano (una sinapsis es un punto de conexión entre células nerviosas, donde las señales pasan de una a otra). El cerebro de un recién nacido tiene aproximadamente 100 billones de sinapsis. El de un adulto tiene menos, porque las conexiones que no se usan desaparecen. Aun así, un adulto es más inteligente que un bebé, porque las conexiones que quedan están bien ajustadas. Número de sinapsis ≠ inteligencia. Número de parámetros ≠ la potencia de un modelo. Lo que lo decide todo es cómo están ajustados.

---

### 9. Ajuste fino: así nace un asistente

Después del preentrenamiento básico, tienes un modelo de lenguaje potente pero "en bruto". Sabe predecir tokens. Pero no sabe ser un asistente útil: podría citar propaganda nazi o dar instrucciones para autolesionarse, simplemente porque "eso también era texto de los datos de entrenamiento".

Para convertir un "predictor de texto" en un "asistente útil", los desarrolladores usan el ajuste fino o fine-tuning (entrenamiento adicional de un modelo ya entrenado con datos específicos para un objetivo específico).

**RLHF: el método clave detrás de ChatGPT, GPT-4 y la mayoría de los modelos comerciales**

RLHF (Reinforcement Learning from Human Feedback, aprendizaje por refuerzo con retroalimentación humana) funciona así:
1. El modelo genera varias respuestas posibles a la misma pregunta
2. Revisores humanos las ordenan: esta es mejor, aquella es peor
3. Esas clasificaciones se usan para entrenar un modelo de recompensa aparte (un modelo que califica respuestas)
4. El modelo principal aprende a producir respuestas que el modelo de recompensa califique alto

**Constitutional AI: el método de Anthropic para Claude**

Constitutional AI o IA constitucional (un método de entrenamiento en el que el modelo se guía por un conjunto de principios) es el enfoque que Anthropic usa como base del entrenamiento de Claude.

En lugar de depender solo de calificaciones humanas (las personas se equivocan y tienen sesgos), Claude se entrena para seguir un conjunto de principios explícitos, una "constitución": ser útil, ser honesto, evitar daños. El modelo aprende a criticar sus propias respuestas con base en esos principios y a mejorarlas.

🎨 **Imagínalo así:** dos niños que leyeron exactamente los mismos libros. Al primero (RLHF) lo criaron padres que simplemente lo felicitaban o lo regañaban: "bien" o "mal", sin explicación. Al segundo (Constitutional AI) lo criaron padres que le explicaban los principios: "Eso no está bien, porque lastima a otra persona. Pensemos cómo decirlo de otra forma". El segundo niño entiende mejor por qué hace lo que hace, y aplica esos principios en situaciones nuevas. Esa es la idea sobre la que Anthropic construye el comportamiento de Claude.

---

### 10. Por qué alucina la IA

Una alucinación (cuando la IA afirma con seguridad algo que es falso) es el problema más común que vas a encontrar con los modelos de lenguaje.

La IA cita con seguridad artículos científicos que no existen. Les atribuye frases a personas reales que nunca las dijeron. Da fechas equivocadas de hechos históricos. Y hace todo eso con el mismo tono seguro que usa cuando tiene razón.

**Por qué pasa:**

Recuerda: el modelo está optimizado para "adivinar el siguiente token de modo que el texto suene creíble". No para "decir la verdad". Creíble y verdadero son dos cosas distintas.

Si en los datos de entrenamiento hay muchos textos que mencionan a alguien como "el profesor Martínez de la Universidad de Guadalajara", el modelo va a producir un creíble "profesor Martínez de la Universidad de Guadalajara" aunque esa persona no exista. Porque es un patrón creíble.

Si un dato concreto apareció pocas veces en los datos de entrenamiento, o en contextos contradictorios, el modelo llena el hueco con la opción "más probable". Que puede ser falsa.

La IA no "sabe" datos como una persona sabe algo que leyó en una fuente confiable. La IA vio patrones en textos sobre hechos, y reproduce esos patrones.

🎨 **Imagínalo así:** una persona con memoria fotográfica que leyó absolutamente todo lo que la humanidad ha escrito, pero nunca ha visto el mundo real. Solo texto. Sabe todo lo que alguna vez se puso por escrito. Pero no tiene forma de comprobar: "¿esto pasó de verdad en la vida real?". Cuando le preguntas por un dato concreto, busca en su memoria el patrón más cercano y lo repite. Si el patrón estaba mal en las fuentes, repite el error. Si no había ningún patrón, crea uno que suena creíble pero no existe.

**Cómo protegerte:**
- Verifica siempre los datos importantes en una fuente independiente
- Revisa dos veces fechas, nombres y estadísticas
- Usa Claude con búsqueda web (herramientas) para información actual
- Pregúntale a Claude: "¿Estás seguro de esto? ¿Qué tan probable es que te equivoques?". Los modelos entrenados para ser honestos muchas veces admiten su incertidumbre

---

### 11. Por qué esto importa en la práctica

Esto no es una clase académica. Cada sección tiene un uso directo en tu trabajo.

**Tokens → ahorrar dinero:**
Pagas por tokens. Cuando entiendes qué es un token:
- Escribes prompts más compactos (menos relleno = menos tokens = menor costo)
- Sabes que el inglés suele ser el idioma más barato en tokens, así que si trabajas en otro idioma y el costo importa, puedes escribir tus prompts en inglés
- No cargas documentos enteros al contexto, solo las partes que necesitas

**Ventana de contexto → trabajar con documentos grandes:**
Sabiendo que el contexto tiene límites:
- Divides los documentos grandes en partes y los trabajas uno por uno
- Usas `/compact` en Claude Code cuando un chat se alarga
- Abres un chat nuevo para cada tarea nueva en lugar de meter todo en uno

**Temperatura → consistencia o creatividad:**
Sabiendo cómo funciona la temperatura:
- Pones una temperatura baja para tareas que necesitan resultados repetibles (generar código, extraer datos), donde tu herramienta te deja cambiarla
- Pones una más alta para lluvias de ideas y generar propuestas
- Entiendes por qué el mismo prompt da resultados distintos en distintos intentos

**Alucinaciones → pensamiento crítico:**
Sabiendo de dónde vienen las alucinaciones:
- No confías ciegamente en la IA en preguntas sobre datos
- Siempre verificas lo importante en fuentes primarias
- Usas la IA para ordenar tus ideas, no como sustituto de la verificación de datos

---

## Práctica

**Ejercicio 1: Un experimento con tokens**

Entra a [claude.ai](https://claude.ai) y escribe:

```
Aquí hay una lista de palabras. Para cada una, dime más o menos cuántos tokens ocupa:
cat, catastrophe, computer, AI, internationalization, hello, hola, computadora, anthropomorphism, i18n
```

Mira la respuesta. Después compárala con la documentación de Anthropic sobre el conteo de tokens: [Token counting](https://platform.claude.com/docs/en/build-with-claude/token-counting) (en inglés). El conteo se hace a través de la API (la interfaz que usan los desarrolladores); la página aparte del tokenizador que antes estaba en un enlace más viejo ya no existe. La cantidad de tokens depende del modelo, y distintas generaciones usan distintos tokenizadores, así que la respuesta de Claude es solo una estimación aproximada.

Objetivo: darte una idea de cómo cambia el número de tokens entre idiomas y entre palabras.

**Ejercicio 2: Un experimento de temperatura repitiendo la pregunta**

Escribe el mismo prompt tres veces seguidas sin cambiar nada (abre un chat nuevo cada vez, para que Claude no vea sus respuestas anteriores):

```
Inventa un nombre poco común para una cafetería al estilo del realismo mágico. Solo el nombre, sin explicación.
```

¿Las respuestas coincidieron? ¿Cambiaron un poco? ¿Cambiaron mucho? Eso es la temperatura en acción.

**Ejercicio 3: Una prueba de la ventana de contexto**

Toma cualquier artículo largo de internet (de al menos 5,000 palabras). Pégalo en un chat con Claude y haz una pregunta sobre detalles del principio del artículo. Después pregunta por detalles del final. Compara qué tan precisas son las respuestas.

Luego prueba dividir el mismo artículo en dos solicitudes y fíjate si cambia la calidad de las respuestas.

**Ejercicio 4: Detectar alucinaciones**

Pregúntale a Claude por un dato concreto y poco conocido: por ejemplo, la segunda ciudad más grande de un país poco conocido, o el año en que se fundó una universidad pequeña en particular. Anota la respuesta. Verifícala en Wikipedia. ¿Coincidió?

Objetivo: crear el reflejo de verificar los datos importantes.

---

## Ideas clave

> La IA no es una máquina que piensa. Es un predictor del siguiente token muy avanzado. Eso explica tanto sus fortalezas (patrones, conexiones, velocidad) como sus debilidades (alucinaciones, ninguna comprensión "real").

> Los tokens son la moneda del trabajo con IA. Cuantos menos tokens innecesarios haya en tu prompt, más barato el resultado, y muchas veces más preciso.

> La ventana de contexto es el escritorio de la IA. Lo que está sobre el escritorio, lo ve. Lo que está fuera, no. Administra lo que pones sobre el escritorio.

> La temperatura fija el equilibrio entre predictibilidad y creatividad. Baja para el código. Alta para las ideas.

> Las alucinaciones son una propiedad de la arquitectura. No son mala intención ni una falla al azar. El modelo está optimizado para lo creíble, no para la verdad. Verifica lo importante.

> El ajuste fino convirtió un "predictor de texto" en un "asistente útil". Constitutional AI es el enfoque de Anthropic, y el comportamiento de Claude se construye sobre él.

---

## Próxima lección

→ [Comparación de modelos de IA](00c-ai-models-comparison.md): Claude, GPT, Gemini, Llama, Mistral. Cuándo elegir cuál, las diferencias reales, los precios y cómo debería elegir un negocio.
