# Música con IA: Suno y diseño de sonido

**Tiempo:** unos 20 min de lectura + 30 min de práctica

---

## La idea

Para alguien que tiene un negocio, la música con IA no se trata de volverse músico. Se trata de cubrir tres necesidades concretas: música de fondo para videos, jingles para tu marca y el paquete de sonido de un podcast. Y todo eso sin contratar aparte a un compositor o a un diseñador de sonido.

🎨 **Imagínalo así:** un jingle para tu marca antes significaba contratar a un músico y un estudio, varias reuniones, un par de semanas y un presupuesto aparte. Ahora son 10 minutos en Suno: un prompt, un par de versiones para elegir, y la pista está lista. No es mejor ni peor que la música en vivo. Es otra herramienta para otra escala.

---

## Conceptos clave

- Suno AI: canciones completas a partir de un prompt de texto (un prompt es tu petición a la IA), con voz incluida
- Udio: otro servicio de música con IA; desde octubre de 2025, la descarga de canciones ahí está desactivada (ver la sección de Udio)
- Un prompt musical: género + ambiente + instrumentos + tempo + duración
- Claude te ayuda a escribir la letra (las palabras de la canción) y los prompts para Suno
- Uso comercial: las reglas varían en 2026, así que es importante revisarlas
- ElevenLabs Sound Effects: sonidos cortos para apps, interfaces y podcasts

---

## Teoría

### Para qué necesita música con IA alguien que tiene un negocio

**Tres usos principales:**

**1. Música de fondo para YouTube y otros videos**
La música de stock cuesta dinero o trae condiciones de licencia, y mucha otra gente usa las mismas pistas. La música con IA es única, generada para el ambiente de un video concreto, y con un plan de pago que incluya derechos comerciales puedes usarla en contenido monetizado.

**2. Un jingle de marca**
Una pista corta de 10-30 segundos con el sonido de tu marca. Antes era caro y lento. Ahora son unos cuantos prompts: eliges el mejor y lo ajustas.

**3. Sonido para un podcast o un curso**
Una entrada y un cierre, música de transición entre secciones, ambiente de fondo para las partes de enseñanza.

🎨 **Imagínalo así:** la música en un video es como la iluminación en un restaurante. No notas de forma consciente una mala iluminación, pero te sientes incómodo. La iluminación correcta crea ambiente y calidez y te dan ganas de quedarte. La música de fondo funciona igual.

---

### Suno AI: canciones completas a partir de un prompt

Suno crea canciones completas, que incluyen:

- La parte instrumental
- La voz (en muchos idiomas)
- La estructura de la canción: estrofa, coro, puente

