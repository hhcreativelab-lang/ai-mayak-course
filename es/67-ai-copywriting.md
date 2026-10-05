# Copywriting con IA: una cadena de prompts que suena como tú

**Tiempo:** unos 25 min de lectura + 40 min de práctica

---

## Lo esencial

Pedirle a la IA simplemente "escríbeme una publicación" te da un texto genérico de IA que todo el mundo reconoce y nadie lee. Lo que funciona es una cadena de prompts de varios pasos, más un archivo de voz de marca que le enseña a Claude a escribir con tu estilo.

Todo en esta lección se hace en un chat normal de Claude, en tu navegador o en tu teléfono. No hace falta programar. La tarea con código al final de la práctica es opcional: es para quienes construyen sus propias herramientas.

🎨 **Imagínalo así:** pedirle a Claude un texto sin contexto es como pedirle a un pintor "algo bonito". Vas a tener un cuadro, pero no va a ser tuyo. Una cadena de prompts es un encargo bien hecho para el pintor: estilo, paleta, formato, ambiente, imágenes de referencia. Así no recibes "algo", sino exactamente lo que tenías en mente.

---

## Conceptos clave

- El patrón de ChatGPT es fácil de reconocer, y los detalles concretos son la forma de evitarlo
- La cadena de prompts: idea → esquema → borrador → edición → versión final (5 pasos)
- Un archivo de voz de marca: un contexto fijo que hace que Claude suene como tú
- Formatos: publicaciones de LinkedIn e Instagram, guiones de YouTube, landing pages, correo (cada uno tiene sus propias reglas)
- Generación por lotes: 30 borradores de publicaciones a la vez con un solo prompt
- Detectores de IA: lo que funciona son los detalles concretos, no el disfraz

---

## Teoría

### Por qué los textos al estilo ChatGPT se reconocen tan fácil

Hay un conjunto estándar de palabras y construcciones a las que la IA recurre de forma predeterminada, porque aparecen muchísimo en sus datos de entrenamiento:

```
❌ Patrones de IA que matan la confianza:
- "En el mundo acelerado de hoy..."
- "En la era digital..."
- "Desata tu potencial"
- "Una solución que lo cambia todo"
- "Aprovecha tus fortalezas"
- "Es importante destacar que..."
- Tres viñetas con guiones y un signo de exclamación al final
- Una primera línea que es una pregunta retórica
```

🎨 **Imagínalo así:** es como la sopa de lata. Técnicamente es sopa, pero todos se dan cuenta de que salió de una lata. La sopa casera huele distinto, se ve distinto, sabe distinto. Un buen texto con IA debería saber a ti, no a lata.

**Por qué pasa:**
Sin contexto, Claude escribe para "el lector promedio de un texto promedio". Tu trabajo es darle suficientes detalles concretos para que lo "promedio" se vuelva "tuyo".

---

### La cadena de prompts: 5 pasos de la idea al texto final

En lugar de un prompt grande, haces una secuencia de pasos pequeños y precisos. Cada paso es un mensaje aparte en el mismo chat.

**Paso 1: Idea → Enfoque**

```
Tema: [sobre qué quieres escribir]
Público: [quién lo va a leer]
Objetivo del texto: [qué debería hacer o sentir el lector]
Enfoque: [una mirada menos obvia del tema, si ya tienes una; si no, borra esta línea]

Propón 5 enfoques distintos para una publicación sobre este tema.
Una frase por enfoque. Sin relleno.
```

**Paso 2: Enfoque → Esquema**

```
Enfoque elegido: [copiado del paso 1]
Formato: [publicación de LinkedIn / texto para Instagram / guion de YouTube / correo / landing page]
Extensión: [número de palabras o caracteres]

Escribe un esquema sin escribir el texto en sí.
Solo los títulos de las secciones y una línea sobre lo que cubre cada una.
```

**Paso 3: Esquema → Borrador**

```
[Pega el esquema del paso 2]
[Pega tu archivo de voz de marca o una descripción corta de tu estilo]

Escribe un borrador que siga el esquema al pie de la letra.
Detalles concretos en lugar de afirmaciones generales.
Usa solo los ejemplos y los números que yo te di. Si necesitas más, pregúntame.
```

