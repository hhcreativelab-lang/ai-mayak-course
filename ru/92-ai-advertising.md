# AI Реклама — генерация креативов, A/B тесты, умные ставки

**Время:** ~25 мин теории + 40 мин практики

---

## Суть урока

Рекламный копирайтер работает 8 часов, пишет 5 вариантов объявления, устаёт и уходит домой. Claude пишет 50 вариантов за 3 минуты, анализирует результаты тестов и сам говорит что работает лучше.

Это не просто быстрее. Это другая игра: больше экспериментов → больше данных → лучше реклама → ниже стоимость клика.

🎨 **Образ:** Раньше рекламное агентство было как ресторан с одним поваром — медленно и дорого. Claude + ваши данные — это как фабрика еды: 50 вариантов за минуту, проверяем какой вкуснее, масштабируем победителя. И фабрика работает ночью, пока повар спит.

---

## Ключевые концепции

- **Рекламный копирайтинг через Claude** — 50 вариантов заголовков за одну команду
- **Meta Ads (Facebook/Instagram)** — тексты + баннеры через AI
- **Google Ads RSA** — адаптивные объявления, Claude оптимизирует заголовки
- **A/B тестирование** — Claude анализирует результаты и объявляет победителя
- **Performance Max** — как Claude помогает с asset groups
- **Adspirer MCP** — управление рекламными кампаниями прямо из Claude
- **Автоматические отчёты** — данные → анализ → конкретные рекомендации

---

## Теория

### Рекламный копирайтинг: 50 вариантов за 3 минуты

Хорошая реклама начинается с тестирования. Чтобы тестировать — нужно много вариантов. Раньше это стоило денег и времени. Теперь нет.

```python
import anthropic
import json

def generate_ad_variants(
    product: str,
    target_audience: str,
    key_benefit: str,
    platform: str,
    count: int = 10
) -> dict:
    """Генерирует варианты рекламных текстов"""

    client = anthropic.Anthropic()

    # Лимиты знаков у площадок меняются: сверяй их со справкой Meta и Google Ads
    platform_specs = {
        "facebook": {
            "headline_chars": 40,
            "primary_text_chars": 125,
            "description_chars": 30
        },
        "google_rsa": {
            "headline_chars": 30,
            "description_chars": 90,
            "headline_count": 15
        },
        "instagram": {
            "caption_chars": 2200,
            "first_line_chars": 125  # видно без "ещё"
        }
    }

    specs = platform_specs.get(platform, platform_specs["facebook"])

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=2000,
        messages=[{
            "role": "user",
            "content": f"""Создай {count} вариантов рекламы для {platform}.

Продукт: {product}
Целевая аудитория: {target_audience}
Ключевая выгода: {key_benefit}
Ограничения платформы: {json.dumps(specs, ensure_ascii=False)}

Для каждого варианта используй разный подход:
- Эмоциональный (страх упустить)
- Рациональный (цифры и факты)
- Социальное доказательство (отзывы, клиенты)
- Любопытство (вопрос или неожиданный факт)
- Прямой (выгода в лоб)

Верни JSON массив:
[
  {{
    "variant_id": 1,
    "approach": "название подхода",
    "headline": "заголовок",
    "primary_text": "основной текст",
    "cta": "призыв к действию",
    "target_emotion": "какую эмоцию вызывает",
    "hypothesis": "почему должно работать"
  }}
]"""
        }]
    )

    return json.loads(response.content[0].text)


# Пример для онлайн-курса по Excel
variants = generate_ad_variants(
    product="Онлайн-курс Excel для финансистов",
    target_audience="Бухгалтеры и финансисты 25-45 лет, тратят 2-3 часа на отчёты",
    key_benefit="Сократить время на отчёты с 3 часов до 20 минут",
    platform="facebook",
    count=10
)

for v in variants[:3]:
    print(f"\n--- Вариант {v['variant_id']}: {v['approach']} ---")
    print(f"Заголовок: {v['headline']}")
    print(f"Текст: {v['primary_text']}")
    print(f"CTA: {v['cta']}")
```

### Meta Ads: тексты + баннеры

Meta (Facebook + Instagram) — самая богатая по данным рекламная платформа. Claude помогает с текстами, а для баннеров работает в паре с генераторами изображений.

**Воронка создания рекламы:**

```
1. Claude → 10 вариантов текстов
2. Flux / Midjourney / генератор картинок в ChatGPT → баннеры под каждый текст
3. Запуск A/B теста (по 5 вариантов)
4. 3-5 дней → собираем данные
5. Claude → анализирует результаты
6. Масштабируем победителя
```

