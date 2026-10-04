# Полный контент-конвейер — от идеи до публикации

**Модуль:** Content Factory AI | **Время:** ~30 мин теории + 60 мин практики

---

## Суть урока

Один человек за один рабочий день производит контент (контент — медиа-материалы) -план на неделю для пяти платформ — текст, голос, видео, расписание публикаций. Не потому что он гений. Потому что у него собран правильный конвейер. Сегодня собираем этот конвейер вместе: тренды → идея → текст → изображение → голос → видео → публикация. Claude выступает дирижёром, остальные инструменты — оркестрантами.

🎨 **Образ:** Автозавод Toyota. Ты не собираешь машину руками — нажимаешь одну кнопку, и роботы ставят колёса, красят, тестируют. На выходе — готовый автомобиль. Идея — это кузов. Claude, ElevenLabs, Runway, Buffer — роботы на конвейере. Ты — директор завода, который решает что производить.

---

## Ключевые концепции

- **Контент-фабрика** — единый оркестратор запускает всю цепочку от тренда до публикации
- **Одна идея → много форматов** — адаптация под каждую платформу без повторного написания
- **Content Calendar как JSON** — машиночитаемое расписание, которое Claude понимает и исполняет
- **Параллельная генерация** — Claude, ElevenLabs, Runway работают одновременно, не последовательно
- **Analytics Loop (петля аналитики)** — метрики опубликованного контента возвращаются в Claude для оптимизации следующей партии
- **Checkpoint система** — точки одобрения, чтобы не публиковать сырое автоматически
- **Батчевое производство** — 30 постов за один запуск; юнит-экономика при масштабе

---

## Теория

### Архитектура: 9 станций конвейера

Прежде чем писать код — рисуем схему. Вся фабрика состоит из 9 станций:

```
ТРЕНД → ИССЛЕДОВАНИЕ → OUTLINE → ТЕКСТ → АДАПТАЦИИ → ИЗОБРАЖЕНИЕ → ГОЛОС → РАСПИСАНИЕ → АНАЛИТИКА
```

Каждая станция — отдельный API (эй-пи-ай — интерфейс программирования)-вызов. Каждая может быть заменена или отключена без пересборки всей системы.

🎨 **Образ:** LEGO Technic. Каждый блок — отдельная деталь с чётким интерфейсом. Сломался один мотор — заменяешь только его, автомобиль не разбираешь. Claude — текстовые блоки. Runway — видео. ElevenLabs — голос. Buffer — доставка.

**Роль каждой станции:**

| Станция | Инструмент | Что делает |
|---|---|---|
| Тренд | Веб-поиск + Claude | Горячие темы сегодня |
| Исследование | Claude + MCP-инструменты (поиск, документация) | Факты, данные, источники |
| Outline | Claude Sonnet | Структура материала |
| Текст (основной) | Claude Sonnet | Полная статья / скрипт |
| Адаптации | Claude Haiku | Telegram, Twitter, LinkedIn |
| Изображение | gpt-image-2 / Ideogram / Nano Banana | Обложка, иллюстрации (DALL-E 3 отключён в API 12.05.2026) |
| Видео (опц.) | Kling / Runway | Короткое видео 5–15 сек |
| Голос (опц.) | ElevenLabs (TTS — ти-ти-эс, Text-to-Speech, синтез речи из текста) | Озвучка для Reels/Shorts |
| Публикация | Buffer API / Telegram Bot | Планирование и отправка |

**Стоимость пакета** считай по тарифам сервисов. Для Claude порядок такой (цены за 1 млн токенов на октябрь 2026: Sonnet 5.5 — $2 на вход и $10 на выход, Haiku 4.5 — $1 и $5): статья в 1200 слов обходится в несколько центов, адаптации — в один-два цента. Изображения, видео и голос стоят по тарифам выбранных сервисов. Сводку по стеку считай по уроку [Сколько стоит набор AI-инструментов](d04-ai-stack-costs.md).

---

### Content Calendar как JSON: машиночитаемое расписание

Контент-календарь — не таблица в Excel. Это JSON-файл, который Claude читает и исполняет. Машиночитаемый формат означает что Claude может сам заполнять следующую неделю на основе аналитики предыдущей.

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

Когда `approved` меняется на `true` — оркестратор запускает производство и заполняет `assets`.

---

### Одна идея → много форматов

🎨 **Образ:** Алмаз-сырец. Один камень — разные огранки: кольцо, серьги, подвеска, брошь. Суть одна, форма под каждый рынок своя.

Вот как Claude Haiku делает мультиплатформенную адаптацию из одной основной статьи за пару центов:

```python
import anthropic
import json
import os

claude = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])


def generate_main_article(topic: str, keywords: list[str],
                           brand_voice: str, word_count: int = 1200) -> str:
    """Генерирует полную SEO-оптимизированную статью через Claude Sonnet."""
    response = claude.messages.create(
        model="claude-sonnet-5-5",  # актуальные идентификаторы моделей: документация Anthropic
        max_tokens=4000,
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
- Конкретные цифры и примеры
- Разговорный но экспертный тон
- Язык: русский, форматирование Markdown"""
        }]
    )
    return response.content[0].text


def adapt_to_all_platforms(main_article: str, brand_context: str,
                            topic: str) -> dict:
    """
    Из одной базовой статьи генерирует контент для всех платформ.
    Claude Haiku — быстро и экономно (пара центов).
    """
    response = claude.messages.create(
        model="claude-haiku-4-5",  # Haiku 4.5: вывод из API возможен не раньше 15.10.2026, сверь идентификаторы в документации Anthropic
        max_tokens=3000,
        messages=[{
            "role": "user",
            "content": f"""Ты контент-стратег бренда. Бренд: {brand_context}

Основная статья на тему "{topic}":
---
{main_article}
---

Адаптируй в следующие форматы. Верни ТОЛЬКО валидный JSON:

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
      "text": "Пост 3 — практический совет + CTA (600 символов)",
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
    return json.loads(response.content[0].text)


def generate_youtube_script(topic: str, duration_minutes: int,
                              brand_voice: str) -> str:
    """Генерирует скрипт для YouTube видео с временными метками."""
    words_per_minute = 130    # средний темп речи на русском
    target_words = duration_minutes * words_per_minute

    response = claude.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=5000,
        messages=[{
            "role": "user",
            "content": f"""Напиши скрипт для YouTube видео.

Тема: {topic}
Длительность: {duration_minutes} мин (~{target_words} слов)
Голос: {brand_voice}

Формат каждого блока:
[MM:SS] НАЗВАНИЕ БЛОКА
(Режиссёрская пометка: показать на экране / B-roll)
Текст ведущего...

Структура:
[00:00] ХУКИ — первые 30 секунд, самое важное
[00:30] ВСТУПЛЕНИЕ — кто ведущий, о чём видео
[01:00] ОСНОВНАЯ ЧАСТЬ — 3–4 блока по 2–3 минуты
[{duration_minutes-1}:00] ВЫВОД — резюме + CTA
[{duration_minutes-1}:30] OUTRO — подписка, следующее видео

Пиши живым разговорным языком, как будто говоришь с другом."""
        }]
    )
    return response.content[0].text
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
```

