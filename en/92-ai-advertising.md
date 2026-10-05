# AI for advertising: ad copy, A/B tests, smart bidding

**Time:** about 25 min reading + 40 min practice

---

## The gist

An ad copywriter works 8 hours, writes 5 versions of an ad, gets tired and goes home. Claude writes 50 versions in a few minutes, analyzes the test results and helps you see which one works best.

It isn't just faster. It's a different game: more experiments → more data → better ads → often a lower cost per click.

🎨 **Picture this:** an ad agency used to be like a restaurant with a single cook: slow and expensive. Claude plus your data is more like a test kitchen: 50 recipes in a minute, you taste which one is best and scale up the winner. And the kitchen keeps working at night while the cook is asleep.

---

## Key concepts

- **Ad copywriting with Claude**: 50 headline variations from a single command
- **Meta Ads (Facebook/Instagram)**: copy and images with AI
- **Google Ads RSA**: responsive search ads, with Claude improving the headlines
- **LinkedIn Ads and TikTok Ads**: the same method, with each platform's own limits and policies
- **A/B testing**: Claude analyzes the results and calls the winner
- **Performance Max**: how Claude helps with asset groups
- **Adspirer MCP**: managing ad campaigns right from Claude
- **Automated reports**: data → analysis → specific recommendations

---

## Theory

### Ad copywriting: 50 versions in 3 minutes

Good advertising starts with testing. To test, you need lots of versions. That used to take a lot of time and money. Now it takes far less.

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
    """Generates ad copy variations"""

    client = anthropic.Anthropic()

    # Platforms change their character limits: check them against the Meta and Google Ads help pages
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
            "first_line_chars": 125  # visible before "more"
        }
    }

    specs = platform_specs.get(platform, platform_specs["facebook"])

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=2000,
        messages=[{
            "role": "user",
            "content": f"""Create {count} ad variations for {platform}.

Product: {product}
Target audience: {target_audience}
Key benefit: {key_benefit}
Platform limits: {json.dumps(specs, ensure_ascii=False)}

Use a different approach for each variation:
- Emotional (fear of missing out)
- Rational (numbers and facts)
- Social proof (reviews, customers)
- Curiosity (a question or a surprising fact)
- Direct (the benefit, stated plainly)

Use only claims that are true for this product. Don't invent numbers, reviews or customer counts.

Return a JSON array:
[
  {{
    "variant_id": 1,
    "approach": "name of the approach",
    "headline": "headline",
    "primary_text": "main text",
    "cta": "call to action",
    "target_emotion": "the emotion it aims for",
    "hypothesis": "why it should work"
  }}
]"""
        }]
    )

    return json.loads(response.content[0].text)


# Example: an online Excel course
variants = generate_ad_variants(
    product="Online Excel course for finance professionals",
    target_audience="Accountants and finance staff aged 25-45 who spend 2-3 hours on reports",
    key_benefit="Cut report time from 3 hours to 20 minutes",
    platform="facebook",
    count=10
)

for v in variants[:3]:
    print(f"\n--- Variation {v['variant_id']}: {v['approach']} ---")
    print(f"Headline: {v['headline']}")
    print(f"Text: {v['primary_text']}")
    print(f"CTA: {v['cta']}")
```

⚠️ **Every claim in an ad has to be true.** In the US, the FTC's truth-in-advertising rules apply to every ad, including the ones AI writes: no made-up reviews or customer counts, no results you can't back up. Each platform (Google, Meta, LinkedIn, TikTok) also has its own ad policies, with extra rules for sensitive categories such as housing, jobs, credit and health. AI drafts the copy; you're responsible for what goes live. If you're unsure about a claim, read the platform's policy pages or ask a lawyer.

### Meta Ads: copy and images

Meta (Facebook + Instagram) is the ad platform with the richest data. Claude helps with the copy and works alongside image generators for the visuals.

**The ad creation funnel:**

```
1. Claude → 10 copy variations
2. Flux / Midjourney / the image generator in ChatGPT → an image for each text
3. Launch an A/B test (5 variations at a time)
4. 3-5 days → collect data
5. Claude → analyzes the results
6. Scale the winner
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
            "content": f"""Create a detailed brief for a Meta Ads campaign.

Product: {product}
Daily budget: ${budget_daily}
Audience: {target_audience_description}

Include:
1. **Campaign structure**: how many ad sets, and the logic behind them
2. **Targeting**: detailed interests, age, location
3. **Lookalike recommendations**: who to base a lookalike audience on
4. **Formats**: which ad formats to use and why
5. **Budget**: how to split it across the ad sets
6. **KPIs**: what counts as success (CPC, CTR, CPL)
7. **Test plan**: what to test first

Be specific: numbers, percentages, recommendations."""
        }]
    )

    return response.content[0].text
