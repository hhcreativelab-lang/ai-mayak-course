# Полный контент-конвейер — от идеи до публикации

**Время:** ~30 мин теории + 60 мин практики

---

## Суть урока

Один человек за один рабочий день готовит материалы на неделю для пяти платформ: текст, голос, видео, расписание публикаций. Не потому что он гений. Потому что у него собран правильный конвейер. Сегодня разбираем этот конвейер по станциям: тренды → идея → текст → изображение → видео → голос → публикация. Claude выступает дирижёром, остальные инструменты — оркестрантами.

В уроке много кода. Теорию можно читать и без него: она объясняет, из каких станций состоит конвейер. В практике есть путь без программирования и путь для тех, кто уже запускает скрипты.

🎨 **Образ:** Автозавод Toyota. Ты не собираешь машину руками — нажимаешь одну кнопку, и роботы ставят колёса, красят, тестируют. На выходе — готовый автомобиль. Идея — это кузов. Claude, ElevenLabs, Runway, Buffer — роботы на конвейере. Ты — директор завода, который решает что производить.

---

## Ключевые концепции

- **Контент-фабрика** — одна управляющая программа (оркестратор) запускает всю цепочку от тренда до публикации
- **Одна идея → много форматов** — адаптация под каждую платформу без повторного написания
- **Календарь публикаций в JSON** — расписание в виде файла, который Claude читает и исполняет (JSON — простой текстовый формат, где данные записаны парами «название: значение»)
- **Параллельная генерация** — Claude, ElevenLabs, Runway работают одновременно, не последовательно
- **Петля аналитики** — показатели опубликованных материалов возвращаются в Claude, чтобы улучшить следующую партию
- **Точки одобрения** — места, где конвейер ждёт твоего «да», чтобы сырое не публиковалось само
- **Производство партиями** — 30 постов за один запуск и расчёт, сколько стоит один пост при таком объёме

---

## Теория

### Архитектура: 9 станций конвейера

Прежде чем писать код — рисуем схему. Вся фабрика состоит из 9 станций:

```
ТРЕНД → ИССЛЕДОВАНИЕ → ПЛАН → ТЕКСТ → АДАПТАЦИИ → ИЗОБРАЖЕНИЕ → ВИДЕО → ГОЛОС → ПУБЛИКАЦИЯ
```

Каждая станция — отдельное обращение к сервису через API (API, «эй-пи-ай» — способ, которым одна программа обращается к другой). Любую станцию можно заменить или отключить, не пересобирая всю систему. После публикации показатели возвращаются в начало конвейера: это петля аналитики, о ней ниже.

🎨 **Образ:** LEGO Technic. Каждый блок — отдельная деталь с понятным способом соединения. Сломался один мотор — заменяешь только его, автомобиль не разбираешь. Claude — текстовые блоки. Runway — видео. ElevenLabs — голос. Buffer — доставка.

**Роль каждой станции:**

| Станция | Инструмент | Что делает |
|---|---|---|
| Тренд | Веб-поиск + Claude | Горячие темы сегодня |
| Исследование | Claude с подключённым поиском (через MCP: так к Claude подключают внешние сервисы) | Факты, данные, источники |
| План | Claude Sonnet | Структура материала |
| Текст (основной) | Claude Sonnet | Полная статья или сценарий |
| Адаптации | Claude Haiku | Telegram, Twitter, LinkedIn |
| Изображение | gpt-image-2 / Ideogram / Nano Banana | Обложка, иллюстрации (DALL-E 3 отключён в API 12.05.2026) |
| Видео (по желанию) | Kling / Runway | Короткий ролик на несколько секунд |
| Голос (по желанию) | ElevenLabs (синтез речи из текста, по-английски TTS) | Озвучка коротких видео (Reels, Shorts) |
| Публикация | Buffer API / Telegram Bot | Планирование и отправка |

**Стоимость пакета** считай по тарифам сервисов. Для Claude порядок такой (цены за 1 млн токенов на октябрь 2026: Sonnet 5.5 — $2 на вход и $10 на выход, Haiku 4.5 — $1 и $5): статья в 1200 слов обходится в несколько центов, адаптации — в один-два цента. Изображения, видео и голос стоят по тарифам выбранных сервисов. Сводку по стеку считай по уроку [Сколько стоит набор AI-инструментов](d04-ai-stack-costs.md).

