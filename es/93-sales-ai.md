# IA para ventas: calificar clientes potenciales, seguimiento y cierre

**Tiempo:** unos 25 min de lectura + 35 min de práctica

---

## Lo esencial

Vender es filtrar. De cien clientes potenciales (personas o empresas que mostraron algún interés), solo una pequeña parte va a comprar. El trabajo de un vendedor es encontrar rápido a los que van a comprar y dedicarles su tiempo a ellos en lugar de a todos los demás.

Claude vuelve ese filtro sistemático: califica a los clientes potenciales con BANT, le da a cada uno una puntuación de qué tan listo está, escribe correos personalizados y prepara respuestas a las objeciones. El vendedor entra a la conversación sabiendo ya quién está del otro lado y qué le importa.

🎨 **Imagínalo así:** un vendedor con experiencia que, antes de cada llamada, recibe un resumen rápido de un colega: "Es Carlos, de Distribuidora del Norte. Están viendo a la competencia, el presupuesto existe, pero el director general todavía no decide, y la objeción principal es la integración con su sistema contable". Eso es lo que hace Claude con cada cliente potencial, de forma automática.

---

## Conceptos clave

- **Calificación BANT**: Budget (presupuesto), Authority (autoridad), Need (necesidad), Timeline (plazo), trabajados con IA
- **Puntuación de clientes potenciales de 0 a 100**: quién está listo para comprar ahora mismo
- **Seguimientos personalizados**: cada correo escrito para una persona concreta
- **Una biblioteca de objeciones**: Claude prepara un borrador de respuesta para cualquier objeción
- **Manual de ventas → asistente de IA**: un documento se convierte en un asesor que trabaja
- **Apollo.io + Claude**: prospección con personalización profunda

---

## Teoría

### Calificación BANT: cuatro preguntas que lo deciden todo

BANT es uno de los métodos de ventas más antiguos, y sigue funcionando:

- **B**udget (presupuesto): ¿hay dinero? ¿Cuánto están dispuestos a gastar?
- **A**uthority (autoridad): ¿esta persona toma la decisión, o solo está juntando información?
- **N**eed (necesidad): ¿hay una necesidad real, o "solo están viendo"?
- **T**imeline (plazo): ¿cuándo piensan comprar? ¿Este trimestre o "algún día"?

Claude saca el BANT de cualquier conversación: correos, chats, notas de llamadas y reuniones:

```python
import anthropic
import json

client = anthropic.Anthropic()

def qualify_lead_bant(
    company_name: str,
    contact_name: str,
    contact_position: str,
    interaction_history: str
) -> dict:
    """Califica a un cliente potencial con BANT a partir del historial de interacciones"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=800,
        messages=[{
            "role": "user",
            "content": f"""Haz una calificación BANT de este cliente potencial con la información disponible.

Empresa: {company_name}
Contacto: {contact_name}, {contact_position}

Historial de interacciones:
{interaction_history}

Califica cada criterio BANT en una escala de 0 a 3:
0 = no hay información
1 = señal débil o dudosa
2 = hay algunas señales
3 = confirmación clara

Devuelve JSON:
{{
    "bant": {{
        "budget": {{
            "score": un número de 0 a 3,
            "evidence": "una cita o un hecho de la conversación",
            "concern": "qué preocupa",
            "recommendation": "qué más averiguar"
        }},
        "authority": {{
            "score": un número de 0 a 3,
            "evidence": "...",
            "concern": "...",
            "recommendation": "..."
        }},
        "need": {{
            "score": un número de 0 a 3,
            "evidence": "...",
            "concern": "...",
            "recommendation": "..."
        }},
        "timeline": {{
            "score": un número de 0 a 3,
            "evidence": "...",
            "concern": "...",
            "recommendation": "..."
        }}
    }},
    "total_score": un número de 0 a 12,
    "qualification_verdict": "hot/warm/cold/disqualify",
    "recommended_next_step": "una siguiente acción concreta",
    "key_questions_to_ask": ["una lista de 3 preguntas para el próximo contacto"]
}}"""
        }]
    )

    result = json.loads(response.content[0].text)

    # Agrega una puntuación en porcentaje
    result["qualification_percent"] = round(result["total_score"] / 12 * 100)

    return result


# Prueba
history = """
15 de abril, primera llamada:
Carlos preguntó por nuestro producto y dijo que están "viendo opciones para
automatizar el departamento". Es gerente de desarrollo de negocios. El director general
"todavía no está involucrado". No se habló de presupuesto. "Nos gustaría resolver esto
antes de fin de año".

22 de abril, segunda llamada:
Carlos regresó con una lista detallada de requisitos. Dijo que el director general aprobó
que lo evaluaran. Mencionó que un producto parecido de la competencia cuesta $10,000 al año,
y que eso les parece caro. Quieren empezar "a más tardar en el tercer trimestre, está atado
a nuestro ciclo de presupuesto".

28 de abril, correo:
"Vimos la demostración. Nos gusta, pero necesitamos entender cómo se integra
con nuestro sistema contable. Además, a nuestro director general le gustaría reunirse en persona.
¿Tienen tiempo la próxima semana?"
"""

result = qualify_lead_bant(
    company_name="Distribuidora del Norte",
    contact_name="Carlos Rivas",
    contact_position="Gerente de Desarrollo de Negocios",
    interaction_history=history
)

print(f"Puntuación BANT: {result['total_score']}/12 ({result['qualification_percent']}%)")
print(f"Estado: {result['qualification_verdict'].upper()}")
print(f"\nSiguiente paso: {result['recommended_next_step']}")
print(f"\nPreguntas para la reunión:")
for q in result['key_questions_to_ask']:
    print(f"  • {q}")
```

