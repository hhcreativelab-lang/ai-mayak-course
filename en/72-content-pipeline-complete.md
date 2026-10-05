# The full AI content pipeline: from idea to post

**Time:** about 30 min reading + 60 min practice

---

## The gist

One person, in a single workday, produces a week's worth of content for five platforms: text, voice, video and a publishing schedule. Not because they're a genius. Because they have the right pipeline in place. Today we build that pipeline together: trends → idea → text → image → voice → video → publishing. Claude is the conductor, and the other tools are the orchestra.

🎨 **Picture this:** a Toyota assembly plant. Nobody builds the car by hand: you press one button, and robots mount the wheels, paint the body and run the tests. A finished car rolls off the line. The idea is the car body. Claude, ElevenLabs, Runway and Buffer are the robots on the line. You're the plant manager who decides what gets built.

---

## Key concepts

- **Content factory**: a single orchestrator runs the whole chain, from a trend to a published post
- **One idea → many formats**: adapting for each platform without writing everything from scratch
- **A content calendar as JSON**: a machine-readable schedule that Claude understands and carries out
- **Parallel generation**: Claude, ElevenLabs and Runway work at the same time, not one after another
- **Analytics loop**: metrics from published content go back into Claude to improve the next batch
- **Checkpoints**: approval points, so nothing half-baked gets published automatically
- **Batch production**: 30 posts in one run, and what the unit economics look like at that scale

---

## Theory

### Architecture: the 9 stations of the pipeline

Before writing any code, we draw the diagram. The whole factory is made of 9 stations:

```
TREND → RESEARCH → OUTLINE → TEXT → ADAPTATIONS → IMAGE → VOICE → SCHEDULE → ANALYTICS
```

Each station is a separate API call (API stands for application programming interface: the way one program talks to another). Any station can be swapped out or switched off without rebuilding the whole system.

🎨 **Picture this:** LEGO Technic. Each block is a separate part with a clear way to connect. If one motor breaks, you replace just that motor; you don't take the whole car apart. Claude is the text blocks. Runway is video. ElevenLabs is voice. Buffer is delivery.

**What each station does:**

| Station | Tool | What it does |
|---|---|---|
| Trend | Web search + Claude | What's hot today |
| Research | Claude + MCP tools (search, documentation) | Facts, data, sources |
| Outline | Claude Sonnet | The structure of the piece |
| Text (main) | Claude Sonnet | The full article or script |
| Adaptations | Claude Haiku | Newsletter, X (Twitter), LinkedIn |
| Image | gpt-image-2 / Ideogram / Nano Banana | Cover, illustrations (DALL-E 3 was turned off in the API on May 12, 2026) |
| Video (optional) | Kling / Runway | A short 5–15 second video |
| Voice (optional) | ElevenLabs (TTS, text-to-speech: turning text into spoken audio) | Voiceover for Reels and Shorts |
| Publishing | Buffer API / your newsletter platform / a direct bot API | Scheduling and sending |

**What one content package costs**: work it out from each service's pricing. For Claude, here's the ballpark (prices per 1 million tokens as of October 2026: Sonnet 5.5 is $2 for input and $10 for output, Haiku 4.5 is $1 and $5): a 1,200-word article costs a few cents, and the adaptations cost a cent or two. Images, video and voice cost whatever the service you pick charges. To add up your whole stack, use the lesson [What AI tools really cost](d04-ai-stack-costs.md).

---

### A content calendar as JSON: a machine-readable schedule

A content calendar isn't an Excel spreadsheet. It's a JSON file that Claude reads and acts on. Machine-readable means Claude can fill in next week by itself, based on last week's analytics.

