# AI в переписке — умная почта, черновики писем, ответы с помощью AI

**Модуль:** Communications AI | **Время:** ~20 мин теории + 30 мин практики

---

## Суть урока

Профессионалы тратят на email заметную часть дня (проверь по своему трекеру времени). Это не потому что писем много — это потому что каждое письмо требует думать: что ответить, как сформулировать, как не забыть. Claude берёт на себя это мышление. Ты остаёшься принимать решения.

Не "AI вместо тебя" — а AI как фильтр и черновик. Ты всё равно нажимаешь "Отправить". Но тратишь на это в разы меньше времени.

🎨 **Образ:** AI-email ассистент — как пресс-секретарь президента. Президент не пишет каждый ответ сам. Пресс-секретарь знает его позицию, стиль, что он никогда не скажет. Готовит текст. Президент читает, правит пару слов, подписывает. Власть и решения остаются у президента — его время освобождено.

---

## Ключевые концепции

- **Gmail MCP** — Claude читает inbox, классифицирует письма, составляет черновики прямо в Claude Code
- **Автодрафт** — черновик ответа в твоём стиле: ты одобряешь, не пишешь
- **Inbox Zero workflow** — утром Claude обрабатывает всё, ты получаешь приоритизированный список
- **Apollo / Hunter.io** — инструменты для нахождения нужных email-адресов и cold outreach
- **Lemlist** — автоматические follow-up последовательности
- **Email sequence** — цепочка писем от регистрации до сделки, генерируется один раз

---

## Теория

### Зачем AI для email: считаем время (условный пример)

Типичный день:

- 80 входящих писем
- Из них 20 требуют ответа
- Каждый ответ: 5-7 минут на обдумывание + написание
- Итого: 100-140 минут = 1.5-2.5 часа

С AI:

- Claude читает всё, классифицирует: срочное / ожидает ответа / информационное / спам
- Для 20 писем, требующих ответа, составляет черновики
- Ты читаешь черновики, правишь 20% из них, одобряешь
- Итого: 25-30 минут

В этом условном примере экономия 1.5-2 часа в день. Подставь свои цифры.

---

### Gmail MCP — Claude читает твой inbox

Gmail подключается к Claude разными способами. После подключения Claude может читать письма, искать по критериям, составлять черновики ответов. Ты пишешь в Claude как будто разговариваешь с ассистентом.

**Способы подключения (на октябрь 2026):**

- **Коннектор Gmail / Google Workspace в настройках Claude** (на платных тарифах): самый простой путь. Какие действия доступны, смотри в справке Claude.
- **Официальный MCP-сервер Gmail от Google** (Google Workspace Developer Preview). По документации Google он ищет письма и треды, читает сообщения, создаёт черновики и ставит ярлыки; отправки писем в списке возможностей нет. Нужны проект в Google Cloud, OAuth-клиент и тариф Claude с поддержкой своих коннекторов.
- **Сторонние MCP-серверы и хабы** (например, Composio): удобно, но доступ к почте получает третья сторона. Проверь права, репутацию и политику хранения данных.

**Принцип доступа:** давай минимальные права (чтение и черновики), отправку оставь себе.

```
# Официальный сервер Gmail от Google подключается как custom connector в Claude:
# Settings → Connectors → Add custom connector
# Remote MCP server URL: https://gmailmcp.googleapis.com/mcp/v1
# OAuth Client ID и Secret создаются в Google Cloud Console
# (инструкция: developers.google.com/workspace/gmail/api/guides/configure-mcp-server)
```

После подключения — команды в Claude:

```
Проверь мой inbox. Найди все письма за последние 3 дня
которые требуют ответа от меня. Классифицируй их:
- Срочные (нужен ответ сегодня)
- Обычные (ответ в течение 3 дней)
- FYI (информация, ответ не нужен)

Для каждого срочного составь черновик ответа в моём стиле:
краткий, конкретный, без лишних слов.
```

Claude прочитает письма, выдаст таблицу с категориями и готовые черновики для срочных. Ты смотришь черновики, правишь где нужно, копируешь в Gmail и отправляешь.

---

### Автодрафты: CLAUDE.md для email-стиля