### Puntuación de clientes potenciales: quién está caliente ahora mismo

BANT es la base, pero hay decenas de señales más que muestran si alguien está listo para comprar. Claude las mira todas a la vez y da una puntuación de 0 a 100.

```python
def score_lead_readiness(
    contact_info: dict,
    interaction_history: str,
    product_type: str,
    avg_deal_cycle_days: int
) -> dict:
    """Evaluación general de qué tan listo está un cliente potencial para comprar"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=700,
        messages=[{
            "role": "user",
            "content": f"""Califica qué tan listo está este cliente potencial para comprar.

Información del contacto:
{json.dumps(contact_info, ensure_ascii=False)}

Tipo de producto: {product_type}
Ciclo de venta promedio: {avg_deal_cycle_days} días

Historial:
{interaction_history}

Analiza las señales:
POSITIVAS: preguntas concretas sobre detalles, pregunta por la integración o la implementación,
menciona fechas límite, dice un presupuesto, pide una reunión con el director general, te compara con la competencia,
pide una propuesta o un contrato

NEGATIVAS: respuestas vagas, "ya veremos", silencios largos sin respuesta,
dice que "no es mi decisión", cambia los requisitos a cada rato, quiere todo más barato

Devuelve JSON:
{{
    "score": un número de 0 a 100,
    "stage": "awareness/consideration/decision/ready_to_buy",
    "hot_signals": ["una lista de señales positivas encontradas en el historial"],
    "cold_signals": ["una lista de señales de alerta"],
    "estimated_close_days": un número (pronóstico de cuántos días faltan para cerrar la venta),
    "confidence": "low/medium/high",
    "action": {{
        "immediate": "qué hacer ahora mismo",
        "this_week": "qué hacer esta semana",
        "if_no_response": "qué hacer si no hay respuesta en 3 días"
    }}
}}"""
        }]
    )

    return json.loads(response.content[0].text)
```

🎨 **Imagínalo así:** un médico mira los síntomas y da un diagnóstico. Un vendedor mira las señales y da una puntuación. Claude es un asistente de diagnóstico que revisa cada síntoma de la lista y no se cansa después del cliente potencial número 50.

### Correos de seguimiento personalizados

Los correos de plantilla rara vez funcionan. "¡Hola! Queremos recordarle nuestra oferta..." suele terminar borrado sin leerse.

La personalización sí funciona. Pero personalizar 50 seguimientos a mano no es realista.