```json
{
  "brand": {
    "name": "Acme Realty",
    "voice": "Friendly expert. Not a salesperson. Facts + stories.",
    "audience": "Americans aged 35–55 who are thinking about moving to or investing in Ecuador",
    "languages": ["en"],
    "channels": ["newsletter", "youtube", "instagram", "linkedin"]
  },
  "week": "2026-10-05",
  "posts": [
    {
      "id": "post-001",
      "publish_at": "2026-10-05T09:00:00-05:00",
      "topic": "What it really costs to live in Cuenca in 2026",
      "content_type": "educational",
      "formats": {
        "blog": { "words": 1200, "status": "pending" },
        "newsletter": { "sections": 3, "status": "pending" },
        "youtube_script": { "duration_min": 8, "status": "pending" },
        "twitter": { "tweets": 5, "status": "pending" },
        "linkedin": { "status": "pending" }
      },
      "assets": {
        "cover_image": null,
        "short_video": null,
        "voice_over": null
      },
      "keywords": ["cost of living in Cuenca", "cost of living in Ecuador", "moving to Ecuador"],
      "approved": false
    }
  ]
}
```

When `approved` changes to `true`, the orchestrator starts production and fills in `assets`.

---

### One idea → many formats

🎨 **Picture this:** a rough diamond. One stone, different cuts: a ring, earrings, a pendant, a brooch. The substance stays the same; the shape is made for each market.

Here's how Claude Haiku turns one main article into versions for every platform for a couple of cents:

```python
import anthropic
import json
import os

claude = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])


def generate_main_article(topic: str, keywords: list[str],
                           brand_voice: str, word_count: int = 1200) -> str:
    """Generates a full SEO-optimized article with Claude Sonnet."""
    response = claude.messages.create(
        model="claude-sonnet-5-5",  # current model IDs: see Anthropic's documentation
        max_tokens=4000,
        messages=[{
            "role": "user",
            "content": f"""Write a blog article.

Topic: {topic}
Length: {word_count} words
SEO keywords: {', '.join(keywords)}
Brand voice: {brand_voice}

Structure:
1. H1 headline (with the main keyword)
2. Introduction (150 words, a hook + a promise)
3. 3–4 H2 sections with specific facts and numbers
4. Practical tips (bulleted list)
5. Conclusion + call to action

Requirements:
- Facts only, no filler like "this is very important"
- Specific numbers and examples
- Conversational but expert tone
- Language: American English, Markdown formatting"""
        }]
    )
    return response.content[0].text


def adapt_to_all_platforms(main_article: str, brand_context: str,
                            topic: str) -> dict:
    """
    Turns one base article into content for every platform.
    Claude Haiku: fast and cheap (a couple of cents).
    """
    response = claude.messages.create(
        model="claude-haiku-4-5",  # Haiku 4.5: retirement from the API is possible no earlier than October 15, 2026; check the IDs in Anthropic's documentation
        max_tokens=3000,
        messages=[{
            "role": "user",
            "content": f"""You are the brand's content strategist. Brand: {brand_context}

Main article on the topic "{topic}":
---
{main_article}
---

Adapt it into the following formats. Return ONLY valid JSON:

{{
  "newsletter": {{
    "subject_line": "Subject line (short and specific)",
    "sections": [
      "Section 1: the main story (up to 1,000 characters, with emoji, friendly)",
      "Section 2: goes deeper on one idea (800 characters)",
      "Section 3: a practical tip + CTA (600 characters)"
    ]
  }},
  "twitter_thread": [
    "Post 1/5: hook (up to 280 characters)",
    "Post 2/5: key fact",
    "Post 3/5: an example or a story",
    "Post 4/5: an unexpected angle",
    "Post 5/5: takeaway + link"
  ],
  "linkedin_post": "LinkedIn version (300–400 words, professional tone)",
  "instagram_caption": "Instagram version (150–200 words + 15 hashtags)",
  "youtube_description": "YouTube description (300 words, timestamps, keywords)"
}}"""
        }]
    )
    return json.loads(response.content[0].text)


def generate_youtube_script(topic: str, duration_minutes: int,
                              brand_voice: str) -> str:
    """Generates a YouTube video script with timestamps."""
    words_per_minute = 130    # a typical speaking pace; time yourself and adjust
    target_words = duration_minutes * words_per_minute

    response = claude.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=5000,
        messages=[{
            "role": "user",
            "content": f"""Write a script for a YouTube video.

Topic: {topic}
Length: {duration_minutes} min (~{target_words} words)
Voice: {brand_voice}

Format for each block:
[MM:SS] BLOCK TITLE
(Director's note: what to show on screen / B-roll)
Host's lines...

Structure:
[00:00] HOOK: the first 30 seconds, the most important part
[00:30] INTRO: who the host is, what the video is about
[01:00] MAIN PART: 3–4 blocks of 2–3 minutes each
[{duration_minutes-1}:00] WRAP-UP: summary + CTA
[{duration_minutes-1}:30] OUTRO: subscribe, next video

Write in a lively, conversational way, as if you're talking to a friend."""
        }]
    )
    return response.content[0].text
```

