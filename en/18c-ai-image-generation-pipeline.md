# AI image generators in 2026: tools and workflows

**Time:** about 25 min reading + 35 min practice

---

## The gist

AI image generation in 2026 is like the smartphone camera in 2010. Anyone can press a button and get a picture. But the difference between a snapshot and a photograph comes down to technique, knowing your tool, and post-processing.

The market splits into 5 main players, each with its own specialty. Midjourney is the artist. ChatGPT Images is the generalist that's already at your fingertips. Flux brings open models and speed. Recraft is the vector specialist. Ideogram is the typographer. There's no single all-around champion. A professional keeps 2 or 3 tools in their pipeline and knows which one is stronger where.

In this lesson we'll take an honest look at how pricing works, professional workflows for different tasks, legal pitfalls, and the anti-patterns that separate an "AI picture" from production-ready material.

You don't need to write any code in this lesson: the exercise in the Practice section is done in a browser or on your phone. The script examples are marked optional; they're for readers who program.

A heads-up: this market changes faster than any other. Version names and terms in this lesson are as of October 2026; for current prices and versions, check the [What's current](https://aimayak.com/en/now/) page and [the Tools catalog](https://aimayak.com/en/tools/). Service prices in this lesson are replaced with links to each service's pricing page, and the numbers in the cost examples are made up.

🎨 **Picture this:** the kitchen of a good restaurant. The chef doesn't own one all-purpose knife; there's a whole set. A fillet knife for fish, a paring knife for vegetables, a cleaver for bones. You could cut everything with one knife, but it would be slow and sloppy. Image generation works the same way: one tool for every job means mediocre results everywhere.

---

## 🎯 Decision tree: which model to pick

The key question is **not "which tool is best"** but "what am I making, and for which platform?"

**Pick Midjourney if:**
- ✓ You're making artistic content, illustrations, concept art
- ✓ You need mood boards or YouTube thumbnails with an artistic look
- ✓ You're fine working in a web app on a subscription (Discord used to be the main way in)
- ✓ Quality matters more to you than fast iteration

**Pick ChatGPT Images (the GPT Image models) if:**
- ✓ You need photorealism plus text in the image
- ✓ You already use ChatGPT (images are available even on the free plan, within limits)
- ✓ You don't want to fiddle with settings: you just describe the picture in words
- ✓ You need quick mockups for presentations

**Pick Flux if:**
- ✓ You need speed and volume (100+ images a day)
- ✓ You want photorealism with photographic precision
- ✓ You need a model with open weights, meaning one you can download and run on your own machine (with a powerful graphics card)
- ✓ You'll check the license up front: it differs from one Flux model to another

**Pick Recraft if:**
- ✓ You're making logos, vector graphics, icons
- ✓ You're working on brand identity or infographics
- ✓ You need SVG files as output (a vector format: the image scales without losing quality and can be edited piece by piece)
- ✓ You need professional-grade text in images

**Pick Ideogram if:**
- ✓ You're making posters, ads, social media ads with typography
- ✓ You need long text in the image (several lines)
- ✓ Your budget is minimal (there's a free plan)

**By default, Flux + Ideogram + Recraft covers most tasks.** Add Midjourney when you need an artistic look, and ChatGPT Images if you already use ChatGPT.

🎨 **Picture this:** a company vehicle fleet. You don't need one all-purpose vehicle for every trip. You need a truck (Flux, for volume), a sedan (ChatGPT Images, for comfort), an SUV (Midjourney, for artistic flair) and a van (Recraft, for special jobs).

---

## Key concepts

- **Diffusion model**: an AI model that learns to rebuild an image out of noise. Many image generators are built on this principle
- **Prompt engineering**: the craft of wording a request so the model gives you what you want. A great deal depends on the prompt
- **Aspect ratio (AR)**: the proportions of the output image. 16:9 for YouTube, 9:16 for Reels/TikTok, 1:1 for Instagram, 4:5 for FB
- **Seed**: a number that controls randomness. Same prompt + same seed = same result
- **Style reference (sref)**: a reference image the model copies the style from
- **Character reference**: a reference image that keeps a character's appearance the same across generations. In Midjourney V8 this is done with the Edit Model; the `--cref` parameter remains only in older versions
- **Inpainting**: editing one part of an image while keeping the rest
- **Outpainting**: extending an image beyond its borders (extend canvas)
- **Negative prompt**: a description of what should NOT appear in the image. Not every model has one
- **Guidance scale (CFG)**: how strictly the model follows the prompt. Each model has its own scale, and not every service has this setting
- **API**: a way to plug the service into your own program. Developers need it; you don't need it to make images on the service's website

---

## Theory

### The 5 main players in 2026

#### Midjourney V8

The oldest and most recognizable player. It puts the emphasis on artistic quality. Since July 24, 2026, the default version is V8.2, with improved aesthetics and personalization to your taste. Starting with V8, there's an HD mode that renders images at 2K right away, plus more accurate text in the frame. Edits by description and work with reference images go through the Edit Model, and you can turn images into short videos.

**Price:** paid subscriptions only; there's no free plan. The cheapest plan is called Basic. Higher plans give you more fast generation time (the service counts it in minutes of work by its graphics cards), and the Pro and Mega plans add Stealth Mode, which keeps your images hidden from other people. HD mode uses up more generation time. Plans and prices: [https://docs.midjourney.com/hc/en-us/articles/27870484040333-Comparing-Midjourney-Plans](https://docs.midjourney.com/hc/en-us/articles/27870484040333-Comparing-Midjourney-Plans)

**Workflow:** a web app on a subscription. Before that, the main way in was a Discord bot with the slash commands `/imagine`, `/blend` and `/describe`, and it still works. Parameters like `--ar` go at the end of the prompt.

**Strengths:**
- Strong artistic styling
- Style and character references for consistency
- A huge community with shared presets
- Stealth Mode on the Pro and Mega plans: your generations aren't publicly visible

**Weaknesses:**
- No official public API (check the service's website for the current status)
- Text in images is better than it used to be, but Ideogram is more reliable for typography
- Hard to iterate with scripts
- The interface and parameters feel unfamiliar to beginners

**Best for:** artistic YouTube thumbnails, book covers, concept art, illustrations for articles, mood boards.

---

#### ChatGPT Images / GPT Image (OpenAI)

DALL-E 2 and DALL-E 3 were shut off in the OpenAI API on May 12, 2026. They were replaced by the GPT Image family of models: in the API these are `gpt-image-2` and two `gpt-image-2.5` models. Inside ChatGPT, image generation is built in and is called ChatGPT Images: it's available on every plan, including the free one, while images with thinking are only on paid plans. Version 2.0 (April 2026) renders text better, including text in non-Latin scripts. Version 2.5 (September 8, 2026) added templates and, in the mobile app, hand-drawn sketches right in the chat and edits based on comments you place on the image itself.

**Price:** in ChatGPT, image generation is included in your plan, within its limits. In the API you pay by tokens (the units the bill is counted in), and the cost of a single image depends on its size and quality. Current prices: [https://developers.openai.com/api/docs/pricing](https://developers.openai.com/api/docs/pricing)

**Strengths:**
- Handles long, descriptive prompts well
- You can edit by description right in the conversation
- Text in the frame (noticeably better in version 2.0 and later)
- A simple API for developers

**Weaknesses:**
- Fewer manual settings than open models
- The "AI look" can be more noticeable than with Flux: compare on your own task
- Filters sometimes block harmless requests

**Best for:** quick mockups for slides, photorealistic product shots, images for blog posts when you need something fast and without fuss.

---

#### Flux (Black Forest Labs)

A team of former Stability AI people launched Flux in 2024. As of October 2026, the company's website (bfl.ai) lists the FLUX 3 family: FLUX 3 Image (launched October 1, 2026), FLUX 3 Video, and FLUX Tools for precise editing. You can use it in the Playground (a page where you try a model right in your browser) or through the API; some of the models have open weights you can download and run on your own machine. Without code, the easiest way in is a hub service like Krea, which gathers models from different companies, Flux among them.

Earlier (Flux 1), the family was split into the fast Schnell, Dev with a non-commercial license, and Pro, available only through the API. You'll still see those names in older materials, but newer versions have a different lineup of models and different licenses. **The license depends on the model: before any commercial use, open the model's page and read the terms.**

**Price:** with API providers (fal.ai, Replicate and others), you pay per image; prices vary by version and change over time. Check your chosen provider's pricing: [https://fal.ai/models](https://fal.ai/models). Running open weights yourself means no per-image fee, but you need a powerful graphics card, and commercial use may require a license.

**Strengths:**
- Strong photorealism
- Speed (the fast versions respond in seconds)
- Open weights for some of the models
- LoRA support: a small add-on used to further train the model on your own images so it keeps your brand's style
- Inpainting/outpainting through the editing tools (FLUX Tools)

**Weaknesses:**
- For text in images, people more often pick Ideogram: compare on your own task
- Usually a less artistic style than Midjourney
- The lineup of versions and licenses changes quickly

**Best for:** e-commerce product shots, real estate photos, food photography, fashion, any photorealism at volume.

---

#### Recraft V4

A startup focused on vector graphics and brand identity. The V4 model came out on February 17, 2026, and V4.1 on May 14, 2026; the website also offers a fast V4.1 Flash. It can produce editable vector graphics (SVG), lets you set up your own style without training a model, and can make mockups, upscale images and remove backgrounds.

**Price:** you can try it for free, but on the Free plan your images are owned by Recraft, are publicly visible and aren't licensed for commercial use. Paid plans give you ownership and commercial rights. For plan terms (credits, API access), see the pricing page: [https://www.recraft.ai/pricing](https://www.recraft.ai/pricing)

**Strengths:**
- Native vector output (SVG)
- Your own brand style without training a model
- Good control over typography
- Icons, logos and infographics are its strong suit

**Weaknesses:**
- Photorealism isn't its main strength
- For artistic illustration, people more often pick Midjourney
- Plans are credit-based: estimate your usage in advance

**Best for:** logos, UI icons, infographics, a brand identity package, presentations.

---

#### Ideogram

Launched by former Google Brain researchers. It specializes in images with lettering: posters, covers, banners, packaging. Ideogram 4.0 (June 3, 2026) is an open-weights model: dense multilingual text, control over where a logo or headline goes using frames (bounding boxes), and 2K output. You can download the weights and run them yourself, but commercial use of the weights requires a separate license from Ideogram. On September 30, 2026, Ideogram 4.5 came out: a model for precise editing of existing images. It works on the website and through the API.

**Price:** there's a free plan (images made on it are visible to everyone); for paid subscriptions and API terms, see this page: [https://ideogram.ai/pricing](https://ideogram.ai/pricing)

**Strengths:**
- One of the best for text in images
- Strong typography (different fonts, stylized lettering)
- Posters, ads, social ads
- There's a free plan

**Weaknesses:**
- Photorealism isn't its main strength
- Less artistic flexibility than Midjourney
- You can keep your images hidden from others only on paid plans

**Best for:** posters with long text, social media ads, podcast covers, typographic compositions.

---

### Comparison table

| Use case | What to use | How you pay | API? |
|---|---|---|---|
| Artistic illustration | Midjourney | Subscription | No official public API (check) |
| Photorealism | Flux | Per image, through an API provider or a hub | ✅ |
| Text in images | Ideogram | Free plan, subscription or API | ✅ |
| Vector / logo | Recraft | Credit-based plans | ✅ |
| Photo + short text | ChatGPT Images | Included in ChatGPT; the API bills by tokens | ✅ |
| Fast prototyping | Fast Flux versions | Per image, through a provider | ✅ |
| Self-hosting (any volume) | Open-weights models (Flux, Ideogram 4.0); check the license for commercial use | Your own graphics card | ✅ |

Specific prices aren't in the table because they change often. Do the math with the formulas in "Real costs" below.

---

### Professional workflows

One tool gives you one result. A combination of tools gives you a production pipeline. Here are 4 workflows that cover most of what a content marketer or designer needs to do. All four can be done by hand on the services' websites; the script in Workflow B is an optional extra.

#### Workflow A: Social media content (an Instagram poster)

**Task:** a weekly poster with an expert quote for an Instagram account.

**Stack:**
1. **Ideogram**: generate the text poster with the quote
2. **Midjourney**: generate an artistic background if you need one
3. **Photopea** (a free Photoshop alternative): final layout

**Time:** 30 minutes per post.
**Setup cost:** a Midjourney subscription (the entry-level Basic plan; see the pricing page) + Ideogram's free plan.
**Cost per asset:** use the formula in the "Real costs" section.

**Pipeline:**
```
Ideogram: "quote on a white background" → PNG
   ↓
Midjourney: "abstract background, deep blue --ar 9:16" → PNG
   ↓
Photopea: overlay text + background → final PNG 1080x1920
```

---

#### Workflow B: E-commerce product photos

**Task:** 100 product photos on a white background for an online store.

**Stack:**
1. **Flux**: generate the product shots
2. **Photoshop / Canva**: add the logo and branding

**Time:** 5 minutes per product (in bulk, with a batch script).
**Setup cost:** $0 (you pay per use through the API).
**Cost:** the provider's price per image × the number of images (plus a margin for failed attempts).

**Pipeline** (optional: an example for people who write Python scripts; without code, you make the same images one at a time on Krea or in the bfl.ai Playground):
```python
# batch_products.py: a simplified example
# the model ID on fal.ai changes; check it on the model's page
import fal_client

products = ["ceramic mug", "wireless headphones", "leather wallet"]

for product in products:
    result = fal_client.run(
        "fal-ai/flux-pro/v1.1",
        arguments={
            "prompt": f"professional product photography, {product}, white background, studio lighting, soft shadow, commercial e-commerce style",
            "image_size": "square_hd"
        }
    )
    # save result["images"][0]["url"]
```

Compare this with what you currently pay for product photography, but keep the limits in mind: AI doesn't replace a studio when you need the exact shape and color of a real product. If buyers expect a real photo (listings on marketplaces like Amazon, Etsy or eBay), check the platform's rules: many require photos of the actual product or a note that the image is AI-made.

---

#### Workflow C: Brand identity package

**Task:** a full brand package for a new project: logo, icons, mood board, mockups.

**Stack:**
1. **Recraft**: logo + icons (SVG)
2. **Midjourney**: mood board (12 artistic references)
3. **Flux**: photorealistic mockups (business cards, packaging)

**Time:** 4-8 hours for the full package.
**Setup cost:** subscriptions for the length of the project (Midjourney, and a paid Recraft plan so that the rights to the logo are yours) + pay-per-image with a Flux provider; see the pricing pages.
**Cost per package:** what you spend on generations + your time.

**Pipeline:**
```
Recraft → 10 logo options in SVG
   ↓ pick 1-2
Recraft → 12 UI icons in SVG (consistent style)
   ↓
Midjourney → mood board (3x4 grid) → references for the team
   ↓
Flux → mockups: business card, mug, packaging, billboard
   ↓
Photoshop → final brand guidelines PDF
```

---

#### Workflow D: Blog / YouTube thumbnails

**Task:** 20 YouTube thumbnails a week, or header images for blog posts.

**Stack:**
1. **Ideogram**: the text overlay for the thumbnail
2. **A fast Flux version**: backgrounds (fast and cheap)
3. **Canva**: final assembly with your channel's templates

**Time:** 15 minutes per thumbnail.
**Cost:** number of generations per thumbnail × price per image (pocket change next to your time, but do the math anyway).

**Pipeline:**
```
Fast Flux version: "background for a YouTube thumbnail" → 4 options
   ↓ pick one
Ideogram: "big HOOK text + small subtitle text"
   ↓
Canva: layout using the channel template + logo
   ↓ export 1920x1080
```

For a channel with several videos a week, add up your weekly spend on thumbnails and compare it with what a freelancer in your area would charge.

---

### Promptcraft for image generation

Quality depends heavily on the prompt. Here are the main techniques that separate a beginner from a pro.

**Style references:**
```
"portrait of a man, in the style of Annie Leibovitz photography"
"landscape, in the style of Studio Ghibli animation"
"product shot, Apple advertising aesthetic, minimalist"
```

Putting the names of living artists and studios into prompts is contested territory (copyright, ethics). It's safer to describe the style in words: lighting, palette, texture, composition.

**Negative prompts (Ideogram and some open models):**
```
prompt: "modern office interior"
negative_prompt: "people, text, logos, clutter, plants"
```

A negative prompt simply lists what you don't want, without the word "no." Flux has no negative prompt: describe what should be in the image instead. Midjourney has the `--no` parameter for this.

**Aspect ratios (ALWAYS set one):**
- `--ar 16:9`: YouTube thumbnails, desktop wallpapers
- `--ar 9:16`: TikTok, Instagram Reels, Stories
- `--ar 1:1`: Instagram feed posts
- `--ar 4:5`: Facebook ads
- `--ar 3:2`: DSLR-style photography
- `--ar 21:9`: cinematic, ultrawide banners

That's how you write aspect ratios in Midjourney. In ChatGPT and other services you pick the ratio with a button or say it in words: "16:9 format."

**Midjourney parameters (for V8; the set changes between versions, so see the service's docs for the full list):**
```
--hd           # a 2K image instead of the standard one (uses more generation time)
--s 250        # medium stylization
--s 750        # strong stylization (more artistic)
--chaos 50     # more variation among the 4 results
```

The `--q` quality parameter from earlier versions doesn't work in V8.

**Guidance scale (in open models; ChatGPT Images doesn't have this setting).** Each model has its own scale, so start from the default value (for Flux on fal.ai it's 3.5) and change it a little at a time:
- below the default: the model improvises more
- around the default: usually the best balance
- well above it: the model follows the prompt rigidly, but the image can look unnatural

**Consistency through references:**
```
Midjourney, style: --sref https://example.com/style.png
Midjourney, character: in V8 you attach a reference image through the Edit Model (up to 4 references); the --cref parameter remains only in older versions
Flux: what you can do depends on the version and the provider
```

---

### Avoiding AI image clichés in 2026

In 2024, the main problems were six fingers, weird eyes and melted hands. By 2026 these are **mostly solved** in current models.

**The new problems of 2026 (the "AI look"):**
- Skin that's too smooth (no pores or wrinkles at all)
- Glossy surfaces with unnatural reflections
- Generic faces (everyone looks like a stock photo)
- Compositions that are too symmetrical
- Yellow / golden hour lighting everywhere (models love this light)
- Perfect focus everywhere (no natural depth of field)

**Fixes: add these to your prompt:**
```
✅ "natural skin texture, visible pores, slight skin imperfections"
✅ "candid pose, asymmetric composition, off-center subject"
✅ "film grain, slight blur on background, shallow depth of field"
✅ "harsh midday lighting" instead of the default golden hour
✅ "real moment captured, not posed, slight motion blur"
✅ "imperfect framing, like phone photography"
```

**Post-processing for a "human touch":**
1. Lightroom / Photoshop → add grain (Filter → Noise → Add Noise, 3-5%)
2. Slight color grading (cooler shadows, warmer highlights)
3. A subtle vignette
4. An imperfect crop (off-center subject)
5. Slight chromatic aberration at the edges

🎨 **Picture this:** AI generates a "perfect" photo. A real photo always has imperfections, and that's what makes it feel alive. Add a little grit, and the image stops looking machine-made.

---

### The legal side

This is an important chapter that many people skip. In 2026 the landscape got more complicated. This is general information, not legal advice: laws differ from country to country, and for anything serious you need a lawyer.

**Copyright on AI-generated images:**
- **USA:** the US Copyright Office decided in 2023 (and confirmed in 2025) that purely AI-generated images **cannot be registered for copyright**. Protection is possible only for what a human contributed: substantial reworking, selection, arrangement
- **EU:** unclear; regulators are still discussing it
- **What it means in practice:** purely generated images aren't protected by copyright in the US, so it's hard to stop other people from copying them. The more of your own work there is in the final piece, the stronger your position

Learn more: [https://www.copyright.gov/ai/](https://www.copyright.gov/ai/)

**Commercial use, service by service:** terms change and depend on the plan, so for the most part the table tells you what to check rather than giving a ready answer.

| Service | What to check before commercial use |
|---|---|
| Midjourney | Subscription terms: commercial use depends on your plan and on the size of your company (Terms of Service page) |
| ChatGPT Images / GPT Image | OpenAI's terms of use: rights to the output and restrictions on content |
| Flux | The specific model's license: some versions are non-commercial (the old Dev), others have different terms; read the model's page |
| Recraft | On the Free plan, images are owned by Recraft and aren't licensed for commercial use; paid plans give you ownership and commercial rights (as of October 2026) |
| Ideogram | On the service's website, commercial use is allowed, but images made on the free plan are visible to everyone; running the open 4.0 weights yourself for commercial purposes requires a license from Ideogram (as of October 2026) |

**Likeness (images of real people):**
- Each service has its own rules about images of real people, especially public figures
- Open models may have no built-in blocks at all, and the legal responsibility is yours
- GDPR (EU) and the right of publicity (US): using a real person's likeness usually requires their consent

**Watermarking and labeling:**
- Google (Nano Banana in Gemini): images are marked with an invisible SynthID watermark
- Other services use different labels (for example, C2PA metadata, a record of where a file came from); check the rules of the specific service
- In the EU, the AI Act's requirements for marking generated content (Article 50) have applied since August 2, 2026; check current sources for who they cover and how

**Best practice:** add an "AI-generated" label if you use the images in marketing. For e-commerce product shots, check the platform's rules.

---

### Real costs: how to calculate them

The prices in this lesson are deliberately not baked into tables: they can change within a month. Instead of ready-made numbers, here are formulas where you plug in current values from the pricing pages.

**For a subscription:**
```
cost per image = monthly subscription price / number of images you actually made
```

**For an API (pay per image):**
```
monthly spend = number of images you need × number of options per image × price per image
```

People usually generate 4-8 options and pick one, so you pay for every image you generate, not just the one you end up using.

**For running it on your own machine (open weights):**
```
payback period (months) = graphics card price / (monthly API spend you're replacing − electricity)
```

An example with made-up numbers (plug in your own; electricity is left out of the example): a graphics card costs $1,500 and the API runs you $50 a month, so it pays for itself in about 30 months; at $200 a month, in about 8. Running it yourself makes sense if you generate a lot and steadily, and also need privacy or full control.

Compare subscriptions and APIs at the same volume: take your own 1,000 images a month and run the numbers through each formula.

---

### Image generation trends in 2026

**Real-time generation:**
- Fast model versions respond in seconds
- LCM (Latent Consistency Models): a few steps instead of 28-50
- Uses: interactive web apps, AR filters, live design

**Multi-image consistency:**
- Character references (in Midjourney, for Flux through hubs, and in Nano Banana) are improving fast
- You can make a comic dozens of pages long with a consistent character
- Storytelling with AI is becoming viable

**Video generation:**
- Runway: Gen-4.5; Kling: VIDEO 3.0 (4.0 was announced at the end of September 2026); Luma: Ray 3.2
- Google Flow: Google's video studio; it runs the Gemini Omni models (released in May 2026) and Veo 3.1
- Sora (OpenAI) has been shut down: the website and app since April 26, 2026, the API since September 24, 2026
- Pika: short clips and a set of apps
- A separate lesson on video generation: [AI video generation](71-ai-video-generation.md)

**3D from images:**
- There are now models that turn a single image into a 3D mesh (for example, Trellis from Microsoft and Hunyuan3D from Tencent; check whether they're still current)
- Uses: game development, 3D product views in e-commerce

**Inpainting / editing:**
- FLUX Tools: precise, targeted editing
- Adobe Firefly: built right into Photoshop
- Ideogram 4.5: precise editing of existing images from a description
- ChatGPT Images: edits based on comments placed on the image itself (version 2.5, in the mobile app)

---

### Anti-patterns

❌ **Using default settings**: the output comes out generic. Always set the aspect ratio and style.

❌ **Not setting an aspect ratio**: the model makes a 1:1 image when you need 16:9 for YouTube. You can't crop it without losing quality.

❌ **Trusting a single generation**: ALWAYS generate 4-8 options and pick the best one. It costs little and saves hours of redoing.

❌ **Photorealistic AI people without disclosure**: it's an ethical and legal problem. It can cost you your reputation and get you into legal trouble.

❌ **Skipping post-processing**: AI output is rarely production-ready. Spend at least 5 minutes in Photoshop/Lightroom on the final touches.

❌ **One tool for every job**: Midjourney for a logo = a weak result compared with Recraft. Each task gets its own tool.

❌ **Hardcoded prompts**: you don't keep template prompts in a library, so you write every prompt from scratch. Keep them in a note, a document or a `prompts/` folder.

❌ **Ignoring the commercial license**: some Flux versions have a non-commercial license, and Recraft's Free plan doesn't allow commercial use. Check the terms of the model and your plan before using anything in production.

---

### Who should use what

No prices here: they change, so use the formulas above and the current pricing pages.

**Beginner (hobby, learning):**
- ChatGPT or Gemini: images are included in the free plan, within limits
- Ideogram: free plan (images made on it are visible to everyone)
- Photopea (a free Photoshop alternative in your browser)
- **Total: $0/month**

**Content marketer (Instagram account, blog, regular content):**
- Midjourney (the entry-level plan; current price on the pricing page)
- Ideogram: free plan
- Recraft: a paid plan if the logos and icons go into your work; the Free plan doesn't allow commercial use
- Canva for final assembly (you don't always need the paid plan)
- **Total: the Midjourney subscription + whatever else you decide to pay for**

**Freelance designer (client projects):**
- Midjourney on a higher plan
- Recraft on a paid plan
- Flux through the API, paying for what you use
- Photoshop (Creative Cloud) or an alternative
- **Total: your subscriptions plus API usage; add it up from the pricing pages**

**Professional studio (high volume, brand consistency):**
- Everything listed above
- Your own graphics card for open models: a one-time purchase plus electricity (and a license, if the model requires one)
- Higher-tier Recraft and Adobe Creative Cloud plans
- **Total: calculate each line item separately**

🎨 **Picture this:** a professional kitchen. A culinary student learns on a single stove, and that's enough. A serious home cook buys a good range and a couple of knives. A head chef has 5 stoves, 20 knives and a pot for every job. Don't buy the chef's setup while you're still a student.

---

## Practice

The exercise below needs no code: all you need is a browser or a phone. Steps 1-4 after it are written for people who write Python scripts. They're optional: if you don't program, skip them and go to Step 5.

**No-code exercise: an image for your own project (about 30 minutes)**

1. Open [chatgpt.com](https://chatgpt.com) or [gemini.google.com](https://gemini.google.com) and sign in. Images are included even in the free plans, but the number you can make per day is limited.
2. In the message box, describe what to draw: what's in the picture, the style, the lighting and the aspect ratio. For example: "Create a cover image for a post about home baking: warm morning light, a wooden table, fresh bread, top-down view, 4:5 format, no text."
3. Wait for the result (it can take a couple of minutes) and ask for one change in plain words: "make the light cooler," "remove the knife," "leave empty space at the top for a headline."
4. Ask for two more options and pick the best of the three.
5. Save the image: open it and use the save button (in ChatGPT it's called Save).
6. Repeat the same request in [Ideogram](https://ideogram.ai), adding lettering: "with a big headline that says 'Bread in an hour.'" Compare where the text came out cleaner. On Ideogram's free plan your images are visible to everyone, so don't use personal photos or data there.

**Check yourself:** you have at least two saved images (one without text and one with), and you can say which service handled the lettering better.

### Step 1 (optional, for people who program): Set up Flux through fal.ai

The fastest start for scripts is Flux through fal.ai: you can try a model in the playground with no code, and for scripts you need a key. Model IDs on fal.ai change as new versions come out: before you run anything, open the page of the model you want and use its current ID in place of the ones in the examples below.

```bash
# Sign up at fal.ai (Google login)
# Check the trial credit terms when you sign up

# Install the Python SDK
pip install fal-client python-dotenv pillow requests aiohttp

# Create a .env file
echo "FAL_KEY=your-fal-key-here" > .env
```

Get your FAL_KEY here: [https://fal.ai/dashboard/keys](https://fal.ai/dashboard/keys)

---

### Step 2 (optional): A simple generator on a fast Flux version

```python
# flux_simple.py: the minimum to get started (check the model ID on fal.ai)
import os
import fal_client
from dotenv import load_dotenv
import requests
from pathlib import Path

load_dotenv()
os.environ["FAL_KEY"] = os.getenv("FAL_KEY")

def generate_image(prompt: str, output_path: str, aspect_ratio: str = "square"):
    """Generate an image with a fast Flux version."""
    print(f"Generating: {prompt[:50]}...")

    result = fal_client.run(
        "fal-ai/flux/schnell",  # check the current ID on fal.ai
        arguments={
            "prompt": prompt,
            "image_size": aspect_ratio,
            "num_inference_steps": 4,
            "num_images": 1,
        }
    )

    # Save it
    image_url = result["images"][0]["url"]
    image_data = requests.get(image_url).content
    Path(output_path).parent.mkdir(parents=True, exist_ok=True)
    Path(output_path).write_bytes(image_data)
    print(f"Saved: {output_path}")
    return output_path


if __name__ == "__main__":
    generate_image(
        prompt="professional product photography, ceramic coffee mug, white background, soft studio lighting, natural shadow",
        output_path="output/mug.png",
        aspect_ratio="square_hd"
    )
```

**Image sizes for Flux on fal.ai:**
- `square_hd`: 1024x1024
- `square`: 512x512
- `portrait_4_3`: 768x1024
- `portrait_16_9`: 576x1024
- `landscape_4_3`: 1024x768
- `landscape_16_9`: 1024x576

---

### Step 3 (optional): Batch-generate product shots

```python
# batch_products.py: generate 10 products in parallel
import os
import fal_client
import asyncio
import aiohttp
from dotenv import load_dotenv
from pathlib import Path

load_dotenv()  # reads FAL_KEY from the .env file
os.environ["FAL_KEY"] = os.getenv("FAL_KEY", "your-key")

# placeholder value: use the price per image from your provider's pricing page
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
    """Generate one product asynchronously."""
    prompt = PROMPT_TEMPLATE.format(product=product)

    # a stronger Flux version for e-commerce (check the ID on fal.ai)
    handler = await fal_client.submit_async(
        "fal-ai/flux-pro/v1.1",
        arguments={
            "prompt": prompt,
            "image_size": "square_hd",
            "num_images": 1,
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
    print(f"\nDone! Generated {len(results)} products.")
    print(f"Cost: ~${len(results) * PRICE_PER_IMAGE:.2f}")


if __name__ == "__main__":
    asyncio.run(main())
```

**Run it:**
```bash
python batch_products.py
# In a minute or two you'll have 10 product shots
# Cost: number of images × your provider's price per image
```

---

### Step 4 (optional): Combine Flux + Ideogram for YouTube thumbnails

```python
# youtube_thumbnails.py: a thumbnail pipeline
import os
import fal_client
import requests
from dotenv import load_dotenv
from pathlib import Path

load_dotenv()  # reads FAL_KEY from the .env file
os.environ["FAL_KEY"] = os.getenv("FAL_KEY")

def generate_background(topic: str, save_path: str):
    """A fast Flux version makes the background."""
    result = fal_client.run(
        "fal-ai/flux/schnell",  # check the current ID on fal.ai
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
    """Ideogram makes the lettering on a transparent background (it's also available through fal.ai)."""
    result = fal_client.run(
        "fal-ai/ideogram/v3/generate-transparent",  # check the current Ideogram version on fal.ai
        arguments={
            "prompt": f"big bold text '{hook_text}', white text with red outline, condensed sans-serif font, dramatic typography for YouTube thumbnail",
            "aspect_ratio": "16:9",
        }
    )
    url = result["images"][0]["url"]
    Path(save_path).write_bytes(requests.get(url).content)
    return save_path


def assemble_thumbnail(bg_path: str, text_path: str, output_path: str):
    """Final assembly with PIL."""
    from PIL import Image

    bg = Image.open(bg_path).convert("RGBA")
    text = Image.open(text_path).convert("RGBA")

    # Resize text overlay to match bg
    text = text.resize(bg.size)

    # Composite
    combined = Image.alpha_composite(bg, text)
    combined.convert("RGB").save(output_path, "PNG")
    print(f"Done: {output_path}")


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

### Step 5: A prompt library: save the prompts that work

Without code: start a note or a document and collect the prompts that gave you good results. Next to each one, write down which task it worked for and in which service. In a month you'll have your own set of ready-made starting points.

If you write scripts, it's handier to keep prompts in folders and files:

```bash
mkdir -p prompts/{product,thumbnail,social,brand}
```

```yaml
# prompts/product/ecommerce-white-bg.yaml
name: "E-commerce white background"
model: "fal-ai/flux-pro/v1.1"
template: |
  professional product photography, {product},
  pure white background, soft studio lighting from top-left,
  subtle natural shadow underneath, centered composition,
  commercial e-commerce style, photorealistic, high detail,
  sharp focus, empty background
params:
  image_size: "square_hd"
notes: |
  - Test 4 generations per product, pick best
  - Post-process: subtle shadow enhancement in Photoshop
  - Cost: per the provider's pricing page
```

**Tip** (optional, for people who work in Claude Code): create `.claude/agents/image-prompt-engineer.md`, a helper that reads these YAML files and builds the final prompts for each task.

---

## Tools and resources

- **[Midjourney](https://www.midjourney.com)**: official site: works in the browser, with a Discord bot as well
- **[ChatGPT Images (GPT Image)](https://learn.chatgpt.com/docs/image-generation)**: image generation built into ChatGPT
- **[OpenAI API Pricing](https://developers.openai.com/api/docs/pricing)**: current API prices for gpt-image-2 and gpt-image-2.5
- **[Black Forest Labs (Flux)](https://bfl.ai)**: the official Flux site, technical details
- **[fal.ai](https://fal.ai)**: one of the API providers for Flux, with a playground for testing
- **[Replicate](https://replicate.com)**: an alternative API host for Flux, Stable Diffusion and other models
- **[Recraft](https://www.recraft.ai)**: vector graphics + brand identity
- **[Ideogram](https://ideogram.ai)**: the go-to tool for text in images
- **[Photopea](https://www.photopea.com)**: a free Photoshop alternative in your browser
- **[Canva](https://www.canva.com)**: final assembly with templates
- **[Lexica](https://lexica.art)**: search by prompts and styles
- **[PromptHero](https://prompthero.com)**: a library of prompts that work
- **[US Copyright Office on AI](https://www.copyright.gov/ai/)**: the official US position on copyright for AI images
- Current prices and versions: [What's current](https://aimayak.com/en/now/)

---

## Checklist: a professional pipeline

✅ A main model is picked for each use case (not one tool for everything)
✅ The workflow is standardized (written down in a note or in the project README)
✅ A prompt library is set up (a note, a document or a `prompts/` folder)
✅ The aspect ratio is set for each platform (16:9, 9:16, 1:1, 4:5)
✅ A post-processing pipeline is in place (at least grain + color grading)
✅ Legal check: the commercial use license fits the use case
✅ A backup tool is ready in case your main one is unavailable
✅ Cost tracking: you know the cost per asset for budgeting
✅ Disclosure policy: AI-generated images are labeled wherever ethics or the law require it
✅ Source files (editor files, source images) are kept in a separate folder for reuse

---

## Key takeaways

> In image generation in 2026, one all-purpose tool means compromising everywhere. A professional keeps 2-3 models in the pipeline: Flux for photorealism, Ideogram for text, Recraft for vectors or Midjourney for artistic work. A combination of tools gives you better results at a reasonable cost.

> Quality depends heavily on the prompt. Aspect ratio, negative prompts, style references and guidance scale aren't "options"; they're required settings (wherever the service supports them). Default settings = generic output.

> The legal landscape in 2026 isn't straightforward. Purely AI-generated images can't be protected by copyright in the US. The commercial license depends on the model and the plan. Check the license **before** you use images in production, not after.

> Post-processing is the difference between an "AI picture" and production-ready material. Spend at least 5 minutes on grain, color grading and tiny imperfections, and the image stops looking machine-made (and still label it as AI-generated where that's required).

---

## Next lesson

→ [AI video generation: Runway, Kling, Luma and more](71-ai-video-generation.md): how to get a short clip from text or an image.