```python
def generate_followup_email(
    contact: dict,
    last_interaction_summary: str,
    days_since_last_contact: int,
    followup_number: int,  # Primer, segundo o tercer seguimiento
    product_name: str,
    your_name: str
) -> dict:
    """Genera un correo de seguimiento personalizado"""

    followup_tone = {
        1: "amable y ligero, aporta valor (un artículo o un caso de estudio)",
        2: "un poco más directo, pregunta si tienen dudas o si algo cambió",
        3: "el último, deja claro que es el seguimiento final, pero sin presionar"
    }

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=600,
        messages=[{
            "role": "user",
            "content": f"""Escribe un correo de seguimiento personalizado.

DATOS DEL CONTACTO:
Nombre: {contact.get('name')}
Empresa: {contact.get('company')}
Puesto: {contact.get('position')}
Interés: {contact.get('main_interest')}

CONTEXTO:
Último contacto: {last_interaction_summary}
Días sin respuesta: {days_since_last_contact}
Este es el seguimiento número: {followup_number} de 3
Tono: {followup_tone.get(followup_number, followup_tone[1])}

Producto: {product_name}
De: {your_name}

REQUISITOS:
- 3-5 oraciones como máximo
- La primera oración se refiere concretamente a la última conversación (no una frase de plantilla)
- Agrega algo útil (una observación práctica, una estadística real con su fuente, un caso real breve); no inventes datos
- Un solo llamado a la acción claro
- Sin presión, sin insistir de más
- Lenguaje natural, no corporativo

Devuelve JSON:
{{
    "subject": "asunto del correo",
    "body": "texto del correo",
    "ps": "una posdata (opcional, solo si hace más fuerte el correo)",
    "value_add": "qué cosa útil aporta el correo"
}}"""
        }]
    )

    return json.loads(response.content[0].text)


# Ejemplo
email = generate_followup_email(
    contact={
        "name": "Carlos",
        "company": "Distribuidora del Norte",
        "position": "Gerente de Desarrollo de Negocios",
        "main_interest": "Automatización del equipo de ventas, integración con su sistema contable"
    },
    last_interaction_summary="Hicimos una demostración. A Carlos le gustó mucho, pero preguntó por la integración con su sistema contable. Quedamos en que lo platicarían con su equipo.",
    days_since_last_contact=4,
    followup_number=1,
    product_name="SalesBot Pro",
    your_name="Daniel"
)

print(f"Asunto: {email['subject']}")
print(f"\n{email['body']}")
if email.get('ps'):
    print(f"\nP.D. {email['ps']}")
```

### Una biblioteca de objeciones: una respuesta para todo

Todo producto se topa con 10-15 objeciones típicas. Un vendedor con experiencia sabe la respuesta a cada una. Uno nuevo se pone nervioso.

Claude nunca se pone nervioso:

```python
def handle_objection(
    objection: str,
    product_name: str,
    product_key_benefits: list[str],
    contact_context: str = ""
) -> dict:
    """Prepara borradores de respuesta a una objeción con varios enfoques"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=800,
        messages=[{
            "role": "user",
            "content": f"""Un cliente puso una objeción. Ayúdame a responder.

PRODUCTO: {product_name}
BENEFICIOS: {', '.join(product_key_benefits)}
OBJECIÓN: "{objection}"
CONTEXTO DEL CLIENTE: {contact_context or "Sin contexto adicional"}

Dame 3 opciones de respuesta:

1. **Directa**: dale la razón en la parte de la objeción que es cierta y luego dale la vuelta
2. **Con una pregunta**: haz una pregunta que ayude al cliente a llegar solo a la respuesta
3. **Con un caso**: la historia de un cliente real que tuvo una objeción parecida (si no hay un caso real, dilo en lugar de inventarlo)

Para cada una:
- La respuesta (2-4 oraciones)
- Cuándo usarla

Además, dame:
- La razón oculta: qué hay de verdad detrás de esta objeción
- Señal de alerta: ¿es una objeción genuina o una señal de que la venta no se va a dar?"""
        }]
    )

    return response.content[0].text


# Objeciones y respuestas comunes
objections = [
    "Esto es demasiado caro para nosotros",
    "Tenemos que hablarlo con la dirección",
    "Ya usamos otra solución",
    "Retomemos esto el próximo trimestre",
    "Tenemos que pensarlo"
]

print("=== BIBLIOTECA DE RESPUESTAS A OBJECIONES ===\n")
for obj in objections[:2]:  # Muestra las dos primeras como ejemplo
    print(f"OBJECIÓN: {obj}")
    print("-" * 50)
    response = handle_objection(
        objection=obj,
        product_name="SalesBot Pro",
        product_key_benefits=["Ahorra 5 horas a la semana", "Integración con tu sistema contable", "Funcionando en 2 días"],
        contact_context="Cliente B2B, empresa mediana, equipo de ventas de 10 personas"
    )
    print(response)
    print("\n")
```

