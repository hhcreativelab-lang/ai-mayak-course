# Presentaciones con IA: Gamma, Beautiful.ai y Claude

**Tiempo:** unos 25 min de lectura + 35 min de práctica

---

## La idea

Hacer una buena presentación antes se llevaba un día entero en PowerPoint. Con IA, un buen borrador queda listo en más o menos media hora, y tú te concentras en tus ideas en lugar de andar acomodando cuadros en una diapositiva.

La parte principal de esta lección se hace en el navegador, sin código. Las secciones sobre python-pptx y la API de Google Slides son para quienes construyen sus propias herramientas; los demás pueden saltárselas.

🎨 **Imagínalo así:** el PowerPoint de siempre es como armar tú mismo un mueble de esos que vienen en caja: las piezas son las correctas, pero te lleva todo el día y te sobran la mitad de los tornillos. Gamma es un mueble que llega ya armado. Dices lo que quieres y cinco minutos después ya está en la sala. Luego mueves lo que no quedó del todo bien.

---

## Conceptos clave

- Gamma: una presentación completa a partir de un solo prompt (tu petición a la IA), con un diseño que se adapta al contenido
- Beautiful.ai: diseño de diapositivas con IA y plantillas inteligentes (una plantilla es un diseño ya hecho)
- Claude + python-pptx: generar archivos de PowerPoint con código (control total; para quienes construyen)
- Claude + la API de Google Slides (una API es la forma en que un programa habla con otro servicio): presentaciones en la nube, hechas con código
- El flujo de trabajo: idea → estructura con Claude → diseño en Gamma → ajustes finales
- Un pitch deck (una presentación para inversionistas) con IA: del concepto a un buen borrador en unas horas

---

## Teoría

### Gamma: una presentación a partir de un prompt

