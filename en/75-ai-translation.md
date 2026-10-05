# AI translation and localization: DeepL and Claude

**Time:** about 20 min reading + 25 min practice

---

## The gist

One piece of content, five markets, one price. An article about the cost of living in Cuenca, Ecuador, is written in English. A few minutes later, and for pennies, it exists in Spanish for the local market and in Portuguese for investors from Brazil, with SEO metadata for each language. Not a word-for-word translation but real localization: the right terms, cultural references people recognize, the right tone.

The same skills work for everyday translation too: a reply to a Spanish-speaking customer, a note to relatives abroad, a letter from a landlord or a school that you need to understand. One thing stays a human job: official documents that need a certified translation (more on that below).

🎨 **Picture this:** you built a brick house. Handsome, solid. Now you want to sell it in five neighborhoods at once, and each neighborhood speaks a different language. It used to take five separate houses. Now it takes one house and a smart interpreter who knows how people in each neighborhood talk and what they care about.

---

## Key concepts

- **DeepL API**: a specialized translator with top quality for European and Latin American languages; many users say it sounds more natural than general-purpose translators
- **DeepL MCP**: the official DeepL integration for Claude Code, so translation becomes part of your workflow instead of a separate step (MCP is the standard way to plug outside services into Claude Code)
- **i18n pipeline** (i18n is developer shorthand for "internationalization"): an automated chain: source content → machine translation → cultural adaptation → SEO metadata
- **Glossary / term base**: a list of terms that must never be translated, or must always be translated one specific way
- **Cultural adaptation**: replacing idioms, examples and cultural references with ones the target audience understands
- **Locale-specific metadata**: a title, description and keywords for each language and market
- **DeepL vs Claude directly**: when the first is cheaper and when the second is more accurate, and how to do the math

---

## Theory

### Comparing the tools: DeepL vs Google Translate vs Claude directly

| | DeepL API | Google Translate | Claude (direct) |
|---|---|---|---|
| Quality, English → Spanish | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| Speed | Very fast | Very fast | Slow |
| Price | per DeepL's plans, with a free tier | per Google Cloud pricing | per token, depends on the model |
| Term glossary | ✅ built in | ✅ available | ⚠️ through the prompt |
| Cultural adaptation | ❌ | ❌ | ✅ the best tool for it |
| Keeps HTML/Markdown formatting | ✅ | ✅ | ⚠️ needs a prompt |
| MCP integration | ✅ official | ⚠️ check the documentation | ✅ native |
| Languages | English, Spanish and other major languages | a huge number, including rare ones | all the major ones |