### Manual de ventas → un asesor de IA que trabaja

Si ya tienes un manual de ventas (una guía por escrito de cómo vende tu empresa: a quién apuntar, qué decir, cómo manejar las objeciones), Claude lo convierte en un asesor interactivo para tus vendedores.

```python
def create_sales_advisor(playbook_content: str):
    """Crea un asesor de ventas a partir de un manual"""

    def ask_advisor(question: str, deal_context: str) -> str:
        response = client.messages.create(
            model="claude-sonnet-5-5",
            max_tokens=600,
            system=f"""Eres un coach de ventas con experiencia. Tienes el manual de ventas de la empresa:

{playbook_content}

Basa tus respuestas estrictamente en el manual. Si una pregunta va más allá del manual,
dilo. Da frases concretas que un vendedor pueda usar ahora mismo.""",
            messages=[{
                "role": "user",
                "content": f"Situación del cliente: {deal_context}\n\nPregunta: {question}"
            }]
        )
        return response.content[0].text

    return ask_advisor

# Ejemplo de uso
playbook = """
# Manual de ventas: Techservice S.A.

## Calificación
- Presupuesto mínimo con el que trabajamos: $5,000
- Puesto objetivo: director general / director comercial / director de TI
- Señal de alerta: si no pueden decir su problema de forma concreta, no son nuestro cliente

## Cómo manejar la objeción "es demasiado caro"
1. Pregunta: "¿Caro comparado con qué?"
2. Llévalo al retorno de inversión: "¿Cuántas horas a la semana dedica tu gente a X ahora mismo?"
3. Muestra un caso de una empresa de tamaño parecido

## Cierre
- Nunca des un descuento sin una razón
- Preguntas de una u otra opción: "¿Te funciona mejor empezar el día 1 o el 15?"
"""

advisor = create_sales_advisor(playbook)

# Un vendedor pide consejo justo antes de una llamada
advice = advisor(
    question="El cliente dice que es demasiado caro, pero se nota que le interesa. ¿Qué hago?",
    deal_context="Empresa de 50 personas, director de TI, llevan 3 meses evaluando, el presupuesto está 'en discusión'"
)
print(advice)
```

### Apollo.io + Claude: prospección personalizada

Apollo.io es una herramienta para encontrar contactos y hacer prospección (correos en frío, LinkedIn). Claude agrega el tipo de personalización que una plantilla no puede dar.

⚠️ Los correos en frío y la recopilación de datos de contacto están regulados por leyes contra el spam y de protección de datos personales, y cada país tiene las suyas. Revisa las reglas de tu país. Antes de lanzar, revisa las lecciones [Regulación y cumplimiento en IA](61c-ai-regulation-compliance.md) y [Prospección en frío en 2026: mensajes directos, correo y voz](39c-cold-outreach-deep.md).

```python
def personalize_cold_outreach(
    prospect_data: dict,  # Datos de Apollo: empresa, puesto, actividad en LinkedIn
    your_product: str,
    your_value_prop: str
) -> dict:
    """Personaliza un correo en frío para una persona concreta"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=500,
        messages=[{
            "role": "user",
            "content": f"""Escribe un correo en frío personalizado.

INFORMACIÓN DEL PROSPECTO (de Apollo/LinkedIn):
{json.dumps(prospect_data, ensure_ascii=False, indent=2)}

NUESTRO PRODUCTO: {your_product}
PROPUESTA DE VALOR: {your_value_prop}

REGLAS:
- La primera oración TIENE que ser sobre ellos (no sobre nosotros)
- Conecta su contexto real (puesto, empresa, actividad) con nuestro producto
- Una sola pregunta clara al final (no un "compra ahora")
- Menos de 100 palabras

Devuelve JSON:
{{
    "subject": "asunto (hasta 50 caracteres)",
    "opening": "la primera oración personalizada",
    "value": "cómo nuestro producto resuelve su problema concreto",
    "question": "una pregunta para que respondan",
    "personalization_source": "en qué se basa la personalización"
}}"""
        }]
    )

    return json.loads(response.content[0].text)
```