```python
def create_meta_campaign_brief(
    product: str,
    budget_daily: float,
    target_audience_description: str
) -> str:
    client = anthropic.Anthropic()

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=1500,
        messages=[{
            "role": "user",
            "content": f"""Создай подробный бриф для рекламной кампании в Meta Ads.

Продукт: {product}
Дневной бюджет: ${budget_daily}
Аудитория: {target_audience_description}

Включи:
1. **Структура кампании**: сколько групп объявлений, какая логика
2. **Таргетинг**: детальные интересы, возраст, география
3. **Lookalike рекомендации**: на кого делать похожую аудиторию
4. **Форматы**: какие форматы рекламы использовать и почему
5. **Бюджет**: как распределить между группами
6. **KPI**: что считаем успехом (CPC, CTR, CPL)
7. **Тест-план**: что тестируем в первую очередь

Пиши конкретно — цифры, проценты, рекомендации."""
        }]
    )

    return response.content[0].text
```

🎨 **Образ:** Раньше медиапланер был отдельным специалистом и работал с 9 до 18. Claude делает черновик плана за секунды, даже в 3 ночи перед запуском. Решение по бюджету всё равно принимает человек.

### Google Ads: RSA и умные ключевики

Google RSA (Responsive Search Ads) — вы даёте до 15 заголовков и 4 описания, Google сам комбинирует. Claude помогает написать 15 заголовков которые реально хорошо работают в комбинациях.

```python
def generate_google_rsa(
    product: str,
    landing_page_theme: str,
    keywords: list[str]
) -> dict:
    client = anthropic.Anthropic()

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=1200,
        messages=[{
            "role": "user",
            "content": f"""Создай RSA объявление для Google Ads.

Продукт: {product}
Тема лендинга: {landing_page_theme}
Ключевые слова: {', '.join(keywords)}

Требования:
- 15 заголовков, каждый до 30 символов
- 4 описания, каждое до 90 символов
- Заголовки должны хорошо работать в любых комбинациях
- Включи ключевые слова в 3-4 заголовка (не все!)
- Разнообразие: выгоды, действия, уникальность, срочность

Верни JSON:
{{
    "headlines": ["заголовок 1", ... "заголовок 15"],
    "descriptions": ["описание 1", ... "описание 4"],
    "pinning_recommendations": {{
        "headline_position_1": "какой заголовок закрепить на 1 позиции",
        "reason": "почему"
    }}
}}"""
        }]
    )

    return json.loads(response.content[0].text)


# Пример для юридической фирмы
rsa = generate_google_rsa(
    product="Юридические услуги по недвижимости",
    landing_page_theme="Оформление купли-продажи квартиры быстро и безопасно",
    keywords=["юрист недвижимость", "оформление сделки", "купля продажа квартира"]
)

print("Заголовки:")
for i, h in enumerate(rsa["headlines"], 1):
    chars = len(h)
    status = "✅" if chars <= 30 else "⚠️"
    print(f"{i}. {status} {h} ({chars} симв)")
```

### A/B тестирование: Claude анализирует победителя

Данные по тестам часто выглядят непонятно. CTR у одного выше, но CPC тоже. Конверсий меньше, но они дешевле. Claude распутывает это за 10 секунд.

```python
def analyze_ab_test(test_results: list[dict]) -> dict:
    """
    test_results: список словарей с результатами каждого варианта
    Пример: [{"variant": "A", "impressions": 5000, "clicks": 150, "conversions": 12, "spend": 200}]
    """
    client = anthropic.Anthropic()

    # Добавляем вычисленные метрики
    for r in test_results:
        r["ctr"] = round(r["clicks"] / r["impressions"] * 100, 2)
        r["cpc"] = round(r["spend"] / r["clicks"], 2) if r["clicks"] > 0 else 0
        r["cpl"] = round(r["spend"] / r["conversions"], 2) if r["conversions"] > 0 else 0
        r["cvr"] = round(r["conversions"] / r["clicks"] * 100, 2) if r["clicks"] > 0 else 0

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=800,
        messages=[{
            "role": "user",
            "content": f"""Проанализируй результаты A/B теста рекламы и дай рекомендации.

Результаты:
{json.dumps(test_results, ensure_ascii=False, indent=2)}

Нужно:
1. **Победитель**: какой вариант лучше и ПОЧЕМУ (учти все метрики)
2. **Статистическая значимость**: хватает ли данных для уверенного вывода
3. **Инсайты**: что говорят результаты о аудитории
4. **Следующий шаг**: что тестировать дальше
5. **Масштабирование**: насколько увеличить бюджет победителя

Будь конкретен: называй цифры, проценты."""
        }]
    )

    return {
        "raw_results": test_results,
        "analysis": response.content[0].text
    }


# Тест
results = [
    {"variant": "A — Страх (потеря)", "impressions": 10000, "clicks": 180, "conversions": 9, "spend": 350},
    {"variant": "B — Выгода (экономия)", "impressions": 10000, "clicks": 220, "conversions": 18, "spend": 350},
    {"variant": "C — Социальное доказательство", "impressions": 10000, "clicks": 195, "conversions": 14, "spend": 350}
]

analysis = analyze_ab_test(results)
print(analysis["analysis"])
# Победитель: B — CTR 2.2%, CPL $19.4, CVR 8.2%
# Вариант A проигрывает несмотря на интригующий заголовок
# Рекомендация: данных мало (9 и 18 конверсий), продолжить тест и поднимать бюджет B постепенно
```

