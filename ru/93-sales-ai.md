# Sales AI — квалификация лидов, follow-up, закрытие сделок

**Время:** ~25 мин теории + 35 мин практики

---

## Суть урока

Продажи — это фильтрация. Из сотни лидов покупает небольшая часть. Задача продавца: быстро найти тех, кто купит, и потратить время на них, а не на остальных.

Claude делает эту фильтрацию системной: квалифицирует лидов по BANT, ставит оценку готовности, пишет персонализированные письма, готовит ответы на возражения. Менеджер приходит к разговору уже зная кто перед ним и что его волнует.

🎨 **Образ:** Представь опытного продавца который перед каждым звонком звонит коллеге и говорит "это Иван из ООО Ромашка, они смотрят конкурентов, бюджет есть но директор не принял решение, главное возражение — интеграция с 1С". Вот что Claude делает для каждого лида автоматически.

---

## Ключевые концепции

- **BANT квалификация** — Budget, Authority, Need, Timeline через AI
- **Lead Scoring 0-100** — кто готов купить прямо сейчас
- **Персонализированные follow-up** — каждое письмо под конкретного человека
- **База возражений** — Claude генерирует ответ на любое возражение
- **Sales playbook → AI-помощник** — документ становится живым советником
- **Apollo.io + Claude** — outreach с гиперперсонализацией

---

## Теория

### BANT квалификация: четыре вопроса которые решают всё

BANT — старейший фреймворк продаж, но работает до сих пор:

- **B**udget — есть ли деньги? Сколько готовы потратить?
- **A**uthority — это лицо принимающее решение? Или он только разведчик?
- **N**eed — есть ли реальная потребность или "просто смотрим"?
- **T**imeline — когда планируют купить? В этом квартале или "когда-нибудь"?

Claude извлекает BANT из любой переписки — письма, чаты, заметки с переговоров:

```python
import anthropic
import json

client = anthropic.Anthropic()

def qualify_lead_bant(
    company_name: str,
    contact_name: str,
    contact_position: str,
    interaction_history: str
) -> dict:
    """Квалифицирует лида по BANT на основе истории взаимодействий"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=800,
        messages=[{
            "role": "user",
            "content": f"""Проведи BANT квалификацию лида на основе имеющихся данных.

Компания: {company_name}
Контакт: {contact_name}, {contact_position}

История взаимодействий:
{interaction_history}

Оцени каждый критерий BANT по шкале 0-3:
0 = нет информации
1 = слабый сигнал / сомнительно
2 = есть признаки
3 = чёткое подтверждение

Верни JSON:
{{
    "bant": {{
        "budget": {{
            "score": число 0-3,
            "evidence": "цитата или факт из переписки",
            "concern": "что настораживает",
            "recommendation": "что узнать дополнительно"
        }},
        "authority": {{
            "score": число 0-3,
            "evidence": "...",
            "concern": "...",
            "recommendation": "..."
        }},
        "need": {{
            "score": число 0-3,
            "evidence": "...",
            "concern": "...",
            "recommendation": "..."
        }},
        "timeline": {{
            "score": число 0-3,
            "evidence": "...",
            "concern": "...",
            "recommendation": "..."
        }}
    }},
    "total_score": число 0-12,
    "qualification_verdict": "hot/warm/cold/disqualify",
    "recommended_next_step": "конкретное следующее действие",
    "key_questions_to_ask": ["список из 3 вопросов для следующего контакта"]
}}"""
        }]
    )

    result = json.loads(response.content[0].text)

    # Добавляем процентную оценку
    result["qualification_percent"] = round(result["total_score"] / 12 * 100)

    return result


# Тест
history = """
15 апреля — первый звонок:
Артём спросил про наш продукт, сказал что "рассматривают варианты для
автоматизации отдела". Он менеджер по развитию. Директор "пока не в теме".
Бюджет не обсуждали. "Хотели бы разобраться до конца года".

22 апреля — повторный звонок:
Артём пришёл с конкретным ТЗ. Сказал что директор одобрил рассмотрение.
Упомянул что у конкурента аналог стоит 80 тыс/год, им кажется дорого.
Хотят начать "не позже 3-го квартала — привязано к бюджетированию".

28 апреля — письмо:
"Мы посмотрели демо. Нам нравится, но нужно понять как интегрируется с нашей
1С. Также директор хочет встретиться лично. Можете на следующей неделе?"
"""

result = qualify_lead_bant(
    company_name="ООО Техпром",
    contact_name="Артём Власов",
    contact_position="Менеджер по развитию",
    interaction_history=history
)

print(f"BANT Score: {result['total_score']}/12 ({result['qualification_percent']}%)")
print(f"Статус: {result['qualification_verdict'].upper()}")
print(f"\nСледующий шаг: {result['recommended_next_step']}")
print(f"\nВопросы для встречи:")
for q in result['key_questions_to_ask']:
    print(f"  • {q}")
```