---

## Práctica

### Ejercicio: arma un sistema para calificar clientes potenciales con puntuación de Claude

**Qué vamos a construir:** un script que recibe los datos de un cliente potencial y devuelve una calificación completa más un plan para trabajarlo.

```python
# lead_qualification_system.py

import anthropic
import json
from dataclasses import dataclass
from typing import Optional

client = anthropic.Anthropic()

@dataclass
class Lead:
    name: str
    company: str
    position: str
    email: str
    phone: Optional[str] = None
    source: str = "inbound"
    notes: str = ""
    interaction_log: str = ""

def full_lead_analysis(lead: Lead) -> dict:
    """
    Análisis completo del cliente potencial: BANT + puntuación + plan de acción
    """

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=1200,
        messages=[{
            "role": "user",
            "content": f"""Haz un análisis completo de este cliente potencial para el equipo de ventas.

CLIENTE POTENCIAL:
Nombre: {lead.name}
Empresa: {lead.company}
Puesto: {lead.position}
Origen: {lead.source}
Notas del vendedor: {lead.notes}

HISTORIAL DE INTERACCIONES:
{lead.interaction_log or "Primer contacto, todavía no hay historial"}

Devuelve un análisis COMPLETO en JSON:
{{
    "qualification": {{
        "bant_score": un número de 0 a 12,
        "readiness_score": un número de 0 a 100,
        "verdict": "hot/warm/cold/disqualify",
        "verdict_reason": "por qué este veredicto"
    }},
    "bant_details": {{
        "budget": {{"score": 0-3, "evidence": "...", "gap": "lo que todavía no se sabe"}},
        "authority": {{"score": 0-3, "evidence": "...", "gap": "..."}},
        "need": {{"score": 0-3, "evidence": "...", "gap": "..."}},
        "timeline": {{"score": 0-3, "evidence": "...", "gap": "..."}}
    }},
    "persona_analysis": {{
        "decision_role": "champion/decision_maker/influencer/blocker/user",
        "communication_style": "analytical/relationship/speed/stability",
        "main_motivation": "qué mueve a esta persona"
    }},
    "action_plan": {{
        "next_24h": "una acción concreta",
        "next_week": "el plan para la semana",
        "key_questions": ["3 preguntas para la próxima reunión"],
        "risks": ["qué podría salir mal"],
        "win_conditions": ["qué hace falta para cerrar esta venta"]
    }},
    "suggested_followup_timing": {{
        "if_interested": "cuántos días hasta volver a escribir",
        "if_silent": "cuántos días hasta mandar un recordatorio",
        "max_attempts": un número
    }}
}}"""
        }]
    )

    return json.loads(response.content[0].text)


def format_lead_report(lead: Lead, analysis: dict) -> str:
    """Da formato a un informe limpio para el vendedor"""

    q = analysis["qualification"]
    bant = analysis["bant_details"]
    action = analysis["action_plan"]

    verdict_emoji = {
        "hot": "🔥", "warm": "☀️", "cold": "❄️", "disqualify": "🚫"
    }.get(q["verdict"], "❓")

    report = f"""
╔══════════════════════════════════════════════╗
║  INFORME:    {lead.name[:30]:<30} ║
╚══════════════════════════════════════════════╝

{verdict_emoji} ESTADO: {q['verdict'].upper()} ({q['readiness_score']}/100)
📊 Puntuación BANT: {q['bant_score']}/12
💡 Motivo: {q['verdict_reason']}

DETALLE BANT:
  💰 Presupuesto: {'█' * bant['budget']['score']}{'░' * (3-bant['budget']['score'])} ({bant['budget']['score']}/3) — {bant['budget']['evidence'][:60]}
  👔 Autoridad:   {'█' * bant['authority']['score']}{'░' * (3-bant['authority']['score'])} ({bant['authority']['score']}/3) — {bant['authority']['evidence'][:60]}
  🎯 Necesidad:   {'█' * bant['need']['score']}{'░' * (3-bant['need']['score'])} ({bant['need']['score']}/3) — {bant['need']['evidence'][:60]}
  ⏰ Plazo:       {'█' * bant['timeline']['score']}{'░' * (3-bant['timeline']['score'])} ({bant['timeline']['score']}/3) — {bant['timeline']['evidence'][:60]}

PLAN DE ACCIÓN:
  ⚡ Hoy: {action['next_24h']}
  📅 Esta semana: {action['next_week']}

PREGUNTAS PARA LA PRÓXIMA REUNIÓN:
"""
    for q_text in action['key_questions']:
        report += f"  • {q_text}\n"

    report += f"""
RIESGOS:
"""
    for risk in action['risks']:
        report += f"  ⚠️ {risk}\n"

    return report


# ===== PRUEBA =====
test_lead = Lead(
    name="Miguel Torres",
    company="Grupo Diamante",
    position="Director de Operaciones",
    email="[correo del cliente potencial]",
    source="llamada entrante",
    notes="Nos llamó por su cuenta, dijo que nos vio en una conferencia. Preguntó por las integraciones.",
    interaction_log="""
    14 de mayo (llamada, 25 min):
    Miguel es director de operaciones; supervisa 3 departamentos, entre ellos ventas (12 personas).
    Problema: los vendedores no mantienen el CRM al día, y se pierden clientes potenciales.
    Buscan una solución "antes de que termine el segundo trimestre"; es su fecha límite interna.
    Presupuesto: "algo razonable, los detalles los ve nuestro director financiero". El director de TI ya está enterado.
    Nos pidió enviar una propuesta y casos de empresas parecidas.
    Competencia: vieron Pipedrive, "no les encantó la interfaz".
    Siguiente paso: una reunión con el director financiero en una semana si les gustan los materiales.
    """
)

print("Analizando al cliente potencial...")
analysis = full_lead_analysis(test_lead)
report = format_lead_report(test_lead, analysis)
print(report)

# Guarda en JSON para el CRM
with open(f"lead_{test_lead.name.replace(' ', '_')}.json", "w", encoding="utf-8") as f:
    json.dump({
        "lead": {
            "name": test_lead.name,
            "company": test_lead.company,
            "position": test_lead.position
        },
        "analysis": analysis
    }, f, ensure_ascii=False, indent=2)

print("\n✅ Análisis guardado en JSON")
```