Чтобы черновики были похожи на тебя, а не на шаблонный корпоративный текст — описываешь свой стиль в CLAUDE.md проекта или в системном промпте.

**Пример CLAUDE.md для email-ассистента:**

```markdown
# Мой стиль email

## Общие правила
- Максимум 150 слов на ответ (если не договор или детальное ТЗ)
- Начинаю сразу с сути, без "Добрый день, надеюсь письмо застанет вас в добром здравии"
- Конкретный CTA в конце каждого письма: что ожидаю от человека и когда
- Предпочитаю списки вместо длинных абзацев

## Запрещено
- "Как я уже упоминал ранее..." — это пассивная агрессия
- "В целом", "в принципе", "по большому счёту" — размытые слова
- Несколько вопросов в одном письме (только один вопрос)

## Примеры хорошего ответа
Запрос о стоимости консультации:
"Первичная консультация — $200/час. 
Следующее окно: завтра в 15:00 или пятница в 11:00.
Подтверди удобное время и вышлю ссылку на Zoom."

## Примеры плохого ответа (не писать так)
"Добрый день! Спасибо за ваш вопрос! Я рад сообщить, что наши 
консультации доступны по различным тарифным планам..."
```

---

### Python-скрипт: автодрафт ответа

Если хочешь встроить в свою систему без MCP — прямой вызов API:

```python
import anthropic
import os

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

def draft_reply(incoming_email: str, context: str = "") -> str:
    """
    Генерирует черновик ответа на входящее письмо.
    Возвращает черновик — НЕ отправляет автоматически.
    Ты проверяешь и отправляешь сам.
    """
    response = client.messages.create(
        model="claude-sonnet-5-5",  # актуальные идентификаторы моделей: документация Anthropic
        max_tokens=500,
        system="""Ты личный email-ассистент. Пишешь ответы в следующем стиле:
        
        - Краткий и по делу: не больше 100-150 слов
        - Начинай сразу с содержания, без светских приветствий
        - В конце всегда конкретный CTA: что ожидаешь от человека и когда
        - Используй списки если есть 3+ пункта
        - Тон: профессиональный, не формальный
        
        ВАЖНО: ты предлагаешь черновик, не финальный текст.
        Никогда не добавляй подпись — владелец добавит сам.""",
        messages=[{
            "role": "user",
            "content": f"""Входящее письмо:
---
{incoming_email}
---

Дополнительный контекст для ответа: {context if context else 'нет'}

Составь черновик ответа."""
        }]
    )
    return response.content[0].text


def classify_email(email_text: str) -> dict:
    """
    Классифицирует письмо: нужен ли ответ, срочность, тип.
    Возвращает dict с классификацией.
    """
    response = client.messages.create(
        model="claude-haiku-4-5",  # Haiku — быстро и дёшево для классификации; Haiku 4.5 может быть выведена из API не раньше 15.10.2026, сверь идентификатор в документации
        max_tokens=150,
        messages=[{
            "role": "user",
            "content": f"""Классифицируй это письмо. Верни только JSON:
{{
  "needs_reply": true/false,
  "urgency": "high"/"medium"/"low",
  "type": "client_inquiry"/"follow_up"/"newsletter"/"spam"/"internal"/"other",
  "summary": "одно предложение о чём письмо"
}}

Письмо:
{email_text}"""
        }]
    )
    import json
    return json.loads(response.content[0].text)


# Пример использования
if __name__ == "__main__":
    incoming = """
    Привет! Меня интересует консультация по недвижимости в Куэнке.
    Мы с женой думаем о переезде в следующем году, хотим понять
    реальную стоимость жилья и что нужно для покупки иностранцем.
    Сколько стоит ваша консультация и когда можете?
    """
    
    # Шаг 1: классифицируем
    classification = classify_email(incoming)
    print(f"Тип: {classification['type']}")
    print(f"Срочность: {classification['urgency']}")
    print(f"Суть: {classification['summary']}")
    print(f"Нужен ответ: {classification['needs_reply']}")
    
    # Шаг 2: если нужен ответ — генерируем черновик
    if classification["needs_reply"]:
        context = "Консультация стоит $200/час. Ближайшее окно: завтра 15:00 или пятница 11:00"
        draft = draft_reply(incoming, context)
        print(f"\nЧерновик ответа:\n{'-'*40}\n{draft}")
```

