# IA para publicidad: textos de anuncios, pruebas A/B y pujas inteligentes

**Tiempo:** unos 25 min de lectura + 40 min de práctica

---

## Lo esencial

Un redactor publicitario trabaja 8 horas, escribe 5 versiones de un anuncio, se cansa y se va a su casa. Claude escribe 50 versiones en unos minutos, analiza los resultados de las pruebas y te ayuda a ver cuál funciona mejor.

No es solo más rápido. Es otro juego: más experimentos → más datos → mejores anuncios → muchas veces un costo por clic más bajo.

🎨 **Imagínalo así:** antes, una agencia de publicidad era como un restaurante con un solo cocinero: lento y caro. Claude más tus datos se parece más a una cocina de pruebas: 50 recetas en un minuto, pruebas cuál es la mejor y haces más de la ganadora. Y la cocina sigue trabajando de noche mientras el cocinero duerme.

---

## Conceptos clave

- **Textos de anuncios con Claude**: 50 variantes de titular con una sola instrucción
- **Meta Ads (Facebook/Instagram)**: textos e imágenes con IA
- **Google Ads RSA**: anuncios de búsqueda adaptables, con Claude mejorando los titulares
- **LinkedIn Ads y TikTok Ads**: el mismo método, con los límites y las políticas de cada plataforma
- **Pruebas A/B**: Claude analiza los resultados y declara al ganador
- **Performance Max**: cómo ayuda Claude con los grupos de recursos
- **Adspirer MCP**: manejar campañas de anuncios directamente desde Claude
- **Informes automáticos**: datos → análisis → recomendaciones concretas

---

## Teoría

### Textos de anuncios: 50 versiones en 3 minutos

La buena publicidad empieza con pruebas. Para probar, necesitas muchas versiones. Antes eso costaba mucho tiempo y dinero. Ahora cuesta mucho menos.

```python
import anthropic
import json

def generate_ad_variants(
    product: str,
    target_audience: str,
    key_benefit: str,
    platform: str,
    count: int = 10
) -> dict:
    """Genera variantes de texto para anuncios"""

    client = anthropic.Anthropic()

    # Las plataformas cambian sus límites de caracteres: compruébalos en las páginas de ayuda de Meta y Google Ads
    platform_specs = {
        "facebook": {
            "headline_chars": 40,
            "primary_text_chars": 125,
            "description_chars": 30
        },
        "google_rsa": {
            "headline_chars": 30,
            "description_chars": 90,
            "headline_count": 15
        },
        "instagram": {
            "caption_chars": 2200,
            "first_line_chars": 125  # lo que se ve antes de "más"
        }
    }

    specs = platform_specs.get(platform, platform_specs["facebook"])

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=2000,
        messages=[{
            "role": "user",
            "content": f"""Crea {count} variantes de anuncio para {platform}.

Producto: {product}
Público objetivo: {target_audience}
Beneficio principal: {key_benefit}
Límites de la plataforma: {json.dumps(specs, ensure_ascii=False)}

Usa un enfoque distinto en cada variante:
- Emocional (miedo a quedarse fuera)
- Racional (números y hechos)
- Prueba social (reseñas, clientes)
- Curiosidad (una pregunta o un dato sorprendente)
- Directo (el beneficio, dicho sin rodeos)

Usa solo afirmaciones que sean ciertas para este producto. No inventes números, reseñas ni cantidades de clientes.

Devuelve un arreglo JSON:
[
  {{
    "variant_id": 1,
    "approach": "nombre del enfoque",
    "headline": "titular",
    "primary_text": "texto principal",
    "cta": "llamado a la acción",
    "target_emotion": "la emoción que busca",
    "hypothesis": "por qué debería funcionar"
  }}
]"""
        }]
    )

    return json.loads(response.content[0].text)


# Ejemplo: un curso de Excel en línea
variants = generate_ad_variants(
    product="Curso de Excel en línea para profesionales de finanzas",
    target_audience="Contadores y personal de finanzas de 25 a 45 años que dedican 2-3 horas a los informes",
    key_benefit="Bajar el tiempo de un informe de 3 horas a 20 minutos",
    platform="facebook",
    count=10
)

for v in variants[:3]:
    print(f"\n--- Variante {v['variant_id']}: {v['approach']} ---")
    print(f"Titular: {v['headline']}")
    print(f"Texto: {v['primary_text']}")
    print(f"CTA: {v['cta']}")
```