**Cómo funciona:**
Entra a [suno.com](https://suno.com) → "Create" (Crear) → escribe un prompt → recibes dos versiones → escucha → sigue ajustando o descarga.

**Planes (a octubre de 2026):**

- Free: sin costo, 50 créditos al día, el modelo v6-mini, sin derechos comerciales. Puedes escuchar tus pistas y compartir un enlace, pero solo tienes unas pocas descargas de prueba en total
- Pro: desde $8/mes si pagas el año, 2,500 créditos al mes, derechos comerciales, un límite mensual de descargas de canciones
- Premier: desde $24/mes si pagas el año, 10,000 créditos al mes, un límite de descargas más alto, Suno Studio
- El precio depende de cómo pagues (por año o por mes) y puede ser distinto en tu país. Precios y condiciones exactos: [suno.com/pricing](https://suno.com/pricing), [Lo vigente](https://aimayak.com/now/)

**Modos** (los nombres en la interfaz cambian):

- **Custom** (personalizado): tú escribes la letra y eliges un estilo
- **Simple** (modo simple): describes el ambiente y Suno escribe la letra por su cuenta

---

### Prompts para Suno: la fórmula

Un prompt musical sigue una fórmula:

```
[género] [tempo] [ambiente] [instrumentos] [detalles especiales]
```

**Ejemplos de buenos prompts:**

```
# Música de fondo para un video de negocios
música de fondo corporativa y animada, 120bpm,
optimista y profesional, piano y cuerdas,
sin voz, adecuada para YouTube

# Jingle de marca
jingle de marca pegajoso, 15 segundos,
enérgico y fácil de recordar,
electrónico con guitarra,
voz masculina tarareando, ambiente de startup moderna

# Entrada de podcast
música de entrada para podcast, 30 segundos,
lo-fi hip hop, relajado y concentrado,
ritmo suave con crujido de vinilo,
entrada y salida gradual (fade in, fade out), sin voz

# Música de transición para un curso
música ambiental educativa, 10 segundos,
tranquila y concentrada, piano suave,
ambiente neutral, adecuada para transiciones de un curso en línea
```

Puedes escribir en español. Si el resultado no se parece a lo que querías, pídele a Claude que traduzca la descripción al inglés e inténtalo otra vez.

**Lo que funciona:**

- Un tempo concreto (BPM, pulsos por minuto)
- La duración que quieres (Suno no siempre la respeta; recorta lo que sobre en un editor)
- Decir "sin voz" si no necesitas canto
- El propósito (para YouTube / para podcast / para un curso en línea)

**Lo que no funciona:**

- "Haz una música bonita": demasiado vago
- Enumerar 10 o más parámetros: el modelo se confunde
- Estilos que no combinan ("jazz metal ambiental")

---

### Udio: qué cambió

Udio ([udio.com](https://udio.com)) era competidor de Suno. El 29 de octubre de 2025 el servicio anunció una alianza con Universal Music Group, y desde entonces la descarga de audio, video y stems (las pistas separadas de voz e instrumentos) está desactivada: la música se queda dentro de la plataforma. Se anunció una plataforma con licencias para 2026. Revisa el sitio para ver cómo está hoy y si las descargas regresaron.

🎨 **Imagínalo así:** a octubre de 2026, Udio es como un estudio de grabación donde puedes escuchar todo lo que quieras, pero no te dejan llevarte la cinta a casa. Para tareas en las que necesitas un archivo (música de fondo para un video, un jingle, sonido para un curso), Udio hoy no sirve.

**Alternativas a Suno a octubre de 2026:** Google Lyria en la app de Gemini (canciones de hasta tres minutos, con o sin voz; las páginas de Google no indican las condiciones de uso comercial, así que lee la política del servicio) y Soundraw (música de fondo; según el servicio, las pistas que creas vienen con licencia para uso comercial). Compáralas con tus propios prompts y lee la licencia antes de monetizar cualquier cosa.

---

### Claude te ayuda a escribir letras y prompts

Claude no genera música por sí mismo, pero es un excelente ayudante para la preparación:

**1. Letra para el modo Custom de Suno:**

```
Escribe la letra de un jingle corto para una marca.
Marca: [nombre]
A qué se dedica: [qué hace el negocio]
Duración: 30 segundos (4-6 líneas)
Estilo: animado, pegajoso, sin clichés
Idioma: español

Formato: estrofa (4 líneas) + coro (2 líneas)
```

**2. Pulir un prompt para Suno:**

```
Necesito música de fondo para un canal de YouTube sobre [tema].
Público: [descripción]
Ambiente de los videos: [descripción]

Escribe 3 versiones de un prompt para Suno en este formato:
[género] [tempo] [ambiente] [instrumentos] [detalles especiales]
Cada versión en un estilo distinto, todas para el mismo propósito.
```

**3. Organizar una biblioteca de sonidos:**

```
Tengo 10 pistas para mi canal de YouTube.
Ayúdame a armar un sistema de nombres y etiquetas:
- por ambiente (enérgico / tranquilo / concentrado / inspirador)
- por duración (entrada / transición / fondo / cierre)
- por tipo de video (tutorial / vlog / anuncio)
```

---

### Uso comercial: las reglas a octubre de 2026

**Suno:**

- Free: sin uso comercial; solo unas pocas descargas de prueba, para uso personal
- Pro y Premier: derechos comerciales sobre las canciones que descargas como suscriptor de pago, y un número limitado de descargas al mes
- Importante: Suno puede cambiar sus condiciones, así que siempre lee los Terms of Service (términos del servicio) vigentes en el sitio

**Udio:**

- La descarga de canciones está desactivada; revisa las condiciones de monetización en el sitio antes de usar cualquier cosa

**La regla general:**
Si un video está monetizado en YouTube o el contenido se usa para vender algo, necesitas un plan de pago con derechos comerciales (en Suno, Pro o Premier). Guarda una captura de pantalla de las condiciones el día en que creas la pista. Esto no es asesoría legal: si tienes dudas, consulta a un abogado.

---

### ElevenLabs Sound Effects: sonidos cortos

ElevenLabs ([elevenlabs.io/sound-effects](https://elevenlabs.io/sound-effects)) genera efectos de sonido cortos a partir de una descripción de texto (consulta los límites de duración en la página del servicio).

**Usos:**

- El sonido de un botón en una app para celular
- Una notificación en un curso en línea
- Un sonido de transición en un video
- Un logo sonoro para tu marca (3-5 segundos)

**Ejemplos de prompts:**

```
# Sonido de notificación
campanita suave de notificación, sonido de app profesional, 0.5 segundos

# Transición de video
sonido de transición tipo whoosh, limpio y moderno, 1 segundo

# Acción exitosa
sonido de confirmación de éxito, positivo y ligero, 0.8 segundos

# Logo sonoro
sonido de logo de marca, 3 segundos, tono ascendente,
sensación de empresa tecnológica moderna, fácil de recordar
```

**Precio:** los efectos de sonido gastan créditos de tu plan de ElevenLabs. El plan Free te da 10,000 créditos, sin licencia comercial (a octubre de 2026; las condiciones actuales están en la página [Lo vigente](https://aimayak.com/now/)); para proyectos que monetizas, necesitas un plan de pago.

---

## Práctica

1. Crea una cuenta en Suno (gratis):

Entra a [suno.com](https://suno.com) → elige Log in (Iniciar sesión) → escoge una forma de entrar, por ejemplo tu cuenta de Google → recibes créditos gratis (50 al día en Free; las descargas en el plan gratis se limitan a unos pocos archivos de prueba, y el uso comercial requiere un plan de pago)

2. Genera música de fondo para YouTube con ayuda de Claude:

```
Prompt para Claude:
Escribe 3 versiones de un prompt para Suno.
Propósito: música de fondo para un canal de YouTube sobre [tu tema].
Formato del prompt: género + BPM + ambiente + instrumentos + duración.
Sin voz.
```

3. Corre cada prompt en Suno y escucha los resultados (6 pistas = 3 prompts × 2 versiones)

4. Pídele a Claude la letra de un jingle de 15 segundos para tu marca:

```
Marca: [la tuya]
A qué se dedica: [una oración]
Estilo: [lo que quieras]
Escribe 4 líneas + un coro de 2 líneas
```

5. Crea una pista en Suno con el modo Custom: pega la letra de Claude y elige un estilo

6. Entra a ElevenLabs Sound Effects y crea un sonido de transición para tus videos:

```
# Prueba algunas variantes:
"whoosh cinematográfico, 1 segundo, limpio"
"sonido suave de pasar página, 0.5 segundos"
"transición tecnológica sutil, 0.8 segundos"
```

**Compruébalo:** en tu biblioteca de Suno hay seis pistas de fondo y un jingle con letra, elegiste la mejor pista de fondo y puedes decir por qué, y en ElevenLabs tienes un sonido de transición. Todo esto se hizo con planes gratis, así que sirve para aprender y para uso personal, pero no para proyectos comerciales.

---

## Herramientas y recursos

- **[Suno](https://suno.com)**: el generador principal de canciones (plan gratis: 50 créditos al día, solo unas pocas descargas de prueba)
- **[Udio](https://udio.com)**: descarga de canciones desactivada, ver la sección de arriba
- **[ElevenLabs Sound Effects](https://elevenlabs.io/sound-effects)**: sonidos cortos a partir de prompts
- **[Soundraw](https://soundraw.io)**: música de fondo, con licencia según las condiciones del servicio
- **[Google Lyria en Gemini](https://gemini.google/overview/music-generation/)**: canciones en la app de Gemini
- **[Freesound](https://freesound.org)**: una biblioteca de sonidos Creative Commons para mezclar
- **Precios y versiones:** [Lo vigente](https://aimayak.com/now/)

---

## Ideas clave

> Suno y servicios parecidos no reemplazan a los músicos en vivo en proyectos complejos, pero cubren buena parte de lo que necesita alguien que mueve su negocio con contenido: música de fondo, jingles, transiciones. Rápido y único, y con un plan de pago con derechos comerciales, con una licencia clara.

> Un buen prompt musical = género + tempo en BPM + ambiente + instrumentos + duración. Esos cinco elementos te dan un resultado predecible, a diferencia de "haz algo bonito".

> En el proceso musical, Claude es el letrista y el editor de prompts: no genera sonido, pero te ayuda a escribir un encargo preciso para las herramientas que sí lo hacen.

---

## Siguiente lección

→ [Cuánto gastar en IA](00e-investment-roadmap.md): calcular qué suscripciones necesitas y cuánto cuestan
