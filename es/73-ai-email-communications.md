# IA para el correo: una bandeja más inteligente, borradores y respuestas

**Tiempo:** unos 20 min de lectura + 30 min de práctica

---

## Lo esencial

Los profesionales pasan una parte considerable de su día de trabajo en el correo (revisa tu propio registro de tiempo si usas uno). No es porque haya tantos correos. Es porque cada correo te obliga a pensar: qué responder, cómo redactarlo, cómo no olvidarlo. Claude se encarga de ese pensar. Tú sigues tomando las decisiones.

Esto no es "la IA en lugar de ti". Es la IA como filtro y como primer borrador. Tú sigues haciendo clic en "Enviar". Solo que tardas una fracción del tiempo en llegar ahí.

Cómo está organizada esta lección: primero va el camino sin código. Ordenas el correo y recibes borradores en un chat normal de Claude. Con eso alcanza para el correo de todos los días, y la práctica empieza ahí. Las secciones y tareas marcadas "para quienes construyen" traen código en Python: son solo para quienes arman su propia automatización, y los demás pueden saltárselas.

🎨 **Imagínalo así:** un asistente de correo con IA es como el vocero de una presidencia. El presidente no escribe cada respuesta en persona. El vocero conoce sus posturas y su estilo, sabe lo que el presidente nunca diría y prepara el texto. El presidente lo lee, cambia un par de palabras y lo aprueba. El poder y las decisiones siguen siendo del presidente; lo que se libera es tiempo.

---

## Conceptos clave

- **Conectar Gmail**: Claude lee tu bandeja de entrada, ordena tus correos y escribe borradores de respuesta. Conectas tu correo con un conector ya hecho o mediante MCP (una forma estándar de conectar apps y servicios externos a Claude).
- **Borradores automáticos**: un borrador de respuesta escrito con tu estilo; lo apruebas en lugar de escribirlo
- **Flujo Inbox Zero (bandeja en cero)**: en la mañana Claude revisa todo, y tú recibes una lista por prioridad
- **Apollo / Hunter.io**: herramientas para encontrar las direcciones de correo correctas y hacer prospección en frío
- **Lemlist**: secuencias automáticas de seguimiento
- **Secuencia de correos**: una cadena de correos que lleva a alguien desde que se registra hasta un trato, escrita una sola vez

---

## Teoría

### Por qué usar IA para el correo: las cuentas del tiempo (un ejemplo inventado)

Un día típico:

- 80 correos entrantes
- 20 necesitan respuesta
- Cada respuesta: 5-7 minutos para pensarla y escribirla
- Total: 100-140 minutos, más o menos 2 horas

Con IA:

- Claude lee todo y lo ordena: urgente / espera tu respuesta / solo información / spam
- Para los 20 correos que necesitan respuesta, escribe borradores
- Tú lees los borradores, editas algunos y apruebas el resto
- Total: 25-30 minutos

En este ejemplo inventado, ahorras más o menos de 70 a 115 minutos al día. Pon tus propios números.

---

### Conectar Gmail: Claude lee tu bandeja de entrada

La forma más sencilla no conecta nada: copia un correo en un chat de Claude y pide un borrador de respuesta. Funciona en cualquier plan y con cualquier servicio de correo, y para unos cuantos correos al día es todo lo que necesitas.

Si recibes mucho correo, puedes conectar tu bandeja. Entonces Claude lee tus correos por su cuenta, los busca por criterios y escribe borradores de respuesta. Le hablas a Claude como le hablarías a un asistente.

**Formas de conectarlo (a octubre de 2026):**

