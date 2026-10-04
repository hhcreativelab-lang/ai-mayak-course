# Notas de reuniones con IA: Otter.ai y Fireflies

**Tiempo:** unos 20 min de lectura + 30 min de práctica

---

## La idea

Una llamada de 45 minutos con un cliente. Luego otros 30 minutos para redactar las notas, repartir las tareas y actualizar el CRM. Con cinco reuniones a la semana, son 2.5 horas de papeleo. Todas las semanas. Puedes recuperar esas horas. Otter.ai graba, Fireflies analiza, Claude ordena, ClickUp recibe las tareas y un resumen llega a tu Slack, todo mientras todavía te estás despidiendo del cliente.

🎨 **Imagínalo así:** el asistente perfecto. Nunca se pierde una palabra, nunca se cansa, nunca pide vacaciones y te manda las notas de la reunión terminadas antes de que cierres la laptop. No es ciencia ficción. Es un webhook + Claude + ClickUp.

---

## Conceptos clave

- **Transcripción automática**: la IA convierte la voz en texto en tiempo real y distingue a quienes hablan
- **Diarización de hablantes** (speaker diarization): el sistema sabe quién dijo qué, aunque haya diez personas en la llamada
- **Extracción de pendientes** (action items): Claude encuentra compromisos, fechas límite y tareas dentro de la conversación
- **Flujo con webhooks**: una cadena de pasos: transcripción → análisis → tareas → aviso. (Un webhook es un mensaje automático de "ya terminé, aquí está la información" que un servicio le manda a otro.)
- **Whisper local**: transcripción en tu propia computadora, sin mandar el audio a la nube (para reuniones bajo un acuerdo de confidencialidad, NDA)
- **Plantillas por tipo de reunión**: prompts distintos para reuniones distintas: llamadas de venta, revisiones con clientes, reuniones diarias del equipo
- **Zoom AI Companion vs Fireflies**: cuándo basta con la herramienta integrada y cuándo necesitas una externa

---

## La teoría

### El problema: una reunión sin sistema te cuesta dos veces

Una reunión de trabajo típica dura cerca de una hora. Después, la persona que lleva el negocio pasa otros 20–40 minutos redactando notas, repartiendo tareas y actualizando el CRM (la base de datos de clientes, como HubSpot o Salesforce). Con 5 reuniones a la semana, son 2–3 horas que simplemente desaparecen.

Peor aún, las notas que tomas a mano son imprecisas. Te concentras en la conversación y se te escapan detalles. O al revés: tomas notas y pierdes el hilo de la conversación. Es una trampa de atención.

La transcripción con IA resuelve esto de raíz: la grabación corre en segundo plano y nadie se pierde nada.

---

### Otter.ai: transcripción en tiempo real

Otter.ai es uno de los pioneros de este mercado. Se une a Zoom, Google Meet y Microsoft Teams como un participante bot, y entra automáticamente cuando empieza la reunión.

**Qué hace:**

- Transcripción en tiempo real con cada hablante identificado
- Un resumen con IA después de la reunión: un resumen estructurado, no solo un bloque de texto
- Pendientes: tareas con el nombre del responsable y una fecha límite
- Búsqueda de texto completo en todas tus transcripciones (¿necesitas algo de hace un mes? No hay problema)
- Integraciones con herramientas de trabajo (ver la lista en su sitio)
- Un servidor MCP para conectarlo con asistentes de IA (en los planes de pago). MCP es una forma estándar de conectar una herramienta a un asistente como Claude.