**Paso 4: Borrador → Edición**

```
[Pega el borrador]

Revisa y mejora:
1. ¿La primera frase atrapa la atención? Reescríbela si no
2. ¿Hay clichés de IA? Reemplázalos por detalles concretos
3. ¿Cada párrafo aporta una idea nueva? Quita las repeticiones
4. ¿La llamada a la acción del final es concreta, y hay solo una?
```

**Paso 5: Edición → Versión final**

```
[El borrador después de las ediciones]

Revisión final:
- ¿La extensión es la adecuada para el formato?
- ¿El tono es el adecuado para [plataforma]?
- ¿Un lector, una acción al final?

Dame el texto final.
```

Una cadena así toma más tiempo que una sola solicitud, pero el texto sale notablemente mejor. Lee tú mismo la versión final antes de publicarla: revisar los datos, los números y los nombres te toca a ti.

---

### El archivo de voz de marca: tu estilo como documento

Un archivo de voz de marca es un documento que le das a Claude antes de cada texto. Describe cómo escribes, qué nunca escribes, quién es tu público, e incluye ejemplos de tus mejores trabajos.

**Estructura de un archivo `brand-voice.md`:**

```markdown
# Voz de marca: [Tu nombre / nombre del proyecto]

## Quién soy
[2-3 frases: quién eres, qué haces, para quién lo haces]

## Público
- Quiénes son: [descripción]
- Qué les importa: [3-5 puntos]
- Qué les molesta: [2-3 puntos]

## Tono
- Escribo: [conversacional / formal / relajado / de experto]
- NO escribo: [jerga de coach / jerga del sector / números sin fuente]
- Ejemplos de un tono que me gusta: [enlaces o muestras]

## Estilo
- Frases: [cortas / medianas / largas / mezcladas]
- Párrafos: [1-3 líneas / más largos]
- Estructura: [listas / prosa / mezcla]
- Emoji: [ninguno / pocas veces / seguido]

## Palabras y frases prohibidas
- "sinergia", "pensar fuera de la caja", "salir de tu zona de confort"
- "es importante destacar", "en el mundo acelerado de hoy"
- [agrega las tuyas]

## Ejemplos de mis mejores textos
[Pega 2-3 de tus mejores publicaciones o correos]

## Fórmulas que me funcionan
- Fórmula de publicación: [gancho → historia → conclusión → pregunta]
- Fórmula de correo: [asunto que nombra el problema → historia → solución → CTA]
```

CTA viene de call to action, llamada a la acción: lo único que le pides al lector que haga.

`brand-voice.md` es un archivo de texto normal: escríbelo en cualquier editor o app de notas y pega su texto al inicio de un chat. Si organizas tus archivos con el sistema PARA, este archivo va en `areas/marketing/brand-voice.md` (es una lección opcional de la biblioteca: [Organiza tus carpetas: el sistema PARA para emprendedores con IA](66-folder-structure-philosophy.md)). Para no tener que pegar el archivo cada vez, puedes convertirlo en una Skill (habilidad) de Claude: una instrucción guardada que Claude carga por su cuenta cuando sirve para la tarea. Las Skills están en Customize → Skills (Personalizar → Habilidades) y, a octubre de 2026, están disponibles en todos los planes.

🎨 **Imagínalo así:** un archivo de voz de marca es como la guía de bienvenida que le darías a un nuevo redactor de tu equipo. Sin ella, escribe "bien". Con ella, escribe como tú.

---

### Formatos: cada uno tiene sus propias reglas

**Publicación de LinkedIn o texto para Instagram (hasta 1,000 caracteres):**

```
Reglas:
- Primera línea = el gancho (sin palabras de calentamiento)
- Párrafos de 1-2 líneas con una línea en blanco entre ellos
- Una conclusión o pregunta al final
- Emoji solo si es tu estilo

Prompt:
"Escribe una publicación de LinkedIn de hasta 800 caracteres.
Tema: [tema]. Gancho en la primera línea, sin calentamiento.
Párrafos de 2 líneas como máximo.
Sin signos de exclamación al final."
```