```

🎨 **Picture this:** a media planner used to be a separate specialist who worked 9 to 5. Claude drafts the plan in seconds, even at 3 a.m. the night before a launch. A person still makes the call on the budget.

### Google Ads: RSA and smart keywords

Google RSA (responsive search ads): you supply up to 15 headlines and 4 descriptions, and Google mixes and matches them on its own. Claude helps you write 15 headlines that actually work well in any combination.

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
            "content": f"""Create an RSA ad for Google Ads.

Product: {product}
Landing page theme: {landing_page_theme}
Keywords: {', '.join(keywords)}

Requirements:
- 15 headlines, each up to 30 characters
- 4 descriptions, each up to 90 characters
- The headlines must work well in any combination
- Put the keywords in 3-4 headlines (not all of them!)
- Variety: benefits, actions, what makes you different, urgency

Return JSON:
{{
    "headlines": ["headline 1", ... "headline 15"],
    "descriptions": ["description 1", ... "description 4"],
    "pinning_recommendations": {{
        "headline_position_1": "which headline to pin to position 1",
        "reason": "why"
    }}
}}"""
        }]
    )

    return json.loads(response.content[0].text)


# Example: a law firm
rsa = generate_google_rsa(
    product="Real estate legal services",
    landing_page_theme="Close on your home purchase quickly and safely",
    keywords=["real estate attorney", "real estate closing", "home purchase lawyer"]
)

print("Headlines:")
for i, h in enumerate(rsa["headlines"], 1):
    chars = len(h)
    status = "✅" if chars <= 30 else "⚠️"
    print(f"{i}. {status} {h} ({chars} chars)")
```

### LinkedIn Ads and TikTok Ads: the same method

The functions above aren't tied to Meta and Google. LinkedIn Ads is the usual choice for B2B: you can target by job title, industry and company size, so the copy speaks to a role ("for HR managers at mid-size companies") rather than to an interest. On TikTok, an ad is a short vertical video, so the "copy" Claude writes is mostly a script for the first few seconds plus a caption. To add either platform, put a new entry in `platform_specs` with the current limits from that platform's own help pages (they change, so don't copy numbers from old blog posts) and run the same `generate_ad_variants()` and `analyze_ab_test()`.

### A/B testing: Claude picks the winner

Test data often looks confusing. One version has a higher CTR, but a higher CPC too. Fewer conversions, but cheaper ones. Claude helps you untangle it in seconds.

```python
def analyze_ab_test(test_results: list[dict]) -> dict:
    """
    test_results: a list of dicts with the results for each variation
    Example: [{"variant": "A", "impressions": 5000, "clicks": 150, "conversions": 12, "spend": 200}]
    """
    client = anthropic.Anthropic()

    # Add the calculated metrics
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
            "content": f"""Analyze the results of this ad A/B test and give recommendations.

Results:
{json.dumps(test_results, ensure_ascii=False, indent=2)}

I need:
1. **Winner**: which variation is better and WHY (consider every metric)
2. **Statistical significance**: is there enough data for a confident conclusion
3. **Takeaways**: what the results say about the audience
4. **Next step**: what to test next
5. **Scaling**: how much to increase the winner's budget

Be specific: give numbers and percentages."""
        }]
    )

    return {
        "raw_results": test_results,
        "analysis": response.content[0].text
    }


# Test
results = [
    {"variant": "A — Fear (loss)", "impressions": 10000, "clicks": 180, "conversions": 9, "spend": 350},
    {"variant": "B — Benefit (savings)", "impressions": 10000, "clicks": 220, "conversions": 18, "spend": 350},
    {"variant": "C — Social proof", "impressions": 10000, "clicks": 195, "conversions": 14, "spend": 350}
]

analysis = analyze_ab_test(results)
print(analysis["analysis"])
# Winner: B — CTR 2.2%, CPL $19.4, CVR 8.2%
# Variation A loses despite its intriguing headline
# Recommendation: not much data yet (9 and 18 conversions); keep the test running and raise B's budget gradually
```

### Performance Max: Claude helps with asset groups

PMax is a type of Google campaign that decides on its own where to show your ads (Search, YouTube, Gmail, Display). The quality of your materials (assets) is critical. For Search campaigns, Google also has AI Max: as of October 2026, the AI features are built into the campaigns themselves, so check names and settings against the Google Ads help pages.

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
            "content": f"""Create all the materials (assets) needed for a Performance Max campaign.

Product: {product}
Key benefits: {', '.join(key_benefits)}
Audience persona: {audience_persona}

Create:
{{
    "headlines": ["5 headlines up to 30 characters"],
    "long_headlines": ["5 long headlines up to 90 characters"],
    "descriptions": ["5 descriptions up to 90 characters"],
    "business_name": "company name (up to 25 characters)",
    "call_to_actions": ["a list of 5 calls to action"],
    "image_prompts": ["5 prompts for generating images in Midjourney/Flux"],
    "audience_signals": {{
        "interests": ["a list of interests for audience signals"],
        "custom_intent_keywords": ["intent keywords"],
        "remarketing_segments": ["remarketing segments"]
    }}
}}"""
        }]
    )

    return json.loads(response.content[0].text)