- **El conector de Gmail en Claude** (planes Pro, Max, Team y Enterprise): el camino más sencillo. En Claude, abre Customize → Connectors (Personalizar → Conectores), busca Gmail, elige Connect (Conectar) e inicia sesión en tu cuenta de Google. Luego actívalo en un chat: el botón + debajo del cuadro de mensaje → Connectors → Gmail. Según la documentación de Claude, el conector solo lee y busca correos: no puede crear, enviar ni modificar mensajes. Claude escribe el borrador en el chat, y tú lo pasas a tu correo.
- **El servidor MCP oficial de Gmail de Google** (Google Workspace Developer Preview). Según la documentación de Google, busca correos e hilos, lee mensajes, crea borradores y aplica etiquetas; enviar correos no está en su lista de funciones. Vas a necesitar un proyecto de Google Cloud, un cliente OAuth (una forma de iniciar sesión con Google) y un plan Pro, Max, Team o Enterprise de Claude. Este camino es para quienes construyen.
- **Servidores MCP y hubs de terceros** (por ejemplo, Composio): cómodos, pero un tercero obtiene acceso a tu correo. Revisa los permisos, la reputación de la empresa y su política de conservación de datos.

**Regla de acceso:** da los permisos mínimos (leer y crear borradores), y el envío déjalo para ti. Si es una cuenta del trabajo, revisa la política de IA de tu empleador antes de conectar cualquier cosa.

```
# Para quienes construyen: el servidor oficial de Gmail de Google se conecta a Claude como conector personalizado:
# Customize → Connectors → Add custom connector (Personalizar → Conectores → Agregar conector personalizado)
# Remote MCP server URL: https://gmailmcp.googleapis.com/mcp/v1
# El Client ID y el Secret de OAuth se crean en Google Cloud Console
# (instrucciones: developers.google.com/workspace/gmail/api/guides/configure-mcp-server)
```

Una vez conectado, esto es lo que escribes en Claude:

```
Revisa mi bandeja de entrada. Encuentra todos los correos de los últimos 3 días
que necesitan respuesta mía. Ordénalos en:
- Urgentes (necesitan respuesta hoy)
- Normales (responder en 3 días)
- Para tu información (solo informativos, no requieren respuesta)

Para cada urgente, escribe un borrador de respuesta con mi estilo:
corto, concreto, sin relleno.
```

Claude lee los correos y te da una tabla con las categorías más borradores listos para los urgentes. Revisas los borradores, editas donde haga falta, los copias a Gmail y los envías.

---

### Borradores con tu estilo: una descripción de tu estilo para Claude

Para que los borradores suenen como tú y no como un texto corporativo de plantilla, describe tu estilo. En un chat normal, pega esa descripción al inicio de la conversación (y guárdala en tus notas para tenerla a la mano). En Claude Code, la misma descripción va en el archivo CLAUDE.md del proyecto, que Claude Code lee como instrucciones fijas. En código, se pasa como prompt de sistema.

**Ejemplo de descripción de estilo (en Claude Code, es el contenido de tu archivo CLAUDE.md):**

```markdown
# Mi estilo de correo

## Reglas generales
- 150 palabras como máximo por respuesta (salvo que sea un contrato o un alcance de trabajo detallado)
- Ir directo al punto; nada de "Espero que te encuentres muy bien"
- Terminar cada correo con una llamada a la acción concreta: qué necesito de la persona y para cuándo
- Listas en lugar de párrafos largos

## Nunca usar
- "Como te comenté en mi correo anterior..." (se lee pasivo-agresivo)
- "Básicamente", "en términos generales", "al final del día" (relleno vago)
- Más de una pregunta por correo (solo una pregunta)

## Ejemplo de una buena respuesta
Alguien pregunta cuánto cuesta una consulta:
"Una consulta inicial cuesta $200 USD la hora.
Próximos horarios libres: mañana a las 3 p. m. o el viernes a las 11 a. m.
Dime cuál te queda y te mando el enlace de Zoom."

## Ejemplo de una mala respuesta (no escribas así)
"¡Buenas tardes! ¡Muchísimas gracias por tu pregunta! Me da muchísimo gusto informarte
que nuestras consultas están disponibles en una gran variedad de planes de precios..."
```

---

### Para quienes construyen: un script de Python que redacta la respuesta

Esta sección es opcional. Es para quienes escriben código y quieren integrar los borradores a su propio sistema mediante la API (la forma en que los programas hablan con Claude directamente, sin el chat). Si no programas, sáltate el código y pasa a la sección de secuencias de correos.