**Córrelo:**
```bash
python lead_qualification_system.py
```

---

## Herramientas y recursos

- **Apollo.io**: encontrar contactos y hacer prospección (revisa en el sitio los planes y los límites)
- **HubSpot CRM**: un CRM para guardar los datos de tus clientes, con plan gratis (revisa en el sitio los planes de pago; consulta también la lección [El CRM en piloto automático](90-crm-autopilot.md))
- **Lemlist / Instantly**: automatización de prospección por correo
- **Notion**: un lugar para guardar tu manual de ventas
- **Claude API**: los nombres de los modelos en el código son de octubre de 2026; los precios y las versiones actuales están en la página [Lo vigente](https://aimayak.com/now/)

---

## Ideas clave

> BANT no es burocracia, es velocidad. Saber rápido si alguien es tu cliente respeta tu tiempo y el suyo.
>
> La personalización ya no es un lujo; es obligatoria. La gente recibe decenas de correos de plantilla al día. Un correo personalizado destaca de inmediato.
>
> Lo más valioso de la IA para ventas no es qué tan rápido escribe. Es la constancia. Claude le da al cliente potencial número cien el mismo nivel de análisis que al primero. Las personas se cansan. La IA no.

---

## Siguiente lección

→ [Atención al cliente con IA: un sistema de tickets, respuestas desde tu base de conocimiento (RAG), un soporte más inteligente](94-ai-customer-support.md)