---

### Apollo + Hunter.io: AI для холодных email

Apollo и Hunter.io решают задачу "найди email нужного человека". Claude превращает найденные контакты в персонализированные письма.

🎨 **Образ:** Apollo + Claude — как рыболовная сеть с умной наживкой. Сеть (Apollo) находит нужных людей. Наживка (Claude) написана лично под каждого, не шаблонно. Рыба (потенциальный клиент) клюёт охотнее.

```
# Подключение зависит от выбранного хаба или сервиса:
# формат команды и способ входа смотри в документации Apollo, Hunter или MCP-хаба.
# Ключи API не вставляй в адрес запроса: храни их в переменных окружения.
```

**Важно про холодные письма:** рассылка незнакомым людям регулируется законами о спаме и о персональных данных (основание для письма, возможность отписаться, хранение контактов). Правила разные в разных странах: проверь правила своей страны и страны получателя. Claude пишет текст, ответственность за рассылку остаётся на тебе.

После подключения — задача в Claude Code:

```
Используй Apollo. Найди 20 владельцев агентств недвижимости
в Куэнке, Эквадор. Для каждого:
1. Найди email через Hunter.io
2. Изучи их LinkedIn профиль (если есть в Apollo)
3. Напиши персонализированный cold email на испанском:
   - Упомяни что-то конкретное из их профиля или бизнеса
   - Объясни в 2 предложениях чем я могу быть полезен
   - Один конкретный вопрос в конце
   - Не больше 120 слов

Сохрани результат в CSV: имя, email, текст письма.
```

Ручная версия без MCP — через прямой вызов API:

```python
import anthropic
import requests
import os
import csv

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])
HUNTER_API_KEY = os.environ["HUNTER_API_KEY"]

def find_email(domain: str, first_name: str, last_name: str) -> str:
    """Находит email через Hunter.io по домену и имени"""
    response = requests.get(
        "https://api.hunter.io/v2/email-finder",
        params={
            "domain": domain,
            "first_name": first_name,
            "last_name": last_name,
            "api_key": HUNTER_API_KEY,
        }
    )
    data = response.json()
    if data.get("data", {}).get("email"):
        return data["data"]["email"]
    return None


def write_cold_email(
    recipient_name: str,
    company: str,
    context_about_them: str,
    language: str = "Spanish"
) -> str:
    """Генерирует персонализированный cold email"""
    
    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=300,
        system=f"""Ты пишешь персонализированные cold email на языке: {language}.
        
        Правила:
        - Максимум 120 слов
        - Упомяни конкретную деталь о человеке или компании
        - Ценность в 1-2 предложениях: что конкретно можешь дать
        - В конце один вопрос (не несколько)
        - Без шаблонных фраз "Надеюсь письмо вас застанет..."
        - Профессиональный тон, не продажный""",
        messages=[{
            "role": "user",
            "content": f"""Получатель: {recipient_name}
Компания: {company}
Что я знаю о них: {context_about_them}

Я: агент Acme Realty, помогаю русскоязычным найти недвижимость в Эквадоре.
Могу предлагать совместные сделки агентствам недвижимости.

Напиши cold email."""
        }]
    )
    return response.content[0].text


# Список контактов для outreach
contacts = [
    {
        "name": "Carlos Rodríguez",
        "company": "InmoCuenca",
        "domain": "example.com",
        "first_name": "Carlos",
        "last_name": "Rodriguez",
        "context": "Специализируются на элитной недвижимости в историческом центре"
    },
    # ... остальные контакты
]

# Генерируем письма и сохраняем в CSV
with open("cold_outreach.csv", "w", newline="", encoding="utf-8") as f:
    writer = csv.writer(f)
    writer.writerow(["Имя", "Компания", "Email", "Письмо"])
    
    for contact in contacts:
        email = find_email(
            contact["domain"],
            contact["first_name"],
            contact["last_name"]
        )
        
        if email:
            letter = write_cold_email(
                contact["name"],
                contact["company"],
                contact["context"],
                language="Spanish"
            )
            writer.writerow([contact["name"], contact["company"], email, letter])
            print(f"Готово: {contact['name']} <{email}>")
        else:
            print(f"Email не найден: {contact['name']}")

print("Сохранено в cold_outreach.csv")
```