```

### Adspirer MCP: managing ads right from Claude

Adspirer is a third-party MCP service for ad accounts. It connects to Claude Code and Cowork as a plugin and, as of October 2026, works with Google Ads, Meta Ads and a number of other platforms. It lets Claude see real campaign data and make recommendations based on facts, not guesses. The service can also launch campaigns, so check its terms, give it the minimum permissions (start with read-only) and keep launching ads and changing budgets for yourself.

```
# In Claude Code, with Adspirer MCP connected:

"Show me campaigns with a CTR below 1% over the last 7 days"
→ Claude sees the data → gives you a list with recommendations

"Which keywords are spending money without any conversions?"
→ Claude analyzes it → a list of keywords to pause

"Create an ROI report for all campaigns for the month"
→ Claude generates it → comparison, conclusions, recommendations
```

### Automated reports: from data to conclusions

```python
def generate_weekly_ad_report(campaigns_data: dict) -> str:
    client = anthropic.Anthropic()

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=1500,
        messages=[{
            "role": "user",
            "content": f"""Generate a weekly report on the ad campaigns.

Data:
{json.dumps(campaigns_data, ensure_ascii=False, indent=2)}

Report format:
## This week's results
[3-4 key numbers]

## What's working
[top 3 things that worked, with numbers]

## What's not working
[top 3 problems, with numbers]

## Actions for next week
[5 specific steps, with the expected effect]

## Budget
[recommendations for reallocating]

Write like an analyst: specific, with numbers, no fluff."""
        }]
    )

    return response.content[0].text
```

---

## Practice

### Exercise: create 10 ad copy variations and analyze a test

**Part 1: Generating the variations (15 minutes)**

```python
# ad_generator.py

import anthropic
import json

client = anthropic.Anthropic()

def create_ad_batch(product_info: dict) -> list:
    """Creates a batch of ads for testing"""

    response = client.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=3000,
        messages=[{
            "role": "user",
            "content": f"""Create 10 ad variations for Facebook.

PRODUCT: {product_info['name']}
DESCRIPTION: {product_info['description']}
PRICE: {product_info['price']}
AUDIENCE: {product_info['audience']}
MAIN BENEFIT: {product_info['main_benefit']}
AUDIENCE PAIN POINT: {product_info['pain_point']}

Create 2 variations for each approach:
1. Fear of loss ("if you don't do X, you'll lose Y")
2. Benefit ("get X and save Y")
3. Social proof ("1,000 customers already...")
4. Curiosity ("Did you know that...")
5. Direct offer ("Get X for Y right now")

Use only facts from the product info above. Don't invent numbers, reviews or customer counts.

JSON format:
[{{
    "id": 1,
    "approach": "name",
    "headline": "up to 40 characters",
    "text": "up to 125 characters",
    "cta": "button",
    "image_direction": "what the image should show"
}}]"""
        }]
    )

    return json.loads(response.content[0].text)