### Lead Scoring: кто горячий прямо сейчас

BANT — это основа, но готовность к покупке определяют ещё десятки сигналов. Claude анализирует всё сразу и выдаёт оценку 0-100.

```python
def score_lead_readiness(
    contact_info: dict,
    interaction_history: str,
    product_type: str,
    avg_deal_cycle_days: int
) -> dict:
    """Комплексная оценка готовности лида к покупке"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=700,
        messages=[{
            "role": "user",
            "content": f"""Оцени готовность лида к покупке.

Информация о контакте:
{json.dumps(contact_info, ensure_ascii=False)}

Тип продукта: {product_type}
Средний цикл сделки: {avg_deal_cycle_days} дней

История:
{interaction_history}

Проанализируй сигналы:
ПОЛОЖИТЕЛЬНЫЕ: конкретные вопросы про детали, спрашивает про интеграцию/внедрение,
упоминает сроки, называет бюджет, просит встречу с директором, сравнивает с конкурентами,
запрашивает КП/договор

ОТРИЦАТЕЛЬНЫЕ: расплывчатые ответы, "посмотрим", долгие паузы без ответа,
говорит что "не его решение", меняет требования, просит всё дешевле

Верни JSON:
{{
    "score": число 0-100,
    "stage": "awareness/consideration/decision/ready_to_buy",
    "hot_signals": ["список положительных сигналов найденных в истории"],
    "cold_signals": ["список тревожных сигналов"],
    "estimated_close_days": число (прогноз сколько дней до закрытия),
    "confidence": "low/medium/high",
    "action": {{
        "immediate": "что сделать прямо сейчас",
        "this_week": "что сделать на этой неделе",
        "if_no_response": "что делать если нет ответа 3 дня"
    }}
}}"""
        }]
    )

    return json.loads(response.content[0].text)
```

🎨 **Образ:** Доктор смотрит на симптомы и ставит диагноз. Продавец смотрит на сигналы и ставит оценку. Claude — это диагностический аппарат который не пропускает ни один симптом и не устаёт после 50-го лида.

### Персонализированные follow-up письма

Шаблонные письма не работают. "Добрый день! Мы хотели бы напомнить о нашем предложении..." — удаляется не читаясь.

Персонализация работает. Но персонализировать 50 follow-up вручную нереально.

```python
def generate_followup_email(
    contact: dict,
    last_interaction_summary: str,
    days_since_last_contact: int,
    followup_number: int,  # Первый, второй или третий follow-up
    product_name: str,
    your_name: str
) -> dict:
    """Генерирует персонализированное follow-up письмо"""

    followup_tone = {
        1: "дружелюбный и лёгкий, добавить ценность (статья/кейс)",
        2: "чуть более прямой, спросить есть ли вопросы или изменилось что-то",
        3: "заключительный, дать понять что это последний контакт — но без давления"
    }

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=600,
        messages=[{
            "role": "user",
            "content": f"""Напиши персонализированное follow-up письмо.

ДАННЫЕ КОНТАКТА:
Имя: {contact.get('name')}
Компания: {contact.get('company')}
Должность: {contact.get('position')}
Интерес: {contact.get('main_interest')}

КОНТЕКСТ:
Последний контакт: {last_interaction_summary}
Дней без ответа: {days_since_last_contact}
Это follow-up номер: {followup_number} из 3
Тон: {followup_tone.get(followup_number, followup_tone[1])}

Продукт: {product_name}
От кого: {your_name}

ТРЕБОВАНИЯ:
- 3-5 предложений максимум
- Первое предложение — конкретная ссылка на прошлый разговор (не шаблон)
- Добавь что-то полезное (полезное наблюдение, статистика, короткий кейс)
- Один чёткий призыв к действию
- Никакого давления, никакой агрессии
- Живой язык, не корпоративный

Верни JSON:
{{
    "subject": "тема письма",
    "body": "текст письма",
    "ps": "постскриптум (опционально, только если усиливает)",
    "value_add": "что полезного добавлено в письме"
}}"""
        }]
    )

    return json.loads(response.content[0].text)


# Пример
email = generate_followup_email(
    contact={
        "name": "Артём",
        "company": "ООО Техпром",
        "position": "Менеджер по развитию",
        "main_interest": "Автоматизация отдела продаж, интеграция с 1С"
    },
    last_interaction_summary="Провели демо, Артём впечатлён, но спросил про интеграцию с 1С. Договорились что они обсудят внутри команды.",
    days_since_last_contact=4,
    followup_number=1,
    product_name="SalesBot Pro",
    your_name="Михаил"
)

print(f"Тема: {email['subject']}")
print(f"\n{email['body']}")
if email.get('ps'):
    print(f"\nP.S. {email['ps']}")
```