```python
import anthropic
import os

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

def draft_reply(incoming_email: str, context: str = "") -> str:
    """
    Genera un borrador de respuesta a un correo entrante.
    Devuelve el borrador. NO envía nada de forma automática.
    Tú lo revisas y lo envías.
    """
    response = client.messages.create(
        model="claude-sonnet-5-5",  # ID de modelo vigentes: mira la documentación de Anthropic
        max_tokens=4000,  # con margen a propósito: el "razonamiento" del modelo cuenta dentro de este límite
        system="""Eres un asistente personal de correo. Escribes respuestas con este estilo:
        
        - Cortas y al punto: no más de 100-150 palabras
        - Empiezas con lo importante, sin saludos de cortesía de relleno
        - Siempre terminas con una llamada a la acción concreta: qué necesitas de la persona y para cuándo
        - Usas una lista si hay 3 puntos o más
        - Tono: profesional, no acartonado
        
        IMPORTANTE: propones un borrador, no el texto final.
        Nunca agregues firma; yo agrego la mía.""",
        messages=[{
            "role": "user",
            "content": f"""Correo entrante:
---
{incoming_email}
---

Contexto adicional para la respuesta: {context if context else 'ninguno'}

Escribe un borrador de respuesta."""
        }]
    )
    # La respuesta puede traer bloques de "razonamiento": nos quedamos solo con el texto
    return "".join(block.text for block in response.content if block.type == "text")


def classify_email(email_text: str) -> dict:
    """
    Clasifica un correo: si necesita respuesta, qué tan urgente es, de qué tipo es.
    Devuelve un dict con la clasificación.
    """
    response = client.messages.create(
        model="claude-haiku-4-5",  # Haiku es rápido y barato para clasificar; Haiku 4.5 podría retirarse de la API no antes del 15 de octubre de 2026, así que revisa el ID de modelo en la documentación
        max_tokens=150,
        messages=[{
            "role": "user",
            "content": f"""Clasifica este correo. Devuelve solo JSON:
{{
  "needs_reply": true/false,
  "urgency": "high"/"medium"/"low",
  "type": "client_inquiry"/"follow_up"/"newsletter"/"spam"/"internal"/"other",
  "summary": "una frase sobre de qué trata el correo"
}}

Correo:
{email_text}"""
        }]
    )
    import json
    text = "".join(block.text for block in response.content if block.type == "text")
    return json.loads(text)


# Ejemplo de uso
if __name__ == "__main__":
    incoming = """
    ¡Hola! Me gustaría agendar una consulta sobre comprar casa en Querétaro.
    Mi esposa y yo estamos pensando en mudarnos allá desde la Ciudad de México el próximo año, y
    queremos entender cuánto cuestan de verdad las casas y cómo funciona comprar desde otra ciudad.
    ¿Cuánto cuesta una consulta y cuándo tienes disponibilidad?
    """
    
    # Paso 1: clasificar
    classification = classify_email(incoming)
    print(f"Tipo: {classification['type']}")
    print(f"Urgencia: {classification['urgency']}")
    print(f"Resumen: {classification['summary']}")
    print(f"Necesita respuesta: {classification['needs_reply']}")
    
    # Paso 2: si necesita respuesta, generar un borrador
    if classification["needs_reply"]:
        context = "Una consulta cuesta $200 USD la hora. Próximos horarios libres: mañana a las 3 p. m. o el viernes a las 11 a. m."
        draft = draft_reply(incoming, context)
        print(f"\nBorrador de respuesta:\n{'-'*40}\n{draft}")
```

---

### Apollo + Hunter.io: IA para el correo en frío

Esta sección es para quienes buscan clientes; puedes volver a ella cuando llegues al módulo de los primeros clientes. Apollo y Hunter.io resuelven el problema de "encontrar el correo de trabajo de esta persona". Claude convierte los contactos que encuentras en correos personalizados. Sin código, se hace a mano: busca la dirección en el sitio de Apollo o de Hunter, pega en un chat de Claude lo que sabes de la persona y pide un correo que siga las reglas del prompt de abajo. Las conexiones y el script son para quienes construyen.

🎨 **Imagínalo así:** Apollo más Claude es como una red de pesca con carnada inteligente. La red (Apollo) encuentra a las personas correctas. La carnada (Claude) se hace para cada una en particular, no se saca de una plantilla. El pez (un posible cliente) tiene más probabilidades de picar.

