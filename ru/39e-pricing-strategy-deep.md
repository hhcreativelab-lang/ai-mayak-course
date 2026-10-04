# Цена AI-продукта — от ценности для клиента, тарифы и упаковка

**Время:** ~35 мин теории + 60 мин практики

Суммы, проценты и тарифные лесенки в этом уроке — условные примеры для объяснения метода, а не рыночная статистика и не прогноз дохода. Свои цифры считай по своему рынку и своим клиентам; базовую версию для новичка см. в уроке [Как назначить цену](d02-pricing-simple.md).

---

## Суть урока

Pricing — не "сколько стоит". Это сигнал value, фильтр клиентов, и source revenue. Три функции в одной цифре.

Большинство фаундеров боятся цены. "Поставлю \$9, чтобы хоть кто-то купил" — и потом два года не могут поднять. Конкуренты ставят \$99 за тот же функционал и получают **заметно больше денег** при том же количестве клиентов. А ещё — лучших клиентов. А ещё — выше retention.

Цена — это не последний шаг в продукте. Это **первый сигнал** который клиент видит после description. \$9 говорит "это игрушка". \$999 говорит "это серьёзный инструмент". То что внутри одинаковое — но восприятие, ожидания и поведение клиента **разные**.

Для AI-продуктов проблема острее: value часто 10-100x от cost. API стоит \$0.10, value клиенту — \$50. Поставишь \$0.20 (cost + margin) — оставишь \$49.80 на столе. Конкурент возьмёт.

В этом уроке разберём как считать pricing для AI-продукта правильно: value-based подход, 3-tier structure, психологические триггеры, как упаковать всё за 30 дней.

🎨 **Образ:** ресторан. Шеф ставит цену не "сколько стоят продукты + газ", а "сколько готов заплатить клиент за этот вечер". Стейк за \$80 не потому что мясо дороже — потому что атмосфера, бренд, ожидания. Тот же стейк в забегаловке стоит \$15. Продукт похожий — value разная — цена разная. AI-продукт работает так же.

---

## 🎯 Главный сдвиг: от cost-thinking к value-thinking

Самая дорогая ошибка в pricing — считать "снизу вверх": себестоимость → margin → цена. Это правильно для commodity (бензин, рис, гайки). Для AI-продукта — катастрофа.

Правильный подход — "сверху вниз": value клиенту → % от value → цена.

**Cost-thinking (плохо для AI):**
- "API стоит \$0.10, добавлю margin → \$0.20"
- Результат: pricing race to the bottom

**Value-thinking (правильно для AI):**
- "Клиент экономит \$5K/мес → adequate price 10-20% = \$500-1000/мес"
- Результат: устойчивая маржа, премиум-позиционирование

🎨 **Образ:** Uber vs такси по счётчику. Счётчик считает километры (cost). Uber считает что ты готов платить за быстрое решение в час пик (value). Поэтому Uber делает прибыль на том же маршруте где такси работает в ноль.

---

## Ключевые концепции

- **Value-based pricing** — цена = % от value которую клиент получает, не функция себестоимости
- **Tier structure** — 3 уровня (Starter / Pro / Business) которые ловят разные сегменты
- **Rule of 3x** — каждый tier ~3x от предыдущего (\$29 → \$99 → \$299)
- **Anchor pricing** — высокая опция первой, чтобы средняя казалась доступной
- **Decoy tier** — "плохой" вариант между good options, заставляет выбрать целевой
- **Grandfathering** — старые клиенты сохраняют старую цену при повышении (защита retention)
- **Usage-based vs flat** — pay-per-use vs fixed subscription, и hybrid между ними
- **Annual discount** — скидка за годовую предоплату (часто 15-20%), улучшает cashflow и retention
- **Freemium vs Free trial** — две разные модели входа, не одно и то же
- **Willingness to pay (WTP)** — максимум сколько клиент готов заплатить, твоя цена должна быть ниже

---

## Теория

### 3 базовые pricing models — и почему две из них опасны для AI