### База возражений: ответ на всё

Каждый продукт имеет 10-15 типичных возражений. Опытный продавец знает ответ на каждое. Новый — теряется.

Claude не теряется никогда:

```python
def handle_objection(
    objection: str,
    product_name: str,
    product_key_benefits: list[str],
    contact_context: str = ""
) -> dict:
    """Генерирует ответ на возражение с несколькими подходами"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=800,
        messages=[{
            "role": "user",
            "content": f"""Клиент высказал возражение. Помоги с ответом.

ПРОДУКТ: {product_name}
ВЫГОДЫ: {', '.join(product_key_benefits)}
ВОЗРАЖЕНИЕ: "{objection}"
КОНТЕКСТ КЛИЕНТА: {contact_context or "Нет дополнительного контекста"}

Дай 3 варианта ответа:

1. **Прямой** — согласись с частью правды в возражении, потом переверни
2. **Через вопрос** — задай вопрос который помогает клиенту самому прийти к ответу
3. **Через кейс** — история другого клиента с похожим возражением

Для каждого:
- Текст ответа (2-4 предложения)
- Когда использовать

Также дай:
- Скрытая причина: что на самом деле за этим возражением
- Красный флаг: это искренное возражение или признак что сделки не будет?"""
        }]
    )

    return response.content[0].text


# Типичные возражения и ответы
objections = [
    "Это слишком дорого для нас",
    "Нам нужно обсудить с руководством",
    "Мы уже пользуемся другим решением",
    "Давайте вернёмся к этому в следующем квартале",
    "Нам нужно подумать"
]

print("=== БАЗА ОТВЕТОВ НА ВОЗРАЖЕНИЯ ===\n")
for obj in objections[:2]:  # Показываем первые два для примера
    print(f"ВОЗРАЖЕНИЕ: {obj}")
    print("-" * 50)
    response = handle_objection(
        objection=obj,
        product_name="SalesBot Pro",
        product_key_benefits=["Экономия 5 часов/неделю", "Интеграция с 1С", "Внедрение за 2 дня"],
        contact_context="B2B клиент, средний бизнес, отдел продаж 10 человек"
    )
    print(response)
    print("\n")
```

### Sales Playbook → живой AI-советник

Если у вас уже есть sales playbook — Claude превращает его в интерактивного советника для менеджеров.

```python
def create_sales_advisor(playbook_content: str):
    """Создаёт советника по продажам на основе плейбука"""

    def ask_advisor(question: str, deal_context: str) -> str:
        response = client.messages.create(
            model="claude-sonnet-5-5",
            max_tokens=600,
            system=f"""Ты опытный тренер по продажам. У тебя есть корпоративный плейбук:

{playbook_content}

Отвечай строго опираясь на плейбук. Если вопрос выходит за рамки плейбука —
так и скажи. Давай конкретные фразы которые менеджер может использовать прямо сейчас.""",
            messages=[{
                "role": "user",
                "content": f"Ситуация с клиентом: {deal_context}\n\nВопрос: {question}"
            }]
        )
        return response.content[0].text

    return ask_advisor

# Пример использования
playbook = """
# Sales Playbook ООО Техсервис

## Квалификация
- Минимальный бюджет для работы: от 50,000 рублей
- Целевая должность: директор / коммерческий директор / IT-директор
- Красный флаг: если не могут назвать боль конкретно — не наш клиент

## Работа с возражением "Дорого"
1. Спросить: "Дорого по сравнению с чем?"
2. Перевести в ROI: "Сколько часов/недель ваши люди тратят сейчас на X?"
3. Показать кейс компании схожего размера

## Закрытие сделки
- Никогда не давать скидку без повода
- Альтернативные вопросы: "Вам удобнее начать 1-го или 15-го?"
"""

advisor = create_sales_advisor(playbook)

# Менеджер спрашивает совет прямо перед звонком
advice = advisor(
    question="Клиент говорит что дорого, но явно заинтересован. Что делать?",
    deal_context="Компания 50 человек, IT-директор, рассматривают 3 месяца, бюджет 'обсуждаем'"
)
print(advice)
```

### Apollo.io + Claude: outreach с персонализацией