```
# Cómo te conectas depende del hub o servicio que elijas:
# mira la documentación de Apollo, Hunter o del hub MCP para el formato del comando y cómo iniciar sesión.
# Guarda las claves de API en variables de entorno y mándalas en un encabezado de la solicitud, no en la URL.
```

**Una advertencia sobre el correo en frío:** escribirles a personas que no conoces está regulado por leyes contra el spam y de privacidad (qué te da motivo para escribirle a alguien, una forma fácil de darse de baja, cómo guardas los contactos). En Estados Unidos, el correo comercial está sujeto a la ley federal CAN-SPAM; otros países tienen sus propias reglas. Revisa las reglas de donde estás tú y de donde está tu destinatario. Claude escribe el texto; la responsabilidad de enviarlo sigue siendo tuya.

Una vez conectado, esta es la tarea para Claude Code:

```
Usa Apollo. Encuentra a 20 dueños de inmobiliarias
en Querétaro, México. Para cada uno:
1. Encuentra su correo con Hunter.io
2. Revisa su perfil de LinkedIn (si Apollo lo tiene)
3. Escribe un correo en frío personalizado en español:
   - Menciona algo concreto de su perfil o de su negocio
   - Explica en 2 frases cómo puedo serle útil
   - Una pregunta concreta al final
   - No más de 120 palabras

Guarda los resultados en un CSV: nombre, correo, texto del correo.
```

La versión manual sin MCP, con una llamada directa a la API:

```python
import anthropic
import requests
import os
import csv

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])
HUNTER_API_KEY = os.environ["HUNTER_API_KEY"]

def find_email(domain: str, first_name: str, last_name: str) -> str:
    """Encuentra una dirección de correo con Hunter.io a partir de un dominio y un nombre"""
    response = requests.get(
        "https://api.hunter.io/v2/email-finder",
        params={
            "domain": domain,
            "first_name": first_name,
            "last_name": last_name,
        },
        # La clave va en un encabezado, no en la URL, para que no quede en registros ni en el historial
        headers={"X-API-KEY": HUNTER_API_KEY},
    )
    data = response.json()
    if data.get("data", {}).get("email"):
        return data["data"]["email"]
    return None


def write_cold_email(
    recipient_name: str,
    company: str,
    context_about_them: str,
    language: str = "español"
) -> str:
    """Genera un correo en frío personalizado"""
    
    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=4000,  # con margen a propósito: el "razonamiento" del modelo cuenta dentro de este límite
        system=f"""Escribes correos en frío personalizados en este idioma: {language}.
        
        Reglas:
        - 120 palabras como máximo
        - Menciona un detalle concreto de la persona o de la empresa
        - El valor en 1-2 frases: exactamente qué puedes ofrecer
        - Una pregunta al final (no varias)
        - Nada de frases de plantilla como "Espero que te encuentres muy bien..."
        - Tono profesional, no de vendedor""",
        messages=[{
            "role": "user",
            "content": f"""Destinatario: {recipient_name}
Empresa: {company}
Lo que sé de esta persona: {context_about_them}

Yo: agente de Acme Inmobiliaria. Ayudo a familias que se mudan a Querétaro a comprar o rentar casa.
Estoy abierto a alianzas por recomendación y a operaciones compartidas con otras inmobiliarias.

Escribe un correo en frío."""
        }]
    )
    # La respuesta puede traer bloques de "razonamiento": nos quedamos solo con el texto
    return "".join(block.text for block in response.content if block.type == "text")


# Lista de contactos para la prospección
contacts = [
    {
        "name": "Carlos Rodríguez",
        "company": "Example Inmobiliaria",
        "domain": "example.com",
        "first_name": "Carlos",
        "last_name": "Rodriguez",
        "context": "Se especializa en casas antiguas cerca del centro histórico"
    },
    # ... el resto de tus contactos
]

# Genera los correos y guárdalos en un CSV
with open("cold_outreach.csv", "w", newline="", encoding="utf-8") as f:
    writer = csv.writer(f)
    writer.writerow(["Nombre", "Empresa", "Correo", "Mensaje"])
    
    for contact in contacts:
        email = find_email(
            contact["domain"],
            contact["first_name"],
            contact["last_name"]
        )
        
        if email:
            letter = write_cold_email(
                contact["name"],
                contact["company"],
                contact["context"],
                language="español"  # o "inglés" para contactos de habla inglesa
            )
            writer.writerow([contact["name"], contact["company"], email, letter])
            print(f"Listo: {contact['name']} <{email}>")
        else:
            print(f"Correo no encontrado: {contact['name']}")

print("Guardado en cold_outreach.csv")
```