Любой pricing подход сводится к одной из трёх философий: считать снизу (cost), смотреть на соседей (competitive), или измерять что получает клиент (value). Для AI-продукта правильный ответ почти всегда третий — но важно понимать почему первые два плохо работают.

#### Model A: Cost-based — плохо для AI

Подход: "API стоит \$0.10, добавлю 100% margin → продаю за \$0.20".

**Проблема для AI:** value часто 10-100x cost. Если AI-инструмент экономит клиенту 10 часов работы (\$500-1000 value) — а ты pricing by cost ставишь \$5 — клиент **с удовольствием** заплатил бы \$100. Ты оставляешь \$95 на столе при каждой продаже.

**Когда cost-based уместен:**
- Commodity products (cloud hosting, raw API resale)
- Low differentiation (твой продукт = такой же как у 10 других)
- Volume play (берёшь объёмом, не маржой)

**Для AI-продуктов:** почти никогда. Differentiation в AI огромная — UX, prompts, integration, domain expertise. Это не commodity.

#### Model B: Competitive — опасно для AI

Подход: "ChatGPT Plus \$20/мес (на октябрь 2026), я тоже \$20/мес".

**Проблема:** copying не учитывает что value delivery разная. ChatGPT — general-purpose. Твой продукт может быть **в 10 раз ценнее** для узкой ниши. Или **в 10 раз менее ценным** для general use.

Pricing на основе конкурентов — это сигнал что у тебя нет своего понимания value.

**Когда competitive pricing уместен:**
- Late market entry с очевидно better/cheaper
- Direct alternative (твой продукт делает то же самое, но лучше один параметр)
- Forced positioning ("мы на 50% дешевле X")

**Для AI-продуктов:** редко. Большинство AI-продуктов целятся в новый use case или специфическую нишу, где прямого сравнения нет.

#### Model C: Value-based — правильно для AI

Подход: измеряем value клиенту → берём 10-20% от value как цену.

**Логика:**
- Клиент получает value на \$5K/мес → готов платить \$500-1000/мес
- Это "easy yes" — clear ROI, payback за 1-2 недели использования
- Маржа высокая (cost \$50-100, выручка \$500-1000)
- Клиент счастлив (он экономит \$4000-4500 net)

**Это и есть AI pricing в 2026.** Многие успешные AI SaaS работают по этой модели: цена привязана к ценности для клиента.

🎨 **Образ:** хирург vs терапевт. Терапевт берёт \$50 за приём (rate market). Хирург берёт \$50K за операцию которая спасает жизнь — потому что value несравнима с rate. AI часто = "хирург": решает дорогую проблему быстро. Pricing должен это отражать.

---

### Value-based pricing — 4 шага

Теория ясна. Теперь как практически посчитать.

#### Step 1: Quantify value клиента

Value бывает четырёх типов. Для каждого AI-продукта обычно работают 1-2.

**Time saved (самый частый для AI):**
- Сколько часов в месяц клиент экономит благодаря твоему продукту?
- Умножить на hourly rate клиента (или его сотрудников)
- Результат: \$value/мес от time savings

**Пример:** AI пишет 50 emails вместо человека. Каждый email = 15 мин ручной работы. 50 × 15 = 12.5 часов/мес. Hourly rate junior marketer = \$40. Value = 12.5 × \$40 = **\$500/мес**.

**Revenue uplift:**
- % увеличения revenue которое продукт даёт
- × текущий revenue клиента
- Результат: \$value/мес от revenue boost

**Пример:** AI sales tool увеличивает conversion на 5%. Клиент делает \$20K/мес sales. Uplift = \$1000/мес. Value = **\$1000/мес**.

**Cost reduction:**
- % снижения существующих costs
- × текущие costs клиента
- Результат: \$value/мес savings

**Пример:** AI customer support снижает поддержку на 30%. Клиент тратит \$10K/мес на саппорт. Reduction = \$3K/мес. Value = **\$3000/мес**.

**Quality improvement (harder to quantify, но real):**
- Снижение risk (юр. нарушений, churn, etc.)
- Better customer experience
- Brand reputation

Этот type сложнее в цифры, но не игнорируй — для enterprise часто решающий.

#### Step 2: Position в value range