Apollo.io — инструмент для поиска контактов и outreach (холодные письма, LinkedIn). Claude добавляет персонализацию которую не сделает шаблон.

⚠️ Холодные письма и сбор контактов регулируются законами о рассылках и о персональных данных, в каждой стране своими. Перед запуском сверься с уроками [Регулирование AI и соответствие требованиям](61c-ai-regulation-compliance.md) и [Cold Outreach: DM, email, voice](39c-cold-outreach-deep.md).

```python
def personalize_cold_outreach(
    prospect_data: dict,  # Данные из Apollo: компания, должность, LinkedIn активность
    your_product: str,
    your_value_prop: str
) -> dict:
    """Персонализирует холодное письмо под конкретного человека"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=500,
        messages=[{
            "role": "user",
            "content": f"""Напиши персонализированное холодное письмо.

ИНФОРМАЦИЯ О ПРОСПЕКТЕ (из Apollo/LinkedIn):
{json.dumps(prospect_data, ensure_ascii=False, indent=2)}

НАШ ПРОДУКТ: {your_product}
ЦЕННОСТНОЕ ПРЕДЛОЖЕНИЕ: {your_value_prop}

ПРАВИЛА:
- Первое предложение ДОЛЖНО быть о них (не о нас)
- Связать их реальный контекст (должность/компания/активность) с нашим продуктом
- Один чёткий вопрос в конце (не призыв "купить")
- До 100 слов

Верни JSON:
{{
    "subject": "тема (до 50 символов)",
    "opening": "первое персонализированное предложение",
    "value": "как наш продукт решает их конкретную проблему",
    "question": "вопрос для ответа",
    "personalization_source": "на чём основана персонализация"
}}"""
        }]
    )

    return json.loads(response.content[0].text)
```

---

## Практика

### Задача: создать систему квалификации лидов с Claude Scoring

**Что строим:** скрипт который принимает данные по лиду и выдаёт полную квалификацию + план работы с ним.