---

### Email Sequence: от регистрации до сделки

Email sequence — цепочка писем которая отправляется автоматически после регистрации или действия пользователя. Claude пишет все письма один раз, ты настраиваешь в Lemlist (или другом сервисе рассылок) или собственном скрипте.

```
Человек оставил заявку на сайте
          |
          v
Сразу:   Welcome email
         (Claude персонализирует по данным формы: имя, откуда, интерес)
          |
          v
День 3:  Value email
         (AI выбирает контент из базы: если интерес "аренда" → статья об аренде)
          |
          v
День 7:  Case study email
         (история реального клиента похожего на этого человека)
          |
          v
День 14: Offer email
         (конкретное предложение с CTA на консультацию)
```

```python
import anthropic
import os
from datetime import datetime

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

def generate_welcome_email(
    name: str,
    interest: str,  # "аренда" / "покупка" / "инвестиции"
    city_of_origin: str
) -> str:
    """Персонализированное welcome письмо"""
    
    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=400,
        system="""Пишешь welcome email для русскоязычного человека
        который заинтересовался недвижимостью в Эквадоре.
        
        Стиль: тёплый, не официальный. Как будто пишет живой человек.
        Длина: 100-120 слов.
        Структура: приветствие → что получит дальше → один вопрос чтобы лучше помочь.""",
        messages=[{
            "role": "user",
            "content": f"""Имя: {name}
Интерес: {interest}
Откуда: {city_of_origin}

Напиши welcome email."""
        }]
    )
    return response.content[0].text


def select_value_content(interest: str, knowledge_base: dict) -> str:
    """
    Выбирает релевантный контент из базы знаний для Value email.
    knowledge_base — словарь тем → тексты статей/советов
    """
    response = client.messages.create(
        model="claude-haiku-4-5",
        max_tokens=600,
        messages=[{
            "role": "user",
            "content": f"""Человек интересуется: {interest}

Доступный контент:
{chr(10).join([f"- {topic}: {text[:100]}..." for topic, text in knowledge_base.items()])}

Выбери наиболее релевантный контент и напиши email на 120-150 слов.
Используй конкретные факты из выбранного контента."""
        }]
    )
    return response.content[0].text


# База знаний (в реальности — читается из файлов или БД; данные ниже условные, для примера)
KNOWLEDGE_BASE = {
    "аренда": "Средняя стоимость аренды в Куэнке: 1-комнатная $350-500, 2-комнатная $500-800. Лучшие районы: El Centro, Ordóñez Lasso...",
    "покупка": "Процесс покупки для иностранца: RUC → счёт в банке → promesa de compraventa → escritura. Занимает 45-90 дней...",
    "инвестиции": "Доходность аренды зависит от района и объекта; в реальной базе здесь лежат твои проверенные данные и оговорки (не инвестиционная рекомендация)...",
}

# Пример: генерируем welcome email
email = generate_welcome_email(
    name="Михаил",
    interest="покупка",
    city_of_origin="Москва"
)
print("Welcome email:")
print(email)
print()

# Value email
value_email = select_value_content("покупка", KNOWLEDGE_BASE)
print("Value email (день 3):")
print(value_email)
```

---

### Inbox Zero workflow: утренний ритуал за 20 минут

Практическая схема на каждый день:

```
07:00  Claude (через Gmail MCP или скрипт) читает все новые письма за ночь
       Классифицирует: срочное / обычное / FYI / спам
       Составляет черновики для всего что требует ответа
       
07:10  Ты открываешь сводку (файл или сообщение в Telegram)
       Видишь: 3 срочных, 8 обычных, 12 FYI
       
07:10-07:30  Просматриваешь черновики срочных писем
             Правишь если нужно (обычно 20-30% требуют правки)
             Отправляешь
             Обычные — ставишь на вечер или завтра
             FYI — архивируешь одной кнопкой
             
07:30  Inbox Zero. День начат.
```