⚠️ **Toda afirmación en un anuncio tiene que ser cierta.** Las reglas de publicidad y de protección al consumidor de tu país se aplican a todos los anuncios, incluidos los que escribe la IA: nada de reseñas ni cantidades de clientes inventadas, nada de resultados que no puedas respaldar. Revisa las reglas de tu país. Además, cada plataforma (Google, Meta, LinkedIn, TikTok) tiene sus propias políticas de anuncios, con reglas extra para categorías delicadas como vivienda, empleo, crédito y salud. La IA escribe el borrador; tú eres responsable de lo que se publica. Si tienes dudas sobre una afirmación, lee las páginas de políticas de la plataforma o consulta a un abogado.

### Meta Ads: textos e imágenes

Meta (Facebook + Instagram) es la plataforma de anuncios con los datos más ricos. Claude ayuda con los textos y trabaja junto con generadores de imágenes para la parte visual.

**El embudo para crear anuncios:**

```
1. Claude → 10 variantes de texto
2. Flux / Midjourney / el generador de imágenes de ChatGPT → una imagen para cada texto
3. Lanza una prueba A/B (5 variantes a la vez)
4. 3-5 días → junta datos
5. Claude → analiza los resultados
6. Escala al ganador
```

```python
def create_meta_campaign_brief(
    product: str,
    budget_daily: float,
    target_audience_description: str
) -> str:
    client = anthropic.Anthropic()

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=1500,
        messages=[{
            "role": "user",
            "content": f"""Crea un brief detallado para una campaña de Meta Ads.

Producto: {product}
Presupuesto diario: ${budget_daily}
Público: {target_audience_description}

Incluye:
1. **Estructura de la campaña**: cuántos conjuntos de anuncios y la lógica detrás
2. **Segmentación**: intereses detallados, edad, ubicación
3. **Recomendaciones de públicos similares**: en quién basar un público similar (lookalike)
4. **Formatos**: qué formatos de anuncio usar y por qué
5. **Presupuesto**: cómo repartirlo entre los conjuntos de anuncios
6. **KPI**: qué cuenta como éxito (CPC, CTR, CPL)
7. **Plan de pruebas**: qué probar primero

Sé específico: números, porcentajes, recomendaciones."""
        }]
    )

    return response.content[0].text
```

🎨 **Imagínalo así:** antes, el planificador de medios era un especialista aparte que trabajaba de 9 a 5. Claude hace un borrador del plan en segundos, incluso a las 3 de la mañana antes de un lanzamiento. La decisión sobre el presupuesto la sigue tomando una persona.

### Google Ads: RSA y palabras clave inteligentes

Google RSA (anuncios de búsqueda adaptables): das hasta 15 titulares y 4 descripciones, y Google los combina por su cuenta. Claude te ayuda a escribir 15 titulares que de verdad funcionen bien en cualquier combinación.

```python
def generate_google_rsa(
    product: str,
    landing_page_theme: str,
    keywords: list[str]
) -> dict:
    client = anthropic.Anthropic()

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=1200,
        messages=[{
            "role": "user",
            "content": f"""Crea un anuncio RSA para Google Ads.

Producto: {product}
Tema de la página de destino: {landing_page_theme}
Palabras clave: {', '.join(keywords)}

Requisitos:
- 15 titulares, cada uno de hasta 30 caracteres
- 4 descripciones, cada una de hasta 90 caracteres
- Los titulares deben funcionar bien en cualquier combinación
- Pon las palabras clave en 3-4 titulares (¡no en todos!)
- Variedad: beneficios, acciones, lo que te hace diferente, urgencia

Devuelve JSON:
{{
    "headlines": ["titular 1", ... "titular 15"],
    "descriptions": ["descripción 1", ... "descripción 4"],
    "pinning_recommendations": {{
        "headline_position_1": "qué titular fijar en la posición 1",
        "reason": "por qué"
    }}
}}"""
        }]
    )

    return json.loads(response.content[0].text)


# Ejemplo: un despacho de abogados
rsa = generate_google_rsa(
    product="Servicios legales inmobiliarios",
    landing_page_theme="Cierra la compra de tu casa de forma rápida y segura",
    keywords=["abogado inmobiliario", "escrituración de inmuebles", "abogado para comprar casa"]
)

print("Titulares:")
for i, h in enumerate(rsa["headlines"], 1):
    chars = len(h)
    status = "✅" if chars <= 30 else "⚠️"
    print(f"{i}. {status} {h} ({chars} caracteres)")
```