Когда знаешь value — выбираешь % от него как pricing.

| Позиция | % value | Когда выбирать |
|---------|---------|----------------|
| **Conservative** | 10% | "Easy yes" для customer, low friction sale, self-serve product |
| **Standard** | 15% | Правильный balance, default для B2B SaaS |
| **Premium** | 20% | Best customers, premium positioning, custom support |

**Пример:** value \$3K/мес.
- Conservative: \$300/мес
- Standard: \$450/мес
- Premium: \$600/мес

Для нового продукта без proof — стартуй conservative (\$300). Когда накопишь cases — поднимешь до standard или premium.

**Не бери больше четверти value (эмпирическое правило, не закон).** Дальше клиент начинает считать ROI слишком долгим.

**Не бери совсем мало (<5% value).** Это signal что продукт не serious, плюс маржа не выдержит support overhead.

#### Step 3: Tier structure (3 tiers always)

Один tier — это потерянные деньги. Распространённый совет по SaaS-ценам: **минимум 3 tiers**.

Логика (условное распределение, у тебя будет своё):
- меньшая часть клиентов выберет Starter (low-touch, price-sensitive)
- большинство выберет Pro (main offering, balance value/price)
- небольшая часть выберет Business (enterprise feel, high WTP)

Без top tier — теряешь часть revenue сверху. Без bottom tier — теряешь mass market entry.

**Стандартная структура:**

| Tier | Назначение | Customer |
|------|-----------|----------|
| **Starter** | Minimum viable | Individual / small team |
| **Pro** | Main offering | Growing business |
| **Business / Scale** | Premium с custom | Enterprise / power user |

Иногда добавляют 4-й tier **Enterprise** (custom pricing, sales-led). Но это поверх 3 base tiers.

#### Step 4: Test in market

Pricing — не fixed forever. Это iterating system.

**Launch playbook:**
1. Поставь начальный pricing (по value calculation)
2. Track 30-60 дней: conversion rate, churn rate, revenue per customer, support load
3. Iterate: если conversion очень низкий — снизь цену или улучши предложение. Если все клиенты выбирают top tier — подними цены.
4. Repeat каждые 6-12 месяцев

**Сигналы что pricing слишком низкий:**
- Все клиенты говорят "это дёшево"
- 0 churn (даже плохие клиенты не уходят)
- Conversion подозрительно высокий (слишком easy yes)
- Низкое восприятие продукта в reviews

**Сигналы что pricing слишком высокий:**
- Conversion очень низкий
- Trial-to-paid очень низкий
- Sales calls затягиваются на price negotiation
- Churn концентрирован в первые 30 дней

---

### Tier design framework

Дизайн tiers сам по себе — наука. Плохой дизайн = клиенты не понимают какой выбрать, выбирают самый дешёвый или не покупают вообще.

#### Bad tier design — anti-patterns

**Antipattern 1: tiers слишком близко**
- Starter \$9 / Pro \$19 / Business \$29
- Проблема: все выберут Pro (small step up), Business не оправдан, Starter "что я теряю".

**Antipattern 2: tiers слишком далеко**
- Free / \$9 / \$99
- Проблема: gap между \$9 и \$99 пугает, клиент не понимает что внутри.

**Antipattern 3: feature scatter**
- Random фичи в каждом tier без логики прогрессии
- Проблема: клиент не понимает что получает.

**Antipattern 4: too many tiers**
- 6 tiers с разными опциями
- Проблема: decision paralysis. Клиент уходит "подумать".

#### Good tier design — rule of 3x

Каждый tier ~3x от предыдущего по цене. Этого достаточно чтобы клиент видел чёткое различие, но не пугался.

**Пример (SaaS B2B):**

| Tier | Цена | Users | Features | Limits |
|------|------|-------|----------|--------|
| **Starter** | \$29/мес | 1 user | Basic features | 1K AI requests/мес |
| **Pro** | \$99/мес | 5 users | All features + priority support | 10K AI requests/мес |
| **Business** | \$299/мес | Unlimited | All features + dedicated CSM + integrations | 100K AI requests/мес |
| **Enterprise** | Custom (≥\$2K/мес) | Unlimited | All features + SLA + custom contracts | Unlimited |