The quality ratings in the table are the author's rough guide, not an independent test: try them on your own texts. Current prices and versions: [What's current](https://aimayak.com/en/now/).

**Bottom line:** DeepL for bulk translation of structured content (product listings, email templates, documents). Claude for cultural adaptation, creative writing and specialized material. Google Translate as a backup for rare languages.

---

### No code needed: everyday translation in a regular chat

Most everyday translation doesn't need a pipeline. Open Claude in your browser, paste the text and add a short prompt. It works for a reply to a customer, a message to family, or a letter you need to understand.

> Translate this message into Spanish for [who it's for: a customer in Texas, my aunt in Mexico]. Keep the tone [warm and polite / businesslike], use plain everyday Spanish, and keep names, dates, addresses and prices exactly as they are. After the translation, list any phrases that could be read two ways. Here's the text: [paste the text]

If you don't speak the target language, ask Claude to translate its own result back into English so you can check the meaning. For anything that really matters (money, health, a contract), have someone who speaks the language read it before you send it.

The rest of this lesson is for people who already use Claude Code and want to translate a lot of content on a schedule.

---

### DeepL MCP: translation inside Claude Code

DeepL has an official MCP server (the `deepl-mcp-server` package; it needs Node.js 18 or newer). Translation becomes part of your workflow, and you don't have to switch between tabs.

**Setup in `.mcp.json`:**

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

Once it's connected, Claude uses DeepL within the same session:

```
Translate the article into Spanish with DeepL,
then adapt it for readers in Ecuador.
```

Claude calls DeepL for the translation, then handles the adaptation itself, without breaking your workflow.

---

### The i18n pipeline: from one text to five markets

🎨 **Picture this:** a furniture factory. One blueprint for an armchair, five assembly lines. Each line turns out the chair adapted for its local market: a different color, different upholstery, a different height. Same chair at heart, with the details fitted to the market.

**How the pipeline flows:**

```
[Source content, EN]
        ↓
[DeepL API: fast machine translation with a glossary]
        ↓
[Claude Sonnet: cultural adaptation and tone]
        ↓
[Claude Haiku: SEO metadata for each market]
        ↓
[Files: article.en.md / article.es.md / article.pt.md]
[Metadata: article.es.meta.json / article.pt.meta.json]
```

**The full Python code for the pipeline:**

```python
import anthropic
import deepl
import json
import os
from pathlib import Path

deepl_client = deepl.Translator(os.environ["DEEPL_API_KEY"])
claude_client = anthropic.Anthropic()

# Glossary: terms that are NOT translated, or are translated one fixed way
GLOSSARY_TERMS = {
    "ES": {
        "Acme Realty": "Acme Realty",            # brand: never translate
        "Acme AI": "Acme AI",                    # service name: never translate
        "apartment": "departamento",             # in Ecuador people say "departamento"
        "real estate agency": "inmobiliaria",    # the standard local term
    },
    "PT-BR": {
        "Acme Realty": "Acme Realty",
        "Acme AI": "Acme AI",
    }
}

MARKET_CONTEXT = {
    "ecuador": (
        "Latin American market, Ecuador. "
        "Audience: local home buyers and expats who live in Ecuador. "
        "Formal but friendly tone. "
        "Emphasis on stability and long-term investment. "
        "Ecuador uses the US dollar, which is an important selling point."
    ),
    "brazil": (
        "Brazilian market. Audience: entrepreneurs and investors. "
        "Direct, concrete tone. Emphasis on ROI and numbers. "
        "Avoid excess emotion: facts only."
    ),
    "spain": (
        "Spanish market. A more formal tone than in Latin America. "
        "Use the Spanish of Spain (not Latin American Spanish). "
        "Audience: educated city dwellers."
    ),
}


def create_deepl_glossary(source_lang: str, target_lang: str) -> str | None:
    """Create a DeepL glossary to protect your terms."""
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
        return None   # A glossary with this name already exists: continue without it


def translate_with_deepl(text: str, target_lang: str,
                          source_lang: str = "EN",
                          glossary_id: str = None) -> str:
    """Fast machine translation that keeps the formatting."""
    result = deepl_client.translate_text(
        text,
        source_lang=source_lang,
        target_lang=target_lang,
        glossary=glossary_id,
        preserve_formatting=True,
        tag_handling="html"   # keep HTML tags in the text
    )
    return result.text


def adapt_culturally(translated_text: str, target_lang: str,
                     target_market: str, content_type: str = "marketing") -> str:
    """
    Claude adapts the translation for the culture.
    It doesn't translate again: it makes the text sound natural and replaces
    idioms and cultural references that don't fit.
    """
    context = MARKET_CONTEXT.get(target_market, "International audience.")

    prompt = f"""You are an expert in adapting content for the {target_market} market.

TASK: Adapt the text for the target audience.
Do NOT translate it again: it has already been machine-translated.
Make it sound more natural, replace idioms that don't fit,
and adapt the examples and cultural references.

MARKET CONTEXT: {context}
CONTENT TYPE: {content_type}

STRICT RULES:
- Do NOT change the brands "Acme Realty" and "Acme AI"
- Do NOT change numbers or statistics
- Do NOT change the key points, only how they are presented
- Output language: {target_lang}

TEXT TO ADAPT:
{translated_text}

Return ONLY the adapted text, with no explanations."""

    message = claude_client.messages.create(
        model="claude-sonnet-5-5",   # current models: see the What's current page
        max_tokens=4096,
        messages=[{"role": "user", "content": prompt}]
    )
    return message.content[0].text


def generate_seo_metadata(content: str, target_lang: str,
                           target_market: str) -> dict:
    """
    Claude Haiku generates SEO metadata for the local market.
    It's cheaper than Sonnet and good enough for a structured task.
    """
    prompt = f"""Based on this content, generate SEO metadata for the {target_market} market.

CONTENT (first 1,500 characters):
{content[:1500]}

Return JSON:
{{
  "title": "up to 60 characters, with the keyword",
  "meta_description": "up to 155 characters",
  "h1": "the main page heading",
  "keywords": ["word1", "word2", "word3", "word4", "word5"],
  "og_title": "for Open Graph (up to 70 characters)",
  "og_description": "for Open Graph (up to 200 characters)"
}}

Language: {target_lang}
Take into account what people in the {target_market} market actually search for.
Return ONLY the JSON, nothing else."""

    message = claude_client.messages.create(
        model="claude-haiku-4-5",   # check that the model is still available in the API
        max_tokens=512,
        messages=[{"role": "user", "content": prompt}]
    )
    try:
        return json.loads(message.content[0].text)
    except json.JSONDecodeError:
        return {"raw": message.content[0].text}


def run_translation_pipeline(source_file: Path, source_lang: str,
                              targets: list[dict]) -> dict:
    """
    The full pipeline: translates one file into several languages.

    The targets parameter is a list of dictionaries:
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

        print(f"  → {lang} for {market}...")

        # 1. Glossary
        glossary_id = create_deepl_glossary(source_lang, lang)

        # 2. Machine translation
        raw_translation = translate_with_deepl(
            source_text,
            target_lang=lang,
            source_lang=source_lang,
            glossary_id=glossary_id
        )

        # 3. Cultural adaptation
        adapted = adapt_culturally(
            raw_translation,
            target_lang=lang,
            target_market=market,
            content_type="real_estate_marketing"
        )

        # 4. SEO metadata
        seo_meta = generate_seo_metadata(adapted, lang, market)

        # 5. Save the files
        output_path.write_text(adapted, encoding="utf-8")
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
        print(f"  ✅ {lang} done: {output_path}")

    return results


# Example usage
if __name__ == "__main__":
    results = run_translation_pipeline(
        source_file=Path("article-en.md"),
        source_lang="EN",
        targets=[
            {"lang": "ES", "market": "ecuador", "output": "article-es.md"},
            {"lang": "PT-BR", "market": "brazil", "output": "article-pt.md"},
        ]
    )

    print("\n📊 Results:")
    for lang, info in results.items():
        print(f"  {lang}: {info['content']} + {info['meta']}")
```

---

### The glossary: your brand's immune system against bad translations

🎨 **Picture this:** a lawyer drafts a contract that uses the term "escrow." The translator writes "depósito en garantía," which is technically correct. But a client in Latin America is used to the word "fideicomiso." One word, one lost deal.

**Categories of terms for your glossary:**

| Category | Examples | Rule |
|---|---|---|
| Brands | Acme Realty, Acme AI | Never translate |
| Legal | fideicomiso, plusvalía, promesa de compraventa | Use the local market's term |
| Technical | API, MCP, dashboard, ROI | Leave as is, or add a translation in parentheses |
| Product | "apartment" = "departamento" (Ecuador) | Depends on the country |
| Marketing | The brand's slogan | Translate by hand ahead of time |

---

### A cultural adaptation example: you can see the difference

**Original (EN):**
> "Putting your money into an apartment is as safe as keeping it in an FDIC-insured savings account."

**After DeepL (ES):**
> "Invertir dinero en un apartamento es tan seguro como tenerlo en una cuenta de ahorros asegurada por la FDIC."

**The problem:** a reader in Latin America has no idea what the FDIC is (it's the US agency that insures bank deposits).

**After Claude (cultural adaptation, Ecuador):**
> "Invertir en un departamento en Cuenca es tan sólido como tener dólares en el Banco del Pacífico, sin riesgo de devaluación."

The swap: the unfamiliar FDIC → the familiar Banco del Pacífico. Local relevance added: Ecuador uses the US dollar, so there's no devaluation risk, which is an important argument for this market.

⚠️ This example shows how translation adapts references, not how to write a real ad. Real estate is not risk-free, and comparing it to an insured bank deposit can count as a misleading investment claim in many countries. In real copy, describe the property and leave out safety promises.

---

### A practical case: Acme Realty, EN → ES → PT

What goes through the pipeline:

1. **Blog articles**: 3 to 5 a week, about 1,500 words each
2. **Property listings**: descriptions of apartments and houses in 3 languages
3. **Email newsletters**: a weekly digest in 3 languages
4. **Page metadata**: title, description and keywords for each language
5. **WhatsApp and text message templates**: welcome and follow-up messages

**Monthly cost:**

- Volume: about 150,000 characters (5 articles × 3 languages × 10,000 characters)
- DeepL (first-pass translation): you pay according to DeepL's plans; at this volume, compare the free tier with the paid plans on DeepL's pricing page
- Claude (adaptation, about 10% of the volume): per token, usually a small part of the budget
- **Total:** usually far less than paying a freelancer to translate everything from scratch. Rates depend on the market and the language, so run the numbers for yourself.

Current prices and versions: [What's current](https://aimayak.com/en/now/).

---

### When DeepL is cheaper than Claude, and when it's the other way around

🎨 **Picture this:** DeepL is the automated line in a factory. Claude is the master craftsman. For mass-produced parts, you use the line. For one-of-a-kind pieces, the craftsman. A smart factory uses both.

| Scenario | Recommendation | Relative cost |
|---|---|---|
| Bulk product descriptions (over 50K characters a month) | DeepL + Claude to adapt 10% | low |
| Marketing copy | Claude directly | per Claude token |
| Legal documents | DeepL + review by a professional | higher: needs an expert's review |
| Technical texts with specialized terms | DeepL with a glossary | low to medium |
| Creative content, blog posts | Claude directly | per Claude token |

**Rule of thumb:** standard structured text → DeepL. Text that has to sound like a person wrote it → Claude.

⚠️ **Official documents stay a human job.** Immigration paperwork, court filings, birth and marriage certificates, diplomas and transcripts usually need a certified translation: a human translator signs a statement that the translation is complete and accurate. Use AI to understand what a document says or to prepare questions for your translator, not to produce the version you submit. The agency, court or school that asks for the translation sets the rules, so check its requirements first. And before you paste a document with Social Security, passport or bank account numbers into any online tool, black those numbers out.

---

## Practice

### Step 1: Get a DeepL API key and set up the MCP (5 min)

1. Sign up at [deepl.com/pro-api](https://www.deepl.com/en/pro-api): there's a free tier to start with (see DeepL's site for the volume and terms)
2. Copy your API key (Account → API Keys)
3. Add it to `.mcp.json` (see the code in the Theory section)
4. Add to `.env`: `DEEPL_API_KEY=your-key`
5. Restart Claude Code → ask: "translate 'Hello, world' into Spanish with DeepL"

**Success check:** Claude uses the DeepL MCP and returns a translation.

### Step 2: Build a glossary for your project (5 min)

```bash
pip install deepl anthropic
```

Create `glossary.json`:

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

Load it with the `create_deepl_glossary()` function from the script. Test it: translate a text that includes your brand name and make sure the name didn't change.

### Step 3: Run the pipeline on a real text (10 min)

1. Take any article or property description (at least 500 words) → `test-article.en.md`
2. Run the pipeline:

```python
from pathlib import Path
results = run_translation_pipeline(
    source_file=Path("test-article.en.md"),
    source_lang="EN",
    targets=[
        {"lang": "ES", "market": "ecuador", "output": "test-article-es.md"},
    ]
)
```

3. Compare three versions: the original → after DeepL → after Claude's adaptation
4. Notice what the cultural adaptation changed

### Step 4: SEO metadata for each language (5 min)

Open the `.meta.json` file from the previous step. Check:

- Title: up to 60 characters, with the keyword?
- Meta description: up to 155 characters?
- Keywords: what local people actually search for, not a word-for-word translation?

If something's off, adjust the prompt in `generate_seo_metadata()`.

---

## Tools and resources

- **[DeepL API](https://www.deepl.com/en/pro-api)**: strong translation for European and Latin American languages, with a free tier
- **[DeepL MCP](https://github.com/DeepL/deepl-mcp-server)**: the official integration for Claude Code
- **[python-deepl](https://pypi.org/project/deepl/)**: the official Python SDK
- **[Google Cloud Translation](https://cloud.google.com/translate)**: a huge number of languages, good for rare ones
- **[Claude Sonnet](https://console.claude.com)**: cultural adaptation and creative content
- **[Crowdin](https://crowdin.com)**: team translation work and translation memory, pricing on the site
- **[Lokalise](https://lokalise.com)**: i18n for SaaS products, pricing on the site
- **[i18next](https://i18next.com)**: i18n for JavaScript/React apps, free

**Recommended stack for a small business:**
DeepL's free tier → a paid plan as your volume grows + Claude for adaptation + the Python script from this lesson.

---

## Key takeaways

> Machine translation translates words. Claude translates meaning. DeepL does it fast and cheap as step one; Claude gets it right as step two.

> A glossary is your brand's immune system in translation. One wrong translation of a product name or a legal term can cost you the trust of a whole market.

> A few dollars a month for tokens and a DeepL plan, instead of paying a freelancer for every translation, isn't just a saving; it's a different business model. You can put the money you save into marketing instead of operating costs.

> Official documents are the exception: when an agency or a court asks for a certified translation, a human translator does it.

---

## Next lesson

→ [AI in messaging apps](76-ai-messengers.md): Slack, Microsoft Teams, WhatsApp and more

We'll build smart bots: answers to customer questions, deal notifications, corporate Teams integrations and access control for private group chats.
