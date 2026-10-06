# Traducción y localización con IA: DeepL y Claude

**Tiempo:** unos 20 min de lectura + 25 min de práctica

---

## Lo esencial

Un contenido, cinco mercados, un solo precio. Un artículo sobre el costo de vida en Cuenca, Ecuador, está escrito en inglés. Unos minutos después, y por centavos, existe en español para el mercado local y en portugués para inversionistas de Brasil, con metadatos SEO para cada idioma. No es una traducción palabra por palabra, sino una localización de verdad: los términos correctos, referencias culturales que la gente reconoce, el tono adecuado.

Las mismas habilidades sirven también para la traducción de todos los días: una respuesta a un cliente que habla inglés, una nota para familiares en el extranjero, una carta de un arrendador o de una escuela que necesitas entender. Una cosa sigue siendo trabajo de personas: los documentos oficiales que necesitan una traducción certificada (más sobre eso abajo).

🎨 **Imagínalo así:** construiste una casa de ladrillo. Bonita, sólida. Ahora la quieres vender en cinco colonias a la vez, y en cada colonia se habla un idioma distinto. Antes hacían falta cinco casas distintas. Ahora basta una casa y un intérprete listo que sabe cómo habla la gente de cada colonia y qué le importa.

---

## Conceptos clave

- **API de DeepL**: un traductor especializado, fuerte en idiomas europeos, incluidos el español y el portugués; a muchas personas sus traducciones les parecen más naturales que las de los traductores de uso general, así que compáralas con tus propios textos
- **DeepL MCP**: la integración oficial de DeepL para Claude Code, para que la traducción sea parte de tu flujo de trabajo en lugar de un paso aparte (MCP es la forma estándar de conectar servicios externos a Claude Code)
- **Flujo i18n** (i18n es la abreviatura que usan los desarrolladores para "internacionalización"): una cadena automatizada: contenido original → traducción automática → adaptación cultural → metadatos SEO
- **Glosario / base terminológica**: una lista de términos que nunca se traducen, o que siempre se traducen de una sola forma
- **Adaptación cultural**: reemplazar modismos, ejemplos y referencias culturales por otros que el público de destino entienda
- **Metadatos por mercado**: un título, una descripción y palabras clave para cada idioma y mercado
- **DeepL vs. Claude directamente**: cuándo el primero es más barato y cuándo el segundo es más preciso, y cómo hacer las cuentas

---

## Teoría

### Comparación de herramientas: DeepL vs. Google Translate vs. Claude directamente

| | API de DeepL | Google Translate | Claude (directo) |
|---|---|---|---|
| Velocidad | Muy rápida | Muy rápida | Más lenta |
| Precio | según los planes de DeepL, con un nivel gratis | según los precios de Google Cloud | por token, depende del modelo |
| Glosario de términos | ✅ integrado | ✅ disponible | ⚠️ a través del prompt |
| Adaptación cultural | ❌ | ❌ | ✅ la hace si se lo pides |
| Conserva las etiquetas HTML | ✅ | ✅ | ⚠️ necesita indicarlo en el prompt |
| Integración MCP | ✅ oficial | ⚠️ revisa la documentación | ✅ nativa |
| Idiomas | inglés, español y otros idiomas principales | una enorme cantidad, incluidos los poco comunes | todos los principales |