---

### Календарь публикаций в JSON: расписание, понятное программе

Календарь публикаций здесь не таблица в Excel. Это файл в формате JSON, который Claude читает и исполняет. Раз формат понятен программе, Claude может сам заполнять следующую неделю по итогам предыдущей. Ниже пример с выдуманной компанией.

```json
{
  "brand": {
    "name": "Acme Realty",
    "voice": "Дружелюбный эксперт. Не продажник. Факты + истории.",
    "audience": "Русскоязычные 35–55 лет, рассматривают переезд или инвестиции в Эквадор",
    "languages": ["ru"],
    "channels": ["telegram", "youtube", "instagram", "linkedin"]
  },
  "week": "2026-10-05",
  "posts": [
    {
      "id": "post-001",
      "publish_at": "2026-10-05T09:00:00-05:00",
      "topic": "Сколько реально стоит жизнь в Куэнке в 2026",
      "content_type": "educational",
      "formats": {
        "blog": { "words": 1200, "status": "pending" },
        "telegram": { "posts": 3, "status": "pending" },
        "youtube_script": { "duration_min": 8, "status": "pending" },
        "twitter": { "tweets": 5, "status": "pending" },
        "linkedin": { "status": "pending" }
      },
      "assets": {
        "cover_image": null,
        "short_video": null,
        "voice_over": null
      },
      "keywords": ["жизнь в Куэнке", "стоимость жизни Эквадор", "переезд Эквадор"],
      "approved": false
    }
  ]
}
```

Когда `approved` («одобрено») меняется на `true`, оркестратор запускает производство и заполняет `assets` (готовые файлы: обложка, ролик, озвучка).

---

### Одна идея → много форматов

🎨 **Образ:** Алмаз-сырец. Один камень — разные огранки: кольцо, серьги, подвеска, брошь. Суть одна, форма под каждый рынок своя.

Вот как Claude Haiku за пару центов переделывает одну основную статью под каждую платформу:

```python
import anthropic
import json
import os

claude = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])


def text_of(response) -> str:
    """Собирает текст ответа: у новых моделей перед текстом могут идти блоки «размышления»."""
    return "".join(block.text for block in response.content if block.type == "text")


def generate_main_article(topic: str, keywords: list[str],
                           brand_voice: str, word_count: int = 1200) -> str:
    """Пишет полную статью с учётом поисковых запросов (SEO) через Claude Sonnet."""
    response = claude.messages.create(
        model="claude-sonnet-5-5",  # актуальные идентификаторы моделей: документация Anthropic
        max_tokens=8000,  # с запасом: «размышления» модели тоже входят в этот лимит
        messages=[{
            "role": "user",
            "content": f"""Напиши статью для блога.

Тема: {topic}
Объём: {word_count} слов
Ключевые слова SEO: {', '.join(keywords)}
Голос бренда: {brand_voice}

Структура:
1. H1 заголовок (с главным ключевым словом)
2. Введение (150 слов, крючок + обещание)
3. 3–4 раздела H2 с конкретными фактами и цифрами
4. Практические советы (маркированный список)
5. Вывод + призыв к действию

Требования:
- Только факты, без общих слов "очень важно"
- Конкретные цифры и примеры; не выдумывай цифры: если точных данных нет, пометь место «проверить»
- Разговорный но экспертный тон
- Язык: русский, форматирование Markdown"""
        }]
    )
    return text_of(response)


def adapt_to_all_platforms(main_article: str, brand_context: str,
                            topic: str) -> dict:
    """
    Из одной базовой статьи генерирует контент для всех платформ.
    Claude Haiku — быстро и экономно (пара центов).
    """
    response = claude.messages.create(
        model="claude-haiku-4-5",  # Haiku 4.5: вывод из API возможен не раньше 15.10.2026, сверь идентификаторы в документации Anthropic
        max_tokens=6000,
        messages=[{
            "role": "user",
            "content": f"""Ты контент-стратег бренда. Бренд: {brand_context}

Основная статья на тему "{topic}":
---
{main_article}
---

Адаптируй в следующие форматы. Верни ТОЛЬКО валидный JSON, без пояснений и без тройных обратных кавычек вокруг:

{{
  "telegram_posts": [
    {{
      "text": "Пост 1 (до 1000 символов, с эмодзи, дружелюбный)",
      "delay_hours": 0
    }},
    {{
      "text": "Пост 2 — углубляет одну мысль (800 символов)",
      "delay_hours": 24
    }},
    {{
      "text": "Пост 3 — практический совет + призыв к действию (600 символов)",
      "delay_hours": 48
    }}
  ],
  "twitter_thread": [
    "Твит 1/5: крючок (до 280 символов)",
    "Твит 2/5: ключевой факт",
    "Твит 3/5: пример или история",
    "Твит 4/5: неожиданный угол",
    "Твит 5/5: вывод + ссылка"
  ],
  "linkedin_post": "LinkedIn версия (300–400 слов, деловой тон)",
  "instagram_caption": "Instagram версия (150–200 слов + 15 хэштегов)",
  "youtube_description": "Описание YouTube (300 слов, таймкоды, ключевые слова)"
}}"""
        }]
    )
    return json.loads(text_of(response))


def generate_youtube_script(topic: str, duration_minutes: int,
                              brand_voice: str) -> str:
    """Пишет сценарий видео для YouTube с временными метками."""
    words_per_minute = 130    # примерный темп речи; замерь свой и поправь
    target_words = duration_minutes * words_per_minute

    response = claude.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=8000,
        messages=[{
            "role": "user",
            "content": f"""Напиши сценарий видео для YouTube.

Тема: {topic}
Длительность: {duration_minutes} мин (~{target_words} слов)
Голос: {brand_voice}

Формат каждого блока:
[MM:SS] НАЗВАНИЕ БЛОКА
(Режиссёрская пометка: что показать на экране, какие перебивки)
Текст ведущего...

Структура:
[00:00] КРЮЧОК — первые 30 секунд, самое важное
[00:30] ВСТУПЛЕНИЕ — кто ведущий, о чём видео
[01:00] ОСНОВНАЯ ЧАСТЬ — 3–4 блока по 2–3 минуты
[{duration_minutes-1}:00] ВЫВОД — резюме + призыв к действию
[{duration_minutes-1}:30] КОНЦОВКА — подписка, следующее видео

Пиши живым разговорным языком, как будто говоришь с другом."""
        }]
    )
    return text_of(response)
```

---

### Планирование: Telegram Bot API и Buffer API

**Путь 1: Telegram Bot API** — прямая публикация, бесплатно:

```python
import asyncio
from telegram import Bot, InputFile
import os

TELEGRAM_BOT_TOKEN = os.environ["TELEGRAM_BOT_TOKEN"]
CHANNEL_ID = os.environ["TELEGRAM_CHANNEL_ID"]


async def publish_to_telegram(text: str, image_path: str = None) -> dict:
    """Публикует пост в Telegram канал."""
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


# Запуск: asyncio.run(publish_to_telegram("Тестовый пост"))
# Бот должен быть администратором канала; TELEGRAM_CHANNEL_ID — это адрес канала вида @imya_kanala
```