# Run it for your product
my_product = {
    "name": "Online business English school for tech professionals",
    "description": "English for working on US teams, in 3 months",
    "price": "$99/month",
    "audience": "Developers and IT professionals aged 25-40 for whom English is a second language",
    "main_benefit": "Feel confident in job interviews and team meetings",
    "pain_point": "I know technical English, but I get lost in fast meetings with native speakers"
}

ads = create_ad_batch(my_product)

print("=== GENERATED ADS ===\n")
for ad in ads:
    print(f"#{ad['id']} — {ad['approach']}")
    print(f"Headline: {ad['headline']}")
    print(f"Text: {ad['text']}")
    print(f"CTA: {ad['cta']}")
    print(f"Image: {ad['image_direction']}")
    print()
```

**Part 2: Analyzing the test results (25 minutes)**

Once the test has run, enter the data and get the analysis:

```python
# Enter your real data after 5 days of testing (the numbers below are made up)
test_data = [
    {"id": 1, "approach": "Fear of loss", "impressions": 8500, "clicks": 102, "conversions": 4, "spend": 180},
    {"id": 2, "approach": "Fear of loss 2", "impressions": 8200, "clicks": 115, "conversions": 5, "spend": 175},
    {"id": 3, "approach": "Benefit", "impressions": 8800, "clicks": 185, "conversions": 12, "spend": 182},
    {"id": 4, "approach": "Benefit 2", "impressions": 8600, "clicks": 172, "conversions": 10, "spend": 178},
    {"id": 5, "approach": "Social proof", "impressions": 8300, "clicks": 166, "conversions": 11, "spend": 176},
    {"id": 6, "approach": "Social proof 2", "impressions": 8700, "clicks": 143, "conversions": 8, "spend": 181},
    {"id": 7, "approach": "Curiosity", "impressions": 9100, "clicks": 228, "conversions": 7, "spend": 185},
    {"id": 8, "approach": "Curiosity 2", "impressions": 8900, "clicks": 214, "conversions": 6, "spend": 183},
    {"id": 9, "approach": "Direct offer", "impressions": 8400, "clicks": 126, "conversions": 9, "spend": 177},
    {"id": 10, "approach": "Direct offer 2", "impressions": 8600, "clicks": 138, "conversions": 8, "spend": 179}
]

analysis = analyze_ab_test(test_data)
print(analysis["analysis"])
```

---

## Tools and resources

- **Meta Business Manager**: business.facebook.com (for running ads)
- **Google Ads**: ads.google.com
- **LinkedIn Campaign Manager**: LinkedIn's own tool for running ads (B2B audiences)
- **TikTok Ads Manager**: TikTok's own tool for running ads (short vertical video)
- **Adspirer MCP**: a tool for analyzing ads through Claude
- **Flux**: bfl.ai, the Black Forest Labs site (generating ad images from a prompt)
- **Meta Ad Library**: facebook.com/ads/library (see the ads your competitors are running)
- **Google Keyword Planner**: Google's keyword planning tool
- **Anthropic SDK**: for building Claude into your ad workflows; the model names in the code are as of October 2026. Current prices and versions: [What's current](https://aimayak.com/en/now/)

---

## Key takeaways

> Advertising is always a test. Whoever tests more variations learns faster. Claude makes testing cheap: 50 variations instead of 5, in minutes instead of days.
>
> Data analysis is the bottleneck on most ad teams. Claude removes that bottleneck: it sees every metric at once, doesn't get lost in spreadsheets and gives a specific conclusion with the reasoning behind it.
>
> The main rule: Claude writes the copy and analyzes the data, but a person launches and scales the ads. The final decision is always yours; AI just gets you there faster.

---

## Next lesson

→ [Sales AI: lead qualification, follow-up and closing deals](93-sales-ai.md)