### LinkedIn Ads y TikTok Ads: el mismo método

Las funciones de arriba no están atadas a Meta y Google. LinkedIn Ads es la opción habitual para B2B (venta a empresas): puedes segmentar por puesto, industria y tamaño de empresa, así que el texto le habla a un rol ("para gerentes de RR. HH. de empresas medianas") y no a un interés. En TikTok, un anuncio es un video vertical corto, así que el "texto" que escribe Claude es sobre todo un guion para los primeros segundos más una descripción. Para agregar cualquiera de las dos plataformas, pon una entrada nueva en `platform_specs` con los límites actuales de las páginas de ayuda de esa plataforma (cambian, así que no copies números de publicaciones viejas de blogs) y corre las mismas `generate_ad_variants()` y `analyze_ab_test()`.

### Pruebas A/B: Claude elige al ganador

Los datos de una prueba muchas veces se ven confusos. Una versión tiene un CTR más alto, pero también un CPC más alto. Menos conversiones, pero más baratas. Claude te ayuda a desenredarlo en segundos.

```python
def analyze_ab_test(test_results: list[dict]) -> dict:
    """
    test_results: una lista de diccionarios con los resultados de cada variante
    Ejemplo: [{"variant": "A", "impressions": 5000, "clicks": 150, "conversions": 12, "spend": 200}]
    """
    client = anthropic.Anthropic()

    # Agrega las métricas calculadas
    for r in test_results:
        r["ctr"] = round(r["clicks"] / r["impressions"] * 100, 2)
        r["cpc"] = round(r["spend"] / r["clicks"], 2) if r["clicks"] > 0 else 0
        r["cpl"] = round(r["spend"] / r["conversions"], 2) if r["conversions"] > 0 else 0
        r["cvr"] = round(r["conversions"] / r["clicks"] * 100, 2) if r["clicks"] > 0 else 0

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=800,
        messages=[{
            "role": "user",
            "content": f"""Analiza los resultados de esta prueba A/B de anuncios y dame recomendaciones.

Resultados:
{json.dumps(test_results, ensure_ascii=False, indent=2)}

Necesito:
1. **Ganador**: qué variante es mejor y POR QUÉ (considera todas las métricas)
2. **Significancia estadística**: si hay suficientes datos para una conclusión confiable
3. **Aprendizajes**: qué dicen los resultados sobre el público
4. **Siguiente paso**: qué probar después
5. **Escalamiento**: cuánto aumentar el presupuesto del ganador

Sé específico: da números y porcentajes."""
        }]
    )

    return {
        "raw_results": test_results,
        "analysis": response.content[0].text
    }


# Prueba
results = [
    {"variant": "A — Miedo (pérdida)", "impressions": 10000, "clicks": 180, "conversions": 9, "spend": 350},
    {"variant": "B — Beneficio (ahorro)", "impressions": 10000, "clicks": 220, "conversions": 18, "spend": 350},
    {"variant": "C — Prueba social", "impressions": 10000, "clicks": 195, "conversions": 14, "spend": 350}
]

analysis = analyze_ab_test(results)
print(analysis["analysis"])
# Ganador: B — CTR 2.2%, CPL $19.4, CVR 8.2%
# La variante A pierde a pesar de su titular intrigante
# Recomendación: todavía hay pocos datos (9 y 18 conversiones); deja correr la prueba y sube poco a poco el presupuesto de B
```

### Performance Max: Claude ayuda con los grupos de recursos

PMax es un tipo de campaña de Google que decide por su cuenta dónde mostrar tus anuncios (Búsqueda, YouTube, Gmail, Display). La calidad de tus materiales (recursos o assets) es fundamental. Para las campañas de Búsqueda, Google también tiene AI Max: a octubre de 2026, las funciones de IA vienen integradas en las propias campañas, así que revisa nombres y configuraciones en las páginas de ayuda de Google Ads.

