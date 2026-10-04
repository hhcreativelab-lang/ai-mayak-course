# El flujo completo de contenido con IA: de la idea a la publicación

**Tiempo:** unos 30 min de lectura + 60 min de práctica

---

## Lo esencial

Una persona, en un solo día de trabajo, produce el contenido de una semana para cinco plataformas: texto, voz, video y un calendario de publicación. No porque sea un genio. Porque tiene armado el flujo correcto. Hoy construimos juntos ese flujo: tendencias → idea → texto → imagen → voz → video → publicación. Claude es el director de orquesta y las demás herramientas son la orquesta.

🎨 **Imagínalo así:** una planta armadora de Toyota. Nadie arma el carro a mano: aprietas un botón y los robots montan las llantas, pintan la carrocería y hacen las pruebas. Un carro terminado sale de la línea. La idea es la carrocería. Claude, ElevenLabs, Runway y Buffer son los robots de la línea. Tú eres el gerente de planta que decide qué se fabrica.

---

## Conceptos clave

- **Fábrica de contenido**: un solo orquestador maneja toda la cadena, de una tendencia a una publicación hecha
- **Una idea → muchos formatos**: adaptar para cada plataforma sin escribir todo desde cero
- **Un calendario de contenido en JSON**: un calendario legible por máquina que Claude entiende y ejecuta
- **Generación en paralelo**: Claude, ElevenLabs y Runway trabajan al mismo tiempo, no uno tras otro
- **Ciclo de análisis**: las métricas del contenido publicado regresan a Claude para mejorar la siguiente tanda
- **Puntos de control**: momentos de aprobación, para que nada a medio hacer se publique solo
- **Producción por tandas**: 30 publicaciones en una sola corrida, y cómo se ve el costo por pieza a esa escala

---

## Teoría

### Arquitectura: las 9 estaciones del flujo

Antes de escribir código, dibujamos el diagrama. Toda la fábrica está hecha de 9 estaciones:

```
TENDENCIA → INVESTIGACIÓN → ESQUEMA → TEXTO → ADAPTACIONES → IMAGEN → VOZ → CALENDARIO → ANÁLISIS
```

Cada estación es una llamada a una API distinta (API significa interfaz de programación de aplicaciones: la forma en que un programa habla con otro). Cualquier estación se puede cambiar o apagar sin reconstruir todo el sistema.

🎨 **Imagínalo así:** LEGO Technic. Cada bloque es una pieza aparte con una forma clara de conectarse. Si se descompone un motor, cambias solo ese motor; no desarmas todo el carro. Claude son los bloques de texto. Runway es el video. ElevenLabs es la voz. Buffer es la entrega.

**Qué hace cada estación:**

| Estación | Herramienta | Qué hace |
|---|---|---|
| Tendencia | Búsqueda web + Claude | Qué está de moda hoy |
| Investigación | Claude + herramientas MCP (búsqueda, documentación) | Hechos, datos, fuentes |
| Esquema | Claude Sonnet | La estructura de la pieza |
| Texto (principal) | Claude Sonnet | El artículo o guion completo |
| Adaptaciones | Claude Haiku | Boletín, X (Twitter), LinkedIn |
| Imagen | gpt-image-2 / Ideogram / Nano Banana | Portada, ilustraciones (DALL-E 3 se apagó en la API el 12 de mayo de 2026) |
| Video (opcional) | Kling / Runway | Un video corto de 5–15 segundos |
| Voz (opcional) | ElevenLabs (TTS, text-to-speech: convertir texto en audio hablado) | Locución para Reels y Shorts |
| Publicación | Buffer API / tu plataforma de boletines / la API directa de un bot | Programar y enviar |

**Cuánto cuesta un paquete de contenido**: calcúlalo con los precios de cada servicio. Para Claude, este es el orden de magnitud (precios por 1 millón de tokens a octubre de 2026: Sonnet 5.5 cuesta $2 de entrada y $10 de salida, Haiku 4.5 cuesta $1 y $5): un artículo de 1,200 palabras cuesta unos centavos, y las adaptaciones cuestan uno o dos centavos. Las imágenes, el video y la voz cuestan lo que cobre el servicio que elijas. Para sumar todas tus herramientas, usa la lección [Cuánto cuestan de verdad las herramientas de IA](d04-ai-stack-costs.md).