**Guion de YouTube (8-12 minutos = unas 1,200-1,800 palabras):**

```
Estructura:
[0:00-0:30] Gancho: qué va a obtener quien ve el video
[0:30-1:30] Problema: por qué importa
[1:30-8:00] Contenido principal: 3-5 secciones
[8:00-9:30] Resumen + práctica
[9:30-10:00] CTA: suscríbete / enlace

Prompt:
"Escribe un guion de YouTube de 10 minutos.
Tema: [tema]. Gancho en los primeros 30 segundos.
Estilo conversacional. Marca los tiempos.
Cada sección lleva a la siguiente."
```

**Textos para una landing page:**

```
Estructura:
Hero: título + subtítulo + CTA
Problema: los dolores del lector (3)
Solución: cómo los resuelves
Cómo funciona: 3 pasos
Prueba: prueba social (testimonios, reseñas, logotipos de clientes)
Preguntas frecuentes: 5 preguntas
CTA: la llamada a la acción final

Prompt:
"Escribe los textos de una landing page.
Producto: [descripción].
Público objetivo: [descripción].
La mayor preocupación del cliente: [preocupación].
El resultado principal que obtiene: [resultado].
Tono: [profesional / cercano]."
```

💡 La prueba social tiene que ser real. No dejes que la IA escriba testimonios o reseñas por ti; dale las palabras que de verdad usaron tus clientes.

---

### Generación por lotes: 30 publicaciones a la vez

En lugar de escribir una publicación a la vez, genera un lote completo:

```
Este es mi calendario de contenido del mes. Temas:
1. [tema 1]
2. [tema 2]
...
30. [tema 30]

Voz de marca: [pega el texto o adjunta el archivo]
Formato: publicación de LinkedIn, de hasta 600 caracteres cada una

Escribe las 30 publicaciones, una tras otra.
Numera cada una.
Pon un separador --- entre publicaciones.
```

El resultado: 30 borradores de publicaciones con una sola solicitud. Después pules los mejores y archivas el resto.

**Importante:** el modo por lotes baja la calidad de cada publicación individual. Úsalo para borradores, no para textos finales.

---

### ¿Y los detectores de IA?

Un detector de IA es un servicio que intenta adivinar si un texto lo escribió una máquina. La verdad es sencilla: los detectores de IA no detectan el "estilo IA", detectan lo predecible. Además se equivocan en ambas direcciones y no pueden probar quién escribió un texto. Así que la meta no es burlar una revisión; es escribir textos concretos que la gente de verdad disfrute leer.

Lo que hace predecible un texto:

- Afirmaciones generales sin detalles concretos
- Frases todas del mismo largo
- Ningún giro conversacional
- Cero experiencia personal

**La solución son los detalles concretos, no el disfraz:**

```
❌ "Muchos emprendedores tienen dificultades para escalar su negocio"
✅ "En abril mi tasa de conversión bajó de 4% a 1.8%. Esto es lo que encontré."

❌ "La inteligencia artificial está transformando los negocios"
✅ "Claude escribió 47 publicaciones en una tarde. Edité 12. Te cuento cuáles."
```

Agrega esto a tu prompt:

```
En el texto, incluye:
- Un número concreto de mi propia experiencia: [escribe el número]
- Un detalle inesperado: [escribe el detalle]
- Una frase que suene como si la estuvieras diciendo en voz alta
```

Dale a Claude tú mismo el número real y el detalle real. Si lo dejas adivinar, puede que simplemente los invente (cuando la IA inventa algo con seguridad se le llama alucinación), y una cifra inventada en tu marketing es peor que ninguna cifra.

---

## Práctica

1. Crea un archivo `brand-voice.md` para tu proyecto con la plantilla de esta lección. Sirve cualquier editor de texto o app de notas: necesitas el archivo para pegar su texto en un chat. Terminaste cuando todas las secciones están llenas y en los ejemplos hay 2-3 textos tuyos de verdad. El comando de abajo es solo para quienes trabajan en una terminal y guardan sus archivos en carpetas; los demás pueden saltárselo:

```bash
mkdir -p ~/workspace/areas/marketing
# Crea el archivo y llena cada sección
```