```python
def create_pmax_assets(
    product: str,
    key_benefits: list[str],
    audience_persona: str
) -> dict:
    client = anthropic.Anthropic()

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=2000,
        messages=[{
            "role": "user",
            "content": f"""Crea todos los materiales (recursos) que necesita una campaña de Performance Max.

Producto: {product}
Beneficios principales: {', '.join(key_benefits)}
Perfil del público: {audience_persona}

Crea:
{{
    "headlines": ["5 titulares de hasta 30 caracteres"],
    "long_headlines": ["5 titulares largos de hasta 90 caracteres"],
    "descriptions": ["5 descripciones de hasta 90 caracteres"],
    "business_name": "nombre de la empresa (hasta 25 caracteres)",
    "call_to_actions": ["una lista de 5 llamados a la acción"],
    "image_prompts": ["5 prompts para generar imágenes en Midjourney/Flux"],
    "audience_signals": {{
        "interests": ["una lista de intereses para las señales de público"],
        "custom_intent_keywords": ["palabras clave de intención"],
        "remarketing_segments": ["segmentos de remarketing"]
    }}
}}"""
        }]
    )

    return json.loads(response.content[0].text)
```

### Adspirer MCP: manejar anuncios directamente desde Claude

Adspirer es un servicio MCP de terceros para cuentas de anuncios. Se conecta a Claude Code y a Cowork como plugin y, a octubre de 2026, funciona con Google Ads, Meta Ads y varias plataformas más. Le permite a Claude ver datos reales de las campañas y hacer recomendaciones basadas en hechos, no en suposiciones. El servicio también puede lanzar campañas, así que revisa sus condiciones, dale los permisos mínimos (empieza con solo lectura) y quédate tú con el lanzamiento de anuncios y los cambios de presupuesto.

```
# En Claude Code, con Adspirer MCP conectado:

"Muéstrame las campañas con un CTR menor a 1% en los últimos 7 días"
→ Claude ve los datos → te da una lista con recomendaciones

"¿Qué palabras clave están gastando dinero sin ninguna conversión?"
→ Claude lo analiza → una lista de palabras clave para pausar

"Crea un informe de ROI de todas las campañas del mes"
→ Claude lo genera → comparación, conclusiones, recomendaciones
```

### Informes automáticos: de los datos a las conclusiones

```python
def generate_weekly_ad_report(campaigns_data: dict) -> str:
    client = anthropic.Anthropic()

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=1500,
        messages=[{
            "role": "user",
            "content": f"""Genera un informe semanal de las campañas de anuncios.

Datos:
{json.dumps(campaigns_data, ensure_ascii=False, indent=2)}

Formato del informe:
## Resultados de esta semana
[3-4 números clave]

## Qué está funcionando
[las 3 cosas que mejor funcionaron, con números]

## Qué no está funcionando
[los 3 problemas principales, con números]

## Acciones para la próxima semana
[5 pasos concretos, con el efecto esperado]

## Presupuesto
[recomendaciones para redistribuirlo]

Escribe como analista: concreto, con números, sin relleno."""
        }]
    )

    return response.content[0].text
```

---

## Práctica

### Ejercicio: crea 10 variantes de texto para anuncios y analiza una prueba

**Parte 1: Generar las variantes (15 minutos)**

```python
# ad_generator.py

import anthropic
import json

client = anthropic.Anthropic()

def create_ad_batch(product_info: dict) -> list:
    """Crea un lote de anuncios para probar"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=3000,
        messages=[{
            "role": "user",
            "content": f"""Crea 10 variantes de anuncio para Facebook.

PRODUCTO: {product_info['name']}
DESCRIPCIÓN: {product_info['description']}
PRECIO: {product_info['price']}
PÚBLICO: {product_info['audience']}
BENEFICIO PRINCIPAL: {product_info['main_benefit']}
PROBLEMA DEL PÚBLICO: {product_info['pain_point']}

Crea 2 variantes para cada enfoque:
1. Miedo a perder ("si no haces X, vas a perder Y")
2. Beneficio ("consigue X y ahorra Y")
3. Prueba social ("1,000 clientes ya...")
4. Curiosidad ("¿Sabías que...?")
5. Oferta directa ("Obtén X por Y ahora mismo")

Usa solo hechos de la información del producto de arriba. No inventes números, reseñas ni cantidades de clientes.

Formato JSON:
[{{
    "id": 1,
    "approach": "nombre",
    "headline": "hasta 40 caracteres",
    "text": "hasta 125 caracteres",
    "cta": "botón",
    "image_direction": "qué debe mostrar la imagen"
}}]"""
        }]
    )

    return json.loads(response.content[0].text)

# Córrelo con tu producto
my_product = {
    "name": "Escuela en línea de inglés de negocios para profesionales de tecnología",
    "description": "Inglés para trabajar en equipos de EE. UU., en 3 meses",
    "price": "$99/mes",
    "audience": "Desarrolladores y profesionales de TI de 25 a 40 años para quienes el inglés es su segundo idioma",
    "main_benefit": "Sentirte seguro en entrevistas de trabajo y en reuniones de equipo",
    "pain_point": "Sé inglés técnico, pero me pierdo en reuniones rápidas con hablantes nativos"
}

ads = create_ad_batch(my_product)

print("=== ANUNCIOS GENERADOS ===\n")
for ad in ads:
    print(f"#{ad['id']} — {ad['approach']}")
    print(f"Titular: {ad['headline']}")
    print(f"Texto: {ad['text']}")
    print(f"CTA: {ad['cta']}")
    print(f"Imagen: {ad['image_direction']}")
    print()
```