**Путь 2: Buffer API** — планировщик для Instagram, LinkedIn, Twitter/X. API у Buffer построен на GraphQL (адрес `https://api.buffer.com`), ключ создаётся в настройках Buffer; на бесплатном тарифе доступен один ключ. Схема перестраивалась в 2026 году, поэтому поля сверяй с [developers.buffer.com](https://developers.buffer.com):

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

### n8n workflow: автоматизация всего процесса

n8n — платформа автоматизации, которая позволяет связать все компоненты конвейера визуально. Исходный код открыт (лицензия Sustainable Use, fair-code), Community Edition можно развернуть на своём сервере и использовать для внутренних задач бесплатно. Аналог Make и Zapier. Подробнее: [n8n + AI — умные воркфлоу](78-n8n-ai-workflows.md).

**Базовый n8n workflow для контент-фабрики:**

```
Cron (Понедельник 09:00)
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

Альтернативы n8n: **Make** (бывший Integromat) и **Zapier** — облачные, с оплатой по кредитам и задачам (цены: [Актуальное сейчас](https://aimayak.com/ru/now/)); подробнее: [Zapier AI](79-zapier-ai.md).

---

### Оркестратор: bash-скрипт для всего конвейера

🎨 **Образ:** Дирижёр оркестра. Он не играет на скрипке — он управляет всем оркестром. Подаёт сигнал скрипкам (Claude), флейтам (ElevenLabs), виолончели (Runway). Каждый знает партию. Дирижёр знает симфонию.

```bash
#!/usr/bin/env bash
# content-factory-orchestrator.sh
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

    # Статья и скрипт YouTube параллельно
    python3 generate_article.py --topic "$TOPIC" --keywords "$KEYWORDS" \
        --output "${POST_DIR}/article.md" &
    python3 generate_script.py --topic "$TOPIC" --duration 8 \
        --output "${POST_DIR}/youtube-script.md" &

    wait

    # Адаптации и обложка параллельно
    python3 adapt_platforms.py --article "${POST_DIR}/article.md" \
        --output "${POST_DIR}/adaptations.json" &
    python3 generate_image.py --topic "$TOPIC" \
        --output "${POST_DIR}/cover.jpg" &

    wait
    log "  ✅ Контент для $POST_ID готов"

    # Планируем публикации
    python3 schedule_content.py --post-id "$POST_ID" \
        --adaptations "${POST_DIR}/adaptations.json" \
        --cover "${POST_DIR}/cover.jpg" \
        --publish-at "$PUBLISH_AT"
done

log "🎉 Готово! Постов запланировано: $(echo "$POSTS" | wc -w)"
```

---

### Analytics Loop: контент учится на результатах

```python
def run_analytics_loop(days_back: int = 7) -> dict:
    """
    Собирает метрики прошлой недели и генерирует темы на следующую.
    """
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
        max_tokens=2000,
        messages=[{
            "role": "user",
            "content": f"""Ты аналитик контент-стратегии.
Проанализируй результаты за {days_back} дней:

{json.dumps(combined_stats, ensure_ascii=False, indent=2)}

Дай структурированный анализ в JSON:
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

    recommendations = json.loads(response.content[0].text)
    update_calendar_with_recommendations(recommendations)
    return recommendations
```

---

### Что стоит конвейер: как считать

Типичный план: 5 тем/неделю × 4 недели = 20 пакетов в месяц.

| Компонент | Как считать |
|---|---|
| Claude Sonnet (статья + скрипт) | токены × цена API. Sonnet 5.5 на октябрь 2026: $2 на вход и $10 на выход за 1 млн токенов; статья в 1200 слов стоит несколько центов |
| Claude Haiku (адаптации) | Haiku 4.5: $1 на вход и $5 на выход за 1 млн токенов; пакет адаптаций стоит один-два цента |
| Изображение (обложка) | по тарифу выбранного сервиса |
| ElevenLabs (озвучка, опц.) | кредиты тарифа |
| Видео Kling или Runway (опц.) | кредиты за секунду видео, обычно самая дорогая строка |
| Планировщик | у Buffer и Typefully есть бесплатные тарифы для старта; платные считаются за канал |

Итог — сумма по тарифам. Посчитай свой вариант по формуле из урока [Сколько стоит набор AI-инструментов](d04-ai-stack-costs.md), прежде чем обещать кому-то регулярный выпуск контента.

---

## Практика

### Шаг 1: Создай структуру проекта

```bash
mkdir -p content-factory/{scripts,templates,output,logs}
cd content-factory
touch content-calendar.json scripts/generate_article.py \
      scripts/adapt_platforms.py scripts/schedule_content.py .env
```

### Шаг 2: Заполни первый пост в calendar.json

Скопируй JSON-шаблон из теории. Замени тему на актуальную для своего бизнеса или ниши клиента. Поставь `"approved": true` для тестового запуска.

### Шаг 3: Реализуй generate_article.py

Используй функцию `generate_main_article()` из теории. Добавь argparse для `--topic`, `--keywords`, `--output`. Запусти — проверь что статья генерируется и сохраняется в файл.

### Шаг 4: Реализуй adapt_platforms.py

Используй `adapt_to_all_platforms()`. Вход — файл статьи, выход — `adaptations.json`. Открой JSON, проверь Telegram-посты — они должны звучать живо, не как машинный перевод.

### Шаг 5: Настрой публикацию в Telegram

```bash
pip install python-telegram-bot
```

Создай бота через @BotFather. Скопируй `publish_to_telegram()`. Отправь тестовое сообщение в свой канал — убедись что форматирование Markdown работает.

### Шаг 6: Запусти оркестратор

Запусти `content-factory-orchestrator.sh`. Наблюдай в реальном времени как конвейер проходит станции. Итоговые файлы будут в `output/{date}/{post-id}/`. Проверь каждый файл.

### Шаг 7: Батчевое производство — 30 постов за день

Добавь 30 записей в calendar.json (все approved: true). Запусти оркестратор и засеки время. Это твой первый опыт масштабного производства контента — тот самый момент, когда понимаешь разницу между ремесленником и фабрикой.

---

## Инструменты и ресурсы

- **[Anthropic API](https://platform.claude.com/docs)** — Claude Sonnet и Haiku (основа конвейера)
- **[python-telegram-bot](https://python-telegram-bot.org)** — обёртка над Telegram Bot API
- **[Buffer API](https://developers.buffer.com)** — планирование публикаций (GraphQL)
- **[Postiz](https://github.com/gitroomhq/postiz-app)** — open-source альтернатива Buffer, self-hosted (проверь актуальность проекта)
- **[n8n](https://n8n.io)** — оркестратор workflow, можно развернуть на своём сервере
- **[ElevenLabs API](https://elevenlabs.io/docs/api-reference)** — TTS с клонированием голоса
- **[OpenAI Images](https://platform.openai.com/docs/guides/images)** — генерация обложек (модель gpt-image-2; DALL-E 2 и 3 отключены в API 12.05.2026)
- **[jq](https://jqlang.github.io/jq/)** — CLI-утилита для работы с JSON в bash
- **[Schedule](https://schedule.readthedocs.io)** — Python cron-like для локальных запусков
- **Цены и версии:** [Актуальное сейчас](https://aimayak.com/ru/now/)

---

## Ключевые выводы

> Фабрика не отдыхает. Один раз настроил конвейер — он производит контент каждую неделю. Ты только одобряешь темы по понедельникам. Остальное — автоматически.

> Одна идея — много форматов. Не пиши шесть разных текстов под шесть платформ. Напиши один основной — Claude Haiku огранит под каждую. Несколько центов против нескольких часов ручного труда.

> Analytics Loop закрывает петлю. Контент без обратной связи — стрельба вслепую. Метрики в Claude → рекомендации → новые темы → лучший контент. Каждая неделя умнее предыдущей.

---

## Следующий урок

→ [AI-коммуникации — умные email, автодрафты, AI-переписка](73-ai-email-communications.md)
