# Встречи с AI — Otter.ai, Fireflies и автоматические протоколы

**Модуль:** Communications AI | **Время:** ~20 мин теории + 30 мин практики

---

## Суть урока

45 минут разговора с клиентом. Потом ещё 30 минут — написать протокол, разослать задачи, обновить CRM. При пяти встречах в неделю это 2.5 часа бюрократии. Каждый раз. Эти часы можно вернуть. Otter.ai записывает, Fireflies анализирует, Claude структурирует, ClickUp получает задачи, Telegram уведомляет тебя — и всё это пока ты ещё прощаешься с клиентом.

🎨 **Образ:** Представь идеального секретаря, который не пропускает ни слова, не устаёт, не просит отпуск и отправляет готовый протокол ещё до того, как ты закрыл ноутбук. Это не фантастика — это webhook + Claude + ClickUp.

---

## Ключевые концепции

- **Автоматическая транскрипция** — AI в реальном времени распознаёт речь и разделяет спикеров
- **Speaker Diarization** — система знает кто что сказал, даже при десяти участниках
- **Action Item Extraction** — Claude находит обязательства, дедлайны и задачи в потоке разговора
- **Webhook-пайплайн** — цепочка: транскрипция → анализ → задачи → уведомление
- **Local Whisper** — локальная транскрипция без отправки данных в облако (для NDA-встреч)
- **Meeting Templates** — разные промпты для разных типов встреч: продажи, ревью, стендап
- **Zoom AI Companion vs Fireflies** — когда встроенный инструмент достаточен, когда нужен внешний

---

## Теория

### Проблема: встреча без системы — деньги выброшенные дважды

Средняя деловая встреча — 50 минут. После неё предприниматель тратит 20–40 минут на протокол, рассылку задач и обновление CRM. При 5 встречах в неделю — 2–3 часа чистого времени в никуда.

Хуже того: ручные протоколы неточны. Ты фокусируешься на разговоре и пропускаешь детали. Или наоборот — пишешь заметки и теряешь нить разговора. Это ловушка внимания.

AI-транскрипция решает радикально: запись ведётся параллельно, никто ничего не пропускает.

---

### Otter.ai — транскрипция в реальном времени

Otter.ai — один из первопроходцев рынка. Интегрируется с Zoom, Google Meet и Microsoft Teams как бот-участник. Подключается автоматически при старте встречи.

**Что умеет:**

- Транскрипция в реальном времени с разделением спикеров
- AI Summary после встречи: структурированный итог, не просто текст
- Action Items: задачи с именем ответственного и дедлайном
- Полнотекстовый поиск по всем транскрипциям (нашёл что-то через месяц — не проблема)
- Интеграции с рабочими инструментами (список смотри на сайте)
- MCP-сервер для подключения к AI-ассистентам (на платных тарифах)