---

### Secuencia de correos: del registro a un trato

Una secuencia de correos es una cadena de correos que se envía de forma automática después de que alguien se registra o hace algo. Claude escribe todos los correos una vez. Sin código: pídele a Claude en un chat que escriba los cuatro correos del diagrama de abajo y pégalos en un servicio de correo (Lemlist u otro), donde configuras el calendario de envío. En cada correo deja una forma de darse de baja. El script que está debajo del diagrama es para quienes construyen.

```
Alguien llena un formulario en tu sitio web
          |
          v
De inmediato: correo de bienvenida
            (Claude lo personaliza con los datos del formulario: nombre, de dónde se muda, qué le interesa)
          |
          v
Día 3:   Correo de valor
         (la IA elige contenido de tu biblioteca: si le interesa rentar → un artículo sobre rentar)
          |
          v
Día 7:   Correo con caso de éxito
         (la historia de un cliente real parecido a esta persona)
          |
          v
Día 14:  Correo con oferta
         (una oferta concreta con una llamada a la acción para agendar una consulta)
```

```python
import anthropic
import os
from datetime import datetime

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

def generate_welcome_email(
    name: str,
    interest: str,  # "renta" / "compra" / "inversión"
    city_of_origin: str
) -> str:
    """Correo de bienvenida personalizado"""
    
    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=4000,  # con margen a propósito: el "razonamiento" del modelo cuenta dentro de este límite
        system="""Escribes un correo de bienvenida para alguien interesado
        en comprar o rentar casa en Querétaro.
        
        Estilo: cálido, no formal. Tiene que sonar como si lo hubiera escrito una persona real.
        Extensión: 100-120 palabras.
        Estructura: saludo → qué va a recibir después → una pregunta para poder ayudarle mejor.""",
        messages=[{
            "role": "user",
            "content": f"""Nombre: {name}
Interés: {interest}
Se muda desde: {city_of_origin}

Escribe un correo de bienvenida."""
        }]
    )
    # La respuesta puede traer bloques de "razonamiento": nos quedamos solo con el texto
    return "".join(block.text for block in response.content if block.type == "text")


def select_value_content(interest: str, knowledge_base: dict) -> str:
    """
    Elige el contenido relevante de la base de conocimiento para el correo de valor.
    knowledge_base: un dict de temas → textos de artículos o consejos
    """
    response = client.messages.create(
        model="claude-haiku-4-5",
        max_tokens=600,
        messages=[{
            "role": "user",
            "content": f"""A esta persona le interesa: {interest}

Contenido disponible:
{chr(10).join([f"- {topic}: {text[:100]}..." for topic, text in knowledge_base.items()])}

Elige el contenido más relevante y escribe un correo de 120-150 palabras.
Usa datos concretos del contenido que elegiste."""
        }]
    )
    return "".join(block.text for block in response.content if block.type == "text")


# Base de conocimiento (en la vida real se lee de archivos o de una base de datos; los datos de abajo son inventados, solo para ilustrar)
KNOWLEDGE_BASE = {
    "renta": "Rentas de ejemplo en nuestra zona: 1 recámara $1,100-1,400 USD al mes, 2 recámaras $1,400-1,900 USD al mes. Colonias por las que más preguntan los clientes: el Centro, la zona norte...",
    "compra": "Pasos típicos para quien compra: preaprobación del crédito → oferta → inspección → avalúo → firma. Muchas veces de 30 a 60 días desde la oferta aceptada hasta la firma...",
    "inversión": "El rendimiento de una renta depende de la zona y de la propiedad; en una base de conocimiento real, aquí van tus propios números verificados y tus advertencias (no es asesoría de inversión)...",
}

# Ejemplo: generar un correo de bienvenida
email = generate_welcome_email(
    name="Miguel",
    interest="compra",
    city_of_origin="Ciudad de México"
)
print("Correo de bienvenida:")
print(email)
print()

# Correo de valor
value_email = select_value_content("compra", KNOWLEDGE_BASE)
print("Correo de valor (día 3):")
print(value_email)
```