**Путь 2: Buffer API** — планировщик для Instagram, LinkedIn, X (Twitter). API у Buffer построен на GraphQL (это язык запросов; адрес `https://api.buffer.com`), ключ создаётся в настройках Buffer (Settings → API). Названия полей сверяй с [developers.buffer.com](https://developers.buffer.com):

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
    Планирует пост через Buffer API (GraphQL).
    due_at: время публикации в формате ISO 8601, UTC, например 2026-10-12T14:00:00.000Z
    Медиа в Buffer API передаются публичной ссылкой: см. документацию.
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

### Сценарий в n8n: автоматизация всего процесса

n8n — сервис автоматизации, в котором шаги конвейера соединяют мышкой на схеме. Исходный код открыт (лицензия Sustainable Use: для своих внутренних задач бесплатно, но это не классический открытый код), версию Community Edition можно поставить на свой сервер. Похожие сервисы: Make и Zapier. Подробнее в уроке библиотеки (по желанию): [n8n + AI — умные воркфлоу](78-n8n-ai-workflows.md).

**Базовый сценарий n8n для контент-фабрики:**

```
Запуск по расписанию (понедельник, 09:00)
  → HTTP: читаем content-calendar.json из GitHub
  → Code: фильтруем approved: true
  → Loop: для каждого поста:
    → Claude API: генерируем статью (Sonnet)
    → Claude API: адаптации платформ (Haiku) [параллельно]
    → Генерация изображения: обложка [параллельно]
    → Buffer API: планируем LinkedIn и Twitter
    → Telegram Bot: планируем 3 Telegram поста
    → Google Docs: сохраняем для финальной проверки
  → Telegram уведомление: "X постов готовы, ожидают проверки"
```

Альтернативы n8n: **Make** (бывший Integromat) и **Zapier** — облачные, с оплатой по кредитам и задачам (цены: [Актуальное сейчас](https://aimayak.com/ru/now/)); о Zapier будет отдельный урок в конце курса: [Zapier AI](79-zapier-ai.md).

---

### Оркестратор: один скрипт для всего конвейера

🎨 **Образ:** Дирижёр оркестра. Он не играет на скрипке — он управляет всем оркестром. Подаёт сигнал скрипкам (Claude), флейтам (ElevenLabs), виолончели (Runway). Каждый знает партию. Дирижёр знает симфонию.

```bash
#!/usr/bin/env bash
# content-factory-orchestrator.sh
# Запускать из папки проекта: bash content-factory-orchestrator.sh (нужна утилита jq)
set -euo pipefail

WEEK_DATE="${1:-$(date +%Y-%m-%d)}"
CALENDAR_FILE="content-calendar.json"
OUTPUT_DIR="./content-output/${WEEK_DATE}"

mkdir -p "$OUTPUT_DIR"
log() { echo "[$(date +%H:%M:%S)] $1"; }

log "🏭 Контент-фабрика запущена. Неделя: $WEEK_DATE"

POSTS=$(jq -r '.posts[] | select(.approved == true) | .id' "$CALENDAR_FILE")

if [ -z "$POSTS" ]; then
    log "⚠️ Нет одобренных постов. Останавливаюсь."
    exit 0
fi

for POST_ID in $POSTS; do
    log "▶️ Обрабатываю: $POST_ID"
    POST_DIR="${OUTPUT_DIR}/${POST_ID}"
    mkdir -p "$POST_DIR"

    TOPIC=$(jq -r ".posts[] | select(.id == \"$POST_ID\") | .topic" "$CALENDAR_FILE")
    KEYWORDS=$(jq -r ".posts[] | select(.id == \"$POST_ID\") | .keywords | join(\", \")" "$CALENDAR_FILE")
    PUBLISH_AT=$(jq -r ".posts[] | select(.id == \"$POST_ID\") | .publish_at" "$CALENDAR_FILE")

    log "  Тема: $TOPIC"

    # Статья и сценарий для YouTube параллельно
    python3 scripts/generate_article.py --topic "$TOPIC" --keywords "$KEYWORDS" \
        --output "${POST_DIR}/article.md" &
    python3 scripts/generate_script.py --topic "$TOPIC" --duration 8 \
        --output "${POST_DIR}/youtube-script.md" &

    wait

    # Адаптации и обложка параллельно
    python3 scripts/adapt_platforms.py --article "${POST_DIR}/article.md" \
        --output "${POST_DIR}/adaptations.json" &
    python3 scripts/generate_image.py --topic "$TOPIC" \
        --output "${POST_DIR}/cover.jpg" &

    wait
    log "  ✅ Контент для $POST_ID готов"

    # Планируем публикации
    python3 scripts/schedule_content.py --post-id "$POST_ID" \
        --adaptations "${POST_DIR}/adaptations.json" \
        --cover "${POST_DIR}/cover.jpg" \
        --publish-at "$PUBLISH_AT"
done

log "🎉 Готово! Постов запланировано: $(echo "$POSTS" | wc -w)"
```

---

### Петля аналитики: контент учится на результатах

```python
def run_analytics_loop(days_back: int = 7) -> dict:
    """
    Собирает метрики прошлой недели и генерирует темы на следующую.
    """
    # get_*_stats() и update_calendar_with_recommendations() здесь только названы:
    # напиши их под свои площадки (или попроси Claude)
    telegram_stats = get_telegram_stats(days_back)
    youtube_stats = get_youtube_stats(days_back)
    instagram_stats = get_instagram_stats(days_back)

    combined_stats = {
        "telegram": telegram_stats,
        "youtube": youtube_stats,
        "instagram": instagram_stats,
        "period_days": days_back,
    }

    response = claude.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=6000,
        messages=[{
            "role": "user",
            "content": f"""Ты аналитик контент-стратегии.
Проанализируй результаты за {days_back} дней:

{json.dumps(combined_stats, ensure_ascii=False, indent=2)}

Дай структурированный анализ. Верни только JSON, без пояснений и без тройных обратных кавычек вокруг:
{{
  "победители": ["пост + почему сработало"],
  "провалы": ["пост + почему не зашло"],
  "паттерны": ["какой тип контента стабильно работает"],
  "лучшее_время": {{"telegram": "HH:MM", "instagram": "HH:MM"}},
  "темы_на_следующую_неделю": ["тема 1", "тема 2", "тема 3", "тема 4", "тема 5"],
  "изменения_стратегии": ["что поменять в производственном процессе"]
}}

Используй только данные из статистики, не придумывай."""
        }]
    )

    recommendations = json.loads(text_of(response))
    update_calendar_with_recommendations(recommendations)
    return recommendations
```

---

### Что стоит конвейер: как считать

Типичный план: 5 тем/неделю × 4 недели = 20 пакетов в месяц.

| Компонент | Как считать |
|---|---|
| Claude Sonnet (статья + сценарий) | токены × цена API. Sonnet 5.5 на октябрь 2026: $2 на вход и $10 на выход за 1 млн токенов; статья в 1200 слов стоит несколько центов |
| Claude Haiku (адаптации) | Haiku 4.5: $1 на вход и $5 на выход за 1 млн токенов; пакет адаптаций стоит один-два цента |
| Изображение (обложка) | по тарифу выбранного сервиса |
| ElevenLabs (озвучка, по желанию) | кредиты тарифа |
| Видео Kling или Runway (по желанию) | кредиты за секунду видео, обычно самая дорогая строка |
| Планировщик | у Buffer и Typefully есть бесплатные тарифы для старта; платные тарифы Buffer считаются за канал, условия Typefully смотри на сайте |

Итог — сумма по тарифам. Посчитай свой вариант по формуле из урока [Сколько стоит набор AI-инструментов](d04-ai-stack-costs.md), прежде чем обещать кому-то регулярный выпуск контента.

---

## Практика

**Без программирования.** Пройди конвейер руками, это займёт около часа. Заполни одну запись календаря: тема, аудитория, ключевые слова. Скопируй текст запроса из функции `generate_main_article()`, подставь свою тему и отправь в чат Claude. Затем отправь запрос из `adapt_to_all_platforms()` вместе с готовой статьёй. Проверь факты и цифры, поправь тексты и поставь посты в очередь планировщика вручную. Так ты поймёшь весь путь, а автоматизацию добавишь позже.

**С кодом.** Шаги ниже рассчитаны на тех, кто уже запускает скрипты на Python: нужны терминал, Python и ключ API Anthropic. Часа хватит на шаги 1–5; весь конвейер из пяти скриптов собирается дольше.

### Шаг 1: Создай структуру проекта

```bash
mkdir -p content-factory/{scripts,templates,logs}
cd content-factory
touch content-calendar.json content-factory-orchestrator.sh .env \
      scripts/generate_article.py scripts/generate_script.py \
      scripts/adapt_platforms.py scripts/generate_image.py \
      scripts/schedule_content.py
```

### Шаг 2: Заполни первый пост в content-calendar.json

Скопируй JSON-шаблон из теории. Замени тему на актуальную для своего бизнеса или ниши клиента. Поставь `"approved": true` для тестового запуска.

### Шаг 3: Реализуй generate_article.py

Установи библиотеку: `pip install anthropic`. Ключ API создаётся в Claude Console (platform.claude.com) и оплачивается по токенам отдельно от подписки. Положи его в переменную окружения `ANTHROPIC_API_KEY`, а не в код. Затем возьми функцию `generate_main_article()` из теории, добавь разбор параметров `--topic`, `--keywords`, `--output` (модуль argparse) и запусти. Проверь, что статья создаётся и сохраняется в файл.

### Шаг 4: Реализуй adapt_platforms.py

Используй `adapt_to_all_platforms()`. На входе файл статьи, на выходе `adaptations.json`. Открой его и проверь посты для Telegram: они должны звучать живо, а не как машинный перевод.

### Шаг 5: Настрой публикацию в Telegram

```bash
pip install python-telegram-bot
```

Создай бота через @BotFather и добавь его администратором в свой канал. Токен бота положи в переменную окружения `TELEGRAM_BOT_TOKEN`, адрес канала (вида `@imya_kanala`) в `TELEGRAM_CHANNEL_ID`. Скопируй `publish_to_telegram()` и отправь тестовое сообщение: `asyncio.run(publish_to_telegram("Тест"))`. Убедись, что оформление Markdown работает.

### Шаг 6: Запусти оркестратор

Сохрани скрипт оркестратора из теории в файл `content-factory-orchestrator.sh` и запусти из папки проекта: `bash content-factory-orchestrator.sh`. Нужна утилита jq (ссылка в ресурсах). Оркестратор вызывает пять скриптов. Два ты собрал на шагах 3–4. Остальные три собери по тому же образцу или попроси Claude написать их по функциям из теории: `generate_script.py` из `generate_youtube_script()`, `schedule_content.py` из функций публикации, `generate_image.py` под выбранный сервис картинок. Пока какого-то скрипта нет, закомментируй его вызов в оркестраторе целиком (все строки вызова). Следи, как конвейер проходит станции. Готовые файлы появятся в `content-output/{date}/{post-id}/`. Проверь каждый файл.

### Шаг 7: Производство партией — 30 постов за день

Добавь 30 записей в content-calendar.json (все approved: true). Для пробы закомментируй в оркестраторе вызов `schedule_content.py`: пусть конвейер только готовит материалы, а ты просмотришь их перед публикацией. Это и есть точка одобрения. Запусти оркестратор и засеки время. Это твой первый опыт производства контента партией: момент, когда видна разница между ремесленником и фабрикой.

---

## Инструменты и ресурсы

- **[Anthropic API](https://platform.claude.com/docs)** — Claude Sonnet и Haiku (основа конвейера)
- **[python-telegram-bot](https://python-telegram-bot.org)** — обёртка над Telegram Bot API
- **[Buffer API](https://developers.buffer.com)** — планирование публикаций (GraphQL)
- **[Postiz](https://github.com/gitroomhq/postiz-app)** — альтернатива Buffer с открытым кодом, которую ставят на свой сервер (на октябрь 2026 проект активно развивается)
- **[n8n](https://n8n.io)** — сервис автоматизации, можно поставить на свой сервер
- **[ElevenLabs API](https://elevenlabs.io/docs/api-reference)** — синтез речи с клонированием голоса
- **[OpenAI Images](https://platform.openai.com/docs/guides/images)** — генерация обложек (модель gpt-image-2; DALL-E 2 и 3 отключены в API 12.05.2026)
- **[jq](https://jqlang.github.io/jq/)** — утилита командной строки для работы с JSON
- **[Schedule](https://schedule.readthedocs.io)** — библиотека Python для запуска задач по расписанию на своём компьютере
- **Цены и версии:** [Актуальное сейчас](https://aimayak.com/ru/now/)

---

## Ключевые выводы

> Фабрика не отдыхает. Один раз настроил конвейер, и он готовит черновики каждую неделю. Твоя работа: одобрить темы в понедельник и просмотреть готовое перед публикацией. Рутинные шаги между ними идут сами.

> Одна идея — много форматов. Не пиши шесть разных текстов под шесть платформ. Напиши один основной — Claude Haiku огранит под каждую. Несколько центов против нескольких часов ручного труда.

> Петля аналитики замыкает круг. Контент без обратной связи — стрельба вслепую. Метрики в Claude → рекомендации → новые темы → контент лучше. Каждая неделя может опираться на то, что ты узнал на прошлой.

---

## Следующий урок

→ [Лид-магниты — воронка от бесплатного материала к платной услуге](39d-lead-magnets-funnels.md)