```python
# lead_qualification_system.py

import anthropic
import json
from dataclasses import dataclass
from typing import Optional

client = anthropic.Anthropic()

@dataclass
class Lead:
    name: str
    company: str
    position: str
    email: str
    phone: Optional[str] = None
    source: str = "входящий"
    notes: str = ""
    interaction_log: str = ""

def full_lead_analysis(lead: Lead) -> dict:
    """
    Полный анализ лида: BANT + scoring + план действий
    """

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=1200,
        messages=[{
            "role": "user",
            "content": f"""Проведи полный анализ лида для отдела продаж.

ЛИД:
Имя: {lead.name}
Компания: {lead.company}
Должность: {lead.position}
Источник: {lead.source}
Заметки менеджера: {lead.notes}

ИСТОРИЯ ВЗАИМОДЕЙСТВИЙ:
{lead.interaction_log or "Первый контакт, истории нет"}

Нужен ПОЛНЫЙ анализ в JSON:
{{
    "qualification": {{
        "bant_score": число 0-12,
        "readiness_score": число 0-100,
        "verdict": "hot/warm/cold/disqualify",
        "verdict_reason": "почему такой вердикт"
    }},
    "bant_details": {{
        "budget": {{"score": 0-3, "evidence": "...", "gap": "что неизвестно"}},
        "authority": {{"score": 0-3, "evidence": "...", "gap": "..."}},
        "need": {{"score": 0-3, "evidence": "...", "gap": "..."}},
        "timeline": {{"score": 0-3, "evidence": "...", "gap": "..."}}
    }},
    "persona_analysis": {{
        "decision_role": "champion/decision_maker/influencer/blocker/user",
        "communication_style": "аналитик/отношения/скорость/стабильность",
        "main_motivation": "что движет этим человеком"
    }},
    "action_plan": {{
        "next_24h": "конкретное действие",
        "next_week": "план на неделю",
        "key_questions": ["3 вопроса для следующей встречи"],
        "risks": ["что может пойти не так"],
        "win_conditions": ["что нужно чтобы закрыть эту сделку"]
    }},
    "suggested_followup_timing": {{
        "if_interested": "через сколько дней писать",
        "if_silent": "через сколько дней напомнить",
        "max_attempts": число
    }}
}}"""
        }]
    )

    return json.loads(response.content[0].text)


def format_lead_report(lead: Lead, analysis: dict) -> str:
    """Форматирует красивый отчёт для менеджера"""

    q = analysis["qualification"]
    bant = analysis["bant_details"]
    action = analysis["action_plan"]

    verdict_emoji = {
        "hot": "🔥", "warm": "☀️", "cold": "❄️", "disqualify": "🚫"
    }.get(q["verdict"], "❓")

    report = f"""
╔══════════════════════════════════════════════╗
║  АНАЛИЗ ЛИДА: {lead.name[:30]:<30} ║
╚══════════════════════════════════════════════╝

{verdict_emoji} СТАТУС: {q['verdict'].upper()} ({q['readiness_score']}/100)
📊 BANT Score: {q['bant_score']}/12
💡 Причина: {q['verdict_reason']}

BANT ДЕТАЛИ:
  💰 Budget:    {'█' * bant['budget']['score']}{'░' * (3-bant['budget']['score'])} ({bant['budget']['score']}/3) — {bant['budget']['evidence'][:60]}
  👔 Authority: {'█' * bant['authority']['score']}{'░' * (3-bant['authority']['score'])} ({bant['authority']['score']}/3) — {bant['authority']['evidence'][:60]}
  🎯 Need:      {'█' * bant['need']['score']}{'░' * (3-bant['need']['score'])} ({bant['need']['score']}/3) — {bant['need']['evidence'][:60]}
  ⏰ Timeline:  {'█' * bant['timeline']['score']}{'░' * (3-bant['timeline']['score'])} ({bant['timeline']['score']}/3) — {bant['timeline']['evidence'][:60]}

ПЛАН ДЕЙСТВИЙ:
  ⚡ Сегодня: {action['next_24h']}
  📅 На неделе: {action['next_week']}

ВОПРОСЫ ДЛЯ СЛЕДУЮЩЕЙ ВСТРЕЧИ:
"""
    for q_text in action['key_questions']:
        report += f"  • {q_text}\n"

    report += f"""
РИСКИ:
"""
    for risk in action['risks']:
        report += f"  ⚠️ {risk}\n"

    return report


# ===== ТЕСТ =====
test_lead = Lead(
    name="Сергей Новиков",
    company="Группа компаний Алмаз",
    position="Директор по операциям",
    email="s.novikov@almaz-group.ru",
    source="входящий звонок",
    notes="Позвонил сам, сказал что видел нас на конференции. Спрашивал про интеграции.",
    interaction_log="""
    14 мая (звонок, 25 мин):
    Сергей — директор по операциям, под ним 3 отдела включая продажи (12 чел).
    Проблема: менеджеры не заполняют CRM, теряются лиды.
    Рассматривают решение "до конца Q2" — это их внутренний дедлайн.
    Бюджет: "в рамках разумного, детали с финдиром". ИТ-директор уже в курсе.
    Попросил прислать КП и кейсы похожих компаний.
    Конкурент: смотрели Битрикс24, "не очень понравился интерфейс".
    Следующий шаг: встреча с финдиром через неделю если материалы понравятся.
    """
)

print("Анализирую лида...")
analysis = full_lead_analysis(test_lead)
report = format_lead_report(test_lead, analysis)
print(report)

# Сохраняем в JSON для CRM
with open(f"lead_{test_lead.name.replace(' ', '_')}.json", "w", encoding="utf-8") as f:
    json.dump({
        "lead": {
            "name": test_lead.name,
            "company": test_lead.company,
            "position": test_lead.position
        },
        "analysis": analysis
    }, f, ensure_ascii=False, indent=2)

print("\n✅ Анализ сохранён в JSON")
```

**Запускаем:**
```bash
python lead_qualification_system.py
```

---

## Инструменты и ресурсы

- **Apollo.io** — поиск контактов и outreach (тарифы и лимиты смотри на сайте)
- **HubSpot CRM** — CRM для хранения данных, есть бесплатный план (платные тарифы смотри на сайте; см. урок [CRM на автопилоте](90-crm-autopilot.md))
- **Lemlist / Instantly** — автоматизация email outreach
- **Notion** — для хранения sales playbook
- **Claude API** — названия моделей в коде даны на октябрь 2026; актуальные цены и версии: [Актуальное сейчас](https://aimayak.com/ru/now/)

---

## Ключевые выводы

> BANT — это не бюрократия, это скорость. Быстро понять "наш клиент или нет" — это уважение к своему времени и времени клиента.
>
> Персонализация больше не роскошь — это необходимость. Люди получают десятки шаблонных писем в день. Одно персонализированное письмо выделяется мгновенно.
>
> Самое ценное в Sales AI: не скорость написания, а системность. Claude применяет одинаковый уровень анализа к сотому лиду как к первому. Люди устают — AI нет.

---

## Следующий урок

→ [AI Customer Support — тикет-система, RAG по базе знаний, умная поддержка](94-ai-customer-support.md)