---

### Flujo Inbox Zero: una rutina matutina de 20 minutos

Inbox Zero (bandeja en cero) es el hábito de dejar tu bandeja vacía todos los días. Una rutina práctica:

```
7:00 a. m.  Claude lee todos los correos nuevos de la noche
            Sin código: abres un chat con Gmail conectado y usas el prompt de la sección Conectar Gmail
            Con código: el script corre solo
            Los ordena: urgente / normal / para tu información / spam
            Escribe borradores para todo lo que necesita respuesta

7:10 a. m.  Abres el resumen (la respuesta en tu chat; con el script, un archivo o un mensaje para ti mismo en Slack o por correo)
            Ves: 3 urgentes, 8 normales, 12 para tu información

7:10-7:30   Revisas los borradores de los correos urgentes
            Editas si hace falta (siempre hay borradores que necesitan cambios)
            Envías
            Normales: los programas para esta tarde o mañana
            Para tu información: los archivas con un clic

7:30 a. m.  Bandeja en cero. Tu día empezó.
```

El script de abajo es para quienes construyen: hace el mismo ordenado y los mismos borradores sin el chat.

```python
import anthropic
import os
from typing import List

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

def process_inbox(emails: List[dict], your_context: str) -> dict:
    """
    Procesa una lista de correos: los clasifica y escribe borradores.
    
    emails: una lista de dicts con los campos subject, sender, body, date
    your_context: una descripción de tu trabajo para que Claude escriba con tu estilo
    """
    
    results = {
        "urgent": [],
        "normal": [],
        "fyi": [],
        "spam": [],
    }
    
    for email in emails:
        # Clasificación
        classification_response = client.messages.create(
            model="claude-haiku-4-5",
            max_tokens=200,
            messages=[{
                "role": "user",
                "content": f"""Clasifica este correo. Devuelve JSON:
{{
  "category": "urgent"/"normal"/"fyi"/"spam",
  "needs_reply": true/false,
  "summary": "una frase"
}}

De: {email['sender']}
Asunto: {email['subject']}
Cuerpo: {email['body'][:500]}"""
            }]
        )
        
        import json
        classification = json.loads(
            "".join(block.text for block in classification_response.content if block.type == "text")
        )
        category = classification["category"]
        
        email_data = {
            **email,
            "summary": classification["summary"],
            "draft": None
        }
        
        # Borrador solo si hace falta responder
        if classification["needs_reply"] and category in ["urgent", "normal"]:
            draft_response = client.messages.create(
                model="claude-sonnet-5-5",
                max_tokens=4000,  # con margen a propósito: el "razonamiento" del modelo cuenta dentro de este límite
                system=f"""Eres un asistente de correo. Sobre la persona para quien escribes:
{your_context}

Estilo de respuesta: corto, al punto, una llamada a la acción concreta al final.""",
                messages=[{
                    "role": "user",
                    "content": f"""Escribe un borrador de respuesta a este correo:

De: {email['sender']}
Asunto: {email['subject']}
Cuerpo: {email['body']}"""
                }]
            )
            # La respuesta puede traer bloques de "razonamiento": nos quedamos solo con el texto
            email_data["draft"] = "".join(
                block.text for block in draft_response.content if block.type == "text"
            )
        
        results[category].append(email_data)
    
    return results


def format_daily_brief(processed: dict) -> str:
    """Da formato al resumen para tu lectura de la mañana"""
    
    lines = [
        f"Resumen de la bandeja del {__import__('datetime').date.today()}",
        f"Urgentes: {len(processed['urgent'])} | "
        f"Normales: {len(processed['normal'])} | "
        f"Para tu información: {len(processed['fyi'])} | "
        f"Spam: {len(processed['spam'])}",
        "",
    ]
    
    if processed["urgent"]:
        lines.append("URGENTES (responder hoy):")
        for email in processed["urgent"]:
            lines.append(f"  De: {email['sender']}")
            lines.append(f"  Resumen: {email['summary']}")
            if email["draft"]:
                lines.append(f"  Borrador:\n  {email['draft'][:200]}...")
            lines.append("")
    
    if processed["normal"]:
        lines.append("NORMALES:")
        for email in processed["normal"]:
            lines.append(f"  - {email['sender']}: {email['summary']}")
    
    return "\n".join(lines)


# Ejemplo de uso (en la vida real los correos llegan por la API de Gmail)
sample_emails = [
    {
        "sender": "carlos@example.com",
        "subject": "¿Trabajamos juntos con un comprador?",
        "body": "¡Hola! Tengo un cliente que se muda desde la Ciudad de México y busca un departamento de alrededor de $150K USD. ¿Podríamos trabajar juntos en este caso?",
        "date": "2026-10-05"
    },
    {
        "sender": "newsletter@realestate-news.com",
        "subject": "Resumen semanal del mercado",
        "body": "El informe de la semana pasada sobre el mercado inmobiliario de Querétaro...",
        "date": "2026-10-05"
    },
]

YOUR_CONTEXT = """
Acme Inmobiliaria ayuda a familias que se mudan a Querétaro a comprar o rentar casa.
Trabajo con clientes de forma directa y a través de inmobiliarias aliadas de la zona.
Estilo de comunicación: cercano, concreto, sin relleno.
"""

processed = process_inbox(sample_emails, YOUR_CONTEXT)
brief = format_daily_brief(processed)
print(brief)
```