**Parte 2: Analizar los resultados de la prueba (25 minutos)**

Cuando la prueba ya haya corrido, captura los datos y obtén el análisis:

```python
# Captura tus datos reales después de 5 días de prueba (los números de abajo son inventados)
test_data = [
    {"id": 1, "approach": "Miedo a perder", "impressions": 8500, "clicks": 102, "conversions": 4, "spend": 180},
    {"id": 2, "approach": "Miedo a perder 2", "impressions": 8200, "clicks": 115, "conversions": 5, "spend": 175},
    {"id": 3, "approach": "Beneficio", "impressions": 8800, "clicks": 185, "conversions": 12, "spend": 182},
    {"id": 4, "approach": "Beneficio 2", "impressions": 8600, "clicks": 172, "conversions": 10, "spend": 178},
    {"id": 5, "approach": "Prueba social", "impressions": 8300, "clicks": 166, "conversions": 11, "spend": 176},
    {"id": 6, "approach": "Prueba social 2", "impressions": 8700, "clicks": 143, "conversions": 8, "spend": 181},
    {"id": 7, "approach": "Curiosidad", "impressions": 9100, "clicks": 228, "conversions": 7, "spend": 185},
    {"id": 8, "approach": "Curiosidad 2", "impressions": 8900, "clicks": 214, "conversions": 6, "spend": 183},
    {"id": 9, "approach": "Oferta directa", "impressions": 8400, "clicks": 126, "conversions": 9, "spend": 177},
    {"id": 10, "approach": "Oferta directa 2", "impressions": 8600, "clicks": 138, "conversions": 8, "spend": 179}
]

analysis = analyze_ab_test(test_data)
print(analysis["analysis"])
```

---

## Herramientas y recursos

- **Meta Business Manager**: business.facebook.com (para manejar anuncios)
- **Google Ads**: ads.google.com
- **LinkedIn Campaign Manager**: la herramienta de LinkedIn para manejar anuncios (públicos B2B)
- **TikTok Ads Manager**: la herramienta de TikTok para manejar anuncios (videos verticales cortos)
- **Adspirer MCP**: una herramienta para analizar anuncios a través de Claude
- **Flux**: bfl.ai, el sitio de Black Forest Labs (genera imágenes para anuncios a partir de un prompt)
- **Meta Ad Library**: facebook.com/ads/library (mira los anuncios que está publicando tu competencia)
- **Google Keyword Planner**: la herramienta de Google para planear palabras clave
- **Anthropic SDK**: para integrar Claude en tus flujos de trabajo de publicidad; los nombres de los modelos en el código son de octubre de 2026. Precios y versiones actuales: [Lo vigente](https://aimayak.com/now/)

---

## Ideas clave

> La publicidad siempre es una prueba. Quien prueba más variantes aprende más rápido. Claude hace que probar sea barato: 50 variantes en lugar de 5, en minutos en lugar de días.
>
> El análisis de datos es el cuello de botella en la mayoría de los equipos de publicidad. Claude quita ese cuello de botella: ve todas las métricas a la vez, no se pierde en hojas de cálculo y da una conclusión concreta con el razonamiento detrás.
>
> La regla principal: Claude escribe los textos y analiza los datos, pero una persona lanza y escala los anuncios. La decisión final siempre es tuya; la IA solo te ayuda a llegar ahí más rápido.

---

## Siguiente lección

→ [IA para ventas: calificación de clientes potenciales, seguimiento y cierre](93-sales-ai.md)