---

### Un calendario de contenido en JSON: un calendario legible por máquina

Un calendario de contenido no es una hoja de Excel. Es un archivo JSON que Claude lee y ejecuta. Legible por máquina significa que Claude puede llenar la semana siguiente por su cuenta, con base en las estadísticas de la semana anterior.

```json
{
  "brand": {
    "name": "Acme Realty",
    "voice": "Experto amable. No un vendedor. Datos + historias.",
    "audience": "Personas de 35 a 55 años que piensan mudarse a Ecuador o invertir ahí",
    "languages": ["es"],
    "channels": ["newsletter", "youtube", "instagram", "linkedin"]
  },
  "week": "2026-10-05",
  "posts": [
    {
      "id": "post-001",
      "publish_at": "2026-10-05T09:00:00-05:00",
      "topic": "Cuánto cuesta de verdad vivir en Cuenca en 2026",
      "content_type": "educational",
      "formats": {
        "blog": { "words": 1200, "status": "pending" },
        "newsletter": { "sections": 3, "status": "pending" },
        "youtube_script": { "duration_min": 8, "status": "pending" },
        "twitter": { "tweets": 5, "status": "pending" },
        "linkedin": { "status": "pending" }
      },
      "assets": {
        "cover_image": null,
        "short_video": null,
        "voice_over": null
      },
      "keywords": ["costo de vida en Cuenca", "costo de vida en Ecuador", "mudarse a Ecuador"],
      "approved": false
    }
  ]
}
```

Cuando `approved` cambia a `true`, el orquestador arranca la producción y llena `assets`.

---

### Una idea → muchos formatos

🎨 **Imagínalo así:** un diamante en bruto. Una sola piedra, distintos cortes: un anillo, aretes, un dije, un broche. La sustancia es la misma; la forma se hace para cada mercado.

Así es como Claude Haiku convierte un artículo principal en versiones para cada plataforma por un par de centavos:

```python
import anthropic
import json
import os

claude = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])


def generate_main_article(topic: str, keywords: list[str],
                           brand_voice: str, word_count: int = 1200) -> str:
    """Genera un artículo completo optimizado para SEO con Claude Sonnet."""
    response = claude.messages.create(
        model="claude-sonnet-5-5",  # IDs de modelo vigentes: revisa la documentación de Anthropic
        max_tokens=4000,
        messages=[{
            "role": "user",
            "content": f"""Escribe un artículo de blog.

Tema: {topic}
Extensión: {word_count} palabras
Palabras clave SEO: {', '.join(keywords)}
Voz de la marca: {brand_voice}

Estructura:
1. Título H1 (con la palabra clave principal)
2. Introducción (150 palabras, un gancho + una promesa)
3. 3–4 secciones H2 con datos y cifras concretas
4. Consejos prácticos (lista con viñetas)
5. Conclusión + llamado a la acción

Requisitos:
- Solo datos, sin relleno como "esto es muy importante"
- Cifras y ejemplos concretos
- Tono conversacional pero experto
- Idioma: español neutro de América Latina, formato Markdown"""
        }]
    )
    return response.content[0].text


def adapt_to_all_platforms(main_article: str, brand_context: str,
                            topic: str) -> dict:
    """
    Convierte un artículo base en contenido para cada plataforma.
    Claude Haiku: rápido y barato (un par de centavos).
    """
    response = claude.messages.create(
        model="claude-haiku-4-5",  # Haiku 4.5: su retiro de la API es posible no antes del 15 de octubre de 2026; revisa los IDs en la documentación de Anthropic
        max_tokens=3000,
        messages=[{
            "role": "user",
            "content": f"""Eres el estratega de contenido de la marca. Marca: {brand_context}

Artículo principal sobre el tema "{topic}":
---
{main_article}
---

Adáptalo a los siguientes formatos. Devuelve SOLO JSON válido:

{{
  "newsletter": {{
    "subject_line": "Asunto (corto y concreto)",
    "sections": [
      "Sección 1: la historia principal (hasta 1,000 caracteres, con emoji, amigable)",
      "Sección 2: profundiza en una idea (800 caracteres)",
      "Sección 3: un consejo práctico + llamado a la acción (600 caracteres)"
    ]
  }},
  "twitter_thread": [
    "Publicación 1/5: gancho (hasta 280 caracteres)",
    "Publicación 2/5: dato clave",
    "Publicación 3/5: un ejemplo o una historia",
    "Publicación 4/5: un ángulo inesperado",
    "Publicación 5/5: conclusión + enlace"
  ],
  "linkedin_post": "Versión para LinkedIn (300–400 palabras, tono profesional)",
  "instagram_caption": "Versión para Instagram (150–200 palabras + 15 hashtags)",
  "youtube_description": "Descripción para YouTube (300 palabras, marcas de tiempo, palabras clave)"
}}"""
        }]
    )
    return json.loads(response.content[0].text)


def generate_youtube_script(topic: str, duration_minutes: int,
                              brand_voice: str) -> str:
    """Genera el guion de un video de YouTube con marcas de tiempo."""
    words_per_minute = 130    # un ritmo de habla típico; mídete y ajústalo
    target_words = duration_minutes * words_per_minute

    response = claude.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=5000,
        messages=[{
            "role": "user",
            "content": f"""Escribe el guion de un video de YouTube.

Tema: {topic}
Duración: {duration_minutes} min (~{target_words} palabras)
Voz: {brand_voice}

Formato de cada bloque:
[MM:SS] TÍTULO DEL BLOQUE
(Nota de dirección: qué mostrar en pantalla / tomas de apoyo)
Texto del presentador...

Estructura:
[00:00] GANCHO: los primeros 30 segundos, la parte más importante
[00:30] INTRO: quién es el presentador, de qué trata el video
[01:00] PARTE PRINCIPAL: 3–4 bloques de 2–3 minutos cada uno
[{duration_minutes-1}:00] CIERRE: resumen + llamado a la acción
[{duration_minutes-1}:30] DESPEDIDA: suscríbete, siguiente video

Escribe de forma viva y conversacional, como si le hablaras a un amigo."""
        }]
    )
    return response.content[0].text
```