---

### Scheduling: a direct bot API and the Buffer API

For US channels, most of the work goes through Path 2 (Buffer): Instagram, LinkedIn, X. Your newsletter usually goes out from its own platform (Beehiiv, Kit, Mailchimp and others). The pipeline hands it a finished draft, and you either paste it in or, if your platform has an API, send it from code using the same pattern as the examples below.

**Path 1: a direct bot API, with Telegram as the example**: posting directly, for free. In the US, Telegram channels are far less common than email newsletters, so treat this code as a pattern rather than a recommendation: a token in an environment variable and one function that sends text with an optional image. A private Telegram channel also works as a free test channel for previewing posts on your phone.

```python
import asyncio
from telegram import Bot, InputFile
import os

TELEGRAM_BOT_TOKEN = os.environ["TELEGRAM_BOT_TOKEN"]
CHANNEL_ID = os.environ["TELEGRAM_CHANNEL_ID"]


async def publish_to_telegram(text: str, image_path: str = None) -> dict:
    """Publishes a post to a Telegram channel."""
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

**Path 2: the Buffer API**: a scheduler for Instagram, LinkedIn and Twitter/X. Buffer's API is built on GraphQL (the address is `https://api.buffer.com`), and you create the key in your Buffer settings; the free plan gives you one key. The schema was rebuilt in 2026, so check the fields against [developers.buffer.com](https://developers.buffer.com):

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
    Schedules a post through the Buffer API (GraphQL).
    due_at: publish time in ISO 8601 format, UTC, for example 2026-10-12T14:00:00.000Z
    Media goes to the Buffer API as a public link: see the documentation.
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

### An n8n workflow: automating the whole process

n8n is an automation platform that lets you connect every part of the pipeline visually. Its source code is open (Sustainable Use license, "fair-code"), and you can run the Community Edition on your own server and use it for internal work for free. It's an alternative to Make and Zapier. More in [n8n + AI: smart workflows](78-n8n-ai-workflows.md).

**A basic n8n workflow for the content factory:**

```
Cron (Monday 09:00)
  → HTTP: read content-calendar.json from GitHub
  → Code: keep only approved: true
  → Loop: for each post:
    → Claude API: generate the article (Sonnet)
    → Claude API: platform adaptations (Haiku) [in parallel]
    → Image generation: cover [in parallel]
    → Buffer API: schedule LinkedIn and Twitter/X
    → Newsletter platform: save the issue as a draft
    → Google Docs: save everything for a final review
  → Slack or email notification: "X posts ready, waiting for review"
```