Заметь:
- \$29 → \$99 → \$299: rule of 3x работает
- Features добавляются прогрессивно (не random)
- Limits 10x growth каждый tier
- Enterprise — открытый верх, sales-led

#### Decoy tier — психологический трюк

Иногда добавляют tier чтобы **подтолкнуть** к целевому.

**Пример:** ты хочешь чтобы большинство выбрало Pro \$99. Создаёшь:
- Starter \$29 (basic)
- Pro \$99 (target)
- Business \$99/year (то же что Pro, но annual) — DECOY

Клиент видит "за те же \$99 я могу взять Pro или Business" → выбирает Pro (monthly flex) или Business (annual savings).

Менее цинично — decoy просто помогает customer decision. Не злоупотребляй.

---

### Pricing levers — что варьировать

В рамках value-based + 3 tiers есть **lever'ы** которые меняют как именно ты pricing'уешь.

| Lever | Effect | When use |
|-------|--------|----------|
| **Per-user** | Scales с team size | Collaboration tools (Slack, Notion) |
| **Per-usage** | Scales с consumption | AI API, voice minutes, transactions |
| **Flat monthly** | Simple, predictable | SaaS standard (Spotify, Netflix) |
| **Annual discount** | Improves cash + retention | 10-20% off если pay yearly |
| **Free trial** | Lower friction | Self-serve products |
| **Freemium** | Land + expand mass market | Mass adoption play (Notion, Figma) |
| **Custom enterprise** | Capture high WTP | Top 5-10% prospects |

**Hybrid обычно лучше pure model:**
- Pure per-usage пугает клиента ("сколько будет?")
- Pure flat не масштабируется с large users
- **Hybrid:** base subscription + overage за heavy usage

🎨 **Образ:** мобильный тариф. Pure per-minute = страшно звонить (счётчик капает). Pure unlimited = переплата для тех кто мало звонит. Hybrid (X минут включено, дальше per-minute) = best of both. AI pricing работает так же.

---

### AI-specific pricing nuances

Pricing для AI-продукта имеет свои подводные камни которые не встречаются в традиционном SaaS.

#### Usage-based pricing trap

Если брать плату за каждый "request", клиенты часто **боятся** делать запросы ("будет дорого"). Используют меньше → получают меньше value → уходят.

**Решение:** hybrid. Базовая subscription (включено N requests/мес) + overage для тех кто превышает. Клиент знает свой floor, не боится использовать, ты получаешь предсказуемый revenue.

#### Token transparency dilemma

Показывать "tokens" на pricing page? Дилемма:
- Show: техническая аудитория понимает, не-техническая теряется
- Hide: чёрный ящик, недоверие
- **Compromise:** показывай "AI requests" или "credits" вместо tokens. Понятно всем.

**Пример:** "10,000 AI requests/мес ≈ 500 long emails + 200 code reviews".

#### Cost variance (важно для AI)

Some users use 100x more than others. Если single-tier flat pricing — power users eat твою margin.

**План для outliers:**
- Hard cap (после X usage — service degrades или stops)
- Per-usage overage (мягче, но непредсказуемо для клиента)
- Tier upgrade prompt ("вы используете много, переходите на Pro?")

Многие AI-сервисы используют лимиты по использованию с прозрачным communication. Это окей если лимит разумный.

---

### Как собрать свои pricing benchmarks

Хочешь sanity check своих цен? Построй свою таблицу из публичных страниц цен конкурентов в твоей нише. Цены на AI-продукты меняются каждые несколько месяцев, поэтому готовой таблицы с цифрами здесь нет.

| Product type | Starter | Pro | Enterprise |
|--------------|---------|-----|-----------|
| AI writing tool | заполни | заполни | заполни |
| AI coding tool | заполни | заполни | заполни |
| AI customer support | заполни | заполни | заполни |
| AI sales tool | заполни | заполни | заполни |
| Voice AI | заполни (за минуту) | заполни | Custom |
| AI consulting retainer | заполни | заполни | заполни |