```python
import anthropic
import os
from typing import List

client = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])

def process_inbox(emails: List[dict], your_context: str) -> dict:
    """
    Обрабатывает список писем: классифицирует и составляет черновики.
    
    emails: список dict с полями subject, sender, body, date
    your_context: описание твоей работы для Claude чтобы писать в твоём стиле
    """
    
    results = {
        "urgent": [],
        "normal": [],
        "fyi": [],
        "spam": [],
    }
    
    for email in emails:
        # Классификация
        classification_response = client.messages.create(
            model="claude-haiku-4-5",
            max_tokens=200,
            messages=[{
                "role": "user",
                "content": f"""Классифицируй письмо. Верни JSON:
{{
  "category": "urgent"/"normal"/"fyi"/"spam",
  "needs_reply": true/false,
  "summary": "одно предложение"
}}

От: {email['sender']}
Тема: {email['subject']}
Текст: {email['body'][:500]}"""
            }]
        )
        
        import json
        classification = json.loads(classification_response.content[0].text)
        category = classification["category"]
        
        email_data = {
            **email,
            "summary": classification["summary"],
            "draft": None
        }
        
        # Черновик только если нужен ответ
        if classification["needs_reply"] and category in ["urgent", "normal"]:
            draft_response = client.messages.create(
                model="claude-sonnet-5-5",
                max_tokens=300,
                system=f"""Ты email-ассистент. Контекст о владельце:
{your_context}

Стиль ответов: краткий, по делу, конкретный CTA в конце.""",
                messages=[{
                    "role": "user",
                    "content": f"""Составь черновик ответа на это письмо:

От: {email['sender']}
Тема: {email['subject']}
Текст: {email['body']}"""
                }]
            )
            email_data["draft"] = draft_response.content[0].text
        
        results[category].append(email_data)
    
    return results


def format_daily_brief(processed: dict) -> str:
    """Форматирует сводку для утреннего чтения"""
    
    lines = [
        f"Inbox сводка — {__import__('datetime').date.today()}",
        f"Срочных: {len(processed['urgent'])} | "
        f"Обычных: {len(processed['normal'])} | "
        f"FYI: {len(processed['fyi'])} | "
        f"Спам: {len(processed['spam'])}",
        "",
    ]
    
    if processed["urgent"]:
        lines.append("СРОЧНЫЕ (ответить сегодня):")
        for email in processed["urgent"]:
            lines.append(f"  От: {email['sender']}")
            lines.append(f"  Суть: {email['summary']}")
            if email["draft"]:
                lines.append(f"  Черновик:\n  {email['draft'][:200]}...")
            lines.append("")
    
    if processed["normal"]:
        lines.append("ОБЫЧНЫЕ:")
        for email in processed["normal"]:
            lines.append(f"  - {email['sender']}: {email['summary']}")
    
    return "\n".join(lines)


# Пример использования (в реальности emails приходят через Gmail API)
sample_emails = [
    {
        "sender": "carlos@example.com",
        "subject": "Совместная сделка",
        "body": "Добрый день! У меня есть клиент из России который ищет квартиру $150K. Можем ли мы поработать вместе?",
        "date": "2026-10-05"
    },
    {
        "sender": "newsletter@realestate-news.com",
        "subject": "Еженедельный дайджест рынка",
        "body": "Отчёт о рынке недвижимости Эквадора за прошлую неделю...",
        "date": "2026-10-05"
    },
]

YOUR_CONTEXT = """
Acme Realty — помогает русскоязычным купить или арендовать недвижимость в Эквадоре.
Работаю с клиентами напрямую и через местные агентства-партнёры.
Стиль общения: дружелюбный, конкретный, без лишних слов.
"""

processed = process_inbox(sample_emails, YOUR_CONTEXT)
brief = format_daily_brief(processed)
print(brief)
```

---

### Многоязычные email: одна система, два языка

Если работаешь на двух рынках (русскоязычный + местный испаноязычный) — Claude переводит и отвечает на нужном языке автоматически.

