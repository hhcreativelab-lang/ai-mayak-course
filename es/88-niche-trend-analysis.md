# Cómo encontrar un nicho con Google Trends y Reddit

**Tiempo:** unos 25 min de lectura + 35 min de práctica

---

## Lo esencial

🎨 **Imagínalo así:** un pescador sale al lago, pesca donde pescan todos y no saca nada. Una pescadora lleva una ecosonda. Ve los cardúmenes a un par de cientos de metros, llega dos horas antes que los demás y regresa a casa con la cubeta llena. Las tendencias en los nichos funcionan igual. La mayoría de los emprendedores van a donde ya está la multitud. Quien sabe leer pronto las señales del mercado toma posición antes que la competencia. Eso no garantiza el éxito, pero mejora las probabilidades.

Claude, junto con herramientas de análisis de tendencias, es tu ecosonda. Ves lo que apenas empieza a crecer mientras los demás todavía no lo notan.

El código de esta lección es opcional. Puedes hacer lo mismo a mano en los sitios de Google Trends y Reddit y pegar lo que juntes en un chat de Claude. Al inicio de la práctica se explica cómo.

---

## Conceptos clave

- **Exploding Topics**: un servicio que encuentra temas en su etapa temprana de crecimiento (según el propio servicio, mucho antes de que lleguen a su punto máximo)
- **Google Trends API** (una API es una forma en que un programa le pide datos a otro): datos reales de la demanda de búsqueda a lo largo del tiempo, por región y con búsquedas relacionadas
- **pytrends**: una biblioteca de Python no oficial para Google Trends que no necesita clave de API (el repositorio está archivado desde abril de 2025 y funciona de forma poco confiable)
- **Reddit como señal**: cuánta gente visita los subreddits de un nicho (sus comunidades en Reddit) y cuánto publica ahí indica cómo crece el público de ese nicho
- **Twitter/X**: temas virales en tiempo real (el acceso a los datos es de pago y las condiciones cambian seguido)
- **Una "ola" vs "ruido"**: la diferencia entre una tendencia real y una moda pasajera
- **Análisis de espacios vacíos (whitespace)**: buscar nichos sin dueño donde se cruzan tendencias en crecimiento
- **Un plan de contenido basado en tendencias**: cómo convertir datos en un calendario editorial
- **SEO** (optimización para buscadores): lograr que tus páginas aparezcan bien posicionadas en los buscadores

---

## Teoría

### Por qué sirve analizar tendencias

El mercado de productos en línea suele moverse en olas. Entrar al principio de una ola es más fácil: hay poca competencia y la demanda apenas empieza a crecer. Quienes notaron el revuelo alrededor de ChatGPT a finales de 2022 tuvieron tiempo de ganarse un lugar en ese nicho antes de que llegara una multitud de competidores. Pero muchas señales tempranas no llevan a ningún lado, así que una tendencia todavía no significa éxito: hay que comprobarla con datos y con un experimento pequeño.

Y "leer tendencias" no significa leer los titulares de TechCrunch. Para cuando una tendencia llega a los titulares, la ola suele ir bastante avanzada. Las señales reales están en los datos de demanda de búsqueda, en el ritmo de las conversaciones en Reddit, en los subreddits que crecen. Ahí buscan servicios como Exploding Topics, y eso es lo que vas a aprender a hacer tú en esta lección.

🎨 **Imagínalo así:** una tendencia es una dirección, una pendiente. No buscas lo que ya es popular (la cima), sino lo que apenas empieza a inclinarse hacia arriba (el pie de la subida). En la cima hay mucha gente. En la pendiente solo te encuentras con quienes saben leer el terreno.

---

### Exploding Topics: encontrar temas que crecen

**Qué es.** Exploding Topics es una plataforma para detectar temas en crecimiento. Según su propia descripción, junta datos de buscadores, redes sociales, foros, noticias y tiendas en línea, encuentra temas con crecimiento constante y los muestra antes de que se vuelvan masivos.

**Cómo funciona.** Cada tema tiene un estado:

- **Exploding**: crecimiento muy por encima del promedio; una subida brusca puede resultar una burbuja
- **Regular**: crecimiento fuerte pero no excepcional; suele ser más parejo y confiable
- **Peaked**: el tema ya es muy conocido y su mayor crecimiento quedó atrás