---

### Correo en varios idiomas: un sistema, dos idiomas

Si algunos de tus clientes te escriben en español y otros en inglés, Claude puede detectar el idioma y responder en ese idioma de forma automática. Sin código: pega el correo en un chat y pídele a Claude "responde en el idioma del correo y dame un resumen de una línea en español". Tú sigues leyendo cada borrador antes de enviarlo; si no lees inglés, el resumen en español te dice de qué trata el correo, y conviene que alguien que domine el idioma revise todo lo importante. El código de abajo es para quienes construyen (continúa el script de la sección anterior).

```python
def multilingual_reply(incoming_email: str, your_context: str) -> dict:
    """
    Detecta el idioma del correo y escribe una respuesta en el mismo idioma.
    Devuelve: {detected_language, draft, summary_in_spanish}
    """
    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=4000,  # con margen a propósito: el "razonamiento" del modelo cuenta dentro de este límite
        system=f"""Eres un asistente de correo bilingüe (español + inglés).

Sobre la persona para quien escribes:
{your_context}

Reglas:
1. Detecta el idioma del correo entrante
2. Responde en el MISMO idioma (no cambies sin motivo)
3. Si es español, mantén un tono profesional propio del correo de negocios en América Latina
4. Si es inglés, usa un estilo breve y de negocios

Devuelve JSON:
{{
  "detected_language": "Spanish"/"English"/"Other",
  "draft": "el borrador de respuesta, en el idioma del correo",
  "summary_in_spanish": "una frase sobre de qué trata el correo, siempre en español"
}}""",
        messages=[{
            "role": "user",
            "content": f"Correo:\n{incoming_email}"
        }]
    )
    import json
    # La respuesta puede traer bloques de "razonamiento": nos quedamos solo con el texto
    text = "".join(block.text for block in response.content if block.type == "text")
    return json.loads(text)


# Prueba
english_email = """
Good morning! I'm a real estate agent in Houston, and I have clients
who are moving to Querétaro and looking for a home. Could we work together?
"""

result = multilingual_reply(english_email, YOUR_CONTEXT)
print(f"Idioma: {result['detected_language']}")
print(f"Resumen (en español): {result['summary_in_spanish']}")
print(f"\nBorrador de respuesta:\n{result['draft']}")
```

---

## Práctica

Las tareas 1 a 3 se hacen en un chat normal, sin código. Las tareas 4 y 5 son para quienes construyen.