Как заполнять: возьми 5-10 прямых конкурентов, открой их страницы цен, запиши цены трёх tiers и дату проверки. Пример свежих цен на AI-ассистентов и API: [Актуальное сейчас](https://aimayak.com/ru/now/).

**Используй как ориентир, не как закон.** Твой value может быть выше или ниже — pricing должен это отражать.

---

### Психологические триггеры — что работает 2026

Pricing — это не только математика. Психология восприятия заметно влияет на conversion.

**Ending in 9 (charm pricing)**
- \$29 perceived ниже чем \$30 (мозг видит "20-something")
- Работает в B2C consistently
- В B2B менее значимо (но не вредит)

**Anchor (high-end first)**
- Показывай Enterprise tier первым на странице
- Средний tier ощущается доступным
- Используй "Most popular" badge на target tier

**Decoy (asymmetric option)**
- "Плохой" tier между good options заставляет выбрать целевой
- Работает осторожно — не злоупотребляй

**Bundle**
- "All-included" psychologically проще чем per-feature
- Клиент не хочет считать "нужна ли мне эта фича"
- Простота побеждает на pricing page

**Money-back guarantee**
- "30-day money back" снижает risk perception
- Обычно повышает conversion
- Актуальные возвраты редки, если продукт хорош (давай гарантию только если готов вернуть деньги)

**Annual discount visualization**
- "Pay \$299 yearly, save \$89" сильнее чем "\$25/мес"
- Показывай savings явно
- Default monthly, highlight annual

---

### Annual pricing strategy

Annual subscription — топовый lever для cashflow и retention. Но требует осторожности.

**Стандартная скидка:** 15-20% off для annual.

**Plus side:**
- Cashflow: получаешь \$X×10 сегодня вместо \$X каждый месяц
- Retention: psychological commitment, churn обычно ниже
- LTV: customer lifetime value растёт

**Minus side:**
- Lock-in feels like commitment (hurts trial conversion)
- Refunds сложнее (annual paid, partial refund process)
- Pricing changes сложнее (annual customers ждут конца term)

**Compromise:**
- Default: monthly
- Annual visible с явной savings ("Save \$89/year")
- Allow upgrade monthly → annual в любой момент

Не делай annual-only (вырезает часть addressable market — клиентов, которые хотят попробовать без commitment).

---

### Pricing changes — как поднимать цены

Через 12-18 месяцев ты захочешь поднять цены. У тебя больше features, кейсов, бренд. Это нормально.

**Playbook:**

**1. Grandfather existing customers**
- Старые клиенты сохраняют старую цену (forever или на 2 года)
- Это builds loyalty + предотвращает churn waves
- Risk: они никогда не upgrade. Окей.

**2. Announce 30-60 days ahead**
- Email + in-app notice
- Объясняй "почему" (new features, more value)
- НЕ говори "we raised prices" — говори "we added X, new pricing reflects value"

**3. Frame as more value**
- New tier с дополнительными features
- Old features всё ещё доступны в существующем tier
- New signups идут на new pricing

**4. Test new pricing on new signups first**
- 30-60 дней A/B (new signups видят new prices)
- Measure conversion + churn impact
- Adjust before full rollout

**5. Communicate value before price**
- В email start с "what's new" (3 features)
- Pricing change в самом конце письма
- Это контекст, не announcement

🎨 **Образ:** ремонт квартиры. Не говоришь арендаторам "плачу больше". Говоришь "сделал ремонт, новая кухня, ванная — поэтому новая цена". Восприятие меняется кардинально.

---

### Common pitfalls

7 ошибок которые делают многие фаундеры — и которые стоят им денег.

❌ **Pricing too low "to start"**
- Слишком низкая цена для B2B = no perceived value
- Клиенты сами говорят "это дёшево, наверное plохо"
- Поднять потом сложно (см. grandfathering)

❌ **Pricing too high без proof**
- Price = expectations. \$999/мес → клиент ожидает enterprise support
- Если не можешь deliver — churn + bad reviews
- Поднимай вместе с product maturity

❌ **Free tier даёт слишком много**
- Если free решает 80% проблемы — нет incentive upgrade
- Free должен быть **trailer** (5-10% capability) для paid
- Notion, Figma — отличные balanced free tiers

❌ **Custom pricing для всех**
- Сильно замедляет sales cycle
- Self-serve impossible
- Используй custom **только** для top 5% (>\$2K/мес)

❌ **Changing pricing часто**
- Каждые 3 месяца = confusion + churn
- Максимум 1-2 изменения в год
- Документируй "why" для transparency

❌ **Annual without monthly option**
- Режет addressable market
- Новые клиенты хотят попробовать без commitment
- Always offer both

❌ **Not raising prices за 2 года**
- Инфляция сама по себе создаёт разрыв
- Looks cheap (signal: low quality / dying product)
- Raise minimum 1x per year

---

### A/B testing pricing — осторожно

A/B testing на pricing — это не как A/B на UI. Высокий риск.

**НЕ делай:**
- Одновременно показывать разные цены разным customers на одной странице
- PR risk: кто-то screenshot'нет, Twitter scandal
- Trust damage

**Делай instead:**
- **Sequential A/B**: 30 days price X, 30 days price Y, compare
- **Cohort A/B**: new signups Cohort A видят old price, Cohort B видят new (transparent — "limited time pricing")
- **Page-level A/B**: разные landing pages → разные pricing pages (когда traffic source очевидно разный)

**Measure комбинированно:**
- Conversion alone misleading (low price → high conversion → low revenue)
- Revenue per visitor = main metric
- Plus: 30-day churn, NPS, support load

**Тестируй one variable at a time:**
- Меняй только цену (не цвет кнопки + цена одновременно)
- Если меняешь несколько — не поймёшь что сработало

---

### Audience рейтинг — где ты сейчас

В зависимости от уровня — разная стратегия pricing.

**Новичок (первый продукт, до 100 paying customers):**
- Simple 3-tier с annual option
- Условные starting points: \$29 / \$99 / \$299 (подбери под свою нишу)
- Skip A/B testing (мало data)
- Skip custom enterprise (тратишь время)
- Focus: get to product-market fit, не optimize pricing yet

**Средний (100-1000 customers, established product):**
- Value-based pricing с quantified \$value/мес
- Usage tracking (cohort analysis)
- A/B testing pricing на new signups
- Consider freemium если mass market play
- Annual + monthly options

**Профессионал (1000+ customers, expanding):**
- Dynamic enterprise pricing с sales team
- Multi-product bundles (cross-sell)
- Custom contracts для top 10%
- Pricing committee quarterly review
- Considered repricing raises (на сколько — решай по данным)

---

## Практика

### Шаг 1: Quantify value клиента (90 минут)

Возьми лист бумаги или Notion doc. Ответь на 4 вопроса:

**1. Какой type value доминирует?**
- Time saved
- Revenue uplift
- Cost reduction
- Quality improvement

Выбери top 1-2.

**2. Quantify в долларах:**

```
Time saved formula:
Hours saved/month × Hourly rate = $value/month

Revenue uplift formula:
% increase × Current revenue = $value/month

Cost reduction formula:
% reduction × Current cost = $value/month
```

**3. Conservative estimate:**

Возьми **низкую** оценку (не optimistic). Лучше undersell value в pricing — overdeliver в реальности.

**4. Document с источником:**

Не "ну, наверное \$5K/мес". А "по интервью с 5 customers: avg time saved 12 hours/мес × \$50/hour = \$600/мес".

**Output:** документ "Customer value analysis" с конкретной \$value цифрой.

---

### Шаг 2: Design 3-tier structure (60 минут)

Используй template:

```markdown
# Pricing Tiers — [Product Name]

## Tier 1: Starter — $[X]/мес
**Target:** Individual / small team trying out
**Limit reasoning:** [почему именно эти limits]

Features:
- [Feature 1]
- [Feature 2]
- [Feature 3]

Limits:
- [N] users
- [N] AI requests/мес
- [Storage / data / etc]

Support: Email (48h response)

## Tier 2: Pro — $[3X]/мес ← TARGET (большинство выберет это)
**Target:** Growing business, main offering
**Limit reasoning:** [почему]

Features:
- Everything in Starter +
- [Feature 4]
- [Feature 5]
- [Feature 6]

Limits:
- [N] users (5-10x Starter)
- [N] AI requests/мес (10x Starter)
- Priority support

Support: Email + Slack (24h response)

## Tier 3: Business — $[9X]/мес
**Target:** Enterprise / power users
**Limit reasoning:** [почему]

Features:
- Everything in Pro +
- [Feature 7]
- [Feature 8]
- Custom integrations
- Dedicated CSM

Limits:
- Unlimited users
- [N] AI requests/мес (10x Pro)

Support: Dedicated CSM + Slack channel

## Tier 4 (optional): Enterprise — Custom
**Target:** Top 5-10% prospects
- Custom contract
- SLA
- Sales-led
- Min commitment: $[2X-5X annually]
```

**Sanity check:**
- Rule of 3x работает? (Starter × 3 ≈ Pro × 3 ≈ Business)
- Каждый tier чёткий step up в value (не random features)?
- Limits растут 5-10x между tiers?
- Target tier (Pro) явно лучший value?

---

### Шаг 3: Build pricing page (120 минут)

Pricing page — это **conversion page**, не info dump. 7 elements обязательны.

```markdown
# Pricing Page Checklist

## 1. Hero section
- [ ] Single H1: "Pricing that scales with you" (или похожее)
- [ ] Subheadline: value statement (NOT feature list)
- [ ] Toggle Monthly / Annual (annual = 20% off)

## 2. 3 pricing cards
- [ ] Starter card
- [ ] Pro card (с "Most Popular" badge)
- [ ] Business card

Per card:
- [ ] Tier name
- [ ] Price (large)
- [ ] Short value statement (1 line)
- [ ] Feature list (5-7 items, не больше)
- [ ] CTA button ("Start free trial" / "Contact sales")

## 3. Enterprise CTA
- [ ] "Need more? Contact sales" link
- [ ] Custom requirements ("100+ users, custom integration")

## 4. Trust signals
- [ ] "30-day money-back guarantee" (только если готов её выполнять)
- [ ] Customer logos (3-5, только реальные клиенты с их согласия)
- [ ] Testimonials (1-2 на pricing page, только настоящие)

## 5. FAQ section (5-7 questions)
- [ ] Can I change plans?
- [ ] What payment methods?
- [ ] How does usage work?
- [ ] Can I cancel anytime?
- [ ] Is there a free trial?
- [ ] Do you offer non-profit / education discount?
- [ ] What's your refund policy?

## 6. Feature comparison table
- [ ] Detailed table all features × all tiers
- [ ] Help users compare specifically
- [ ] Use checkmarks для clarity

## 7. Footer
- [ ] Contact sales link
- [ ] Help / docs link
- [ ] Money-back guarantee restate
```

**Pro tip:** look at Linear, Notion, Figma pricing pages. Они оптимизировали это годами — копируй structure (не price). Цены на их страницах меняются, смотри актуальные.

---

### Шаг 4: Test pricing — 30-day plan

После launch — собираешь data.

**Week 1-2: Baseline**
- Track conversion (visitors → trial → paid)
- Track tier distribution (% Starter / Pro / Business)
- Track 1-on-1 calls с trial users — слушай objections

**Week 3-4: Iterate**
- Если conversion очень низкий — пересмотри цену Starter и предложение
- Если почти все берут Starter — увеличь gap (Starter limits жёстче)
- Если 0 идут на Business — improve Business value statement
- Sales objections повторяются 3+ раз? → adjust

**Day 30: Review**

Условные targets для первого сравнения; свои возьми из своих данных.

| Metric | Target (условно) | Action if low |
|--------|--------|---------------|
| Visitor → Trial | 5-10% | Improve pricing page copy |
| Trial → Paid | 15-25% | Improve onboarding |
| Pro selection | 50-65% | Adjust tier balance |
| Monthly churn | <5% | Improve product / support |

---

### Шаг 5: Document pricing decisions

Создай `pricing.md` в проекте:

```markdown
# Pricing — Decision Log

## Current pricing (vYYYY-MM)
- Starter: $29/мес
- Pro: $99/мес
- Business: $299/мес
- Annual: 20% off

## Reasoning
- Customer value avg $700/мес (from 5 interviews)
- Pricing 15% of value = $105 target
- Rounded to $99 (charm pricing)
- 3x rule: $29 → $99 → $299 ✓

## A/B tests history
- [Date]: Tested $79 vs $99 Pro → $99 won on revenue
- [Date]: Tested $29 vs $39 Starter → $29 won on conversion

## Pricing changes
- [Date]: Initial launch
- [Date]: Added Business tier
- [Date]: Raised from $19/79/199 to $29/99/299

## Next review
- [Date]: Quarterly pricing committee
```

Это становится твоим pricing memory — через год не помнишь почему именно \$99.

---

## Чеклист готовности

✅ **Value клиента quantified** (\$X/мес с источником интервью)
✅ **3 tiers designed** с rule of 3x (\$29/\$99/\$299 или аналог)
✅ **Tier features mapped** (что в каждом, прогрессивно)
✅ **Annual discount calculated** (15-20% off, явно visible)
✅ **Pricing page live** с 7 elements (hero, cards, trust, FAQ, comparison, CTA)
✅ **Money-back guarantee** announced (30 дней default)
✅ **A/B testing plan** ready (sequential, не одновременно)
✅ **Pricing.md** documented с decision log
✅ **30-day review** scheduled (conversion, tier distribution, churn)
✅ **Grandfather policy** decided (для будущих повышений)

Если 8/10 — готов к launch. Если меньше 6/10 — вернись к Step 1.

---

## Инструменты и ресурсы

- **[Stripe Pricing Page](https://stripe.com/pricing)** — пример hybrid pricing (per-use + flat)
- **[Linear Pricing Page](https://linear.app/pricing)** — clean tier example
- **[Notion Pricing Page](https://www.notion.com/pricing)** — freemium + tiers reference
- **[Цены на AI-ассистентов и API](https://aimayak.com/ru/now/)** — актуальные цифры для твоих расчётов маржи
- **Books:** "Monetizing Innovation" (Madhavan Ramanujam), "Pricing Done Right" (Tim Smith)

---

## Ключевые выводы

> Pricing — это не "сколько стоит". Это сигнал value (что клиент ожидает), фильтр клиентов (кого пускаешь), и source revenue (сколько зарабатываешь). Три функции в одной цифре. Занижение цены "чтобы хоть кто-то купил" — потерянный бизнес.

> Value-based pricing — единственно правильный путь для AI. Cost-based оставляет деньги на столе, competitive игнорирует твою differentiation. Quantify value (\$X/мес savings/uplift/reduction), бери 10-20% от него. Это и есть AI pricing 2026.

> 3 tiers обязательно, rule of 3x (\$29 → \$99 → \$299 как условный пример). Один tier теряет часть рынка сверху и снизу. Pro tier — main offering, большинство выберет его. Starter — entry, Business — premium.

> Hybrid pricing бьёт pure model. Pure usage-based пугает клиента ("сколько будет?"), pure flat не scales. База subscription + overage для heavy users = predictable + scalable. Mobile tariff pattern работает для AI.

> Annual + grandfathering = сильный инструмент retention. Скидка за annual → cashflow + commitment + обычно ниже churn. Grandfather existing customers при повышении → loyalty и меньше churn waves.

> A/B testing на pricing — sequential, не одновременно. Никогда не показывай разные цены одновременно (PR risk). 30 days price X, 30 days price Y, compare revenue per visitor (не conversion alone).

---

## Cross-references

- [Ценообразование](39-monetization-pricing.md) — введение в pricing models
- [Реальные кейсы монетизации](47-monetization-cases.md) — pricing examples
- [Unit Economics AI-стека](99b-unit-economics-deep.md) — LTV / CAC / payback period detail
- [Funnel Design для AI products](42b-funnel-design-ai-products.md) — pricing page внутри funnel

---

## Следующий урок

→ [MCP Builder: создание собственного MCP сервера](40-mcp-builder.md)
