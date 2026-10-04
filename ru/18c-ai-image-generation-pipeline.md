# Картинки с помощью AI в 2026 — Midjourney, ChatGPT Images, Flux, Recraft, Ideogram

**Модуль:** Технические инструменты | **Время:** ~25 мин теории + 35 мин практики

---

## Суть урока

AI image generation в 2026 — это камера в смартфоне 2010 года. Каждый может нажать кнопку и получить картинку. Но разница между "фоткой" и "фотографией" — в технике, понимании инструмента и постобработке.

5 главных направлений рынка делят пирог по специализациям. Midjourney — художник. ChatGPT Images — универсал, который уже под рукой. Flux — открытые модели и скорость. Recraft — векторщик. Ideogram — типограф. Универсального чемпиона нет. Профессионал держит 2-3 инструмента в pipeline и знает который где сильнее.

В этом уроке разберём честно: ориентиры по ценам, профессиональные workflows для разных задач, юридические подводные камни и анти-паттерны которые отличают "AI-картинку" от продакшн-готового материала.

Предупреждение: этот рынок меняется быстрее остальных. Названия версий и условия в уроке даны на октябрь 2026, а актуальные цены и версии смотри на странице [Актуальное сейчас](https://aimayak.com/ru/now/) и в [каталоге инструментов](https://aimayak.com/ru/tools/). Если без цифры пример не работает, она стоит с пометкой даты, в остальных местах цена заменена на ссылку на прайс сервиса.

🎨 **Образ:** кухня хорошего ресторана. У шефа не один универсальный нож — у него набор. Нож для рыбы, нож для овощей, тесак для костей. Можно резать всё одним — но медленно и плохо. То же самое с image gen: один инструмент на все случаи = посредственный результат везде.

---

## 🎯 Decision tree: какую модель выбрать

Главный вопрос — **не "какой инструмент лучше"**, а "что я делаю и для какой платформы".

**Берёшь Midjourney если:**
- ✓ Художественный контент, иллюстрации, концепт-арт
- ✓ Mood boards, обложки YouTube с артистичным стилем
- ✓ Готов работать через веб-интерфейс по подписке (раньше основным способом был Discord)
- ✓ Качество важнее скорости итераций

**Берёшь ChatGPT Images (модели GPT Image) если:**
- ✓ Фотореализм + текст в изображении
- ✓ Уже пользуешься ChatGPT (базовый режим генерации есть и на бесплатном тарифе)
- ✓ Нужен простой API без танцев с настройками
- ✓ Quick mockups для презентаций

**Берёшь Flux если:**
- ✓ Скорость и объём (100+ изображений в день)
- ✓ Photorealism с фотографической точностью
- ✓ Нужны открытые веса или запуск у себя (мощная видеокарта)
- ✓ Лицензию проверишь заранее: у разных моделей Flux она разная

**Берёшь Recraft если:**
- ✓ Логотипы, векторная графика, иконки
- ✓ Brand identity, инфографика
- ✓ Нужны SVG на выходе
- ✓ Текст-в-изображении профессионального уровня

**Берёшь Ideogram если:**
- ✓ Постеры, реклама, social media ads с типографикой
- ✓ Длинный текст в изображении (несколько строк)
- ✓ Минимальный бюджет (есть бесплатный тариф)

**По умолчанию — связка Flux + Ideogram + Recraft закрывает большинство задач.** Midjourney если нужна артистичность, ChatGPT Images если уже пользуешься ChatGPT.

🎨 **Образ:** автомобильный парк. Тебе не нужен один универсальный автомобиль на все случаи. Нужны: грузовик (Flux — объём), седан (ChatGPT Images — комфорт), внедорожник (Midjourney — артистичность), фургон (Recraft — спецзадачи).

---

## Ключевые концепции

- **Diffusion model** — нейросеть которая учится восстанавливать изображение из шума. На этом принципе построены многие генераторы картинок
- **Prompt engineering** — искусство формулировать запрос так чтобы модель выдала желаемое. От промпта зависит очень многое
- **Aspect ratio (AR)** — пропорции выходного изображения. 16:9 для YouTube, 9:16 для Reels/TikTok, 1:1 для Instagram, 4:5 для FB
- **Seed** — число определяющее randomness. Одинаковый prompt + одинаковый seed = одинаковый результат
- **Style reference (sref)** — изображение-эталон с которого модель копирует стиль
- **Character reference (cref)** — изображение-эталон для сохранения внешности персонажа между генерациями
- **Inpainting** — редактирование части изображения сохраняя остальное
- **Outpainting** — расширение изображения за границы (extend canvas)
- **Negative prompt** — описание того что НЕ должно быть на изображении
- **Guidance scale (CFG)** — насколько строго модель следует промпту. Ориентиры: 7-8 для photorealism, 4-6 для creative (зависят от модели, не у всех сервисов этот параметр есть)

---

## Теория

### 5 главных направлений рынка 2026

#### Midjourney V8

Старейший и наиболее узнаваемый игрок. Делает упор на художественное качество. В июле 2026 вышла V8.2 (24.07.2026): доработаны эстетика и персонализация под твой вкус. Начиная с V8 есть режим HD с нативным разрешением 2K и выше и более точный текст в кадре; есть Edit Model для правок по референсам, а из картинок можно делать короткие видео.

**Цена (на октябрь 2026):** подписка стартует примерно с $10 в месяц (тариф Basic). Более высокие тарифы дают больше быстрого GPU-времени и скрытые генерации (stealth mode). Бесплатного тарифа нет. Режим HD и часть функций расходуют больше GPU-времени. Точные тарифы: [https://www.midjourney.com/account](https://www.midjourney.com/account)

**Workflow:** веб-интерфейс по подписке. Раньше основным способом был Discord-бот со slash-командами `/imagine`, `/blend`, `/describe`; параметры вроде `--ar` пишутся в конце запроса.

**Сильные стороны:**
- Сильная художественная стилизация
- Референсы стиля и персонажа для консистентности
- Огромная community с пресетами
- Stealth mode на старших тарифах — твои генерации не видны публично

**Слабые стороны:**
- Нет официального публичного API (проверь актуальность на сайте сервиса)
- Текст в изображениях лучше, чем раньше, но для типографики надёжнее Ideogram
- Сложно итерировать через скрипты
- Интерфейс и параметры непривычны новичкам

**Best for:** YouTube thumbnails художественные, обложки книг, концепт-арт, иллюстрации к статьям, mood boards.

---

#### ChatGPT Images / GPT Image (OpenAI)

DALL-E 2 и DALL-E 3 отключены в API OpenAI 12 мая 2026. Им на смену пришли модели семейства GPT Image: в API это `gpt-image-2` и `gpt-image-2.5`. Внутри ChatGPT генерация встроена: базовый режим доступен и на бесплатном тарифе, режим Thinking — на платных. Версия 2.0 (апрель 2026) лучше рендерит текст, в том числе не на латинице. Версия 2.5 (8 сентября 2026) добавила набросок прямо в чате, шаблоны для постеров и правки по комментариям на самой картинке.

**Цена (на октябрь 2026):** в ChatGPT генерация входит в тариф с его лимитами. В API оплата по токенам: у `gpt-image-2` $8 за 1 млн входных токенов изображения и $30 за 1 млн выходных. Стоимость одной картинки зависит от размера и качества. Актуальные цены: [https://developers.openai.com/api/docs/pricing](https://developers.openai.com/api/docs/pricing)

**Сильные стороны:**
- Хорошо понимает длинные описательные промпты
- Правка по описанию прямо в диалоге
- Текст в кадре (версии 2.0 и новее заметно лучше)
- Простой REST API

**Слабые стороны:**
- Меньше ручных настроек, чем у открытых моделей
- "AI look" заметнее чем у Flux
- Фильтры иногда блокируют безобидные запросы

**Best for:** quick mockups для слайдов, фотореалистичные product shots, картинки для блог-постов когда нужно быстро и без танцев.

---

#### Flux (Black Forest Labs)

Команда выходцев из Stability AI запустила Flux в 2024. На сайте компании (bfl.ai) в октябре 2026 — семейство FLUX 3: FLUX 3 Image (запуск 1 октября 2026), FLUX 3 Video и FLUX Tools для точной правки. Пользоваться можно через Playground в браузере, по API или скачав открытые веса для запуска у себя. Без кода проще всего через сервисы-хабы вроде Krea, где FLUX 3 Image уже подключена.

Раньше (Flux 1) семейство делилось на быструю Schnell, Dev с некоммерческой лицензией и Pro только через API. Эти названия ещё встречаются в старых материалах, а в новых версиях набор моделей и их лицензии другие. **Лицензия зависит от модели: перед коммерческим использованием открой её страницу и прочитай условия.**

**Цена:** у провайдеров API (fal.ai, Replicate и другие) оплата идёт за изображение, цены различаются по версиям и меняются. Смотри прайс выбранного провайдера: [https://fal.ai/models](https://fal.ai/models). Запуск открытых весов у себя бесплатен, но нужна мощная видеокарта.

**Сильные стороны:**
- Сильный photorealism
- Скорость (быстрые версии отвечают за секунды)
- Открытые веса у части моделей
- Поддержка LoRA для fine-tuning под бренд
- Inpainting/outpainting через инструменты правки (FLUX Tools)

**Слабые стороны:**
- Текст в изображениях слабее, чем у Ideogram
- Менее художественный стиль чем Midjourney
- Набор версий и лицензий быстро меняется

**Best for:** e-commerce product shots, real estate photos, food photography, fashion, любой photorealism в объёме.

---

#### Recraft V4

Стартап с фокусом на vector graphics и brand identity. Модель V4 вышла 17 февраля 2026, V4.1 — 14 мая 2026; на сайте также есть быстрая V4.1 Flash. Умеет выдавать редактируемую векторную графику (SVG), позволяет задать собственный стиль без обучения модели, делать мокапы, увеличивать изображения и убирать фон.

**Цена:** попробовать можно бесплатно, условия платных тарифов (кредиты, доступ к API) смотри на странице цен: [https://www.recraft.ai/pricing](https://www.recraft.ai/pricing)

**Сильные стороны:**
- Native vector output (SVG)
- Собственный стиль бренда без обучения модели
- Хороший контроль над типографикой
- Иконки, логотипы, инфографика — сильная сторона

**Слабые стороны:**
- Не для photorealism
- Меньше готовых стилей чем Midjourney
- Тарифы в кредитах: считай расход заранее

**Best for:** логотипы, иконки UI, инфографика, brand identity package, презентации.

---

#### Ideogram 4.0

Запущен бывшими исследователями Google Brain. Специализируется на изображениях с надписями: постеры, обложки, баннеры, упаковка. Ideogram 4.0 (3 июня 2026) — модель с открытыми весами и коммерческой лицензией: плотный многоязычный текст, управление положением логотипа или заголовка через рамки (bounding boxes) и вывод в 2K. Работает на сайте и через API.

**Цена:** есть бесплатный тариф, платные подписки и условия API смотри на странице: [https://ideogram.ai/manage-subscription/subscribe](https://ideogram.ai/manage-subscription/subscribe)

**Сильные стороны:**
- Один из лучших для текста в изображениях
- Магия с типографикой (разные шрифты, стилизация букв)
- Постеры, реклама, social ads
- Есть бесплатный тариф

**Слабые стороны:**
- Photorealism средний
- Меньше художественной гибкости чем Midjourney
- Доступ к API зависит от тарифа

**Best for:** постеры с длинным текстом, реклама в социалках, обложки для подкастов, типографические композиции.

---

### Сравнительная таблица

| Use case | Что взять | Как платишь | API? |
|---|---|---|---|
| Артистичная иллюстрация | Midjourney | Подписка | Официального публичного API нет (проверь) |
| Photorealism | Flux | За изображение у провайдера API или через хабы | ✅ |
| Текст в изображении | Ideogram | Бесплатный тариф, подписка или API | ✅ |
| Vector / Logo | Recraft | Тарифы с кредитами | ✅ |
| Фото + короткий текст | ChatGPT Images | Входит в ChatGPT; API по токенам | ✅ |
| Быстрое прототипирование | Быстрые версии Flux | За изображение у провайдера | ✅ |
| Self-host (любой объём) | Модели с открытыми весами (Flux, Ideogram 4.0) | Своя видеокарта | ✅ |

Конкретные цены в таблицу не вынесены, потому что они меняются каждый месяц. Считай по формуле из раздела "Реальные расходы" ниже.

---

### Профессиональные workflows

Один инструмент — один результат. Связка инструментов — продакшн-pipeline. Вот 4 workflow которые покрывают 80% задач контент-маркетолога / дизайнера.

#### Workflow A: Social Media Content (Instagram / Telegram poster)

**Задача:** еженедельный постер для Telegram-канала с цитатой эксперта.

**Stack:**
1. **Ideogram** — генерируем текстовый постер с цитатой
2. **Midjourney** — генерируем артистичный background если нужен
3. **Photopea** (бесплатный Photoshop) — финальная компоновка

**Time:** 30 минут на пост.
**Cost setup:** подписка Midjourney (тариф Basic, около $10/мес на октябрь 2026) + бесплатный тариф Ideogram.
**Cost per asset:** считай по формуле из раздела "Реальные расходы".

**Pipeline:**
```
Ideogram: "цитата на белом фоне" → PNG
   ↓
Midjourney: "abstract background, deep blue --ar 9:16" → PNG
   ↓
Photopea: overlay text + background → финальный PNG 1080x1920
```

---

#### Workflow B: E-commerce Product Photos

**Задача:** 100 фотографий товаров на белом фоне для интернет-магазина.

**Stack:**
1. **Flux** — генерация product shots
2. **Photoshop / Canva** — добавление логотипа и брендинга

**Time:** 5 минут на product (массово через batch script).
**Cost setup:** $0 (оплата за использование API).
**Cost:** цена за картинку у провайдера × число картинок (с запасом на неудачные варианты).

**Pipeline:**
```python
# batch_products.py — упрощённый пример
# идентификатор модели в fal.ai меняется: сверь его на странице модели
import fal_client

products = ["ceramic mug", "wireless headphones", "leather wallet"]

for product in products:
    result = fal_client.run(
        "fal-ai/flux-pro",
        arguments={
            "prompt": f"professional product photography, {product}, white background, studio lighting, soft shadow, commercial e-commerce style",
            "image_size": "square_hd",
            "num_inference_steps": 28
        }
    )
    # сохраняем result["images"][0]["url"]
```

Сравни со своей текущей ценой фотосъёмки, но помни про ограничения: AI не заменяет студию, когда нужна точная форма и цвет реального товара. Если покупатель ожидает реальное фото (карточки на маркетплейсах), проверь правила площадки: многие требуют снимки настоящего товара или пометку об AI.

---

#### Workflow C: Brand Identity Package

**Задача:** полный brand package для нового проекта — логотип, иконки, mood board, mockups.

**Stack:**
1. **Recraft** — логотип + иконки (SVG)
2. **Midjourney** — mood board (12 артистичных референсов)
3. **Flux** — фотореалистичные mockups (визитки, упаковка)

**Time:** 4-8 часов на full package.
**Cost setup:** подписки на время проекта (Recraft, Midjourney) + оплата за картинки у провайдера Flux; цены смотри в прайсах.
**Cost per package:** расход на генерации + твоё время.

**Pipeline:**
```
Recraft → 10 вариантов логотипа в SVG
   ↓ выбор 1-2
Recraft → 12 иконок UI в SVG (consistent style)
   ↓
Midjourney → mood board (3x4 grid) → референсы для команды
   ↓
Flux → mockups: визитка, кружка, упаковка, billboard
   ↓
Photoshop → финальная сборка brand guidelines PDF
```

---

#### Workflow D: Blog / YouTube Thumbnails

**Задача:** 20 thumbnails в неделю для YouTube или header-картинок для блог-постов.

**Stack:**
1. **Ideogram** — текст-overlay на thumbnail
2. **Быстрая версия Flux** — backgrounds (быстро и дёшево)
3. **Canva** — финальная сборка с шаблонами канала

**Time:** 15 минут на thumbnail.
**Cost:** число генераций на один thumbnail × цена за картинку (мелочь в сравнении с твоим временем, но посчитай).

**Pipeline:**
```
Быстрая версия Flux: "background для YouTube thumbnail" → 4 варианта
   ↓ выбор
Ideogram: "большой текст ХУК + малый текст подзаголовок"
   ↓
Canva: компоновка по template канала + лого
   ↓ export 1920x1080
```

Для канала с несколькими видео в неделю посчитай недельный расход на thumbnails и сравни с ценой фрилансера в твоём регионе.

---

### Promptcraft для image gen

Качество сильно зависит от промпта. Вот главные приёмы которые отличают новичка от профи.

**Style references:**
```
"portrait of a man, in the style of Annie Leibovitz photography"
"landscape, in the style of Studio Ghibli animation"
"product shot, Apple advertising aesthetic, minimalist"
```

Имена живых авторов и студий в промптах — спорная территория (авторское право, этика). Безопаснее описывать стиль словами: свет, палитра, фактура, композиция.

**Negative prompts (Flux, Ideogram):**
```
prompt: "modern office interior"
negative_prompt: "no people, no text, no logos, no clutter, no plants"
```

**Aspect ratios (используй ВСЕГДА):**
- `--ar 16:9` — YouTube thumbnails, desktop wallpapers
- `--ar 9:16` — TikTok, Instagram Reels, Stories
- `--ar 1:1` — Instagram feed posts
- `--ar 4:5` — Facebook ads
- `--ar 3:2` — DSLR-style photography
- `--ar 21:9` — cinematic, ultrawide banners

**Quality flags (Midjourney; параметры меняются между версиями, список — в документации текущей версии):**
```
--q 2          # двойное качество (медленнее, дороже)
--s 250        # средняя стилизация
--s 750        # сильная стилизация (артистичнее)
--chaos 50     # больше variation между 4 результатами
```

**Guidance scale (Flux и другие открытые модели; у ChatGPT Images такого параметра нет):**
- 4-6: креативный, модель импровизирует
- 7-8: оптимум для photorealism
- 9-10: жёстко следует промпту (может выглядеть "форсированно")

**Consistency через references:**
```
Midjourney sref: --sref https://example.com/style.png
Midjourney cref: --cref https://example.com/character.png  (в новых версиях для персонажей могут быть другие параметры)
Flux: возможности зависят от версии и провайдера
```

---

### Избегаем AI image клише 2026

В 2024 году главная проблема была — 6 пальцев, weird eyes, melted hands. К 2026 это **в основном решено** в современных моделях.

**Новые проблемы 2026 ("AI look"):**
- Слишком гладкая кожа (полное отсутствие пор, морщин)
- Глянцевые поверхности с unnatural reflections
- Generic faces (все люди похожи на стоковые фото)
- Слишком симметричные композиции
- Yellow / golden hour lighting везде (модели любят этот свет)
- Идеальный фокус везде (нет естественной DoF)

**Решения — добавляй в prompt:**
```
✅ "natural skin texture, visible pores, slight skin imperfections"
✅ "candid pose, asymmetric composition, off-center subject"
✅ "film grain, slight blur on background, shallow depth of field"
✅ "harsh midday lighting" вместо стандартного golden hour
✅ "real moment captured, not posed, slight motion blur"
✅ "imperfect framing, like phone photography"
```

**Post-processing для "human touch":**
1. Lightroom / Photoshop → добавить grain (Filter → Noise → Add Noise, 3-5%)
2. Slight color grading (cooler shadows, warmer highlights)
3. Subtle vignette
4. Imperfect crop (off-center subject)
5. Slight chromatic aberration на краях

🎨 **Образ:** AI генерирует "идеальную" фотографию. Реальная фотография всегда содержит несовершенства — они и делают её живой. Добавь немного "грязи" — и зритель перестаёт видеть AI.

---

### Юридические аспекты

Важная глава которую многие игнорируют. В 2026 ландшафт усложнился. Это общая информация, а не юридическая консультация: законы разных стран отличаются, а в серьёзных случаях нужен юрист.

**Copyright на AI-generated images:**
- **USA:** US Copyright Office решил в 2023 (и подтвердил в 2025) — pure AI-generated изображения **не могут быть зарегистрированы copyright**. Только если есть значительный human modification (например, серьёзная переработка в Photoshop)
- **EU:** ambiguous, идёт нормативное обсуждение
- **Practical implication:** чисто сгенерированные картинки в США не защищены авторским правом, значит защитить их от копирования сложно. Защита появляется, если делаешь существенный editing

Подробнее: [https://www.copyright.gov/ai/](https://www.copyright.gov/ai/)

**Commercial use по сервисам:** условия меняются и зависят от тарифа, поэтому в таблице стоит не готовый ответ, а то, что нужно проверить.

| Сервис | Что проверить перед коммерческим использованием |
|---|---|
| Midjourney | Условия подписки: коммерческое использование зависит от тарифа и от размера компании (страница Terms of Service) |
| ChatGPT Images / GPT Image | Условия использования OpenAI: права на результат и ограничения на содержание |
| Flux | Лицензия конкретной модели: у части версий она некоммерческая (старый Dev), у других иная; читай страницу модели |
| Recraft | Условия тарифа: на каком тарифе разрешено коммерческое использование |
| Ideogram | У модели 4.0 с открытыми весами заявлена коммерческая лицензия; на сервисе условия зависят от тарифа |

**Likeness (изображения реальных людей):**
- У сервисов свои правила про изображения реальных людей, особенно публичных персон
- У открытых моделей встроенных блокировок может не быть — ответственность по закону на тебе
- Закон GDPR (EU) и right of publicity (US): использовать образ реального человека обычно нужно только с согласия

**Watermarking и маркировка:**
- Google (Nano Banana в Gemini): изображения помечаются невидимым водяным знаком SynthID
- У других сервисов набор меток разный (например, метаданные C2PA); проверяй правила конкретного сервиса
- Тренд 2026-2027: закон ЕС об ИИ (EU AI Act) вводит требования к маркировке сгенерированного контента; сроки и детали проверяй по актуальным источникам

**Best practice:** добавляй пометку "AI-generated" если используешь в маркетинге. Для product shots e-commerce уточни правила площадки.

---

### Реальные расходы: как посчитать

Цены в этом уроке специально не зашиты в таблицы: за месяц они успевают поменяться. Вместо готовых цифр — формулы, куда ты подставляешь актуальные значения с прайсов.

**Для подписки:**
```
стоимость одной картинки = цена подписки в месяц / число картинок, которые ты реально сделал
```

**Для API (оплата за картинку):**
```
расход в месяц = число картинок × цена за картинку × (1 + доля неудачных вариантов)
```

Доля неудачных вариантов обычно существенная: генерируют 4-8 вариантов, выбирают один.

**Для запуска у себя (открытые веса):**
```
срок окупаемости (мес) = цена видеокарты / (месячный расход на API, который ты заменяешь − электричество)
```

Пример с условными цифрами (подставь свои): видеокарта стоит 1500, API обходится в 50 в месяц, значит окупаемость около 30 месяцев; при 200 в месяц — около 8. Запуск у себя имеет смысл, если генераций много и стабильно, а ещё нужна приватность или полный контроль.

Подписки и API сравнивай на одинаковом объёме: возьми свои 1000 изображений в месяц и посчитай по каждой формуле.

---

### 2026 тренды в image generation

**Real-time generation:**
- Быстрые версии моделей отвечают за секунды
- LCM (Latent Consistency Models) — несколько шагов вместо 28-50
- Применение: интерактивные web apps, AR filters, live design

**Multi-image consistency:**
- Референсы персонажа (в Midjourney, у Flux через хабы и в Nano Banana) улучшаются быстро
- Можно делать комикс из десятков страниц с consistent персонажем
- Storytelling через AI становится viable

**Video generation:**
- Runway — Gen-4.5, Kling — VIDEO 3.0 (в конце сентября 2026 анонсирована 4.0), Luma — Ray 3.2
- Google Flow — видео в Gemini и Flow делает Gemini Omni (заменила Veo 3.1)
- Sora (OpenAI) закрыта: сайт и приложение с 26.04.2026 (проверь по сообщению OpenAI), API с 24.09.2026
- Pika — короткие клипы и набор приложений
- Отдельный урок про video gen: [AI видеогенерация](71-ai-video-generation.md)

**3D from images:**
- Появились модели, которые превращают одно изображение в 3D-сетку (например Trellis от Microsoft, Hunyuan3D от Tencent; актуальность проверяй)
- Применение: game dev, e-commerce 3D views

**Inpainting / editing:**
- FLUX Tools — точечное редактирование
- Adobe Firefly — нативно в Photoshop
- Ideogram — текстовое редактирование изображений
- ChatGPT Images — правки по комментариям на самой картинке (версия 2.5)

---

### Anti-patterns

❌ **Использовать default settings** — outputs получаются generic. Всегда настраивай aspect ratio, style, quality.

❌ **Не указывать aspect ratio** — модель сделает 1:1, а нужно 16:9 для YouTube. Crop'нуть нельзя без потери качества.

❌ **Доверять single generation** — ВСЕГДА генерируй 4-8 вариантов, выбирай лучший. Стоимость небольшая, экономит часы переделок.

❌ **Photo-realistic AI людей без disclosure** — этика и закон. Может стоить репутации и юридических проблем.

❌ **Skip post-processing** — AI output редко production-ready. Минимум 5 мин в Photoshop/Lightroom для финального touch.

❌ **Один инструмент на все задачи** — Midjourney для логотипа = слабый результат vs Recraft. Каждой задаче — свой инструмент.

❌ **Hardcoded prompts** — не сохраняешь template-промпты в библиотеке. Каждый раз пишешь с нуля. Заведи `prompts/` папку.

❌ **Игнорировать commercial license** — у части версий Flux лицензия некоммерческая; коммерческое использование без проверки условий = нарушение. Проверь условия модели и тарифа перед production использованием.

---

### Audience рейтинг — что взять

Цены не указаны: они меняются, считай по формулам выше и по актуальным прайсам.

**Новичок (хобби, learning):**
- Flux через бесплатные playground или хабы
- Ideogram — бесплатный тариф
- Photopea (free Photoshop в браузере)
- **Total: $0/мес**

**Контент-маркетолог (Telegram канал, блог, регулярный контент):**
- Midjourney (стартовый тариф, около $10/мес на октябрь 2026)
- Ideogram и Recraft — бесплатные тарифы
- Canva для финальной сборки (платный тариф нужен не всегда)
- **Total: подписка Midjourney + то, что выберешь платным**

**Дизайнер-фрилансер (клиентские проекты):**
- Midjourney на более высоком тарифе
- Recraft на платном тарифе
- Flux через API по факту использования
- Photoshop (Creative Cloud) или аналог
- **Total: сумма подписок и API, посчитай по прайсам**

**Профессиональная студия (high volume, brand consistency):**
- Всё перечисленное выше
- Своя видеокарта для открытых моделей: разовая покупка плюс электричество
- Расширенные планы Recraft и Adobe Creative Cloud
- **Total: считай отдельно по каждой статье**

🎨 **Образ:** профессиональная кухня. Студент учится на одной плите — этого хватит. Домашний кулинар берёт хорошую плиту и пару ножей. Шеф-повар имеет 5 плит, 20 ножей, набор кастрюль на каждую задачу. Не покупай шеф-сетап если ты студент.

---

## Практика

### Шаг 1: Setup Flux через fal.ai

Самый быстрый старт — Flux через fal.ai: в playground можно попробовать без кода, а для скриптов нужен ключ. Идентификаторы моделей на fal.ai меняются с выходом новых версий: перед запуском открой страницу нужной модели и подставь её актуальный идентификатор вместо тех, что в примерах ниже.

```bash
# Регистрируешься на fal.ai (Google login)
# Условия пробных кредитов смотри при регистрации

# Установка Python SDK
pip install fal-client python-dotenv pillow

# Создаёшь .env
echo "FAL_KEY=your-fal-key-here" > .env
```

Получить FAL_KEY: [https://fal.ai/dashboard/keys](https://fal.ai/dashboard/keys)

---

### Шаг 2: Простой генератор на быстрой версии Flux

```python
# flux_simple.py — минимум для старта (идентификатор модели сверь на fal.ai)
import os
import fal_client
from dotenv import load_dotenv
import requests
from pathlib import Path

load_dotenv()
os.environ["FAL_KEY"] = os.getenv("FAL_KEY")

def generate_image(prompt: str, output_path: str, aspect_ratio: str = "square"):
    """Генерируем изображение через быструю версию Flux."""
    print(f"Генерируем: {prompt[:50]}...")

    result = fal_client.run(
        "fal-ai/flux/schnell",  # сверь актуальный идентификатор на fal.ai
        arguments={
            "prompt": prompt,
            "image_size": aspect_ratio,
            "num_inference_steps": 4,
            "num_images": 1,
        }
    )

    # Сохраняем
    image_url = result["images"][0]["url"]
    image_data = requests.get(image_url).content
    Path(output_path).write_bytes(image_data)
    print(f"Сохранено: {output_path}")
    return output_path


if __name__ == "__main__":
    generate_image(
        prompt="professional product photography, ceramic coffee mug, white background, soft studio lighting, natural shadow",
        output_path="output/mug.png",
        aspect_ratio="square_hd"
    )
```

**Aspect ratios для Flux:**
- `square_hd` — 1024x1024
- `square` — 512x512
- `portrait_4_3` — 768x1024
- `portrait_16_9` — 576x1024
- `landscape_4_3` — 1024x768
- `landscape_16_9` — 1024x576

---

### Шаг 3: Batch генерация product shots

```python
# batch_products.py — генерируем 10 продуктов параллельно
import os
import fal_client
import asyncio
import aiohttp
from pathlib import Path

os.environ["FAL_KEY"] = os.getenv("FAL_KEY", "your-key")

# условное значение: подставь цену за картинку из прайса провайдера
PRICE_PER_IMAGE = 0.05

PRODUCTS = [
    "ceramic coffee mug",
    "wireless bluetooth headphones",
    "leather wallet brown",
    "stainless steel water bottle",
    "wooden cutting board",
    "scented candle in glass jar",
    "linen tote bag",
    "minimalist desk lamp",
    "ceramic plant pot",
    "knit wool scarf grey",
]

PROMPT_TEMPLATE = (
    "professional product photography, {product}, pure white background, "
    "soft studio lighting from top-left, subtle natural shadow underneath, "
    "centered composition, commercial e-commerce style, photorealistic, "
    "high detail, sharp focus, no people, no text"
)

async def generate_one(session, product: str, idx: int):
    """Генерируем один продукт асинхронно."""
    prompt = PROMPT_TEMPLATE.format(product=product)

    # более сильная версия Flux для e-commerce (идентификатор сверь на fal.ai)
    handler = await fal_client.submit_async(
        "fal-ai/flux-pro/v1.1",
        arguments={
            "prompt": prompt,
            "image_size": "square_hd",
            "num_images": 1,
            "guidance_scale": 7.5,
        }
    )
    result = await handler.get()

    image_url = result["images"][0]["url"]
    async with session.get(image_url) as resp:
        data = await resp.read()

    filename = f"output/product_{idx:02d}_{product.replace(' ', '_')}.png"
    Path(filename).write_bytes(data)
    print(f"✅ [{idx}/10] {product}")
    return filename


async def main():
    Path("output").mkdir(exist_ok=True)
    async with aiohttp.ClientSession() as session:
        tasks = [
            generate_one(session, product, i + 1)
            for i, product in enumerate(PRODUCTS)
        ]
        results = await asyncio.gather(*tasks)
    print(f"\nГотово! Сгенерировано {len(results)} продуктов.")
    print(f"Стоимость: ~${len(results) * PRICE_PER_IMAGE:.2f}")


if __name__ == "__main__":
    asyncio.run(main())
```

**Запуск:**
```bash
python batch_products.py
# Через минуту-две получаешь 10 product shots
# Стоимость: число картинок × цена за картинку у провайдера
```

---

### Шаг 4: Микс Flux + Ideogram для YouTube thumbnails

```python
# youtube_thumbnails.py — pipeline для thumbnails
import os
import fal_client
import requests
from pathlib import Path

os.environ["FAL_KEY"] = os.getenv("FAL_KEY")

def generate_background(topic: str, save_path: str):
    """Быстрая версия Flux — background."""
    result = fal_client.run(
        "fal-ai/flux/schnell",  # сверь актуальный идентификатор на fal.ai
        arguments={
            "prompt": f"abstract dramatic background for YouTube thumbnail, {topic} theme, dark blue and orange tones, cinematic lighting, no text, no people, vignette",
            "image_size": "landscape_16_9",  # 1024x576
            "num_inference_steps": 4,
        }
    )
    url = result["images"][0]["url"]
    Path(save_path).write_bytes(requests.get(url).content)
    return save_path


def generate_text_overlay(hook_text: str, save_path: str):
    """Ideogram — текст-overlay (через fal.ai тоже доступен)."""
    result = fal_client.run(
        "fal-ai/ideogram/v2",  # сверь актуальную версию Ideogram на fal.ai
        arguments={
            "prompt": f"big bold text '{hook_text}' on transparent background, white text with red outline, condensed sans-serif font, dramatic typography for YouTube thumbnail",
            "aspect_ratio": "16:9",
            "style": "design",
        }
    )
    url = result["images"][0]["url"]
    Path(save_path).write_bytes(requests.get(url).content)
    return save_path


def assemble_thumbnail(bg_path: str, text_path: str, output_path: str):
    """Финальная сборка через PIL."""
    from PIL import Image

    bg = Image.open(bg_path).convert("RGBA")
    text = Image.open(text_path).convert("RGBA")

    # Resize text overlay to match bg
    text = text.resize(bg.size)

    # Composite
    combined = Image.alpha_composite(bg, text)
    combined.convert("RGB").save(output_path, "PNG")
    print(f"Готово: {output_path}")


if __name__ == "__main__":
    Path("output").mkdir(exist_ok=True)

    bg = generate_background(
        topic="AI image generation tools comparison",
        save_path="output/bg.png"
    )
    text = generate_text_overlay(
        hook_text="MIDJOURNEY vs FLUX",
        save_path="output/text.png"
    )
    assemble_thumbnail(bg, text, "output/thumbnail_final.png")
```

---

### Шаг 5: Prompt library — сохраняем рабочие промпты

```bash
mkdir -p prompts/{product,thumbnail,social,brand}
```

```yaml
# prompts/product/ecommerce-white-bg.yaml
name: "E-commerce white background"
model: "flux-pro"
template: |
  professional product photography, {product},
  pure white background, soft studio lighting from top-left,
  subtle natural shadow underneath, centered composition,
  commercial e-commerce style, photorealistic, high detail,
  sharp focus, no people, no text, no logos
params:
  image_size: "square_hd"
  guidance_scale: 7.5
  num_inference_steps: 28
negative_prompt: "blurry, low quality, distorted, watermark, signature"
notes: |
  - Test 4 generations per product, pick best
  - Post-process: subtle shadow enhancement в Photoshop
  - Cost: по прайсу провайдера
```

**Совет:** заведи `.claude/agents/image-prompt-engineer.md` который читает эти YAML-файлы и генерирует финальные промпты под задачу.

---

## Инструменты и ресурсы

- **[Midjourney](https://www.midjourney.com)** — официальный сайт, Discord access, web UI
- **[ChatGPT Images (GPT Image)](https://learn.chatgpt.com/docs/image-generation)** — встроенная генерация в ChatGPT
- **[OpenAI API Pricing](https://developers.openai.com/api/docs/pricing)** — актуальные цены на gpt-image-2 и gpt-image-2.5 в API
- **[Black Forest Labs (Flux)](https://bfl.ai)** — официальный сайт Flux, технические детали
- **[fal.ai](https://fal.ai)** — главный provider для Flux API, playground для тестирования
- **[Replicate](https://replicate.com)** — альтернативный API host для Flux, Stable Diffusion и других
- **[Recraft](https://www.recraft.ai)** — vector graphics + brand identity
- **[Ideogram](https://ideogram.ai)** — text-in-images champion
- **[Photopea](https://www.photopea.com)** — бесплатный Photoshop в браузере
- **[Canva](https://www.canva.com)** — финальная сборка с шаблонами
- **[Lexica](https://lexica.art)** — поиск по промптам и стилям
- **[PromptHero](https://prompthero.com)** — библиотека рабочих промптов
- **[US Copyright Office on AI](https://www.copyright.gov/ai/)** — официальная позиция США по copyright AI-изображений
- Актуальные цены и версии: [Актуальное сейчас](https://aimayak.com/ru/now/)

---

## Чек-лист профессионального pipeline

✅ Выбран main model для use case (не один универсал на все задачи)
✅ Workflow стандартизирован (документирован в README проекта)
✅ Prompt library заведён (`prompts/` папка с YAML/JSON шаблонами)
✅ Aspect ratio указан для каждой платформы (16:9, 9:16, 1:1, 4:5)
✅ Post-processing pipeline настроен (минимум grain + color grade)
✅ Юридический check: commercial use license подходит для use case
✅ Backup workflow если main API недоступен (открытая модель локально как fallback)
✅ Cost tracking — знаешь стоимость per asset для бюджетирования
✅ Disclosure policy: AI-generated помечается где требуется этикой/законом
✅ Source files (PSD, source images) хранятся в `/sources` для повторного использования

---

## Ключевые выводы

> Один универсальный инструмент в image generation 2026 — это компромисс везде. Профессионал держит 2-3 модели в pipeline: Flux для photorealism, Ideogram для текста, Recraft для векторов или Midjourney для артистики. Связка инструментов даёт лучший результат при разумных costs.

> Качество сильно зависит от промпта. Aspect ratio, negative prompts, style references, guidance scale — это не "опции", а обязательные настройки (там, где сервис их поддерживает). Default settings = generic output.

> Юридический ландшафт 2026 неочевиден. AI-images не защищены copyright в США. Commercial license зависит от модели и tier. Проверяй license **перед** production использованием, не после.

> Post-processing — это разница между "AI-картинкой" и "продакшн-материалом". Минимум 5 минут на grain, color grade и крошечные несовершенства — и зритель перестаёт видеть AI.

---

## Следующий урок

→ [Что такое Skills](19-skills-intro.md): начало модуля про переиспользуемую экспертизу. Если нужно видео, смотри [AI видеогенерация](71-ai-video-generation.md).