1. Elige 5 correos reales que tengas que responder. Pégalos en un chat de Claude uno por uno y pide un borrador de respuesta. Quita antes los datos personales de otras personas: no los mandes a servicios con los que no tienes permiso de compartirlos. Terminaste cuando tengas 5 borradores.

2. Escribe una descripción de tu estilo siguiendo el ejemplo de esta lección: tus reglas, de 3 a 5 frases prohibidas, un ejemplo de una buena respuesta y uno de una mala. Pégala al inicio de un chat nuevo y pide borradores para los mismos 5 correos. Compáralos con la primera ronda: los segundos deberían sonar como tú. (Si trabajas en Claude Code, guarda la descripción como CLAUDE.md.)

3. Si tienes un plan de pago de Claude, conecta Gmail con el conector (Customize → Connectors, ver arriba) y haz una revisión matutina: usa el prompt de la sección Conectar Gmail y revisa que Claude haya ordenado bien tus correos en urgentes, normales y para tu información. ¿No tienes plan de pago? Haz lo mismo con 10 correos pegados en un chat.

4. Para quienes construyen: escribe un script `email_classifier.py` con las funciones `classify_email` y `draft_reply` de esta lección y pruébalo con los mismos 5 correos. Luego configura `process_inbox` + `format_daily_brief`, ejecútalos con tu propio correo y fíjate qué tan buenos son los borradores. Si conectas el servidor MCP oficial de Gmail de Google, dale los permisos mínimos: leer y crear borradores, sin enviar.

5. Para quienes construyen y buscan clientes: elige una tarea de prospección en frío (5-10 contactos) y prueba `write_cold_email` con datos reales. Antes de enviar nada, revisa cada correo y las reglas de envíos masivos del país de tu destinatario.

---

## Herramientas y recursos

- **[Composio](https://composio.dev)**: un hub MCP para conectar Gmail, Apollo, Hunter y otros servicios a Claude (un tercero obtiene acceso a tu correo, así que revisa los permisos)
- **[Gmail API](https://developers.google.com/gmail/api)**: la documentación oficial, si te conectas directamente
- **[Servidor MCP de Gmail de Google](https://developers.google.com/workspace/gmail/api/guides/configure-mcp-server)**: vista previa para desarrolladores; búsqueda, lectura, borradores, etiquetas
- **[Apollo.io](https://apollo.io)**: base de datos de contactos + buscador de correos (tiene plan gratuito; condiciones y precios en el sitio)
- **[Hunter.io](https://hunter.io)**: encuentra direcciones de correo por dominio (tiene plan gratuito; condiciones en el sitio)
- **[Lemlist](https://lemlist.com)**: correo en frío con seguimientos automáticos (condiciones en el sitio)
- **[Instantly.ai](https://instantly.ai)**: una alternativa a Lemlist para envíos en volumen (condiciones en el sitio)
- **[anthropic Python SDK](https://github.com/anthropics/anthropic-sdk-python)**: para los scripts de esta lección
- **Precios y versiones:** [Lo vigente](https://aimayak.com/now/)

---

## Ideas clave

> El correo no se trata en realidad de escribir texto. Se trata de tomar decisiones: a quién responder, qué decir y cuándo. Claude se encarga de la parte mecánica (escribir el texto con tu estilo). Las decisiones siguen siendo tuyas.

> Los borradores solo salen bien si Claude conoce tu estilo. Dedica 30 minutos a una descripción de tu estilo con buenos y malos ejemplos; se paga sola todos los días.

> La bandeja en cero es posible. Ordenar más borradores para el correo entrante reduce bastante el tiempo que pasas en el correo. La clave: no automatices por completo el envío; quédate con la revisión final.

> La prospección en frío con IA es personalización sin el trabajo manual. Apollo encuentra a las personas, Hunter.io encuentra las direcciones de correo y Claude escribe cada correo como si hubieras pasado 20 minutos investigando a la persona. En realidad, son unos cinco segundos de una llamada a la API, así que revisa los detalles que usó antes de darle a Enviar.

---

## Próxima lección

→ [IA para reuniones: transcripciones y notas automáticas](74-ai-meetings.md): graba tus reuniones y conviértelas en tareas