La calidad de la traducción no está en la tabla: no tenemos una prueba independiente, y el resultado depende del par de idiomas y del tema. Compara las herramientas con tus propios textos. Precios y versiones vigentes: [Lo vigente](https://aimayak.com/now/).

**En resumen:** DeepL para traducir en volumen contenido estructurado (fichas de producto, plantillas de correo, documentos). Claude para la adaptación cultural, la escritura creativa y el material especializado. Google Translate como respaldo para idiomas poco comunes.

---

### Sin código: la traducción de todos los días en un chat normal

La mayor parte de la traducción diaria no necesita un flujo automatizado. Abre Claude en tu navegador, pega el texto y agrega un prompt corto. Sirve para una respuesta a un cliente, un mensaje a la familia o una carta que necesitas entender.

> Traduce este mensaje al inglés para [a quién va: un cliente en Estados Unidos, mi tía en Canadá]. Mantén el tono [cálido y amable / formal de negocios], usa un inglés sencillo y cotidiano, y deja los nombres, fechas, direcciones y precios exactamente como están. Después de la traducción, haz una lista de las frases que se podrían entender de dos maneras. Este es el texto: [pega el texto]

Si no hablas el idioma de destino, pídele a Claude que traduzca su propio resultado de vuelta al español para que puedas revisar el sentido. Para todo lo que de verdad importa (dinero, salud, un contrato), pide que alguien que hable el idioma lo lea antes de mandarlo.

El resto de esta lección es para quienes ya usan Claude Code y quieren traducir mucho contenido de forma programada.

---

### DeepL MCP: traducción dentro de Claude Code

Aquí empieza la parte para quienes construyen: necesitas Claude Code y una terminal. DeepL tiene un servidor MCP oficial (el paquete `deepl-mcp-server`; necesita Node.js 18 o más reciente). La traducción se vuelve parte de tu flujo de trabajo y no tienes que andar cambiando de pestaña.

**Configuración en `.mcp.json`:**

```json
{
  "mcpServers": {
    "deepl": {
      "command": "npx",
      "args": ["-y", "deepl-mcp-server"],
      "env": {
        "DEEPL_API_KEY": "${DEEPL_API_KEY}"
      }
    }
  }
}
```

La clave en sí no va en el archivo: Claude Code reemplaza `${DEEPL_API_KEY}` por el valor de la variable de entorno, que defines en la terminal antes de iniciar Claude Code (el comando está en la sección de Práctica).

Una vez conectado, Claude usa DeepL dentro de la misma sesión:

```
Traduce el artículo al español con DeepL,
y luego adáptalo para lectores de Ecuador.
```

Claude llama a DeepL para la traducción y luego se encarga él mismo de la adaptación, sin cortar tu flujo de trabajo.

---

### El flujo i18n: de un texto a cinco mercados

🎨 **Imagínalo así:** una fábrica de muebles. Un solo plano de un sillón, cinco líneas de ensamble. Cada línea saca el sillón adaptado a su mercado local: otro color, otra tapicería, otra altura. En el fondo es el mismo sillón, con los detalles ajustados al mercado.

**Cómo avanza el flujo:**

```
[Contenido original, EN]
        ↓
[API de DeepL: traducción automática rápida con un glosario]
        ↓
[Claude Sonnet: adaptación cultural y de tono]
        ↓
[Claude Haiku: metadatos SEO para cada mercado]
        ↓
[Archivos: article.en.md / article.es.md / article.pt.md]
[Metadatos: article.es.meta.json / article.pt.meta.json]
```

**El código completo en Python del flujo:**

```python
import anthropic
import deepl
import json
import os
from pathlib import Path

deepl_client = deepl.Translator(os.environ["DEEPL_API_KEY"])
claude_client = anthropic.Anthropic()

# Glosario: términos que NO se traducen, o que se traducen de una forma fija
GLOSSARY_TERMS = {
    "ES": {
        "Acme Realty": "Acme Realty",            # marca: nunca se traduce
        "Acme AI": "Acme AI",                    # nombre del servicio: nunca se traduce
        "apartment": "departamento",             # en Ecuador se dice "departamento"
        "real estate agency": "inmobiliaria",    # el término local habitual
    },
    "PT-BR": {
        "Acme Realty": "Acme Realty",
        "Acme AI": "Acme AI",
    }
}

MARKET_CONTEXT = {
    "ecuador": (
        "Mercado latinoamericano, Ecuador. "
        "Público: compradores de vivienda locales y extranjeros que viven en Ecuador. "
        "Tono formal pero amable. "
        "Énfasis en la estabilidad y la inversión a largo plazo. "
        "Ecuador usa el dólar estadounidense, lo cual es un argumento de venta importante."
    ),
    "brazil": (
        "Mercado brasileño. Público: emprendedores e inversionistas. "
        "Tono directo y concreto. Énfasis en el ROI y en las cifras. "
        "Evita el exceso de emoción: solo hechos."
    ),
    "spain": (
        "Mercado español. Un tono más formal que en América Latina. "
        "Usa el español de España (no el español latinoamericano). "
        "Público: gente de ciudad con estudios."
    ),
}


def create_deepl_glossary(source_lang: str, target_lang: str) -> str | None:
    """Crea un glosario de DeepL para proteger tus términos."""
    terms = GLOSSARY_TERMS.get(target_lang, {})
    if not terms:
        return None

    try:
        glossary = deepl_client.create_glossary(
            name=f"acme-{source_lang}-{target_lang}-{hash(str(terms)) % 10000}",
            source_lang=source_lang,
            target_lang=target_lang,
            entries=terms
        )
        return glossary.glossary_id
    except deepl.DeepLException:
        return None   # DeepL no creó el glosario (por ejemplo, no soporta este par de idiomas): sigue sin él


def translate_with_deepl(text: str, target_lang: str,
                          source_lang: str = "EN",
                          glossary_id: str = None) -> str:
    """Traducción automática rápida que conserva el formato."""
    result = deepl_client.translate_text(
        text,
        source_lang=source_lang,
        target_lang=target_lang,
        glossary=glossary_id,
        preserve_formatting=True,
        tag_handling="html"   # conserva las etiquetas HTML del texto
    )
    return result.text


def adapt_culturally(translated_text: str, target_lang: str,
                     target_market: str, content_type: str = "marketing") -> str:
    """
    Claude adapta la traducción a la cultura.
    No vuelve a traducir: hace que el texto suene natural y reemplaza
    los modismos y las referencias culturales que no encajan.
    """
    context = MARKET_CONTEXT.get(target_market, "Público internacional.")

    prompt = f"""Eres experto en adaptar contenido para el mercado {target_market}.

TAREA: Adapta el texto al público de destino.
NO lo vuelvas a traducir: ya pasó por una traducción automática.
Haz que suene más natural, reemplaza los modismos que no encajan
y adapta los ejemplos y las referencias culturales.

CONTEXTO DEL MERCADO: {context}
TIPO DE CONTENIDO: {content_type}

REGLAS ESTRICTAS:
- NO cambies las marcas "Acme Realty" y "Acme AI"
- NO cambies cifras ni estadísticas
- NO cambies los puntos clave, solo la forma de presentarlos
- Idioma de salida: {target_lang}

TEXTO PARA ADAPTAR:
{translated_text}

Devuelve SOLO el texto adaptado, sin explicaciones."""

    message = claude_client.messages.create(
        model="claude-sonnet-5-5",   # modelos vigentes: revisa la página Lo vigente
        max_tokens=16000,   # con margen a propósito: el "razonamiento" del modelo cuenta dentro de este límite
        messages=[{"role": "user", "content": prompt}]
    )
    # La respuesta puede traer bloques de "razonamiento": nos quedamos solo con el texto
    return "".join(block.text for block in message.content if block.type == "text")


def generate_seo_metadata(content: str, target_lang: str,
                           target_market: str) -> dict:
    """
    Claude Haiku genera los metadatos SEO para el mercado local.
    Es más barato que Sonnet y suficiente para una tarea estructurada.
    """
    prompt = f"""Con base en este contenido, genera metadatos SEO para el mercado {target_market}.

CONTENIDO (primeros 1,500 caracteres):
{content[:1500]}

Devuelve JSON:
{{
  "title": "hasta 60 caracteres, con la palabra clave",
  "meta_description": "hasta 155 caracteres",
  "h1": "el encabezado principal de la página",
  "keywords": ["palabra1", "palabra2", "palabra3", "palabra4", "palabra5"],
  "og_title": "para Open Graph (hasta 70 caracteres)",
  "og_description": "para Open Graph (hasta 200 caracteres)"
}}

Idioma: {target_lang}
Toma en cuenta lo que la gente del mercado {target_market} realmente busca.
Devuelve SOLO el JSON, nada más."""

    message = claude_client.messages.create(
        model="claude-haiku-4-5",   # revisa que el modelo siga disponible en la API
        max_tokens=512,
        messages=[{"role": "user", "content": prompt}]
    )
    text = "".join(block.text for block in message.content if block.type == "text")
    try:
        return json.loads(text)
    except json.JSONDecodeError:
        return {"raw": text}


def run_translation_pipeline(source_file: Path, source_lang: str,
                              targets: list[dict]) -> dict:
    """
    El flujo completo: traduce un archivo a varios idiomas.

    El parámetro targets es una lista de diccionarios:
    [
        {"lang": "ES", "market": "ecuador", "output": "article.es.md"},
        {"lang": "PT-BR", "market": "brazil", "output": "article.pt.md"},
    ]
    """
    source_text = source_file.read_text(encoding="utf-8")
    results = {}

    for target in targets:
        lang = target["lang"]
        market = target["market"]
        output_path = Path(target.get("output", f"output.{lang.lower()}.md"))

        print(f"  → {lang} para {market}...")

        # 1. Glosario
        glossary_id = create_deepl_glossary(source_lang, lang)

        # 2. Traducción automática
        raw_translation = translate_with_deepl(
            source_text,
            target_lang=lang,
            source_lang=source_lang,
            glossary_id=glossary_id
        )

        # 3. Adaptación cultural
        adapted = adapt_culturally(
            raw_translation,
            target_lang=lang,
            target_market=market,
            content_type="real_estate_marketing"
        )

        # 4. Metadatos SEO
        seo_meta = generate_seo_metadata(adapted, lang, market)

        # 5. Guardar los archivos (también la traducción de DeepL antes de adaptarla: sirve para compararla con el resultado)
        output_path.write_text(adapted, encoding="utf-8")
        output_path.with_suffix(".deepl.md").write_text(raw_translation, encoding="utf-8")
        meta_path = output_path.with_suffix(".meta.json")
        meta_path.write_text(
            json.dumps(seo_meta, ensure_ascii=False, indent=2),
            encoding="utf-8"
        )

        results[lang] = {
            "content": str(output_path),
            "meta": str(meta_path),
            "chars": len(source_text),
            "market": market
        }
        print(f"  ✅ {lang} listo: {output_path}")

    return results


# Ejemplo de uso
if __name__ == "__main__":
    results = run_translation_pipeline(
        source_file=Path("article-en.md"),
        source_lang="EN",
        targets=[
            {"lang": "ES", "market": "ecuador", "output": "article-es.md"},
            {"lang": "PT-BR", "market": "brazil", "output": "article-pt.md"},
        ]
    )

    print("\n📊 Resultados:")
    for lang, info in results.items():
        print(f"  {lang}: {info['content']} + {info['meta']}")
```

---

### El glosario: el sistema inmune de tu marca contra las malas traducciones

🎨 **Imagínalo así:** un abogado redacta un contrato en inglés que usa el término "escrow". El traductor pone "depósito en garantía", que técnicamente es correcto. Pero un cliente en América Latina está acostumbrado a la palabra "fideicomiso". Una palabra, un trato perdido.

**Categorías de términos para tu glosario:**

| Categoría | Ejemplos | Regla |
|---|---|---|
| Marcas | Acme Realty, Acme AI | Nunca se traducen |
| Legales | fideicomiso, plusvalía, promesa de compraventa | Usa el término del mercado local |
| Técnicos | API, MCP, dashboard, ROI | Se dejan igual, o con una traducción entre paréntesis |
| De producto | "apartment" = "departamento" (Ecuador) | Depende del país |
| De marketing | El eslogan de la marca | Tradúcelo a mano con anticipación |

---

### Un ejemplo de adaptación cultural: se nota la diferencia

**Original (EN):**
> "Putting your money into an apartment is as safe as keeping it in an FDIC-insured savings account."

**Después de DeepL (ES):**
> "Invertir dinero en un apartamento es tan seguro como tenerlo en una cuenta de ahorros asegurada por la FDIC."

**El problema:** un lector en América Latina no tiene idea de qué es la FDIC (es la agencia de Estados Unidos que asegura los depósitos bancarios).

**Después de Claude (adaptación cultural, Ecuador):**
> "Invertir en un departamento en Cuenca es tan sólido como tener dólares en el Banco del Pacífico, sin riesgo de devaluación."

El cambio: la desconocida FDIC → el conocido Banco del Pacífico. Se agregó relevancia local: Ecuador usa el dólar estadounidense, así que no hay riesgo de devaluación, un argumento importante para este mercado.

⚠️ Este ejemplo muestra cómo la traducción adapta las referencias, no cómo escribir un anuncio real. Los bienes raíces no están libres de riesgo, y compararlos con un depósito bancario asegurado puede considerarse una afirmación de inversión engañosa en muchos países. En un texto real, describe la propiedad y no prometas seguridad.

---

### Un caso práctico: Acme Realty, EN → ES → PT

Lo que pasa por el flujo:

1. **Artículos de blog**: unos 5 al mes, de unas 1,500 palabras (10,000 caracteres) cada uno
2. **Fichas de propiedades**: descripciones de departamentos y casas en 3 idiomas
3. **Boletines por correo**: un resumen semanal en 3 idiomas
4. **Metadatos de las páginas**: título, descripción y palabras clave para cada idioma
5. **Plantillas para WhatsApp y mensajes de texto**: mensajes de bienvenida y de seguimiento

**Costo mensual (solo los artículos):**

- Volumen: unos 100,000 caracteres (5 artículos × 2 idiomas de destino × 10,000 caracteres)
- DeepL (la primera traducción): pagas según los planes de DeepL; con este volumen, compara el nivel gratis con los planes de pago en la página de precios de DeepL
- Claude (adaptación): por token. El código de esta lección adapta todo el texto; para gastar menos, adapta solo las páginas que importan
- **Total:** normalmente mucho menos que pagarle a un traductor freelance para traducir todo desde cero. Las tarifas dependen del mercado y del idioma, así que haz tus propias cuentas.

Precios y versiones vigentes: [Lo vigente](https://aimayak.com/now/).

---

### Cuándo DeepL es más barato que Claude, y cuándo es al revés

🎨 **Imagínalo así:** DeepL es la línea automatizada de una fábrica. Claude es el maestro artesano. Para piezas en serie, usas la línea. Para piezas únicas, al artesano. Una fábrica inteligente usa los dos.

| Escenario | Recomendación | Costo relativo |
|---|---|---|
| Descripciones de producto en volumen (más de 50K caracteres al mes) | DeepL + Claude para adaptar las páginas que importan | bajo |
| Textos de marketing | Claude directamente | por token de Claude |
| Documentos legales | DeepL + revisión de un profesional | más alto: necesita la revisión de un experto |
| Textos técnicos con términos especializados | DeepL con un glosario | de bajo a medio |
| Contenido creativo, publicaciones de blog | Claude directamente | por token de Claude |

**Regla práctica:** texto estándar y estructurado → DeepL. Texto que tiene que sonar escrito por una persona → Claude.

⚠️ **Los documentos oficiales siguen siendo trabajo de personas.** Los trámites migratorios, los escritos para un juzgado, las actas de nacimiento y de matrimonio, los títulos y los certificados de estudios normalmente necesitan una traducción certificada: un traductor humano firma una declaración de que la traducción es completa y fiel. Usa la IA para entender qué dice un documento o para preparar preguntas para tu traductor, no para producir la versión que vas a entregar. La dependencia, el juzgado o la escuela que pide la traducción pone las reglas, así que revisa primero sus requisitos. Y antes de pegar en cualquier herramienta en línea un documento con números de identificación oficial, de pasaporte o de cuentas bancarias, tacha esos números.

---

## Práctica

**Sin código.** Traduce un mensaje real con el prompt de la sección "Sin código", pídele a Claude que traduzca el resultado de vuelta al español y revisa el sentido. Terminaste cuando la traducción de vuelta dice lo que querías decir y corregiste las frases que Claude marcó como ambiguas. Los pasos 1 a 4 de abajo son para quienes construyen: necesitan Claude Code y una terminal.

### Paso 1: Consigue una clave de API de DeepL y configura el MCP (5 min)

1. Regístrate en [deepl.com/pro-api](https://www.deepl.com/en/pro-api): hay un nivel gratis para empezar (revisa en el sitio de DeepL el volumen y las condiciones)
2. Copia tu clave de API: está en tu cuenta de DeepL, en la sección de claves (deepl.com/your-account/keys)
3. Agrega el servidor a `.mcp.json` (mira el código en la sección de Teoría)
4. Define la clave como variable de entorno en la terminal desde la que inicias Claude Code: `export DEEPL_API_KEY="tu-clave"` (en PowerShell de Windows: `$env:DEEPL_API_KEY="tu-clave"`). No pongas la clave en sí dentro de `.mcp.json`
5. Reinicia Claude Code, aprueba el servidor deepl cuando Claude Code te lo pida y pídele: "traduce 'Hello, world' al español con DeepL"

**Cómo saber que funcionó:** Claude usa el MCP de DeepL y te devuelve una traducción.

### Paso 2: Arma un glosario para tu proyecto (5 min)

```bash
pip install deepl anthropic
```

Guarda el código del flujo de la sección de Teoría como `translation_pipeline.py`. Anota tus términos en `glossary.json`; es tu lista de trabajo:

```json
{
  "brand_names": ["Acme Realty", "Acme AI"],
  "do_not_translate": ["API", "MCP", "dashboard", "ROI", "CRM"],
  "market_specific": {
    "ecuador_es": {
      "apartment": "departamento",
      "real estate": "bienes raíces"
    }
  }
}
```

Luego pasa los términos al diccionario `GLOSSARY_TERMS` del script: la función `create_deepl_glossary()` los lee de ahí. Lo vas a comprobar en el siguiente paso: el nombre de tu marca no debe cambiar en la traducción.

### Paso 3: Corre el flujo con un texto real (10 min)

1. Toma cualquier artículo o descripción de propiedad en inglés (al menos 500 palabras) y guárdalo junto al script como `test-article.en.md`
2. Define tu clave de Anthropic en la misma terminal: `export ANTHROPIC_API_KEY="..."`. Luego guarda el código de abajo como `run_test.py` y córrelo con `python run_test.py`:

```python
from pathlib import Path
from translation_pipeline import run_translation_pipeline

results = run_translation_pipeline(
    source_file=Path("test-article.en.md"),
    source_lang="EN",
    targets=[
        {"lang": "ES", "market": "ecuador", "output": "test-article-es.md"},
    ]
)
```

3. Compara tres versiones: el original, la traducción de DeepL (`test-article-es.deepl.md`) y el texto después de la adaptación de Claude (`test-article-es.md`)
4. Fíjate en qué cambió la adaptación cultural

### Paso 4: Metadatos SEO para cada idioma (5 min)

Abre el archivo `test-article-es.meta.json` del paso anterior. Revisa:

- Título: ¿hasta 60 caracteres, con la palabra clave?
- Meta descripción: ¿hasta 155 caracteres?
- Palabras clave: ¿lo que la gente local realmente busca, no una traducción palabra por palabra?

Si algo no cuadra, ajusta el prompt en `generate_seo_metadata()`.

---

## Herramientas y recursos

- **[API de DeepL](https://www.deepl.com/en/pro-api)**: traducción sólida para idiomas europeos, incluidos el español y el portugués, con un nivel gratis
- **[DeepL MCP](https://github.com/DeepL/deepl-mcp-server)**: la integración oficial para Claude Code
- **[python-deepl](https://pypi.org/project/deepl/)**: el SDK oficial para Python
- **[Google Cloud Translation](https://cloud.google.com/translate)**: una enorme cantidad de idiomas, buena para los poco comunes
- **[Claude Sonnet](https://console.claude.com)**: adaptación cultural y contenido creativo
- **[Crowdin](https://crowdin.com)**: trabajo de traducción en equipo y memoria de traducción, precios en el sitio
- **[Lokalise](https://lokalise.com)**: i18n para productos SaaS, precios en el sitio
- **[i18next](https://i18next.com)**: i18n para apps de JavaScript/React, gratis

**Herramientas recomendadas para un pequeño negocio:**
El nivel gratis de DeepL → un plan de pago cuando crezca tu volumen + Claude para la adaptación + el script de Python de esta lección.

---

## Ideas clave

> La traducción automática traduce palabras. Claude traduce el sentido. DeepL lo hace rápido y barato como primer paso; Claude lo hace sonar natural como segundo paso.

> Un glosario es el sistema inmune de tu marca en la traducción. Una sola mala traducción del nombre de un producto o de un término legal te puede costar la confianza de todo un mercado.

> Tokens y un plan de DeepL en lugar de pagarle a un freelance por cada traducción no es solo un ahorro; es otra forma de trabajar. Aun así, todo lo importante muéstraselo a alguien que hable el idioma.

> Los documentos oficiales son la excepción: cuando una dependencia o un juzgado pide una traducción certificada, la hace un traductor humano.

---

## Siguiente lección

→ [Generadores de imágenes con IA](18c-ai-image-generation-pipeline.md): empieza el módulo de imágenes, video y música: qué generador de imágenes elegir para cada tarea

Opcional, en la biblioteca: [IA en apps de mensajería](76-ai-messengers.md): Slack, Microsoft Teams, WhatsApp y más. Bots inteligentes que responden a los clientes, avisan de operaciones y controlan el acceso a chats grupales privados.