Para un negocio, se suelen buscar temas **Regular** con un volumen de búsqueda notable pero no enorme. Un nicho así crece de forma más pareja, con menos riesgo de burbuja, y todavía no está saturado. El filtro por estado es parte de la versión de pago.

**Filtros prácticos en Exploding Topics:**

- Categoría: elige la tuya (por ejemplo AI, Technology, Marketing, Fitness)
- Periodo: crecimiento en los últimos 2 años
- Volumen: suficiente para que la demanda se note (elige el umbral que le quede a tu proyecto)

**Un ejemplo de cómo usarlo (hipotético).** Digamos que el servicio muestra un crecimiento constante de "AI meeting notes" mientras el nicho todavía tiene pocos jugadores. Los primeros en entrar a un nicho así suelen llegar con contenido SEO y con un público. Uno o dos años después puede llenarse, así que revisa tu propio nicho con datos frescos, no con un ejemplo de una lección.

(En esta lección te vas a topar con algunos términos. **Ahrefs** es una marca de herramientas de análisis SEO. Un **prompt** es tu solicitud a una IA. Un **flujo de trabajo** es una secuencia de pasos de trabajo. Un **panel** (dashboard) muestra tus cifras clave. Un **token** es la unidad de texto con la que se cobra el uso de la IA. Un **script** es un programa corto. Una **clave de API** es una contraseña personal con la que un servicio reconoce a tu programa.)

**Acceso gratis.** Una parte de la base de tendencias está abierta en el sitio: una lista de temas con su gráfica y su crecimiento. El filtro por estado, la búsqueda de tus propios temas y la base completa están en los planes de pago, que tienen un periodo de prueba (los precios y las condiciones están en el sitio del servicio). Para revisar tu idea una sola vez, la parte abierta más un poco de análisis manual puede ser suficiente.

---

### Google Trends API: datos reales de demanda de búsqueda

**Qué muestra.** Google Trends muestra la popularidad relativa de un término de búsqueda a lo largo del tiempo y por región. Importante: no muestra el número absoluto de búsquedas, sino un índice de 0 a 100 (100 = punto máximo).