**Planes:** hay un plan Free con un límite mensual de minutos y planes de pago con más minutos; los precios y límites actuales están en otter.ai y en la página [Lo vigente](https://aimayak.com/es/now/). Revisa los idiomas compatibles antes de depender de él: si tus reuniones son en español u otro idioma distinto del inglés, asegúrate de que tu idioma esté en la lista de Otter, o usa un servicio que cubra más idiomas (por ejemplo, Fireflies).

🎨 **Imagínalo así:** Otter.ai es un taquígrafo de juzgado que se sienta en cada reunión y escribe todo lo que oye en tiempo real. Solo que este nunca se cansa y no cuesta mucho (igual conviene revisar la transcripción por si tiene errores).

---

### Fireflies.ai: transcripción + análisis + integración con el CRM

Fireflies va más allá que Otter: no solo graba, sino que analiza lo que se dijo.

**Además de la transcripción** (según la descripción del propio servicio; revisa qué incluye tu plan):

- **AI Summary** (resumen con IA): un resumen estructurado de qué hablaron, qué decidieron y qué quedó pendiente
- **Speaker Analytics** (análisis de hablantes): quién habló cuánto tiempo, quién dominó la conversación
- **Sentiment Analysis** (análisis de sentimiento): el tono de la conversación (positivo / neutral / preocupado)
- **Topic Tracker** (rastreador de temas): sigue las menciones de temas clave (presupuesto, competidores, plazos)
- **CRM Push** (envío al CRM): manda automáticamente el resumen a HubSpot, Salesforce o Pipedrive
- **Webhooks**: manda datos a cualquier endpoint (una dirección web en la que escucha tu propio código) cuando termina la reunión

Los webhooks son justo lo que convierte a Fireflies en el centro de nuestro flujo.

**Planes (a octubre de 2026):** Free, Pro, Business y Enterprise; consulta fireflies.ai para ver límites y precios. El acceso a la API y a los webhooks depende del plan. Soporta más de 60 idiomas y detecta el idioma automáticamente.

**Consentimiento para grabar:** grabar una reunión requiere el consentimiento de los participantes, y las reglas cambian según el lugar; en Estados Unidos, por ejemplo, varían por estado, y algunos estados exigen que todos en la llamada estén de acuerdo. Revisa la ley de tu país, y avisa que estás grabando al inicio de cada llamada.

---

### Zoom AI Companion vs Fireflies: cuál elegir

| Función | Zoom AI Companion | Fireflies.ai |
|---|---|---|
| Costo | Incluido en los planes de pago de Zoom sin costo extra (revisa tu plan) | Suscripción aparte (hay un plan gratis) |
| Integración | Integrado en Zoom | Funciona con Zoom, Meet, Teams |
| Sincronización con el CRM | Limitada | HubSpot, Salesforce, Pipedrive |
| Webhooks | Mediante la API de Zoom (configuración aparte) | ✅ una función central (depende del plan) |
| Prompts personalizados | Limitados | ✅ uno para cada tipo de reunión |
| Seguimiento de menciones de competidores | — | ✅ Topic Tracker |
| Ideal para | Equipos que viven en Zoom | Un flujo propio + CRM |

**En resumen:** Zoom AI Companion alcanza si solo necesitas un resumen. Necesitas Fireflies cuando armas un flujo automático: tareas → CRM → avisos.

---

### Microsoft Teams: el entorno corporativo

Si tus clientes son empresas grandes, probablemente usan Teams. Tienes dos opciones:

**Copilot en Teams** (integrado): resúmenes, pendientes y respuestas a preguntas sobre lo que se dijo en la reunión. Requiere una licencia de Microsoft 365 Copilot (precios a octubre de 2026: Copilot Business desde $18 por usuario al mes con pago anual, un precio publicado hasta el 31 de diciembre de 2026, o $25.20 pagando mes a mes). Como freelancer, solo lo tendrías si pagas la licencia tú mismo.

**Fireflies + Teams**: Fireflies entra a Teams como un bot externo. Conservas todas las funciones de Fireflies, incluidos los webhooks. Es la mejor opción si trabajas con clientes corporativos en Teams pero quieres mantener tu propio flujo.

---

### Whisper local: para reuniones confidenciales

Para tener privacidad total, cuando los datos no deben salir de tu computadora, corre OpenAI Whisper de forma local. Es de código abierto y funciona sin conexión.

```bash
pip install openai-whisper
# Más rápido en Mac con Apple Silicon:
pip install mlx-whisper
```

```python
import whisper

# small/medium/large: un equilibrio entre velocidad, calidad y RAM
model = whisper.load_model("medium")

result = model.transcribe(
    "meeting_recording.mp3",
    language="en",          # fija el idioma (más preciso); "es" para español
    word_timestamps=True    # una marca de tiempo para cada palabra
)

print(result["text"])
```

**Cuándo usar Whisper local:**

- Negociaciones legales
- Reuniones bajo un acuerdo de confidencialidad (NDA)
- Datos financieros de clientes
- Cualquier reunión con datos sensibles

La calidad está un poco por debajo de Otter o Fireflies, pero alcanza para la mayoría de las tareas de negocio.

Sin código: MacWhisper corre de forma local en una Mac con modelos Whisper y Parakeet y soporta más de 100 idiomas.

Si eres empleado, revisa la política de tu empresa sobre IA y grabaciones antes de conectar cualquiera de estas herramientas a las reuniones de trabajo.

---

### Plantillas de prompts para distintos tipos de reunión

Un solo prompt no sirve para todo. Una llamada de descubrimiento y una revisión técnica son trabajos distintos.

**Llamada de descubrimiento (tu primera reunión con un posible cliente):**

```
Analiza la transcripción de esta llamada de descubrimiento. Extrae:
1. Los dolores y problemas del cliente (citas de la conversación)
2. Presupuesto y plazos (si se mencionaron)
3. Quién toma la decisión
4. Objeciones y dudas
5. Próximos pasos para ambas partes
6. Probabilidad de cerrar el trato (Baja/Media/Alta), con tu razonamiento

Formato: JSON con estos campos.
```

**Revisión con un cliente (trabajo en curso con un cliente actual):**

```
Analiza la transcripción de esta reunión con un cliente. Extrae:
1. Estado del proyecto: qué está hecho y qué no
2. Los comentarios del cliente y los cambios que pidió (palabra por palabra)
3. Prioridades para el siguiente periodo
4. Riesgos y bloqueos
5. Tareas para nuestro equipo (responsable + fecha límite)
6. Tareas para el cliente (responsable + fecha límite)
```

**Reunión diaria del equipo (standup):**

```
Analiza esta reunión diaria. Para cada participante:
- Qué hizo ayer
- Qué planea hacer hoy
- Bloqueos y preguntas para el equipo

Luego enumera los pendientes compartidos con sus responsables.
```

---

### El flujo con webhooks: de la reunión a una tarea en ClickUp

🎨 **Imagínalo así:** si la reunión es la planta de producción, el webhook es la línea de ensamble que viene después. La pieza (la transcripción) sale de una máquina → pasa por control de calidad (Claude) → llega al almacén (ClickUp) → y el supervisor de planta recibe un mensaje (Slack).

```
Reunión en Zoom/Meet
      ↓
Fireflies graba y transcribe
      ↓
Fireflies manda un webhook a tu servidor (solo el id de la reunión)
      ↓
Python Flask obtiene la transcripción mediante la API GraphQL de Fireflies
      ↓
La API de Claude la analiza con tu plantilla y devuelve JSON
      ↓
La API de ClickUp crea las tareas automáticamente
      ↓
Slack publica el resumen en tu canal
```

**Código del servidor de webhooks (revisa el formato de las solicitudes de Fireflies en docs.fireflies.ai):**

```python
from flask import Flask, request, jsonify
import anthropic
import requests
import json
import os

app = Flask(__name__)

claude_client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])
FIREFLIES_API_KEY = os.environ["FIREFLIES_API_KEY"]
CLICKUP_API_KEY = os.environ["CLICKUP_API_KEY"]
CLICKUP_LIST_ID = os.environ["CLICKUP_LIST_ID"]
SLACK_WEBHOOK_URL = os.environ["SLACK_WEBHOOK_URL"]

MEETING_PROMPT = """
Eres un asistente que analiza transcripciones de reuniones de trabajo.

Transcripción:
{transcript}

Título de la reunión: {meeting_title}
Participantes: {participants}

Extrae la información estructurada como JSON:
{{
  "summary": "Un resumen corto de 3-5 oraciones",
  "decisions": ["decisión 1", "decisión 2"],
  "action_items": [
    {{
      "description": "Qué hay que hacer",
      "assignee": "Nombre del responsable o 'Sin asignar'",
      "deadline": "Fecha límite o 'No especificada'",
      "priority": "High|Medium|Low"
    }}
  ],
  "open_questions": ["pregunta 1", "pregunta 2"]
}}
"""


TRANSCRIPT_QUERY = """
query Transcript($transcriptId: String!) {
  transcript(id: $transcriptId) {
    title
    participants
    sentences {
      text
      speaker_name
    }
  }
}
"""


def fetch_transcript(meeting_id: str) -> dict:
    """El webhook de Fireflies solo manda el id de la reunión: obtenemos el texto con la API GraphQL."""
    response = requests.post(
        "https://api.fireflies.ai/graphql",
        headers={"Authorization": f"Bearer {FIREFLIES_API_KEY}"},
        json={"query": TRANSCRIPT_QUERY, "variables": {"transcriptId": meeting_id}},
        timeout=60,
    )
    response.raise_for_status()
    transcript = response.json()["data"]["transcript"]
    text = "\n".join(
        f"{s['speaker_name']}: {s['text']}" for s in transcript["sentences"]
    )
    return {
        "title": transcript["title"],
        "participants": transcript["participants"],
        "text": text,
    }


def analyze_meeting(transcript: str, title: str,
                    participants: list) -> dict:
    """Analiza la transcripción con Claude."""
    participants_str = ", ".join(participants) if participants else "Desconocidos"

    message = claude_client.messages.create(
        model="claude-sonnet-5-5",  # para los IDs de modelos actuales, ver la documentación de Anthropic
        max_tokens=2048,
        messages=[{
            "role": "user",
            "content": MEETING_PROMPT.format(
                transcript=transcript,
                meeting_title=title,
                participants=participants_str
            )
        }]
    )

    response_text = message.content[0].text
    # Quita los delimitadores de código markdown si Claude los agregó
    if "```json" in response_text:
        start = response_text.find("```json") + 7
        end = response_text.find("```", start)
        response_text = response_text[start:end].strip()

    return json.loads(response_text)


def create_clickup_task(task_data: dict, meeting_title: str) -> str:
    """Crea una tarea en ClickUp."""
    priority_map = {"High": 1, "Medium": 2, "Low": 3}

    payload = {
        "name": task_data["description"],
        "description": f"Origen: reunión '{meeting_title}'\n"
                       f"Responsable: {task_data['assignee']}",
        "priority": priority_map.get(task_data["priority"], 2),
    }

    response = requests.post(
        f"https://api.clickup.com/api/v2/list/{CLICKUP_LIST_ID}/task",
        headers={
            "Authorization": CLICKUP_API_KEY,
            "Content-Type": "application/json"
        },
        json=payload
    )
    if response.status_code == 200:
        return response.json().get("url", "")
    return ""


def send_slack_summary(analysis: dict, meeting_title: str,
                       task_urls: list) -> None:
    """Publica el resumen en un canal de Slack mediante un webhook entrante."""
    tasks_text = ""
    priority_emoji = {"High": "🔴", "Medium": "🟡", "Low": "🟢"}

    for item, url in zip(analysis["action_items"], task_urls):
        emoji = priority_emoji.get(item["priority"], "⚪")
        tasks_text += f"{emoji} {item['description']}\n"
        tasks_text += f"   → {item['assignee']} | {item['deadline']}"
        if url:
            tasks_text += f" | <{url}|Tarea>"
        tasks_text += "\n\n"

    open_q = "\n".join(f"• {q}" for q in analysis["open_questions"])

    message = f"""📋 *{meeting_title}*

📝 *Resumen:*
{analysis['summary']}

✅ *Pendientes ({len(analysis['action_items'])}):*
{tasks_text}
❓ *Preguntas abiertas:*
{open_q}""".strip()

    requests.post(
        SLACK_WEBHOOK_URL,
        json={"text": message},
        timeout=30,
    )


@app.route("/webhook/fireflies", methods=["POST"])
def fireflies_webhook():
    """Recibe el webhook de Fireflies cuando termina una reunión."""
    data = request.json or {}

    # El webhook solo trae metadatos: meetingId y eventType
    if data.get("eventType") != "Transcription completed":
        return jsonify({"status": "skip", "reason": "other event"}), 200

    meeting = fetch_transcript(data["meetingId"])
    title = meeting["title"] or "Reunión sin título"
    transcript = meeting["text"]
    participants = meeting["participants"] or []

    if not transcript:
        return jsonify({"status": "skip", "reason": "no transcript"}), 200

    # 1. Analizar con Claude
    analysis = analyze_meeting(transcript, title, participants)

    # 2. Crear tareas en ClickUp
    task_urls = [
        create_clickup_task(item, title)
        for item in analysis.get("action_items", [])
    ]

    # 3. Publicar el resumen en Slack
    send_slack_summary(analysis, title, task_urls)

    return jsonify({
        "status": "processed",
        "tasks_created": len(task_urls),
        "meeting": title
    }), 200


if __name__ == "__main__":
    app.run(port=5000, debug=False)
```

**A dónde va el resumen:** esta versión publica en un canal de Slack mediante un webhook entrante: una URL privada que te da Slack, y todo lo que se manda ahí aparece en ese canal. ¿Prefieres el correo? Cambia `send_slack_summary` por una función que mande el mismo texto con tu servicio de correo. El resto del flujo queda igual.

**Publicarlo en un servidor:** Railway, Render u otro hosting para Python (consulta los precios en los sitios de los proveedores). Asegúrate de que las solicitudes a tu webhook de verdad vengan de Fireflies (revisa en la documentación de Fireflies si soporta solicitudes firmadas).

---

### Retorno de la inversión: las cuentas de automatizar reuniones

| Tarea | Antes de automatizar | Después |
|---|---|---|
| Notas de la reunión | 20–40 min | 0 min |
| Repartir tareas al equipo | 10–15 min | 0 min |
| Actualizar el CRM | 5–10 min | 0 min |
| Total por reunión | 35–65 min | 2 min (revisión) |
| Con 5 reuniones a la semana | 3–5 horas/semana | 10 min/semana |

Pon tu propia tarifa: horas ahorradas al mes × lo que vale una hora de tu tiempo. Esa es la cantidad que regresa al trabajo productivo. Las cifras de la tabla son ilustrativas.

Lo que cuesta el sistema: una suscripción a un servicio de reuniones (hay planes gratis) + el uso de la API de Claude. Con los precios de Sonnet 5.5 a octubre de 2026 ($2 por millón de tokens de entrada y $10 por millón de tokens de salida), una reunión de una hora equivale más o menos a 15,000–20,000 tokens de entrada, lo que sale en unos cuantos centavos por reunión (una estimación; compruébala con tus propias grabaciones). Los tokens son las unidades en las que se cobra el uso de la IA. Precios actuales: [Lo vigente](https://aimayak.com/es/now/).

🎨 **Imagínalo así:** contratas a un asistente por el precio de una suscripción. Trabaja día y noche, nunca pide vacaciones y hace una sola cosa bien: convierte las reuniones en tareas concretas. Pero revisar su trabajo sigue siendo tu responsabilidad.

---

## Práctica

### Paso 1: Conecta Fireflies a tus reuniones (5 min)

1. Regístrate en [fireflies.ai](https://fireflies.ai). El plan Free alcanza para empezar
2. En Settings → Integrations (Configuración → Integraciones), conecta Google Calendar u Outlook
3. Fireflies va a entrar automáticamente a tus reuniones como bot
4. Haz una reunión de prueba en Zoom o Meet (aunque sea contigo mismo)
5. Revisa que en tu panel de Fireflies aparezcan una transcripción y un AI Summary

**Sabes que funcionó si:** Fireflies grabó la reunión por su cuenta y generó un resumen.

### Paso 2: Configura el webhook (10 min)

1. En Fireflies, abre la sección para desarrolladores (Developer settings) y agrega un webhook (revisa en su sitio si tu plan incluye webhooks)
2. Para probar, usa [webhook.site](https://webhook.site) como endpoint temporal
3. Evento: `Transcription completed`
4. Haz una reunión de prueba (5–10 min)
5. Abre webhook.site y mira la estructura del JSON que llegó

**Sabes que funcionó si:** ves un JSON con los campos `meetingId` y `eventType` (el texto de la transcripción llega con una solicitud aparte a la API GraphQL).

### Paso 3: Corre el servidor de Python (10 min)

```bash
pip install flask anthropic requests
```

Guarda el código de la sección de teoría como `meeting_pipeline.py`. Luego consigue una URL de webhook de Slack: en Slack, crea una app para tu espacio de trabajo, activa Incoming Webhooks (webhooks entrantes), agrega un webhook para el canal donde quieres recibir los resúmenes y copia su URL. (En el Slack de una empresa, puede que un administrador tenga que aprobar la app.) Ahora define las variables de entorno:

```bash
export ANTHROPIC_API_KEY="sk-ant-..."
export FIREFLIES_API_KEY="..."
export CLICKUP_API_KEY="pk_..."
export CLICKUP_LIST_ID="..."
export SLACK_WEBHOOK_URL="https://hooks.slack.com/services/..."

python meeting_pipeline.py
```

Para tener una URL pública mientras desarrollas:

```bash
ngrok http 5000
# Copia la URL HTTPS, agrégale /webhook/fireflies al final → pégala en la configuración del webhook de Fireflies
```

### Paso 4: Prueba el flujo completo (5 min)

Haz una reunión de prueba de 10 minutos. Habla de algunas tareas con fechas límite y responsables. Espera 5–10 minutos después de que termine. Revisa que las tareas aparezcan en ClickUp y que el resumen llegue a Slack.

**Sabes que funcionó si:** todo el ciclo corre solo, sin pasos manuales.

### Paso 5: Ajusta el prompt a tus reuniones (5 min)

Reemplaza `MEETING_PROMPT` con la plantilla de la sección de teoría que vaya con tu tipo de reuniones. O escribe la tuya. Conserva los marcadores `{transcript}`, `{meeting_title}` y `{participants}` y los campos JSON que lee el código (`summary`, `action_items`, `open_questions`), o ajusta el código para que coincida. Pruébalo con una reunión real y asegúrate de que el resultado se vea como esperas.

---

## Herramientas y recursos

- **[Fireflies](https://fireflies.ai)**: transcripción + webhooks, más de 60 idiomas, tiene plan gratis (el acceso a la API y a los webhooks depende del plan)
- **[Otter.ai](https://otter.ai)**: transcripción en tiempo real, tiene plan gratis; revisa los idiomas compatibles si no todas tus reuniones son en inglés
- **[tl;dv](https://tldv.io)**: graba reuniones en Zoom, Meet y Teams, tiene plan gratis
- **[Granola](https://www.granola.ai)**: un bloc de notas para reuniones sin un bot que entre a la llamada; macOS, Windows, iOS y Android (a octubre de 2026)
- **[OpenAI Whisper](https://github.com/openai/whisper)**: transcripción privada sin conexión, gratis
- **[mlx-whisper](https://github.com/ml-explore/mlx-examples)**: Whisper rápido en Apple Silicon
- **[MacWhisper](https://www.macwhisper.com)**: transcripción local en una Mac, sin código
- **[Claude API](https://platform.claude.com/docs)**: análisis de transcripciones; calcula el costo por tokens ([Lo vigente](https://aimayak.com/es/now/))
- **[ClickUp API v2](https://clickup.com/api)**: creación de tareas
- **[ngrok](https://ngrok.com)**: un túnel para desarrollo, gratis
- **[Railway](https://railway.app)**: hosting para el servidor de Python, precios en el sitio del proveedor

---

## Ideas clave

> Una reunión sin notas automáticas te hace perder dinero dos veces: primero gastas el tiempo en la reunión y luego lo vuelves a gastar escribiendo lo que pasó.

> La diferencia entre Otter/Fireflies y Whisper local es la diferencia entre comodidad y privacidad. Para la mayoría de las reuniones, la nube es lo bastante segura. Para negociaciones bajo un NDA, corre Whisper de forma local.

> Un flujo con webhooks cambia la forma de trabajar de la gente. Cuando las tareas aparecen solas en ClickUp después de cada reunión, la gente empieza a tomarse más en serio sus compromisos: lo que se dice se vuelve un registro al instante.

---

## Siguiente lección

→ [Traducción y localización: DeepL MCP y un flujo de i18n](75-ai-translation.md)

Vamos a armar un sistema que toma un contenido en inglés y lo convierte automáticamente al español, al portugués y a otros idiomas, con adaptación cultural, un glosario de términos y metadatos SEO para cada mercado.
