# Переводы и локализация — DeepL MCP, i18n pipeline

**Время:** ~20 мин теории + 25 мин практики

---

## Суть урока

Один контент → пять рынков за одну цену. Статья про стоимость жизни в Куэнке написана на русском — через несколько минут и за копейки она существует на испанском для местного рынка, на английском для международных инвесторов, с SEO-метаданными под каждый язык. Не дословный перевод, а полноценная локализация: правильные термины, понятные культурные отсылки, нужный тон.

🎨 **Образ:** Ты построил кирпичный дом. Красивый, прочный. Теперь хочешь продать его одновременно в пяти кварталах, где говорят на разных языках. Раньше — пять отдельных домов. Сейчас — один дом и умный переводчик, который знает культурный код каждого района.

---

## Ключевые концепции

- **DeepL API** — специализированный переводчик с лучшим качеством для европейских и латиноамериканских языков; по отзывам многих пользователей звучит естественнее общих переводчиков
- **DeepL MCP** — официальная интеграция DeepL в Claude Code: перевод как часть рабочего процесса, а не отдельный шаг
- **i18n pipeline** — автоматизированная цепочка: исходный контент → машинный перевод → культурная адаптация → SEO-метаданные
- **Глоссарий / term base** — база терминов, которые нельзя переводить или нужно переводить строго определённым образом
- **Культурная адаптация** — замена идиом, примеров и культурных отсылок на понятные целевой аудитории
- **Locale-specific metadata** — title, description, keywords под каждый язык и рынок
- **DeepL vs Claude напрямую** — когда первый дешевле, когда второй точнее: математика выбора

---

## Теория

### Сравнение инструментов: DeepL vs Google Translate vs Claude напрямую

| Параметр | DeepL API | Google Translate | Claude (прямой) |
|---|---|---|---|
| Качество EN→ES | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| Качество RU→ES | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| Скорость | Очень быстро | Очень быстро | Медленно |
| Цена | по тарифу DeepL, есть бесплатный уровень | по тарифу Google Cloud | по токенам, зависит от модели |
| Глоссарий терминов | ✅ встроенный | ✅ есть | ⚠️ через промпт |
| Культурная адаптация | ❌ | ❌ | ✅ лучший инструмент |
| Сохранение HTML/MD | ✅ | ✅ | ⚠️ нужен промпт |
| MCP интеграция | ✅ официальный | ⚠️ уточняйте в документации | ✅ нативно |
| Поддержка языков | русский, английский, испанский и другие основные | очень много, включая редкие | все основные |