**pytrends: Python sin clave oficial.** Durante mucho tiempo no hubo una API oficial, y los desarrolladores usaban la biblioteca pytrends, que imita las solicitudes de un navegador a Google Trends. Es un método no oficial: el repositorio de pytrends está archivado desde abril de 2025, Google responde seguido con el error 429 (demasiadas solicitudes) y los scripts se rompen cada vez que el sitio cambia. En julio de 2025, Google abrió una prueba alfa de la API oficial de Google Trends (acceso por solicitud, por ahora para un número limitado de desarrolladores): [developers.google.com/search/apis/trends](https://developers.google.com/search/apis/trends). Los ejemplos de abajo sirven como ejercicios de aprendizaje; para un trabajo serio, revisa la API oficial.

```python
# Instalación
# pip install pytrends pandas matplotlib

from pytrends.request import TrendReq
import pandas as pd

# Configuración
pytrends = TrendReq(hl='en-US', tz=360)

# Compara competidores en un nicho de IA
keywords = ["claude code", "cursor ai", "github copilot", "bolt.new"]

pytrends.build_payload(
    keywords,
    timeframe='today 12-m',   # últimos 12 meses
    geo='US'                   # EE. UU., o '' para todo el mundo (por ejemplo, 'MX' para México)
)

# Datos a lo largo del tiempo
interest_over_time = pytrends.interest_over_time()
print(interest_over_time.tail(10))

# Búsquedas relacionadas (¡la técnica clave!)
related = pytrends.related_queries()
for kw in keywords:
    print(f"\n--- {kw}: búsquedas en aumento ---")
    if related[kw]['rising'] is not None:
        print(related[kw]['rising'].head(5))
```

**Las búsquedas relacionadas son una mina de oro para planear contenido.** Las búsquedas en aumento (rising) muestran búsquedas relacionadas que crecen junto con la principal. Son temas listos para artículos, videos y productos.

**Ejemplo de análisis: buscar un nicho sin dueño en herramientas de IA:**

```python
from pytrends.request import TrendReq
import pandas as pd
import time

pytrends = TrendReq()

# Paso 1: revisa el crecimiento de varios nichos
niches = [
    ["ai video editor", "ai image generator", "ai music generator"],
    ["ai for lawyers", "ai for doctors", "ai for teachers"],
    ["local llm", "ollama", "self hosted ai"]
]

results = {}
for group in niches:
    pytrends.build_payload(group, timeframe='today 5-y')
    df = pytrends.interest_over_time()
    for kw in group:
        if kw in df.columns:
            # Crecimiento del último año vs el año anterior
            last_year = df[kw].tail(52).mean()
            prev_year = df[kw].iloc[-104:-52].mean()
            growth = ((last_year - prev_year) / (prev_year + 1)) * 100
            results[kw] = round(growth, 1)
    time.sleep(2)  # pausa para que no te bloqueen

# Nichos que más crecen
sorted_results = sorted(results.items(), key=lambda x: x[1], reverse=True)
print("Nichos que más crecen:")
for kw, growth in sorted_results[:10]:
    print(f"  {kw}: +{growth}%")
```

Este script te da una lista lista de nichos con su porcentaje de crecimiento. Mándasela directo a Claude para que la analice.

---

### Reddit como sistema de alerta temprana

Reddit es donde profesionales y aficionados hablan de los temas antes de que lleguen a los medios masivos. Una comunidad de Reddit sobre un tema se llama subreddit. Un subreddit que crece = un público que crece para el nicho.

**Qué seguir:**

1. Los **visitantes por semana** (weekly visitors): Reddit muestra este número en la página de la comunidad en lugar del número de miembros. Anótalo una vez al mes para ver el crecimiento
2. La **actividad** (weekly contributions): cuántas publicaciones y comentarios hubo en una semana
3. Las **preguntas frecuentes** (what is / how to / best X for Y): son pedidos de contenido

**Herramientas:**

- **SubredditStats** (subredditstats.com): un archivo de estadísticas de comunidades. El propio sitio avisa que sus datos probablemente están desactualizados, así que no sirve para cifras recientes
- **PRAW (Python Reddit API Wrapper)**: una biblioteca para leer publicaciones y comentarios desde un programa. Solo funciona con acceso aprobado a la API de Reddit (ver abajo)

```python
# pip install praw

import praw
from collections import Counter
import re

reddit = praw.Reddit(
    client_id="YOUR_CLIENT_ID",
    client_secret="YOUR_CLIENT_SECRET",
    user_agent="python:trend-analyzer:v1.0 (by /u/YOUR_USERNAME)"
)

def analyze_subreddit_trends(subreddit_name, limit=200):
    """Analiza las publicaciones principales de un subreddit para encontrar temas en tendencia"""
    
    subreddit = reddit.subreddit(subreddit_name)
    
    titles = []
    for post in subreddit.hot(limit=limit):
        titles.append(post.title.lower())
    
    # Extrae palabras clave (versión simplificada)
    all_words = ' '.join(titles)
    words = re.findall(r'\b[a-z]{4,}\b', all_words)
    
    # Palabras vacías
    stopwords = {'that', 'this', 'with', 'from', 'have', 'been', 'will', 'your', 'what'}
    filtered = [w for w in words if w not in stopwords]
    
    counter = Counter(filtered)
    
    print(f"\nTemas principales en r/{subreddit_name}:")
    for word, count in counter.most_common(20):
        print(f"  {word}: {count} menciones")
    
    return counter

# Analiza algunos subreddits de nicho
for sub in ['ClaudeAI', 'LocalLLaMA', 'ChatGPT']:
    analyze_subreddit_trends(sub)
```

**Cómo configurar PRAW:**

1. Pide acceso a la Reddit Data API: el enlace al formulario está en la ayuda de Reddit, en la página Reddit Data API Wiki. Explica para qué necesitas los datos y espera la aprobación
2. Cuando te aprueben, Reddit te dirá cómo registrar una app (del tipo "script")
3. Obtén tu client_id y tu client_secret, ponlos en el código y escribe tu nombre de usuario de Reddit en user_agent

Importante: según las reglas de Reddit (la Responsible Builder Policy), tienes que pedir acceso y recibir una aprobación explícita antes de tocar cualquier dato de Reddit por medio de la API. Usar datos de Reddit con fines comerciales requiere la aprobación por escrito de Reddit. Sin aprobación, el código de arriba no va a funcionar. Si no tienes acceso, revisa las comunidades a mano, como en el paso 5 de la práctica: para leer Reddit en el navegador no hace falta ninguna solicitud.

---

### Claude analiza los datos de tendencias: el flujo completo

Juntar los datos es la mitad del trabajo. La otra mitad es entenderlos. Aquí es donde Claude se gana su lugar como analista.

**Prompt de ejemplo para analizar datos de Google Trends:**

```python
import anthropic
import json

client = anthropic.Anthropic()

# Datos de ejemplo hipotéticos (no son cifras reales): cámbialos por los resultados de tus propios scripts
trend_data = {
    "period": "últimos 12 meses",
    "keywords_growth": {
        "ai meeting notes": 340,
        "local llm": 280,
        "ai for lawyers": 195,
        "cursor ai": 450,
        "ai video editor": 120
    },
    "reddit_growing_subreddits": [
        {"name": "LocalLLaMA", "weekly_visitors_3m_ago": 45000, "weekly_visitors_now": 180000},
        {"name": "ClaudeAI", "weekly_visitors_3m_ago": 8000, "weekly_visitors_now": 95000}
    ],
    "exploding_topics": [
        "agentic ai", "ai coding assistant", "rag pipeline", "model context protocol"
    ]
}

message = client.messages.create(
    model="claude-opus-5-5",   # modelos actuales: consulta la página Lo vigente
    max_tokens=8000,   # con margen a propósito: el "razonamiento" del modelo también cuenta para este límite
    messages=[
        {
            "role": "user",
            "content": f"""Analiza estos datos de tendencias y dame recomendaciones estratégicas:

{json.dumps(trend_data, ensure_ascii=False, indent=2)}

Mi situación: soy desarrollador independiente, sé trabajar con Claude Code y quiero lanzar un micro-SaaS o un proyecto de contenido sobre IA. Presupuesto inicial: hasta $500.

Responde estas preguntas:
1. ¿Cuáles son los 3 nichos más prometedores para entrar ahora mismo, y por qué?
2. ¿Qué nichos ya están sobrecalentados (demasiado tarde para entrar)?
3. ¿Qué ángulo sin dueño hay donde se cruzan dos tendencias en crecimiento?
4. Un plan concreto: ¿qué construir, qué contenido crear y cómo ganar dinero con eso?

Sé específico, pero apóyate solo en los datos de arriba. Si los datos no alcanzan para sacar una conclusión, dilo y no inventes números."""
        }
    ]
)

# La respuesta llega en bloques; nos quedamos solo con los de texto
answer = "".join(block.text for block in message.content if block.type == "text")
print(answer)
```

🎨 **Imagínalo así:** los datos de tendencias son un mapa lleno de alfileres. Ves los puntos, pero no ves la ruta. Claude es un guía con experiencia que mira el mismo mapa y te dice: "Aquí hay un sendero de montaña casi sin gente que va directo a la cima. Y allá hay un camino precioso, pero ya está lleno de turistas". Un guía también se puede equivocar, así que revisa tú la conclusión.

---

### Tendencias en Twitter/X: una señal viral en tiempo real

Twitter/X te da otro tipo de datos: no crecimiento constante, sino picos virales. Sirve para planear contenido sobre temas "calientes", pero ten cuidado: las tendencias en X se apagan rápido.

**Cómo obtener los datos:**

- La API oficial de X es de pago y se cobra por uso; revisa los precios en la página para desarrolladores de X (las condiciones han cambiado varias veces)
- No uses servicios de terceros que recolectan datos de X por fuera de la API oficial: las condiciones de X prohíben de forma expresa recolectar datos sin el consentimiento por escrito de la empresa
- La forma gratis: mira a mano dentro del propio X. Usa la búsqueda por palabras clave y la sección de tendencias (en la app está en la pestaña Explorar)

**Cuándo sirven las tendencias de X:**

- Nichos alrededor de noticias del momento (un lanzamiento nuevo de IA, un escándalo de la industria)
- Estrategia de contenido para un público de X/Twitter
- Validación rápida: "¿la gente está hablando de esto ahora mismo?"

**Consejo.** Para la mayoría de los análisis de negocio, Google Trends + Reddit es más confiable que X. X te da la "temperatura" del momento; Google Trends te da demanda de búsqueda real que se convierte en tráfico.

---

### Análisis de espacios vacíos: encontrar el lugar sin dueño

La habilidad más valiosa no es encontrar una tendencia que crece. Es encontrar un cruce de dos tendencias que nadie ha ocupado.

**Matriz de cruces:**

| | Herramientas de IA | Automatización | Local primero |
|---|---|---|---|
| **Abogados** | Algunos competidores | Pocos | Casi ninguno |
| **Maestros** | Algunos competidores | Competencia moderada | Pocos |
| **Arquitectos** | Casi ninguno | Casi ninguno | Ninguno |

En esta tabla hipotética, la celda "herramientas de IA para arquitectos, local primero" parece un nicho con competencia mínima. Eso la vuelve candidata a espacio vacío: todavía tienes que comprobar la demanda y los competidores con datos reales. La tabla solo ilustra el método.

**Cómo revisar un espacio vacío con Claude:**

```
Revisa los siguientes cruces de nichos para ver si siguen abiertos.
Para cada celda, estima:
- ¿Hay productos que ya existen (1-5, donde 5 = muchos competidores)?
- ¿Cuál es la demanda de búsqueda (adjunto datos de Google Trends)?
- ¿Hay comunidades en Reddit o en foros?
- ¿Qué tan factible es construir aquí un micro-SaaS en 30 días?

Nichos a analizar:
[pega los datos de Google Trends + una lista de competidores de una búsqueda rápida]
```

---

## Práctica

### Ejercicio: arma un panel de tendencias para tu nicho en 35 minutos

**Escenario:** quieres encontrar un nicho prometedor para un micro-SaaS (un producto de software pequeño que maneja una persona o un equipo muy chico) o un proyecto de contenido sobre IA.

**Si no programas,** sáltate los pasos 1-4 y haz lo mismo a mano. Abre [Google Trends](https://trends.google.com), escribe un término de búsqueda, agrega algunos más para comparar y elige el periodo de los últimos 5 años. Descarga los datos con el botón de descarga, arriba a la derecha de la gráfica: el archivo se abre en Google Sheets. Pega la tabla en un chat de Claude y pídele: "Estos son datos de Google Trends de mis términos de búsqueda. ¿Qué temas crecen de forma constante, cuál me conviene evitar y por qué? Apóyate solo en estos datos; si no alcanzan, dilo". Después pasa al paso 5. Los pasos 1-4 son para quien quiere juntar los datos con un programa en Python. Treinta y cinco minutos alcanzan si ya tienes Python instalado y una clave de la API de Claude; la primera vez, calcula más tiempo.

---

**Paso 1: Instala las dependencias (3 minutos)**

```bash
mkdir trend-analyzer && cd trend-analyzer
python3 -m venv venv && source venv/bin/activate
pip install pytrends pandas matplotlib anthropic python-dotenv
```

En Windows, escribe `venv\Scripts\activate` en lugar de `source venv/bin/activate`.

---

**Paso 2: El script para juntar datos (10 minutos)**

Crea un archivo llamado `trend_collector.py`:

```python
from pytrends.request import TrendReq
import pandas as pd
import json
import time

def collect_trend_data(keyword_groups, timeframe='today 5-y', geo=''):
    """
    Junta datos de tendencias para grupos de palabras clave.
    keyword_groups: una lista de listas (no más de 5 palabras clave por grupo: es el límite de pytrends)
    """
    pytrends = TrendReq(hl='en-US', tz=360)
    all_results = {}
    
    for group in keyword_groups:
        print(f"Procesando: {group}")
        pytrends.build_payload(group, timeframe=timeframe, geo=geo)
        
        df = pytrends.interest_over_time()
        if not df.empty:
            for kw in group:
                if kw in df.columns:
                    # Crecimiento: promedio de la mitad reciente del periodo vs la mitad anterior
                    vals = df[kw].values
                    half = len(vals) // 2
                    recent_avg = vals[half:].mean()
                    old_avg = vals[:half].mean()
                    growth_pct = ((recent_avg - old_avg) / (old_avg + 0.001)) * 100
                    
                    all_results[kw] = {
                        'current_avg': round(float(recent_avg), 1),
                        'growth_pct': round(float(growth_pct), 1),
                        'peak': int(df[kw].max()),
                        'trend': 'growing' if growth_pct > 20 else 
                                 'stable' if growth_pct > -10 else 'declining'
                    }
        
        time.sleep(3)  # pausa obligatoria entre solicitudes
    
    return all_results

# Elige los nichos que quieres analizar (cámbialos según tu campo)
keyword_groups = [
    ["claude code", "cursor ai", "github copilot"],
    ["ai for small business", "ai automation tools", "no code ai"],
    ["local llm", "ollama", "private ai"],
    ["ai meeting assistant", "ai note taker", "ai transcription"],
]

print("Juntando datos de tendencias...")
# 'today 5-y' = los últimos 5 años. Google Trends no acepta otro periodo expresado en años
results = collect_trend_data(keyword_groups, timeframe='today 5-y')

# Guarda los resultados
with open('trend_data.json', 'w', encoding='utf-8') as f:
    json.dump(results, f, ensure_ascii=False, indent=2)

print("\nResultados:")
sorted_r = sorted(results.items(), key=lambda x: x[1]['growth_pct'], reverse=True)
for kw, data in sorted_r:
    symbol = '📈' if data['trend'] == 'growing' else '➡️' if data['trend'] == 'stable' else '📉'
    print(f"{symbol} {kw}: crecimiento {data['growth_pct']}%, máximo {data['peak']}")
```

Ejecútalo: `python trend_collector.py`

---

**Paso 3: Claude analiza los resultados (10 minutos)**

Primero, en la misma carpeta, crea un archivo llamado `.env` con una sola línea: `ANTHROPIC_API_KEY=tu_clave`. La clave se obtiene en la Claude Console (el enlace está en "Herramientas y recursos") y las solicitudes se cobran por token. No le muestres la clave a nadie y no la pegues directo en el código.

Crea `analyze_with_claude.py`:

```python
import anthropic
import json
from dotenv import load_dotenv

load_dotenv()
client = anthropic.Anthropic()

# Carga los datos de tendencias
with open('trend_data.json', encoding='utf-8') as f:
    trend_data = json.load(f)

# Los 10 que más crecen
growing = sorted(
    [(k, v) for k, v in trend_data.items() if v['trend'] == 'growing'],
    key=lambda x: x[1]['growth_pct'],
    reverse=True
)[:10]

analysis_prompt = f"""Soy desarrollador independiente y sé trabajar con Python y Claude Code.
Quiero lanzar un micro-SaaS o un proyecto de contenido educativo sobre IA/automatización.
Presupuesto: hasta $500. Tiempo disponible: 10-15 horas a la semana.

Datos de Google Trends (crecimiento: los últimos 2.5 años frente a los 2.5 años anteriores):
{json.dumps(dict(growing), ensure_ascii=False, indent=2)}

Dame:
1. Los 3 MEJORES nichos para entrar ahora mismo, con tu razonamiento
2. Qué nicho evitar (demasiado tarde, o una burbuja)
3. Un producto o formato de contenido concreto para cada uno de los 3 MEJORES
4. Las primeras 3 acciones para esta semana
5. Dónde buscar a los primeros clientes o lectores

Que la respuesta sea estructurada y específica. Si los datos no alcanzan para sacar una conclusión, dilo."""

message = client.messages.create(
    model="claude-opus-5-5",   # modelos actuales: consulta la página Lo vigente
    max_tokens=8000,   # con margen a propósito: el "razonamiento" del modelo también cuenta para este límite
    messages=[{"role": "user", "content": analysis_prompt}]
)

# La respuesta llega en bloques; nos quedamos solo con los de texto
answer = "".join(block.text for block in message.content if block.type == "text")

print("=== ANÁLISIS DE NICHOS ===\n")
print(answer)

# Guarda el análisis
with open('niche_analysis.md', 'w', encoding='utf-8') as f:
    f.write("# Análisis de nichos - " + __import__('datetime').date.today().isoformat() + "\n\n")
    f.write(answer)

print("\nAnálisis guardado en niche_analysis.md")
```

Ejecútalo: `python analyze_with_claude.py`

---

**Paso 4: Una gráfica rápida (5 minutos)**

Crea un archivo llamado `trend_chart.py` y ejecútalo: `python trend_chart.py`

```python
import matplotlib.pyplot as plt
import json

with open('trend_data.json', encoding='utf-8') as f:
    data = json.load(f)

# Solo los nichos que crecen
growing = {k: v for k, v in data.items() if v['trend'] == 'growing'}
sorted_g = sorted(growing.items(), key=lambda x: x[1]['growth_pct'], reverse=True)

keywords = [x[0] for x in sorted_g]
growths = [x[1]['growth_pct'] for x in sorted_g]

plt.figure(figsize=(12, 6))
colors = ['#2ecc71' if g > 100 else '#f39c12' if g > 30 else '#3498db' for g in growths]
bars = plt.barh(keywords, growths, color=colors)
plt.xlabel('Crecimiento (%)')
plt.title('Nichos en crecimiento: análisis de Google Trends')
plt.tight_layout()
plt.savefig('trends_chart.png', dpi=150)
print("Gráfica guardada: trends_chart.png")
```

---

**Paso 5: Revisa en Reddit (5 minutos, a mano)**

Para cada uno de tus 3 mejores nichos:

1. Abre reddit.com/search y escribe la palabra clave
2. Revisa si hay una comunidad activa (subreddit) sobre el tema
3. Abre la comunidad y mira dos números en su página: weekly visitors (visitantes por semana) y weekly contributions (publicaciones y comentarios en una semana). Reddit ya no muestra el número de miembros
4. Anota el nombre y los dos números. Revisa otra vez en un mes: el crecimiento solo se ve al comparar

Suma estas notas a los datos que le das a Claude: la conclusión final será más precisa.

---

## Herramientas y recursos

- **[Exploding Topics](https://explodingtopics.com)**: encuentra temas que crecen. Una parte de la base está abierta gratis; los planes de pago están en el sitio
- **[Google Trends](https://trends.google.com)**: la herramienta básica, gratis
- **[pytrends](https://github.com/GeneralMills/pytrends)**: una biblioteca de Python no oficial para Google Trends, gratis; el repositorio está archivado
- **[Google Trends API (alfa)](https://developers.google.com/search/apis/trends)**: la API oficial, en alfa: acceso por solicitud, por ahora para un número limitado de desarrolladores
- **[SubredditStats](https://subredditstats.com)**: un archivo de estadísticas de comunidades de Reddit; el propio sitio avisa que sus datos probablemente están desactualizados
- **[PRAW](https://praw.readthedocs.io)**: la biblioteca de Python para la API de Reddit (necesitas que Reddit apruebe tu acceso)
- **[Ahrefs Free Tools](https://ahrefs.com/free-seo-tools)**: herramientas gratis para encontrar ideas de palabras clave y ver qué tan difícil es posicionarse con una
- **[Semrush Keyword Gap](https://www.semrush.com)**: compara con qué búsquedas aparecen tu sitio y los de tu competencia; las condiciones de prueba están en el sitio (Semrush pertenece a Adobe desde abril de 2026, y el producto sigue funcionando)
- **[Anthropic API](https://console.claude.com)**: Claude para analizar datos; la clave y el cobro por token se manejan en la Claude Console (precios: [Lo vigente](https://aimayak.com/now/))

---

## Ideas clave

> "Las tendencias no son una moda. Son datos medibles sobre la demanda de búsqueda. Quienes saben leer esos datos y probarlos con un experimento pequeño toman decisiones basadas en hechos, no en corazonadas."

> "Google Trends te da la demanda, Reddit te da el público, Exploding Topics te da las señales tempranas. Claude te ayuda a juntarlo todo en un borrador de estrategia de forma rápida y barata, pero la decisión y la verificación siguen siendo tuyas: el modelo puede equivocarse y solo trabaja con los datos que le diste."

> "El espacio vacío, el cruce de dos tendencias en crecimiento en un nicho sin dueño, es el hallazgo más valioso. No busques donde hay ruido. Busca donde hay silencio pero la dirección es clara."

---

## Siguiente lección

→ [Economía unitaria en simple](d01-unit-economics-simple.md): cuánto vale un cliente

Ya elegiste un nicho y revisaste la demanda. Ahora toca el dinero: cuánto deja un cliente y cuánto cuesta conseguirlo. Si quieres seguir a tu competencia de forma automática, hay una lección opcional en la biblioteca: [Inteligencia competitiva con IA](89-competitive-intelligence.md).