Alternatives to n8n: **Make** (formerly Integromat) and **Zapier**, both cloud services that charge by credits and tasks (prices: [What's current](https://aimayak.com/en/now/)). More in [Zapier AI](79-zapier-ai.md).

---

### The orchestrator: one bash script for the whole pipeline

🎨 **Picture this:** an orchestra conductor. The conductor doesn't play the violin; they lead the whole orchestra. They cue the violins (Claude), the flutes (ElevenLabs), the cello (Runway). Every musician knows their part. The conductor knows the whole symphony.

```bash
#!/usr/bin/env bash
# content-factory-orchestrator.sh
set -euo pipefail

WEEK_DATE="${1:-$(date +%Y-%m-%d)}"
CALENDAR_FILE="content-calendar.json"
OUTPUT_DIR="./content-output/${WEEK_DATE}"

mkdir -p "$OUTPUT_DIR"
log() { echo "[$(date +%H:%M:%S)] $1"; }

log "🏭 Content factory started. Week: $WEEK_DATE"

POSTS=$(jq -r '.posts[] | select(.approved == true) | .id' "$CALENDAR_FILE")

if [ -z "$POSTS" ]; then
    log "⚠️ No approved posts. Stopping."
    exit 0
fi

for POST_ID in $POSTS; do
    log "▶️ Processing: $POST_ID"
    POST_DIR="${OUTPUT_DIR}/${POST_ID}"
    mkdir -p "$POST_DIR"

    TOPIC=$(jq -r ".posts[] | select(.id == \"$POST_ID\") | .topic" "$CALENDAR_FILE")
    KEYWORDS=$(jq -r ".posts[] | select(.id == \"$POST_ID\") | .keywords | join(\", \")" "$CALENDAR_FILE")
    PUBLISH_AT=$(jq -r ".posts[] | select(.id == \"$POST_ID\") | .publish_at" "$CALENDAR_FILE")

    log "  Topic: $TOPIC"

    # Article and YouTube script in parallel
    python3 generate_article.py --topic "$TOPIC" --keywords "$KEYWORDS" \
        --output "${POST_DIR}/article.md" &
    python3 generate_script.py --topic "$TOPIC" --duration 8 \
        --output "${POST_DIR}/youtube-script.md" &

    wait

    # Adaptations and cover image in parallel
    python3 adapt_platforms.py --article "${POST_DIR}/article.md" \
        --output "${POST_DIR}/adaptations.json" &
    python3 generate_image.py --topic "$TOPIC" \
        --output "${POST_DIR}/cover.jpg" &

    wait
    log "  ✅ Content for $POST_ID is ready"

    # Schedule the posts
    python3 schedule_content.py --post-id "$POST_ID" \
        --adaptations "${POST_DIR}/adaptations.json" \
        --cover "${POST_DIR}/cover.jpg" \
        --publish-at "$PUBLISH_AT"
done

log "🎉 Done! Posts scheduled: $(echo "$POSTS" | wc -w)"
```

---

### The analytics loop: content that learns from results

```python
def run_analytics_loop(days_back: int = 7) -> dict:
    """
    Collects last week's metrics and generates topics for next week.
    """
    newsletter_stats = get_newsletter_stats(days_back)
    youtube_stats = get_youtube_stats(days_back)
    instagram_stats = get_instagram_stats(days_back)

    combined_stats = {
        "newsletter": newsletter_stats,
        "youtube": youtube_stats,
        "instagram": instagram_stats,
        "period_days": days_back,
    }

    response = claude.messages.create(
        model="claude-sonnet-5-5",
        max_tokens=2000,
        messages=[{
            "role": "user",
            "content": f"""You are a content strategy analyst.
Analyze the results for the last {days_back} days:

{json.dumps(combined_stats, ensure_ascii=False, indent=2)}

Give a structured analysis in JSON:
{{
  "winners": ["post + why it worked"],
  "flops": ["post + why it didn't land"],
  "patterns": ["what type of content works consistently"],
  "best_time": {{"newsletter": "HH:MM", "instagram": "HH:MM"}},
  "next_week_topics": ["topic 1", "topic 2", "topic 3", "topic 4", "topic 5"],
  "strategy_changes": ["what to change in the production process"]
}}

Use only the data in these statistics; don't make anything up."""
        }]
    )

    recommendations = json.loads(response.content[0].text)
    update_calendar_with_recommendations(recommendations)
    return recommendations
```

---

### What the pipeline costs: how to calculate it

A typical plan: 5 topics a week × 4 weeks = 20 content packages a month.

| Component | How to calculate it |
|---|---|
| Claude Sonnet (article + script) | tokens × API price. Sonnet 5.5 as of October 2026: $2 for input and $10 for output per 1 million tokens; a 1,200-word article costs a few cents |
| Claude Haiku (adaptations) | Haiku 4.5: $1 for input and $5 for output per 1 million tokens; a set of adaptations costs a cent or two |
| Image (cover) | the pricing of whichever service you pick |
| ElevenLabs (voiceover, optional) | credits on your plan |
| Kling or Runway video (optional) | credits per second of video, usually the most expensive line |
| Scheduler | Buffer and Typefully both have free plans to get started; paid plans are priced per channel |

The total is the sum of those prices. Work out your own version with the formula from the lesson [What AI tools really cost](d04-ai-stack-costs.md) before you promise anyone a regular flow of content.

---

## Practice

### Step 1: Create the project structure

```bash
mkdir -p content-factory/{scripts,templates,output,logs}
cd content-factory
touch content-calendar.json scripts/generate_article.py \
      scripts/adapt_platforms.py scripts/schedule_content.py .env
```

### Step 2: Fill in the first post in calendar.json

Copy the JSON template from the theory section. Replace the topic with one that fits your business or your client's niche. Set `"approved": true` for a test run.

### Step 3: Build generate_article.py

Use the `generate_main_article()` function from the theory section. Add argparse for `--topic`, `--keywords` and `--output`. Run it and check that the article gets generated and saved to a file.

### Step 4: Build adapt_platforms.py

Use `adapt_to_all_platforms()`. The input is the article file; the output is `adaptations.json`. Open the JSON and read the newsletter sections: they should sound like a person wrote them, not like a stiff machine translation.

### Step 5: Set up publishing

For Instagram, LinkedIn and X, connect the accounts in Buffer and test `schedule_to_buffer()` with one post scheduled for tomorrow. To see a post exactly the way a subscriber would, the quickest free option is a private Telegram test channel (Path 1):

```bash
pip install python-telegram-bot
```

Create a bot through @BotFather. Copy `publish_to_telegram()`. Send a test message to your channel and make sure the Markdown formatting works.

### Step 6: Run the orchestrator

Run `content-factory-orchestrator.sh`. Watch in real time as the pipeline moves through the stations. The final files will be in `content-output/{date}/{post-id}/`. Check every file.

### Step 7: Batch production: 30 posts in a day

Add 30 entries to calendar.json (all with approved: true). Run the orchestrator and time it. This is your first experience producing content at scale: the moment you feel the difference between a craftsman and a factory.

---

## Tools and resources

- **[Anthropic API](https://platform.claude.com/docs)**: Claude Sonnet and Haiku (the backbone of the pipeline)
- **[python-telegram-bot](https://python-telegram-bot.org)**: a wrapper around the Telegram Bot API (for the Path 1 example)
- **[Buffer API](https://developers.buffer.com)**: scheduling posts (GraphQL)
- **[Postiz](https://github.com/gitroomhq/postiz-app)**: an open-source alternative to Buffer that you host yourself (check that the project is still active)
- **[n8n](https://n8n.io)**: a workflow orchestrator you can run on your own server
- **[ElevenLabs API](https://elevenlabs.io/docs/api-reference)**: TTS with voice cloning
- **[OpenAI Images](https://platform.openai.com/docs/guides/images)**: generating covers (the gpt-image-2 model; DALL-E 2 and 3 were turned off in the API on May 12, 2026)
- **[jq](https://jqlang.github.io/jq/)**: a command-line tool for working with JSON in bash
- **[Schedule](https://schedule.readthedocs.io)**: cron-like scheduling in Python for local runs
- **Prices and versions:** [What's current](https://aimayak.com/en/now/)

---

## Key takeaways

> The factory doesn't take days off. Set up the pipeline once, and it produces drafts every week. Your job is to approve the topics on Mondays and review what comes out before it's published; the routine steps in between run automatically.

> One idea, many formats. Don't write six different texts for six platforms. Write one main piece, and Claude Haiku cuts it to fit each one. A few cents versus a few hours of manual work.

> The analytics loop closes the circle. Content without feedback is shooting in the dark. Metrics into Claude → recommendations → new topics → better content. Each week can build on what you learned the week before.

---

## Next lesson

→ [AI for email: a smarter inbox, drafts and replies](73-ai-email-communications.md)