Оценки качества в таблице — ориентир автора, а не независимый тест: проверьте на своих текстах. Актуальные цены и версии: [Актуальное сейчас](https://aimayak.com/ru/now/).

**Вывод:** DeepL — для массового перевода структурированного контента (карточки, email-шаблоны, документы). Claude — для культурной адаптации, творческих текстов, специализированных материалов. Google Translate — запасной вариант для редких языков.

---

### DeepL MCP: перевод внутри Claude Code

У DeepL есть официальный MCP-сервер (пакет `deepl-mcp-server`, нужен Node.js 18 или новее). Перевод становится частью рабочего процесса, не нужно переключаться между вкладками.

**Установка в .mcp.json:**

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

После подключения Claude использует DeepL в рамках одной сессии:

```
Переведи статью через DeepL на испанский,
затем адаптируй под аудиторию Эквадора.
```

Claude вызовет DeepL для перевода, потом сам займётся адаптацией — без разрыва рабочего процесса.

---

### i18n Pipeline: от одного текста к пяти рынкам

🎨 **Образ:** Завод по производству мебели. Один чертёж кресла — пять сборочных линий. Каждая выдаёт кресло с адаптацией под локальный рынок: другой цвет, другая обивка, другая высота. Суть одна, детали под рынок.

**Схема pipeline:**

```
[Исходный контент RU]
        ↓
[DeepL API — быстрый машинный перевод с глоссарием]
        ↓
[Claude Sonnet — культурная адаптация и тональность]
        ↓
[Claude Haiku — SEO-метаданные под каждый рынок]
        ↓
[Файлы: article.ru.md / article.es.md / article.en.md]
[Метаданные: article.es.meta.json / article.en.meta.json]
```

**Полный Python-код pipeline:**

```python
import anthropic
import deepl
import json
import os
from pathlib import Path

deepl_client = deepl.Translator(os.environ["DEEPL_API_KEY"])
claude_client = anthropic.Anthropic()

# Глоссарий: термины которые НЕ переводятся или переводятся строго
GLOSSARY_TERMS = {
    "ES": {
        "Acme Realty": "Acme Realty",           # бренд — не переводить
        "Acme AI": "Acme AI",                    # название сервиса — не переводить
        "apartamento": "departamento",            # в Эквадоре говорят "departamento"
        "inmobiliaria": "inmobiliaria",           # риелтор — не трогать
    },
    "EN-US": {
        "Acme Realty": "Acme Realty",
        "Acme AI": "Acme AI",
    }
}

MARKET_CONTEXT = {
    "ecuador": (
        "Латиноамериканский рынок, Эквадор. "
        "Аудитория: русскоязычные эмигранты и местные покупатели недвижимости. "
        "Формальный, но дружелюбный тон. "
        "Акцент на стабильности и долгосрочной инвестиции. "
        "Эквадор использует доллар США — это важный аргумент."
    ),
    "us": (
        "Американский рынок. Аудитория: предприниматели и инвесторы. "
        "Прямой, конкретный тон. Акцент на ROI и числах. "
        "Избегай излишних эмоций — только факты."
    ),
    "spain": (
        "Испанский рынок. Более формальный тон, чем в Латамерике. "
        "Используй испанский стандарт (не латиноамериканский). "
        "Аудитория: образованные городские жители."
    ),
}


def create_deepl_glossary(source_lang: str, target_lang: str) -> str | None:
    """Создаём глоссарий в DeepL для защиты терминов."""
    terms = GLOSSARY_TERMS.get(target_lang, {})
    if not terms:
        return None

    try:
        glossary = deepl_client.create_glossary(
            name=f"mayak-{source_lang}-{target_lang}-{hash(str(terms)) % 10000}",
            source_lang=source_lang,
            target_lang=target_lang,
            entries=terms
        )
        return glossary.glossary_id
    except deepl.DeepLException:
        return None   # Глоссарий с таким именем уже существует — продолжаем без него


def translate_with_deepl(text: str, target_lang: str,
                          source_lang: str = "RU",
                          glossary_id: str = None) -> str:
    """Быстрый машинный перевод с сохранением форматирования."""
    result = deepl_client.translate_text(
        text,
        source_lang=source_lang,
        target_lang=target_lang,
        glossary=glossary_id,
        preserve_formatting=True,
        tag_handling="html"   # сохраняем HTML-теги в тексте
    )
    return result.text


def adapt_culturally(translated_text: str, target_lang: str,
                     target_market: str, content_type: str = "marketing") -> str:
    """
    Claude адаптирует перевод культурно.
    Не переводит заново — улучшает естественность и заменяет
    неуместные идиомы и культурные отсылки.
    """
    context = MARKET_CONTEXT.get(target_market, "Международная аудитория.")

    prompt = f"""Ты эксперт по культурной адаптации контента для рынка {target_market}.

ЗАДАЧА: Адаптируй текст для целевой аудитории.
НЕ переводи заново — текст уже переведён машинно.
Улучши естественность, замени неуместные идиомы,
адаптируй примеры и культурные отсылки.

КОНТЕКСТ РЫНКА: {context}
ТИП КОНТЕНТА: {content_type}

СТРОГИЕ ПРАВИЛА:
- Бренды "Acme Realty" и "Acme AI" — НЕ менять
- Числа и статистику — НЕ менять
- Ключевые тезисы — НЕ менять, только форму подачи
- Язык вывода: {target_lang}

ТЕКСТ ДЛЯ АДАПТАЦИИ:
{translated_text}

Верни ТОЛЬКО адаптированный текст без пояснений."""

    message = claude_client.messages.create(
        model="claude-sonnet-5-5",   # актуальные модели: страница «Актуальное сейчас»
        max_tokens=4096,
        messages=[{"role": "user", "content": prompt}]
    )
    return message.content[0].text


def generate_seo_metadata(content: str, target_lang: str,
                           target_market: str) -> dict:
    """
    Claude Haiku генерирует SEO-метаданные под локальный рынок.
    Дешевле Sonnet, для структурированной задачи достаточно.
    """
    prompt = f"""На основе этого контента сгенерируй SEO-метаданные для рынка {target_market}.

КОНТЕНТ (первые 1500 символов):
{content[:1500]}

Верни JSON:
{{
  "title": "до 60 символов, с ключевым словом",
  "meta_description": "до 155 символов",
  "h1": "основной заголовок страницы",
  "keywords": ["слово1", "слово2", "слово3", "слово4", "слово5"],
  "og_title": "для Open Graph (до 70 символов)",
  "og_description": "для Open Graph (до 200 символов)"
}}

Язык: {target_lang}
Учитывай локальные поисковые запросы для рынка {target_market}.
Верни ТОЛЬКО JSON, без других слов."""

    message = claude_client.messages.create(
        model="claude-haiku-4-5",   # проверьте, что модель ещё доступна в API
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
    Полный pipeline перевода одного файла в несколько языков.

    Параметр targets — список словарей:
    [
        {"lang": "ES", "market": "ecuador", "output": "article.es.md"},
        {"lang": "EN-US", "market": "us", "output": "article.en.md"},
    ]
    """
    source_text = source_file.read_text(encoding="utf-8")
    results = {}

    for target in targets:
        lang = target["lang"]
        market = target["market"]
        output_path = Path(target.get("output", f"output.{lang.lower()}.md"))

        print(f"  → {lang} для {market}...")

        # 1. Глоссарий
        glossary_id = create_deepl_glossary(source_lang, lang)

        # 2. Машинный перевод
        raw_translation = translate_with_deepl(
            source_text,
            target_lang=lang,
            source_lang=source_lang,
            glossary_id=glossary_id
        )

        # 3. Культурная адаптация
        adapted = adapt_culturally(
            raw_translation,
            target_lang=lang,
            target_market=market,
            content_type="real_estate_marketing"
        )

        # 4. SEO-метаданные
        seo_meta = generate_seo_metadata(adapted, lang, market)

        # 5. Сохраняем файлы
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
        print(f"  ✅ {lang} готов: {output_path}")

    return results


# Пример использования
if __name__ == "__main__":
    results = run_translation_pipeline(
        source_file=Path("article-ru.md"),
        source_lang="RU",
        targets=[
            {"lang": "ES", "market": "ecuador", "output": "article-es.md"},
            {"lang": "EN-US", "market": "us", "output": "article-en.md"},
        ]
    )

    print("\n📊 Результат:")
    for lang, info in results.items():
        print(f"  {lang}: {info['content']} + {info['meta']}")
```

---

### Глоссарий: иммунная система бренда от неверного перевода

🎨 **Образ:** Юрист написал договор. Там используется термин "escrow". Переводчик пишет "условное депонирование" — технически верно. Но клиент в Латинской Америке привык к слову "fideicomiso". Одно слово — потерянная сделка.

**Категории терминов для глоссария:**

| Категория | Примеры | Правило |
|---|---|---|
| Бренды | Acme Realty, Acme AI | Не переводить никогда |
| Юридические | fideicomiso, plusvalía, promesa de compraventa | Использовать локальный термин рынка |
| Технические | API, MCP, dashboard, ROI | Оставить или дать перевод в скобках |
| Продуктовые | "квартира" = "departamento" (Эквадор) | Зависит от страны |
| Маркетинговые | Слоган бренда | Перевести вручную заранее |

---

### Пример культурной адаптации: разница видна наглядно

**Оригинал (RU):**
> "Вложить деньги в квартиру — надёжно, как вклад в Сбербанке."

**После DeepL (ES):**
> "Invertir dinero en un apartamento es tan confiable como un depósito en Sberbank."

**Проблема:** Латиноамериканский читатель не знает что такое Сбербанк.

**После Claude (культурная адаптация, Эквадор):**
> "Invertir en un departamento en Cuenca es tan sólido como tener dólares en el Banco del Pacífico — sin riesgo de devaluación."

Замена: незнакомый Сбербанк → знакомый Banco del Pacífico. Добавлена местная актуальность: Эквадор использует доллар, нет девальвации — важный аргумент для рынка.

---

### Практический кейс: Acme Realty RU → ES → EN

Что переводится в пайплайне:

1. **Статьи блога** — 3–5 штук в неделю, ~1500 слов каждая
2. **Карточки объектов** — описания квартир и домов на 3 языка
3. **Email-рассылки** — еженедельный дайджест на 3 языка
4. **Метаданные страниц** — title, description, keywords для каждого языка
5. **WhatsApp/Telegram шаблоны** — приветственные и follow-up сообщения

**Стоимость в месяц:**

- Объём: ~150 000 символов (5 статей × 3 языка × 10 000 символов)
- DeepL (первичный перевод): платите по тарифу; при таком объёме сравните бесплатный уровень и платные тарифы на странице DeepL
- Claude (адаптация, ~10% объёма): по токенам, обычно это небольшая часть бюджета
- **Итого:** на порядок меньше, чем у фрилансера: ставки зависят от рынка и языка, посчитайте для себя

Актуальные цены и версии: [Актуальное сейчас](https://aimayak.com/ru/now/).

---

### Когда DeepL дешевле Claude, а когда наоборот

🎨 **Образ:** DeepL — автоматическая линия на заводе. Claude — мастер-ремесленник. Для массовых деталей — линия. Для уникальных изделий — мастер. Умный завод использует обоих.

| Сценарий | Рекомендация | Относительная стоимость |
|---|---|---|
| Массовые описания товаров (>50K символов/мес) | DeepL + Claude для адаптации 10% | низкая |
| Маркетинговые тексты | Claude напрямую | по токенам Claude |
| Юридические документы | DeepL + профессиональная ревизия | выше: нужна ревизия специалиста |
| Технические тексты с терминологией | DeepL с глоссарием | низкая–средняя |
| Творческий контент, блог | Claude напрямую | по токенам Claude |

**Правило большого пальца:** типовой структурированный текст → DeepL. Текст должен звучать как написанный человеком → Claude.

---

## Практика

### Шаг 1: Получи DeepL API ключ и настрой MCP (5 мин)

1. Зарегистрируйся на [deepl.com/pro-api](https://www.deepl.com/en/pro-api) — для старта есть бесплатный уровень (объём и условия смотри на сайте DeepL)
2. Скопируй API ключ (раздел Account → API Keys)
3. Добавь в `.mcp.json` (см. код из теории)
4. Добавь в `.env`: `DEEPL_API_KEY=your-key`
5. Перезапусти Claude Code → попроси: "переведи 'Привет мир' на испанский через DeepL"

**Критерий успеха:** Claude использует DeepL MCP и возвращает перевод.

### Шаг 2: Создай глоссарий для своего проекта (5 мин)

```bash
pip install deepl anthropic
```

Создай `glossary.json`:

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

Загрузи через функцию `create_deepl_glossary()` из скрипта. Протестируй: переведи текст с брендовым именем — убедись, что оно не изменилось.

### Шаг 3: Запусти pipeline на реальном тексте (10 мин)

1. Возьми любую статью или описание объекта (минимум 500 слов) → `test-article.ru.md`
2. Запусти pipeline:

```python
from pathlib import Path
results = run_translation_pipeline(
    source_file=Path("test-article.ru.md"),
    source_lang="RU",
    targets=[
        {"lang": "ES", "market": "ecuador", "output": "test-article-es.md"},
    ]
)
```

3. Сравни три версии: оригинал → после DeepL → после адаптации Claude
4. Обрати внимание на что изменила культурная адаптация

### Шаг 4: SEO-метаданные для каждого языка (5 мин)

Открой `.meta.json` файл из результата предыдущего шага. Проверь:

- Title — до 60 символов, есть ключевое слово?
- Meta description — до 155 символов?
- Keywords — локальные запросы, а не дословный перевод?

Если что-то не так — скорректируй промпт в `generate_seo_metadata()`.

---

## Инструменты и ресурсы

- **[DeepL API](https://www.deepl.com/en/pro-api)** — сильный перевод для европейских и латиноамериканских языков, есть бесплатный уровень
- **[DeepL MCP](https://github.com/DeepL/deepl-mcp-server)** — официальная интеграция в Claude Code
- **[python-deepl](https://pypi.org/project/deepl/)** — официальная Python SDK
- **[Google Cloud Translation](https://cloud.google.com/translate)** — очень много языков, подходит для редких
- **[Claude Sonnet](https://console.claude.com)** — культурная адаптация и творческий контент
- **[Crowdin](https://crowdin.com)** — командная работа с переводами и память переводов, тарифы на сайте
- **[Lokalise](https://lokalise.com)** — i18n для SaaS-продуктов, тарифы на сайте
- **[i18next](https://i18next.com)** — i18n для JavaScript/React приложений, бесплатно

**Рекомендованный стек для малого бизнеса:**
бесплатный уровень DeepL → платный тариф при росте объёма + Claude для адаптации + Python-скрипт из этого урока.

---

## Ключевые выводы

> Машинный перевод переводит слова. Claude переводит смысл. DeepL делает это быстро и дёшево как первый шаг, Claude делает это правильно как второй шаг.

> Глоссарий — иммунная система бренда в переводах. Один неверный перевод названия продукта или юридического термина может уничтожить доверие целого рынка.

> Несколько долларов в месяц на токены и тариф DeepL вместо оплаты каждого перевода у фрилансера — это не просто экономия, а смена модели. Сэкономленное можно направить в продвижение, а не в операционные расходы.

---

## Следующий урок

→ [AI в мессенджерах](76-ai-messengers.md) — Telegram, Slack, WhatsApp и Microsoft Teams

Построим умных ботов: ответы на вопросы клиентов, уведомления о сделках, корпоративные интеграции Teams и управление доступом к закрытым чатам.