Gamma ([gamma.app](https://gamma.app)) es una de las formas más rápidas de pasar de una idea a una presentación que se ve bien.

**Cómo funciona:**

1. Escribes una oración o pegas un bloque de texto
2. Gamma sugiere una estructura (tú la editas)
3. Gamma genera el diseño
4. Tú afinas los detalles

**Qué puede crear:**

- Presentaciones (diapositivas)
- Documentos (con buen formato)
- Páginas web (landing pages públicas)

**Precios (a octubre de 2026):** Gamma te deja empezar gratis, la generación gasta créditos, y los límites y las opciones de exportación dependen del plan. Según el centro de ayuda de Gamma, los créditos iniciales del plan gratis no se recargan solos, así que gástalos en una tarea real. Precios de Gamma: [gamma.app/pricing](https://gamma.app/pricing). Precios de los asistentes de IA: [Lo vigente](https://aimayak.com/now/).

**Lo que Gamma hace bien:**

- Un diseño que se adapta a cualquier contenido
- Tipografía automática
- Imágenes integradas que van con el tema
- Elementos interactivos (gráficas, contenido incrustado)
- Gamma Agent: en un chat, cambia el estilo, el texto y el tono de toda la presentación de una vez
- Smart Diagrams (diagramas inteligentes): dibuja diagramas a partir de una descripción
- Idiomas: según el centro de ayuda de Gamma, puedes escribir tu prompt en tu propio idioma, y el español está en la lista de idiomas de la interfaz. De todos modos, revisa la calidad del texto con tu propio tema

🎨 **Imagínalo así:** Gamma es como un buen diseñador freelance. Le dices qué necesitas y lo deja bonito; le dices qué cambiar y lo cambia. No es perfecto, pero la mayor parte del trabajo ya está hecha.

---

### Beautiful.ai: plantillas inteligentes de diapositivas

Beautiful.ai ([beautiful.ai](https://beautiful.ai)) tiene un enfoque distinto al de Gamma: la prioridad es que las diapositivas se vean profesionales de forma automática. También tiene un modo Create with AI (crear con IA): le das un tema o un esquema, ajustas la estructura y obtienes un diseño.

**La función clave: Smart Slides (diapositivas inteligentes).**
Cuando agregas un elemento (texto, una imagen, un ícono), la diapositiva se reacomoda sola para que todo se vea bien. No puedes hacer que se vea "chueca"; el sistema no te deja.

| | Gamma | Beautiful.ai |
|--|-------|--------------|
| Generar a partir de un prompt | ✅ Sí | ✅ Sí (Create with AI) |
| Control del diseño | Medio | Alto |
| Plantillas inteligentes | Básicas | Avanzadas |
| Colaboración | ✅ Sí | ✅ Sí |
| Exportar a PPTX | depende del plan | depende del plan |
| Precio | ver la página de precios | ver la página de precios (ahí están las condiciones de la prueba) |

Las filas "Control del diseño" y "Plantillas inteligentes" son una valoración del autor, no el resultado de una comparación independiente: pruébalas con tu propia tarea.

**Cuándo usar Beautiful.ai en lugar de Gamma:**

- Necesitas más control sobre el diseño
- Un equipo trabaja junto en la presentación
- Tienes una guía de marca corporativa que hay que seguir al pie de la letra

**Si vives en PowerPoint o Google Slides:** Copilot en PowerPoint (Agent Mode) y Gemini en Google Slides también pueden armar una presentación a partir de una petición. Necesitas las suscripciones correspondientes (Microsoft 365 con Copilot, o Google Workspace y planes de Google AI), y las funciones se van habilitando poco a poco. Si presentas en un idioma distinto del inglés, revisa primero si lo soporta: en su lanzamiento, Gemini en Slides solo funcionaba en inglés.

---

### Para quienes construyen: Claude + python-pptx, PowerPoint con código

Esta sección y la siguiente son opcionales: son para quienes escriben código. Si no programas, pasa a la sección "El flujo de trabajo". Cuando necesitas control total, o generar muchas presentaciones de forma automática, Claude escribe código que crea archivos PPTX (el formato de archivo de PowerPoint).

**Instalación:**

```bash
pip install python-pptx
```

**Un ejemplo básico: el código arma una presentación a partir de un esquema ya hecho:**

```python
from pptx import Presentation
from pptx.util import Inches, Pt
from pptx.dml.color import RGBColor
from pptx.enum.text import PP_ALIGN

def create_presentation(title, slides_data):
    """
    slides_data = [
        {"title": "Título de la diapositiva", "content": ["punto 1", "punto 2"]},
        ...
    ]
    """
    prs = Presentation()
    
    # Tamaño de diapositiva (16:9, pantalla ancha)
    prs.slide_width = Inches(13.33)
    prs.slide_height = Inches(7.5)
    
    # Diapositiva de título
    slide_layout = prs.slide_layouts[0]
    slide = prs.slides.add_slide(slide_layout)
    slide.shapes.title.text = title
    slide.placeholders[1].text = "Hecho con Claude + python-pptx"
    
    # Diapositivas de contenido
    for slide_data in slides_data:
        slide_layout = prs.slide_layouts[1]  # título + contenido
        slide = prs.slides.add_slide(slide_layout)
        
        # Título
        slide.shapes.title.text = slide_data["title"]
        
        # Contenido
        tf = slide.placeholders[1].text_frame
        tf.clear()
        for i, point in enumerate(slide_data["content"]):
            if i == 0:
                tf.text = point
            else:
                p = tf.add_paragraph()
                p.text = point
                p.level = 0
    
    return prs

# Uso
slides = [
    {"title": "El problema", "content": [
        "Problema 1: ...",
        "Problema 2: ...",
        "Problema 3: ..."
    ]},
    {"title": "Nuestra solución", "content": [
        "Cómo resolvemos el problema 1",
        "Cómo resolvemos el problema 2"
    ]},
]

prs = create_presentation("Pitch Deck: Nombre del proyecto", slides)
prs.save("presentation.pptx")
print("¡Listo!")
```

**Un prompt para Claude:** "Escribe un script de Python que cree un pitch deck profesional para [descripción del proyecto]. Usa python-pptx. 10 diapositivas: problema, solución, mercado, producto, modelo de negocio, equipo, tracción, finanzas, hoja de ruta, llamado a la acción."

---

### Claude + la API de Google Slides: presentaciones en la nube

Para el trabajo en equipo y la generación automática en la nube, existe la API de Google Slides. Esta sección también es para quienes construyen.

**Por qué es útil:**

- La presentación queda directo en tu Google Drive, y tú mismo la compartes con tu equipo
- Se puede actualizar de forma automática (reportes trimestrales, por ejemplo)
- No depende de archivos PPTX ni de nada guardado en tu computadora

**Configuración:**

```bash
pip install google-api-python-client google-auth-httplib2 google-auth-oauthlib
```

En Google Cloud Console, activa la API de Google Slides, crea un cliente OAuth de tipo "Desktop app" (app de escritorio) y descarga su archivo como `credentials.json` (la documentación de la API de Google Slides, enlazada al final de esta lección, lo explica paso a paso).

**Código básico:**

```python
from google_auth_oauthlib.flow import InstalledAppFlow
from googleapiclient.discovery import build

# Configurar la autorización: se abre una ventana del navegador e inicias sesión en tu cuenta de Google
SCOPES = ['https://www.googleapis.com/auth/presentations']
flow = InstalledAppFlow.from_client_secrets_file('credentials.json', SCOPES)
credentials = flow.run_local_server(port=0)

service = build('slides', 'v1', credentials=credentials)

# Crear una presentación nueva
presentation = service.presentations().create(
    body={"title": "Mi presentación con IA"}
).execute()

presentation_id = presentation['presentationId']
print(f"Creada: https://docs.google.com/presentation/d/{presentation_id}")
```

A partir de ahí, Claude te ayuda a escribir solicitudes en lote (batch) que agregan diapositivas, texto e imágenes.

⚠️ Trata el archivo `credentials.json` como una contraseña: no lo pongas en carpetas compartidas, correos ni repositorios de código públicos.

---

### El flujo de trabajo: idea → Claude → Gamma → versión final

Un orden cómodo para la mayoría de las presentaciones:

**Paso 1: Estructura con Claude (5 min)**

```
Tarea: una presentación sobre [tema] para [público]
Objetivo: [qué debe hacer el público después]
Extensión: [N diapositivas]

Crea la estructura:
- Un título para cada diapositiva
- 3-5 puntos clave para cada una
- Sugerencias de elementos visuales
```

**Paso 2: Generar en Gamma (5 min)**

- Pega en Gamma la estructura de Claude
- Elige un tema visual
- Gamma genera el diseño

**Paso 3: Editar en Gamma (10-15 min)**

- Corrige la redacción
- Cambia imágenes si hace falta
- Quita lo que no necesitas

**Paso 4: Revisión final con Claude (5 min)**

```
[Pega los puntos clave finales de cada diapositiva]

Revisa:
1. ¿La lógica fluye de una diapositiva a otra? ¿Hay una historia?
2. ¿Cada diapositiva plantea una sola idea, o varias?
3. ¿El llamado a la acción de la última diapositiva es concreto?
4. ¿Alguna diapositiva contradice a otra?
```

Total: 25-30 minutos para un buen borrador de presentación. Revisar los datos y los números de las diapositivas te toca a ti.

---

### Un pitch deck para inversionistas, hecho con IA

Un pitch deck es un formato especial: estructura estricta, muy poco texto, la mayor cantidad posible de números.

**La estructura estándar (10-12 diapositivas):**

```
1. Título: nombre, eslogan, datos de contacto
2. Problema: un dolor concreto y qué tan grande es
3. Solución: cómo lo resuelves, en 1 oración
4. Producto: capturas de pantalla, una demo, 3 funciones clave
5. Mercado: TAM, SAM, SOM, con fuentes
6. Modelo de negocio: cómo ganas dinero
7. Tracción: crecimiento, métricas, clientes
8. Competencia: una matriz comparativa
9. Equipo: fotos + 1 línea sobre por qué ustedes
10. Finanzas: una proyección de P&L a 3 años
11. La petición: cuánto, para qué, runway
12. Gracias: datos de contacto + seguimiento
```

Algunos términos, por si son nuevos para ti: TAM, SAM y SOM son tres tamaños de tu mercado (el mercado total, la parte que podrías atender y la porción que puedes ganar de forma realista). P&L significa pérdidas y ganancias (el estado de resultados). Runway es cuántos meses te va a durar el dinero.

Verifica cada cifra del mercado con su fuente. La IA puede inventar números con total seguridad (una alucinación), y un tamaño de mercado equivocado en la diapositiva 5 te puede costar toda la reunión.

**Un prompt para Claude:**

```
Crea la estructura de un pitch deck para [descripción de la startup].
Inversionistas: [tipo de inversionistas, etapa].
Ronda: [pre-seed / seed / Serie A], monto: [N].

Para cada diapositiva:
- Un título (máximo 5 palabras)
- Los 3 puntos principales (con números concretos siempre que se pueda)
- Qué datos necesita la diapositiva
- Qué NO poner en ella (errores comunes en esta diapositiva)
```

🎨 **Imagínalo así:** un pitch deck es un currículum para inversionistas. Un buen currículum no explica cada trabajo con detalle; muestra lo esencial rápido. Si un inversionista necesita más de 3 minutos para recorrer tus 12 diapositivas, algo está mal.

---

## Práctica

1. Crea una cuenta en Gamma (es gratis y puedes entrar con Google):

Entra a [gamma.app](https://gamma.app) → Create new AI (Crear con IA). Ahí vas a usar dos modos: Generate (Generar: una presentación a partir de un prompt corto) y Paste in text (Pegar texto: una presentación a partir de un texto o esquema ya hecho). Los nombres de los botones en la interfaz cambian de vez en cuando

2. Pídele a Claude que cree la estructura de tu presentación:

```
Tema: [elige algo real: la descripción de tu proyecto,
curso, servicio o idea]
Público: [quién la va a ver]
Objetivo: [qué deben hacer después]
Diapositivas: 10

Crea la estructura: un título para cada diapositiva +
3-4 puntos clave para cada una.
```

3. En Gamma, elige Paste in text, pega la estructura, elige Presentation (Presentación) y un tema visual, y genera la presentación

4. Pídele a Claude que mejore las primeras 3 diapositivas:

```
[Pega el texto de las primeras 3 diapositivas de Gamma]

Para cada diapositiva:
- Sugiere un título más fuerte (máximo 6 palabras)
- Quita la redacción genérica y agrega detalles concretos
- Haz que el primer punto sea el dato más importante
```

Terminaste cuando tengas una presentación de 10 diapositivas que podrías mostrarle a alguien, con los datos y los números de las diapositivas revisados por ti. Hasta aquí llega la práctica sin código.

5. Opcional, para quienes construyen: instala python-pptx y crea una presentación sencilla con código:

```bash
pip install python-pptx
```

```python
# Pídele a Claude que escriba un script para una presentación de 5 diapositivas
# sobre tu proyecto, usando el código de esta lección como punto de partida
```

6. Opcional, para quienes construyen: un generador automático de reportes semanales:

```
Pídele a Claude que escriba un script que:
1. Lea datos de un archivo CSV (las métricas de la semana)
2. Genere un archivo PPTX con 4 diapositivas:
   - Números clave
   - Lo que logramos
   - Lo que no funcionó
   - Planes para la próxima semana
3. Lo guarde con la fecha en el nombre del archivo
```

---

## Herramientas y recursos

- **[Gamma](https://gamma.app)**: un camino rápido de una idea a las diapositivas
- **[Beautiful.ai](https://beautiful.ai)**: plantillas inteligentes para controlar el diseño
- **[python-pptx](https://python-pptx.readthedocs.io)**: una biblioteca para generar archivos PPTX con código
- **[Google Slides API](https://developers.google.com/slides)**: presentaciones en la nube mediante una API
- **[Canva Presentations](https://www.canva.com)**: una alternativa con una gran biblioteca de plantillas
- **Precios y versiones:** [Lo vigente](https://aimayak.com/now/)

---

## Ideas clave

> Gamma más una estructura hecha con Claude es la combinación mínima que te da un buen borrador en media hora: Claude se encarga de la lógica y el contenido, Gamma lo deja bonito y tú ajustas los detalles y revisas los datos.

> Necesitas python-pptx cuando las presentaciones se generan de forma automática o desde una plantilla: reportes semanales, propuestas a la medida para clientes, materiales de capacitación, cualquier cosa que necesites reproducir muchas veces.

> Un pitch deck hecho con IA es un borrador, no la versión final. Los inversionistas han visto muchas presentaciones hechas con plantillas como estas; deciden por el contenido y los números, no por el diseño.

---

## Siguiente lección

→ [Traducción y localización con IA: DeepL y Claude](75-ai-translation.md): traducir correos y textos para que suenen naturales

El video viene en el siguiente módulo: [Generación de video con IA: Runway, Kling y más](71-ai-video-generation.md): dale vida a tus ideas con video