2. Escribe tu primera publicación de LinkedIn (o texto para Instagram) con la cadena de 5 pasos:

```
Tema: [elige algo de tu propio trabajo]
Haz cada paso como un prompt aparte
Guarda el resultado de cada paso
```

3. Cuando termines la cadena, pídele a Claude que califique el texto final:

```
Califica este texto en una escala del 1 al 10 según estos criterios:
- Concreción (sin frases genéricas)
- Coincidencia con mi voz de marca
- Fuerza de la primera frase
- Claridad de la llamada a la acción

Para cada criterio: una calificación y una frase sobre qué mejorar.
```

4. Genera un lote de 10 borradores de publicaciones. Escribe tu lista de 10 temas directamente en el chat. El comando de abajo crea la misma lista como archivo en una terminal; es opcional:

```bash
# Crea un archivo con tus temas
echo "1. [tema 1]
2. [tema 2]
...
10. [tema 10]" > content-plan.txt
```

Dale a Claude la lista de temas más tu voz de marca, recibe 10 borradores y elige los 3 mejores.

5. Opcional, para quienes construyen sus propias herramientas y ya trabajan con código: un script generador en Python. Los demás pueden saltarse esta tarea; la lección está completa sin ella.

```python
import os
import anthropic

client = anthropic.Anthropic()
os.makedirs("posts", exist_ok=True)

with open("brand-voice.md", encoding="utf-8") as f:
    brand_voice = f.read()

topics = [
    "tema 1",
    "tema 2",
    "tema 3",
]

for i, topic in enumerate(topics, 1):
    message = client.messages.create(
        model="claude-sonnet-5-5",  # para los ID de modelo vigentes, mira la documentación de Anthropic
        max_tokens=4000,  # con margen a propósito: el "razonamiento" del modelo cuenta dentro de este límite
        messages=[{
            "role": "user",
            "content": f"""Voz de marca:
{brand_voice}

Escribe una publicación de LinkedIn sobre: {topic}
Hasta 600 caracteres. Gancho en la primera línea."""
        }]
    )
    # La respuesta puede traer bloques de "razonamiento": nos quedamos solo con el texto
    text = "".join(block.text for block in message.content if block.type == "text")

    with open(f"posts/post-{i:02d}.md", "w", encoding="utf-8") as f:
        f.write(f"# Publicación {i}: {topic}\n\n")
        f.write(text)

    print(f"Publicación {i} lista")
```

El script lee tu clave de API desde la variable de entorno `ANTHROPIC_API_KEY`. Nunca pegues la clave en el código.

---

## Herramientas y recursos

- **[Claude.ai](https://claude.ai)**: tu herramienta principal para la cadena de prompts
- **[Anthropic API](https://claude.com/api)**: para la generación por lotes con código (precios y modelos: [Lo vigente](https://aimayak.com/now/))
- **[Hemingway App](https://hemingwayapp.com)**: revisa qué tan fácil de leer es tu texto (funciona en inglés)
- **[QuillBot](https://quillbot.com)**: para reformular en el pulido final
- **[GPTZero](https://gptzero.me)**: un detector de IA por el que puedes pasar tu texto (para ver cómo estás)

---

## Ideas clave

> Una cadena de prompts de 5 pasos produce textos de otra calidad que un solo prompt grande. Es la diferencia entre la comida rápida y una comida en un buen restaurante: las dos se hacen con ingredientes, pero el proceso no es el mismo.

> Un archivo de voz de marca es una inversión de una sola vez: escríbelo bien, y cada texto que hagas con Claude después va a salir más cerca de tu voz, sin explicaciones de más.

> Los detectores de IA detectan lo predecible, no el "estilo IA". Agrega números concretos, experiencia personal y frases conversacionales, y tu texto se va a sentir vivo sin importar con qué herramienta lo escribiste.

---

## Qué sigue

→ [IA para el correo: una bandeja más inteligente, borradores y respuestas](73-ai-email-communications.md): ordenar tu bandeja y preparar borradores de respuesta

Opcional, en la biblioteca: [Voz con IA: ElevenLabs, texto a voz y contenido de audio](68-voice-tts-elevenlabs.md): convertir tus textos terminados en audio