---

### Programar publicaciones: la API directa de un bot y la API de Buffer

Para la mayoría de los canales, casi todo el trabajo pasa por la Vía 2 (Buffer): Instagram, LinkedIn, X. Tu boletín normalmente sale desde su propia plataforma (Beehiiv, Kit, Mailchimp y otras). El flujo le entrega un borrador terminado, y tú lo pegas o, si tu plataforma tiene API, lo mandas desde el código con el mismo patrón que los ejemplos de abajo.

**Vía 1: la API directa de un bot, con Telegram como ejemplo**: publicar directamente, gratis. Telegram es solo un ejemplo: según tu audiencia puede ser más o menos usado que un boletín por correo, así que trata este código como un patrón y no como una recomendación: un token en una variable de entorno y una función que manda texto con una imagen opcional. Un canal privado de Telegram también sirve como canal de prueba gratis para ver las publicaciones en tu celular.

```python
import asyncio
from telegram import Bot, InputFile
import os

TELEGRAM_BOT_TOKEN = os.environ["TELEGRAM_BOT_TOKEN"]
CHANNEL_ID = os.environ["TELEGRAM_CHANNEL_ID"]


async def publish_to_telegram(text: str, image_path: str = None) -> dict:
    """Publica en un canal de Telegram."""
    bot = Bot(token=TELEGRAM_BOT_TOKEN)

    if image_path:
        with open(image_path, "rb") as img:
            message = await bot.send_photo(
                chat_id=CHANNEL_ID,
                photo=InputFile(img),
                caption=text,
                parse_mode="Markdown"
            )
    else:
        message = await bot.send_message(
            chat_id=CHANNEL_ID,
            text=text,
            parse_mode="Markdown"
        )

    return {"message_id": message.message_id, "date": str(message.date)}
```