### Performance Max: Claude помогает с asset groups

PMax — кампании Google которые сами выбирают где показываться (поиск, YouTube, Gmail, Display). Качество материалов (assets) критично. Для поисковых кампаний у Google есть ещё AI Max: на октябрь 2026 AI-функции встроены в сами кампании, поэтому названия и настройки сверяй со справкой Google Ads.

```python
def create_pmax_assets(
    product: str,
    key_benefits: list[str],
    audience_persona: str
) -> dict:
    client = anthropic.Anthropic()

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=2000,
        messages=[{
            "role": "user",
            "content": f"""Создай все необходимые материалы (assets) для кампании Performance Max.

Продукт: {product}
Ключевые выгоды: {', '.join(key_benefits)}
Портрет аудитории: {audience_persona}

Создай:
{{
    "headlines": ["5 заголовков до 30 символов"],
    "long_headlines": ["5 длинных заголовков до 90 символов"],
    "descriptions": ["5 описаний до 90 символов"],
    "business_name": "название компании (до 25 символов)",
    "call_to_actions": ["список из 5 призывов к действию"],
    "image_prompts": ["5 промптов для генерации изображений через Midjourney/Flux"],
    "audience_signals": {{
        "interests": ["список интересов для сигналов аудитории"],
        "custom_intent_keywords": ["ключевые слова намерения"],
        "remarketing_segments": ["сегменты ремаркетинга"]
    }}
}}"""
        }]
    )

    return json.loads(response.content[0].text)
```

### Adspirer MCP: управление рекламой прямо из Claude

Adspirer — сторонний MCP-сервис для рекламных кабинетов. Подключается к Claude Code и Cowork как плагин, и на октябрь 2026 работает с Google Ads, Meta Ads и рядом других площадок. Позволяет Claude видеть реальные данные по кампаниям и давать рекомендации на основе фактов, а не гипотез. Сервис умеет и запускать кампании, поэтому проверь его условия, выдавай права по минимуму (начни с чтения) и оставляй запуск рекламы и изменение бюджета за собой.

```
# В Claude Code с Adspirer MCP подключённым:

"Покажи мне кампании с CTR ниже 1% за последние 7 дней"
→ Claude видит данные → выдаёт список с рекомендациями

"Какие ключевые слова тратят деньги без конверсий?"
→ Claude анализирует → список для паузы

"Создай отчёт по ROI всех кампаний за месяц"
→ Claude генерирует → сравнение, выводы, рекомендации
```

### Автоматические отчёты: данные → инсайты

```python
def generate_weekly_ad_report(campaigns_data: dict) -> str:
    client = anthropic.Anthropic()

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=1500,
        messages=[{
            "role": "user",
            "content": f"""Сгенерируй еженедельный отчёт по рекламным кампаниям.

Данные:
{json.dumps(campaigns_data, ensure_ascii=False, indent=2)}

Формат отчёта:
## Итоги недели
[3-4 ключевые цифры]

## Что работает
[топ-3 успешных вещи с цифрами]

## Что не работает
[топ-3 проблемы с цифрами]

## Действия на следующую неделю
[5 конкретных шагов с ожидаемым эффектом]

## Бюджет
[рекомендации по перераспределению]

Пиши как аналитик — конкретно, с цифрами, без воды."""
        }]
    )

    return response.content[0].text
```

---

## Практика

### Задача: создать 10 вариантов рекламного текста + провести анализ теста

**Часть 1: Генерация вариантов (15 минут)**