```python
def multilingual_reply(incoming_email: str, your_context: str) -> dict:
    """
    Определяет язык письма и составляет ответ на том же языке.
    Возвращает: {language, draft, translation_to_russian}
    """
    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=500,
        system=f"""Ты двуязычный email-ассистент (русский + испанский).

Контекст о владельце:
{your_context}

Правила:
1. Определи язык входящего письма
2. Ответь на ТОМ ЖЕ языке (не переключай без причины)
3. Если испанский — сохрани профессиональный латиноамериканский тон
4. Если русский — краткий деловой стиль

Верни JSON:
{{
  "detected_language": "Russian"/"Spanish"/"Other",
  "draft": "черновик ответа на языке письма",
  "summary_in_russian": "одно предложение о чём письмо — всегда на русском"
}}""",
        messages=[{
            "role": "user",
            "content": f"Письмо:\n{incoming_email}"
        }]
    )
    import json
    return json.loads(response.content[0].text)


# Тест
spanish_email = """
Buenos días! Soy agente inmobiliario en Cuenca y tengo clientes 
de Rusia que buscan apartamentos. ¿Podríamos colaborar?
"""

result = multilingual_reply(spanish_email, YOUR_CONTEXT)
print(f"Язык: {result['detected_language']}")
print(f"Суть (по-русски): {result['summary_in_russian']}")
print(f"\nЧерновик ответа:\n{result['draft']}")
```

---

## Практика

1. Подключи Gmail к Claude: коннектор Gmail / Google Workspace в настройках Claude или официальный MCP-сервер Gmail от Google (см. выше). Права давай минимальные: чтение и черновики, без отправки.

2. Напиши скрипт `email_classifier.py` с функциями `classify_email` и `draft_reply` из урока. Протестируй на 5 письмах из твоего inbox (обезличь данные клиентов: не отправляй чужие персональные данные в сервисы, на которые у тебя нет права).

3. Создай CLAUDE.md для email-ассистента: опиши свой стиль, 3-5 запрещённых фраз, 2 примера хорошего и плохого ответа.

4. Настрой `process_inbox` + `format_daily_brief` — запусти на своих email, посмотри качество черновиков.

5. Выбери одну задачу cold outreach (5-10 контактов), попробуй `write_cold_email` на реальных данных.

---

## Инструменты и ресурсы

- **[Composio](https://composio.dev)** — MCP-хаб для подключения Gmail, Apollo, Hunter и других сервисов к Claude (доступ к почте получает третья сторона: проверь права)
- **[Gmail API](https://developers.google.com/gmail/api)** — официальная документация если подключаешь напрямую
- **[Gmail MCP-сервер Google](https://developers.google.com/workspace/gmail/api/guides/configure-mcp-server)** — developer preview: поиск, чтение, черновики, ярлыки
- **[Apollo.io](https://apollo.io)** — база контактов + email finder (есть бесплатный план; условия и цены на сайте)
- **[Hunter.io](https://hunter.io)** — поиск email по домену (есть бесплатный план; условия на сайте)
- **[Lemlist](https://lemlist.com)** — cold email с автоматическими follow-up (условия на сайте)
- **[Instantly.ai](https://instantly.ai)** — альтернатива Lemlist для массовых рассылок (условия на сайте)
- **[anthropic Python SDK](https://github.com/anthropics/anthropic-sdk-python)** — для скриптов из урока
- **Цены и версии:** [Актуальное сейчас](https://aimayak.com/ru/now/)

---

## Ключевые выводы

> Email — не про написание текста. Про принятие решений: кому ответить, что сказать, когда. Claude берёт техническую часть (написать текст в твоём стиле). Решения остаются за тобой.

> Автодрафт работает только если Claude знает твой стиль. Потрать 30 минут на CLAUDE.md с примерами хорошего и плохого — это окупается каждый день.

> Inbox Zero — достижимо. Классификация + черновики на входящие заметно сокращают время на почту. Ключ: не автоматизировать отправку полностью, оставить себе финальный просмотр.

> Cold outreach с AI — персонализация без ручной работы. Apollo находит людей, Hunter.io находит email, Claude пишет письмо как будто ты изучал человека 20 минут. На самом деле — 5 секунд API.

---

## Следующий урок

→ [Встречи с AI — транскрипция и автоматические протоколы](74-ai-meetings.md) — записываем встречи и превращаем их в задачи