**Vía 2: la API de Buffer**: un programador para Instagram, LinkedIn y Twitter/X. La API de Buffer está hecha sobre GraphQL (la dirección es `https://api.buffer.com`), y la clave la creas en la configuración de Buffer; el plan gratis te da una clave. El esquema se rehízo en 2026, así que revisa los campos en [developers.buffer.com](https://developers.buffer.com):

```python
import json
import os
import requests

BUFFER_API_KEY = os.environ["BUFFER_API_KEY"]
BUFFER_CHANNEL_IDS = {
    "instagram": os.environ["BUFFER_INSTAGRAM_CHANNEL_ID"],
    "linkedin": os.environ["BUFFER_LINKEDIN_CHANNEL_ID"],
    "twitter": os.environ["BUFFER_TWITTER_CHANNEL_ID"],
}


def schedule_to_buffer(text: str, platform: str, due_at: str) -> dict:
    """
    Programa una publicación con la API de Buffer (GraphQL).
    due_at: hora de publicación en formato ISO 8601, UTC, por ejemplo 2026-10-12T14:00:00.000Z
    Los archivos multimedia se mandan a la API de Buffer como un enlace público: revisa la documentación.
    """
    query = f"""
    mutation {{
      createPost(input: {{
        text: {json.dumps(text, ensure_ascii=False)},
        channelId: "{BUFFER_CHANNEL_IDS[platform]}",
        schedulingType: automatic,
        mode: customScheduled,
        dueAt: "{due_at}"
      }}) {{
        ... on PostActionSuccess {{ post {{ id dueAt }} }}
        ... on MutationError {{ message }}
      }}
    }}
    """
    response = requests.post(
        "https://api.buffer.com",
        headers={"Authorization": f"Bearer {BUFFER_API_KEY}"},
        json={"query": query},
    )
    return response.json()
```

---

### Un flujo en n8n: automatizar todo el proceso

n8n es una plataforma de automatización que te deja conectar de forma visual cada parte del flujo. Su código fuente es abierto (licencia Sustainable Use, "fair-code"), y puedes correr la Community Edition en tu propio servidor y usarla gratis para trabajo interno. Es una alternativa a Make y Zapier. Más en [n8n + IA: flujos inteligentes](78-n8n-ai-workflows.md).

**Un flujo básico de n8n para la fábrica de contenido:**

```
Cron (lunes 09:00)
  → HTTP: leer content-calendar.json desde GitHub
  → Code: quedarse solo con approved: true
  → Loop: para cada publicación:
    → API de Claude: generar el artículo (Sonnet)
    → API de Claude: adaptaciones por plataforma (Haiku) [en paralelo]
    → Generación de imagen: portada [en paralelo]
    → API de Buffer: programar LinkedIn y Twitter/X
    → Plataforma de boletines: guardar la edición como borrador
    → Google Docs: guardar todo para una revisión final
  → Aviso por Slack o correo: "X publicaciones listas, esperando revisión"
```

Alternativas a n8n: **Make** (antes Integromat) y **Zapier**, ambos servicios en la nube que cobran por créditos y tareas (precios: [Lo vigente](https://aimayak.com/es/now/)). Más en [Zapier AI](79-zapier-ai.md).

---

### El orquestador: un solo script de bash para todo el flujo

🎨 **Imagínalo así:** un director de orquesta. El director no toca el violín; dirige a toda la orquesta. Les da la entrada a los violines (Claude), a las flautas (ElevenLabs), al chelo (Runway). Cada músico conoce su parte. El director conoce toda la sinfonía.

```bash
#!/usr/bin/env bash
# content-factory-orchestrator.sh
set -euo pipefail

WEEK_DATE="${1:-$(date +%Y-%m-%d)}"
CALENDAR_FILE="content-calendar.json"
OUTPUT_DIR="./content-output/${WEEK_DATE}"

mkdir -p "$OUTPUT_DIR"
log() { echo "[$(date +%H:%M:%S)] $1"; }

log "🏭 La fábrica de contenido arrancó. Semana: $WEEK_DATE"

POSTS=$(jq -r '.posts[] | select(.approved == true) | .id' "$CALENDAR_FILE")

if [ -z "$POSTS" ]; then
    log "⚠️ No hay publicaciones aprobadas. Deteniendo."
    exit 0
fi

for POST_ID in $POSTS; do
    log "▶️ Procesando: $POST_ID"
    POST_DIR="${OUTPUT_DIR}/${POST_ID}"
    mkdir -p "$POST_DIR"

    TOPIC=$(jq -r ".posts[] | select(.id == \"$POST_ID\") | .topic" "$CALENDAR_FILE")
    KEYWORDS=$(jq -r ".posts[] | select(.id == \"$POST_ID\") | .keywords | join(\", \")" "$CALENDAR_FILE")
    PUBLISH_AT=$(jq -r ".posts[] | select(.id == \"$POST_ID\") | .publish_at" "$CALENDAR_FILE")

    log "  Tema: $TOPIC"

    # Artículo y guion de YouTube en paralelo
    python3 generate_article.py --topic "$TOPIC" --keywords "$KEYWORDS" \
        --output "${POST_DIR}/article.md" &
    python3 generate_script.py --topic "$TOPIC" --duration 8 \
        --output "${POST_DIR}/youtube-script.md" &

    wait

    # Adaptaciones e imagen de portada en paralelo
    python3 adapt_platforms.py --article "${POST_DIR}/article.md" \
        --output "${POST_DIR}/adaptations.json" &
    python3 generate_image.py --topic "$TOPIC" \
        --output "${POST_DIR}/cover.jpg" &

    wait
    log "  ✅ El contenido de $POST_ID está listo"

    # Programar las publicaciones
    python3 schedule_content.py --post-id "$POST_ID" \
        --adaptations "${POST_DIR}/adaptations.json" \
        --cover "${POST_DIR}/cover.jpg" \
        --publish-at "$PUBLISH_AT"
done

log "🎉 ¡Listo! Publicaciones programadas: $(echo "$POSTS" | wc -w)"
```

---

### El ciclo de análisis: contenido que aprende de los resultados

```python
def run_analytics_loop(days_back: int = 7) -> dict:
    """
    Reúne las métricas de la semana pasada y genera temas para la próxima semana.
    """
    newsletter_stats = get_newsletter_stats(days_back)
    youtube_stats = get_youtube_stats(days_back)
    instagram_stats = get_instagram_stats(days_back)

    combined_stats = {
        "newsletter": newsletter_stats,
        "youtube": youtube_stats,
        "instagram": instagram_stats,
        "period_days": days_back,
    }

    response = claude.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=2000,
        messages=[{
            "role": "user",
            "content": f"""Eres analista de estrategia de contenido.
Analiza los resultados de los últimos {days_back} días:

{json.dumps(combined_stats, ensure_ascii=False, indent=2)}

Da un análisis estructurado en JSON:
{{
  "winners": ["publicación + por qué funcionó"],
  "flops": ["publicación + por qué no pegó"],
  "patterns": ["qué tipo de contenido funciona de forma constante"],
  "best_time": {{"newsletter": "HH:MM", "instagram": "HH:MM"}},
  "next_week_topics": ["tema 1", "tema 2", "tema 3", "tema 4", "tema 5"],
  "strategy_changes": ["qué cambiar en el proceso de producción"]
}}

Usa solo los datos de estas estadísticas; no inventes nada."""
        }]
    )

    recommendations = json.loads(response.content[0].text)
    update_calendar_with_recommendations(recommendations)
    return recommendations
```

---

### Cuánto cuesta el flujo: cómo calcularlo

Un plan típico: 5 temas a la semana × 4 semanas = 20 paquetes de contenido al mes.

| Componente | Cómo calcularlo |
|---|---|
| Claude Sonnet (artículo + guion) | tokens × precio de la API. Sonnet 5.5 a octubre de 2026: $2 de entrada y $10 de salida por 1 millón de tokens; un artículo de 1,200 palabras cuesta unos centavos |
| Claude Haiku (adaptaciones) | Haiku 4.5: $1 de entrada y $5 de salida por 1 millón de tokens; un juego de adaptaciones cuesta uno o dos centavos |
| Imagen (portada) | los precios del servicio que elijas |
| ElevenLabs (locución, opcional) | créditos de tu plan |
| Video de Kling o Runway (opcional) | créditos por segundo de video, normalmente el renglón más caro |
| Programador | Buffer y Typefully tienen planes gratis para empezar; los planes de pago se cobran por canal |

El total es la suma de esos precios. Calcula tu propia versión con la fórmula de la lección [Cuánto cuestan de verdad las herramientas de IA](d04-ai-stack-costs.md) antes de prometerle a nadie un flujo regular de contenido.

---

## Práctica

### Paso 1: Crea la estructura del proyecto

```bash
mkdir -p content-factory/{scripts,templates,output,logs}
cd content-factory
touch content-calendar.json scripts/generate_article.py \
      scripts/adapt_platforms.py scripts/schedule_content.py .env
```

### Paso 2: Llena la primera publicación en calendar.json

Copia la plantilla JSON de la sección de teoría. Cambia el tema por uno que encaje con tu negocio o con el nicho de tu cliente. Pon `"approved": true` para una corrida de prueba.

### Paso 3: Arma generate_article.py

Usa la función `generate_main_article()` de la sección de teoría. Agrega argparse para `--topic`, `--keywords` y `--output`. Córrelo y revisa que el artículo se genere y se guarde en un archivo.

### Paso 4: Arma adapt_platforms.py

Usa `adapt_to_all_platforms()`. La entrada es el archivo del artículo; la salida es `adaptations.json`. Abre el JSON y lee las secciones del boletín: deben sonar como si las hubiera escrito una persona, no como una traducción rígida de máquina.

### Paso 5: Configura la publicación

Para Instagram, LinkedIn y X, conecta las cuentas en Buffer y prueba `schedule_to_buffer()` con una publicación programada para mañana. Para ver una publicación exactamente como la vería un suscriptor, la opción gratis más rápida es un canal privado de prueba en Telegram (Vía 1):

```bash
pip install python-telegram-bot
```

Crea un bot con @BotFather. Copia `publish_to_telegram()`. Manda un mensaje de prueba a tu canal y confirma que el formato Markdown funciona.

### Paso 6: Corre el orquestador

Corre `content-factory-orchestrator.sh`. Mira en tiempo real cómo el flujo avanza por las estaciones. Los archivos finales van a quedar en `content-output/{date}/{post-id}/`. Revisa cada archivo.

### Paso 7: Producción por tandas: 30 publicaciones en un día

Agrega 30 entradas a calendar.json (todas con approved: true). Corre el orquestador y mide el tiempo. Esta es tu primera experiencia produciendo contenido a escala: el momento en que sientes la diferencia entre un artesano y una fábrica.

---

## Herramientas y recursos

- **[Anthropic API](https://platform.claude.com/docs)**: Claude Sonnet y Haiku (la columna vertebral del flujo)
- **[python-telegram-bot](https://python-telegram-bot.org)**: un envoltorio de la API de bots de Telegram (para el ejemplo de la Vía 1)
- **[Buffer API](https://developers.buffer.com)**: programar publicaciones (GraphQL)
- **[Postiz](https://github.com/gitroomhq/postiz-app)**: una alternativa de código abierto a Buffer que instalas tú mismo (revisa que el proyecto siga activo)
- **[n8n](https://n8n.io)**: un orquestador de flujos que puedes correr en tu propio servidor
- **[ElevenLabs API](https://elevenlabs.io/docs/api-reference)**: TTS con clonación de voz
- **[OpenAI Images](https://platform.openai.com/docs/guides/images)**: generar portadas (el modelo gpt-image-2; DALL-E 2 y 3 se apagaron en la API el 12 de mayo de 2026)
- **[jq](https://jqlang.github.io/jq/)**: una herramienta de línea de comandos para trabajar con JSON en bash
- **[Schedule](https://schedule.readthedocs.io)**: programación tipo cron en Python para corridas locales
- **Precios y versiones:** [Lo vigente](https://aimayak.com/es/now/)

---

## Ideas clave

> La fábrica no se toma días libres. Configura el flujo una vez y produce borradores cada semana. Tu trabajo es aprobar los temas los lunes y revisar lo que sale antes de que se publique; los pasos de rutina de en medio corren solos.

> Una idea, muchos formatos. No escribas seis textos distintos para seis plataformas. Escribe una pieza principal, y Claude Haiku la recorta a la medida de cada una. Unos centavos contra unas horas de trabajo manual.

> El ciclo de análisis cierra el círculo. Contenido sin retroalimentación es disparar a ciegas. Métricas a Claude → recomendaciones → temas nuevos → mejor contenido. Cada semana puede construir sobre lo que aprendiste la semana anterior.

---

## Siguiente lección

→ [IA para el correo: una bandeja más inteligente, borradores y respuestas](73-ai-email-communications.md)