```python
# ad_generator.py

import anthropic
import json

client = anthropic.Anthropic()

def create_ad_batch(product_info: dict) -> list:
    """Создаёт батч рекламных объявлений для тестирования"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=3000,
        messages=[{
            "role": "user",
            "content": f"""Создай 10 вариантов рекламных объявлений для Facebook.

ПРОДУКТ: {product_info['name']}
ОПИСАНИЕ: {product_info['description']}
ЦЕНА: {product_info['price']}
АУДИТОРИЯ: {product_info['audience']}
ГЛАВНАЯ ВЫГОДА: {product_info['main_benefit']}
БОЛЬ АУДИТОРИИ: {product_info['pain_point']}

Создай по 2 варианта для каждого подхода:
1. Страх потери ("если не сделаешь X, то потеряешь Y")
2. Выгода ("получи X и сэкономь Y")
3. Социальное доказательство ("1000 клиентов уже...")
4. Любопытство ("Знаете ли вы, что...")
5. Прямое предложение ("Купить X за Y прямо сейчас")

Формат JSON:
[{{
    "id": 1,
    "approach": "название",
    "headline": "до 40 символов",
    "text": "до 125 символов",
    "cta": "кнопка",
    "image_direction": "что должно быть на картинке"
}}]"""
        }]
    )

    return json.loads(response.content[0].text)

# Запускаем для вашего продукта
my_product = {
    "name": "Онлайн-школа английского для IT-специалистов",
    "description": "Английский для работы в международных командах за 3 месяца",
    "price": "9,900 рублей/месяц",
    "audience": "Разработчики и IT-специалисты 25-40 лет",
    "main_benefit": "Пройти интервью в Google, Netflix, Spotify",
    "pain_point": "Знаю технический английский но теряюсь на встречах с иностранцами"
}

ads = create_ad_batch(my_product)

print("=== СГЕНЕРИРОВАННЫЕ ОБЪЯВЛЕНИЯ ===\n")
for ad in ads:
    print(f"#{ad['id']} — {ad['approach']}")
    print(f"Заголовок: {ad['headline']}")
    print(f"Текст: {ad['text']}")
    print(f"CTA: {ad['cta']}")
    print(f"Картинка: {ad['image_direction']}")
    print()
```

**Часть 2: Анализ результатов теста (25 минут)**

После запуска теста вводим данные и получаем анализ:

```python
# Вводим реальные данные после 5 дней теста
test_data = [
    {"id": 1, "approach": "Страх потери", "impressions": 8500, "clicks": 102, "conversions": 4, "spend": 180},
    {"id": 2, "approach": "Страх потери 2", "impressions": 8200, "clicks": 115, "conversions": 5, "spend": 175},
    {"id": 3, "approach": "Выгода", "impressions": 8800, "clicks": 185, "conversions": 12, "spend": 182},
    {"id": 4, "approach": "Выгода 2", "impressions": 8600, "clicks": 172, "conversions": 10, "spend": 178},
    {"id": 5, "approach": "Соц.доказательство", "impressions": 8300, "clicks": 166, "conversions": 11, "spend": 176},
    {"id": 6, "approach": "Соц.доказательство 2", "impressions": 8700, "clicks": 143, "conversions": 8, "spend": 181},
    {"id": 7, "approach": "Любопытство", "impressions": 9100, "clicks": 228, "conversions": 7, "spend": 185},
    {"id": 8, "approach": "Любопытство 2", "impressions": 8900, "clicks": 214, "conversions": 6, "spend": 183},
    {"id": 9, "approach": "Прямое предложение", "impressions": 8400, "clicks": 126, "conversions": 9, "spend": 177},
    {"id": 10, "approach": "Прямое предложение 2", "impressions": 8600, "clicks": 138, "conversions": 8, "spend": 179}
]

analysis = analyze_ab_test(test_data)
print(analysis["analysis"])
```

---

## Инструменты и ресурсы

- **Meta Business Manager** — business.facebook.com (для запуска рекламы)
- **Google Ads** — ads.google.com
- **Adspirer MCP** — инструмент анализа рекламы через Claude
- **Flux** — bfl.ai, сайт Black Forest Labs (генерация баннеров по промпту)
- **Meta Ads Library** — facebook.com/ads/library (смотреть рекламу конкурентов)
- **Google Keyword Planner** — планировщик ключевых слов
- **Anthropic SDK** — для интеграции Claude в рекламные воркфлоу; названия моделей в коде даны на октябрь 2026, актуальные цены и версии: [Актуальное сейчас](https://aimayak.com/ru/now/)

---

## Ключевые выводы

> Реклама — это всегда тест. Кто тестирует больше вариантов — побеждает. Claude делает тестирование дешёвым: 50 вариантов вместо 5, за минуты вместо дней.
>
> Анализ данных — узкое место в большинстве рекламных команд. Claude убирает это узкое место: видит все метрики одновременно, не теряется в таблицах, даёт конкретный вывод с обоснованием.
>
> Главное правило: Claude пишет тексты и анализирует данные, но запускает и масштабирует рекламу человек. Окончательное решение всегда за вами — AI ускоряет путь к этому решению.

---

## Следующий урок

→ [Sales AI — квалификация лидов, follow-up, закрытие сделок](93-sales-ai.md)