**Тарифы (на октябрь 2026):** Free — 300 минут в месяц. Pro — \$8,33 в месяц при оплате за год (\$16,99 помесячно), 1 200 минут. Важно: русского языка нет в списке поддерживаемых, поэтому для русскоязычных встреч нужен другой сервис (например, Fireflies). Актуально: [Актуальное сейчас](https://aimayak.com/ru/now/).

🎨 **Образ:** Otter.ai — стенографист, который сидит на каждой встрече и в реальном времени печатает всё что слышит. Только он не устаёт и стоит недорого (ошибки в расшифровке всё равно проверяй).

---

### Fireflies.ai — транскрипция + аналитика + CRM-интеграция

Fireflies идёт дальше Otter: не просто записывает, но и глубоко анализирует.

**Дополнительно к транскрипции** (по описанию сервиса, проверь на своём тарифе):

- **AI Summary** — структурированный итог: что обсуждали, что решили, что осталось открытым
- **Speaker Analytics** — кто говорил сколько времени, кто доминировал
- **Sentiment Analysis** — тональность разговора (позитивная / нейтральная / тревожная)
- **Topic Tracker** — отслеживает упоминание ключевых тем (бюджет, конкуренты, сроки)
- **CRM Push** — автоматически отправляет summary в HubSpot, Salesforce, Pipedrive
- **Webhooks** — отправляет данные на любой endpoint после завершения встречи

Именно вебхуки делают Fireflies центром нашего пайплайна.

**Тарифы (на октябрь 2026):** Free, Pro, Business и Enterprise; лимиты и цены смотри на fireflies.ai, доступность API и вебхуков зависит от тарифа. Русский язык поддерживается (60+ языков, автоопределение).

**Согласие на запись:** запись встречи требует согласия участников, правила зависят от страны. Предупреждай о записи в начале звонка.

---

### Zoom AI Companion vs Fireflies — когда что выбирать

| Критерий | Zoom AI Companion | Fireflies.ai |
|---|---|---|
| Стоимость | Входит в платные тарифы Zoom без доплаты (проверь свой тариф) | Отдельная подписка (есть бесплатный тариф) |
| Интеграция | Нативная внутри Zoom | Работает с Zoom, Meet, Teams |
| CRM sync | Ограниченно | HubSpot, Salesforce, Pipedrive |
| Webhooks | Через Zoom API (отдельная настройка) | ✅ — ключевая функция (зависит от тарифа) |
| Custom промпты | Ограниченно | ✅ — для каждого типа встречи |
| Анализ конкурентов в речи | — | ✅ Topic Tracker |
| Лучше для | Команды на Zoom | Кастомный пайплайн + CRM |

**Вывод:** Zoom AI Companion достаточен если тебе нужен только summary. Fireflies нужен когда ты строишь автоматический пайплайн задач → CRM → уведомления.

---

### Microsoft Teams — корпоративный контекст

Если твои клиенты — корпорации, они работают в Teams. Два варианта:

**Copilot в Teams** (встроенный): Summary, Action Items, ответы на вопросы о содержании встречи. Требует Microsoft 365 Copilot лицензию (цены на октябрь 2026: Copilot Business от $18 в месяц за пользователя при оплате за год, до 31.12.2026, или $25,20 помесячно). Для тебя как фрилансера — только если ты сам платишь.

**Fireflies + Teams**: Fireflies подключается к Teams как внешний бот. Все возможности Fireflies + вебхуки остаются. Лучший выбор если ты работаешь с корпоративными клиентами на Teams но хочешь сохранить свой пайплайн.

---

### Local Whisper — для конфиденциальных встреч

Для полной приватности — данные не должны покидать твой компьютер — используй OpenAI Whisper локально. Open-source, работает офлайн.

```bash
pip install openai-whisper
# Ускорение на Mac Apple Silicon:
pip install mlx-whisper
```

```python
import whisper

# small/medium/large — баланс скорость/качество/RAM
model = whisper.load_model("medium")

result = model.transcribe(
    "meeting_recording.mp3",
    language="ru",          # принудительно русский (точнее)
    word_timestamps=True    # временные метки для каждого слова
)

print(result["text"])
```

**Когда использовать Local Whisper:**

- Юридические переговоры
- Встречи с NDA
- Финансовые данные клиентов
- Любые встречи с чувствительными данными

Качество немного уступает Otter/Fireflies, но для большинства бизнес-задач — достаточно.

Без кода: MacWhisper на Mac работает локально на моделях Whisper и Parakeet, поддерживает 100+ языков, русский включён.

---

### Шаблоны промптов для разных типов встреч

Один промпт не подходит для всего. Discovery call и технический ревью — разные задачи.

**Discovery Call (первая встреча с клиентом):**

```
Проанализируй транскрипцию discovery call. Извлеки:
1. Боли и проблемы клиента (цитаты из разговора)
2. Бюджет и сроки (если упоминались)
3. Лицо принимающее решение (ЛПР)
4. Возражения и сомнения
5. Следующие шаги с обеих сторон
6. Вероятность сделки (Low/Medium/High) с обоснованием

Формат: JSON с этими полями.
```

**Client Review (работа с текущим клиентом):**

```
Проанализируй транскрипцию встречи с клиентом. Извлеки:
1. Статус проекта — что сделано, что нет
2. Замечания и правки клиента (дословно)
3. Приоритеты на следующий период
4. Риски и блокеры
5. Задачи для нашей команды (ответственный + дедлайн)
6. Задачи для клиента (ответственный + дедлайн)
```

**Team Standup:**

```
Проанализируй стендап. Для каждого участника:
- Что сделано вчера
- Что планируется сегодня
- Блокеры и вопросы к команде

Общие action items с ответственными.
```

---

### Webhook-пайплайн: от встречи до задачи в ClickUp

🎨 **Образ:** Если встреча — это производство, то webhook — это конвейер после. Деталь (транскрипция) выезжает с одного станка → проходит контроль качества (Claude) → поступает на склад (ClickUp) → уведомляет прораба (Telegram).

```
Zoom/Meet встреча
      ↓
Fireflies записывает и транскрибирует
      ↓
Fireflies отправляет webhook на твой сервер (только id встречи)
      ↓
Python Flask — забирает транскрипцию через GraphQL API Fireflies
      ↓
Claude API — анализирует по шаблону, создаёт JSON
      ↓
ClickUp API — создаёт задачи автоматически
      ↓
Telegram Bot — отправляет сводку тебе
```

**Код webhook-сервера (схему запросов Fireflies сверяй с docs.fireflies.ai):**

```python
from flask import Flask, request, jsonify
import anthropic
import requests
import json
import os

app = Flask(__name__)

claude_client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])
FIREFLIES_API_KEY = os.environ["FIREFLIES_API_KEY"]
CLICKUP_API_KEY = os.environ["CLICKUP_API_KEY"]
CLICKUP_LIST_ID = os.environ["CLICKUP_LIST_ID"]
TELEGRAM_BOT_TOKEN = os.environ["TELEGRAM_BOT_TOKEN"]
TELEGRAM_CHAT_ID = os.environ["TELEGRAM_CHAT_ID"]

MEETING_PROMPT = """
Ты ассистент, который анализирует транскрипции деловых встреч.

Транскрипция:
{transcript}

Название встречи: {meeting_title}
Участники: {participants}

Извлеки структурированную информацию в JSON:
{{
  "summary": "Краткое резюме 3–5 предложений",
  "decisions": ["решение 1", "решение 2"],
  "action_items": [
    {{
      "description": "Описание задачи",
      "assignee": "Имя ответственного или 'Не определён'",
      "deadline": "Срок или 'Не указан'",
      "priority": "Высокий|Средний|Низкий"
    }}
  ],
  "open_questions": ["вопрос 1", "вопрос 2"]
}}
"""


TRANSCRIPT_QUERY = """
query Transcript($transcriptId: String!) {
  transcript(id: $transcriptId) {
    title
    participants
    sentences {
      text
      speaker_name
    }
  }
}
"""


def fetch_transcript(meeting_id: str) -> dict:
    """Webhook Fireflies присылает только id встречи: текст забираем через GraphQL API."""
    response = requests.post(
        "https://api.fireflies.ai/graphql",
        headers={"Authorization": f"Bearer {FIREFLIES_API_KEY}"},
        json={"query": TRANSCRIPT_QUERY, "variables": {"transcriptId": meeting_id}},
        timeout=60,
    )
    response.raise_for_status()
    transcript = response.json()["data"]["transcript"]
    text = "\n".join(
        f"{s['speaker_name']}: {s['text']}" for s in transcript["sentences"]
    )
    return {
        "title": transcript["title"],
        "participants": transcript["participants"],
        "text": text,
    }


def analyze_meeting(transcript: str, title: str,
                    participants: list) -> dict:
    """Анализируем транскрипцию через Claude."""
    participants_str = ", ".join(participants) if participants else "Неизвестны"

    message = claude_client.messages.create(
        model="claude-sonnet-5-5",  # актуальные идентификаторы моделей: документация Anthropic
        max_tokens=2048,
        messages=[{
            "role": "user",
            "content": MEETING_PROMPT.format(
                transcript=transcript,
                meeting_title=title,
                participants=participants_str
            )
        }]
    )

    response_text = message.content[0].text
    # Убираем markdown code blocks если есть
    if "```json" in response_text:
        start = response_text.find("```json") + 7
        end = response_text.find("```", start)
        response_text = response_text[start:end].strip()

    return json.loads(response_text)


def create_clickup_task(task_data: dict, meeting_title: str) -> str:
    """Создаём задачу в ClickUp."""
    priority_map = {"Высокий": 1, "Средний": 2, "Низкий": 3}

    payload = {
        "name": task_data["description"],
        "description": f"Источник: встреча '{meeting_title}'\n"
                       f"Ответственный: {task_data['assignee']}",
        "priority": priority_map.get(task_data["priority"], 2),
    }

    response = requests.post(
        f"https://api.clickup.com/api/v2/list/{CLICKUP_LIST_ID}/task",
        headers={
            "Authorization": CLICKUP_API_KEY,
            "Content-Type": "application/json"
        },
        json=payload
    )
    if response.status_code == 200:
        return response.json().get("url", "")
    return ""


def send_telegram_summary(analysis: dict, meeting_title: str,
                           task_urls: list) -> None:
    """Отправляем сводку в Telegram."""
    tasks_text = ""
    priority_emoji = {"Высокий": "🔴", "Средний": "🟡", "Низкий": "🟢"}

    for item, url in zip(analysis["action_items"], task_urls):
        emoji = priority_emoji.get(item["priority"], "⚪")
        tasks_text += f"{emoji} {item['description']}\n"
        tasks_text += f"   → {item['assignee']} | {item['deadline']}"
        if url:
            tasks_text += f" | [Задача]({url})"
        tasks_text += "\n\n"

    open_q = "\n".join(f"• {q}" for q in analysis["open_questions"])

    message = f"""📋 *{meeting_title}*

📝 *Резюме:*
{analysis['summary']}

✅ *Задачи ({len(analysis['action_items'])}):*
{tasks_text}
❓ *Открытые вопросы:*
{open_q}""".strip()

    requests.post(
        f"https://api.telegram.org/bot{TELEGRAM_BOT_TOKEN}/sendMessage",
        json={
            "chat_id": TELEGRAM_CHAT_ID,
            "text": message,
            "parse_mode": "Markdown",
            "disable_web_page_preview": True
        }
    )


@app.route("/webhook/fireflies", methods=["POST"])
def fireflies_webhook():
    """Принимаем webhook от Fireflies после завершения встречи."""
    data = request.json or {}

    # Webhook содержит только метаданные: meetingId и eventType
    if data.get("eventType") != "Transcription completed":
        return jsonify({"status": "skip", "reason": "other event"}), 200

    meeting = fetch_transcript(data["meetingId"])
    title = meeting["title"] or "Встреча без названия"
    transcript = meeting["text"]
    participants = meeting["participants"] or []

    if not transcript:
        return jsonify({"status": "skip", "reason": "no transcript"}), 200

    # 1. Анализ через Claude
    analysis = analyze_meeting(transcript, title, participants)

    # 2. Задачи в ClickUp
    task_urls = [
        create_clickup_task(item, title)
        for item in analysis.get("action_items", [])
    ]

    # 3. Уведомление в Telegram
    send_telegram_summary(analysis, title, task_urls)

    return jsonify({
        "status": "processed",
        "tasks_created": len(task_urls),
        "meeting": title
    }), 200


if __name__ == "__main__":
    app.run(port=5000, debug=False)
```

**Деплой:** Railway, Render или другой хостинг для Python (цены смотри на сайтах провайдеров). Проверяй подлинность запросов к webhook (в документации Fireflies смотри, поддерживается ли подпись запроса).

---

### ROI: математика автоматизации встреч

| Задача | До автоматизации | После |
|---|---|---|
| Протокол встречи | 20–40 мин | 0 мин |
| Рассылка задач команде | 10–15 мин | 0 мин |
| Обновление CRM | 5–10 мин | 0 мин |
| Итого на 1 встречу | 35–65 мин | 2 мин (проверка) |
| При 5 встречах/нед | 3–5 часов/нед | 10 мин/нед |

Подставь свою ставку: часы в месяц × стоимость твоего часа. Это и есть сумма, которая возвращается в продуктивность. Цифры в таблице условные.

Стоимость системы: подписка на сервис встреч (есть бесплатные тарифы) + расход на Claude API. По ценам Sonnet 5.5 на октябрь 2026 ($2 на вход и $10 на выход за 1 млн токенов) час встречи — это примерно 15–20 тысяч токенов на вход, то есть несколько центов на встречу (оценка, проверь на своих записях). Актуальные цены: [Актуальное сейчас](https://aimayak.com/ru/now/).

🎨 **Образ:** Ты нанимаешь ассистента по цене подписки. Он работает 24/7, не просит отпуск и делает одно хорошо — превращает встречи в конкретные задачи. Но проверяешь его работу ты.

---

## Практика

### Шаг 1: Подключи Fireflies к твоим встречам (5 мин)

1. Зарегистрируйся на [fireflies.ai](https://fireflies.ai) — Free план достаточно для старта
2. В Settings → Integrations подключи Google Calendar или Outlook
3. Fireflies автоматически будет присоединяться к твоим встречам как бот
4. Проведи тестовую встречу в Zoom или Meet (даже с самим собой)
5. Проверь: в Fireflies Dashboard появилась транскрипция и AI Summary

**Критерий успеха:** Fireflies самостоятельно записал встречу и сгенерировал Summary.

### Шаг 2: Настрой Webhook (10 мин)

1. В Fireflies открой раздел для разработчиков (Developer settings) и добавь Webhook (доступность на твоём тарифе проверь на сайте)
2. Для теста используй [webhook.site](https://webhook.site) как временный endpoint
3. Событие: `Transcription completed`
4. Проведи тестовую встречу (5–10 мин)
5. Открой webhook.site — проверь структуру полученного JSON

**Критерий успеха:** видишь JSON с полями `meetingId` и `eventType` (текст транскрипции придёт отдельным запросом к GraphQL API).

### Шаг 3: Разверни Python-сервер (10 мин)

```bash
pip install flask anthropic requests
```

Сохрани код из теории в `meeting_pipeline.py`. Установи переменные:

```bash
export ANTHROPIC_API_KEY="sk-ant-..."
export FIREFLIES_API_KEY="..."
export CLICKUP_API_KEY="pk_..."
export CLICKUP_LIST_ID="..."
export TELEGRAM_BOT_TOKEN="..."
export TELEGRAM_CHAT_ID="..."

python meeting_pipeline.py
```

Для публичного URL во время разработки:

```bash
ngrok http 5000
# Скопируй HTTPS URL → вставь в Fireflies Webhook
```

### Шаг 4: Протестируй полный пайплайн (5 мин)

Проведи 10-минутную тестовую встречу. Обсуди несколько задач с дедлайнами и ответственными. Подожди 5–10 минут после завершения. Проверь: задачи появились в ClickUp, сводка пришла в Telegram.

**Критерий успеха:** полный автоматический цикл без ручного участия.

### Шаг 5: Кастомизируй промпт под свои встречи (5 мин)

Замени `MEETING_PROMPT` на один из шаблонов из теории, который подходит твоему типу встреч. Или создай свой. Протестируй на реальной встрече — убедись что формат вывода соответствует твоим ожиданиям.

---

## Инструменты и ресурсы

- **[Fireflies](https://fireflies.ai)** — транскрипция + webhook, русский язык поддерживается, есть бесплатный тариф (условия API и вебхуков зависят от тарифа)
- **[Otter.ai](https://otter.ai)** — транскрипция в реальном времени; русского языка нет в списке поддерживаемых, есть бесплатный тариф
- **[tl;dv](https://tldv.io)** — запись встреч в Zoom, Meet и Teams, русский язык поддерживается, есть бесплатный тариф
- **[Granola](https://www.granola.ai)** — блокнот для встреч без бота; macOS, Windows, iOS и Android (на октябрь 2026)
- **[OpenAI Whisper](https://github.com/openai/whisper)** — приватная транскрипция офлайн, бесплатно
- **[mlx-whisper](https://github.com/ml-explore/mlx-examples)** — быстрый Whisper на Apple Silicon
- **[MacWhisper](https://www.macwhisper.com)** — локальная транскрипция на Mac без кода
- **[Claude API](https://platform.claude.com/docs)** — анализ транскрипций; стоимость считай по токенам ([Актуальное сейчас](https://aimayak.com/ru/now/))
- **[ClickUp API v2](https://clickup.com/api)** — создание задач
- **[ngrok](https://ngrok.com)** — тоннель для разработки, бесплатно
- **[Railway](https://railway.app)** — деплой Python-сервера, цены на сайте провайдера

---

## Ключевые выводы

> Встреча без автоматического протокола — деньги выброшенные дважды: сначала потратил время на встречу, потом ещё раз потратил на запись того, что на ней было.

> Разница между Otter/Fireflies и Local Whisper — это разница между удобством и приватностью. Для большинства встреч облако безопасно. Для переговоров с NDA — запускай Whisper локально.

> Webhook-пайплайн меняет культуру работы. Когда задачи появляются в ClickUp автоматически после каждой встречи, люди начинают серьёзнее относиться к обязательствам: слова моментально становятся записями.

---

## Следующий урок

→ [Переводы и локализация — DeepL MCP, i18n pipeline](75-ai-translation.md)

Построим систему: один контент на русском → автоматически на испанский, английский, португальский. С культурной адаптацией, глоссарием терминов и SEO-метаданными для каждого рынка.
