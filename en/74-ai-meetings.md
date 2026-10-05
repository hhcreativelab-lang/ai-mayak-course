# AI meeting notes with Otter.ai and Fireflies

**Time:** about 20 min reading + 30 min practice

---

## The gist

A 45-minute call with a client. Then another 30 minutes to write up the notes, send out the tasks and update the CRM. With five meetings a week, that's 2.5 hours of paperwork. Every single week. You can get those hours back. Otter.ai records, Fireflies analyzes, Claude organizes, ClickUp gets the tasks and a summary lands in your Slack, all while you're still saying goodbye to the client.

🎨 **Picture this:** the perfect assistant. Never misses a word, never gets tired, never asks for vacation, and sends you finished meeting notes before you've even closed your laptop. That isn't science fiction. It's a webhook + Claude + ClickUp.

---

## Key concepts

- **Automatic transcription**: AI turns speech into text in real time and tells the speakers apart
- **Speaker diarization**: the system knows who said what, even with ten people on the call
- **Action item extraction**: Claude finds commitments, deadlines and tasks in the flow of the conversation
- **Webhook pipeline**: a chain of steps: transcription → analysis → tasks → notification. (A webhook is an automatic "it's done, here's the info" message that one service sends to another.)
- **Local Whisper**: transcription on your own computer, without sending the audio to the cloud (for meetings under an NDA)
- **Meeting templates**: different prompts for different kinds of meetings: sales calls, client reviews, standups
- **Zoom AI Companion vs Fireflies**: when the built-in tool is enough and when you need an outside one

---

## The theory

### The problem: a meeting without a system costs you twice

A typical business meeting runs close to an hour. Afterward, a business owner spends another 20–40 minutes writing up notes, sending out tasks and updating the CRM (the customer database, like HubSpot or Salesforce). At 5 meetings a week, that's 2–3 hours that simply disappear.

Worse, notes you take by hand are inaccurate. You focus on the conversation and miss details. Or the opposite: you take notes and lose the thread of the conversation. It's an attention trap.

AI transcription fixes this at the root: the recording runs in the background, and nobody misses anything.

---

### Otter.ai: real-time transcription

Otter.ai is one of the pioneers in this market. It joins Zoom, Google Meet and Microsoft Teams as a bot participant, and it joins automatically when the meeting starts.

**What it does:**

- Real-time transcription with each speaker labeled
- An AI summary after the meeting: a structured recap, not just a wall of text
- Action items: tasks with the owner's name and a deadline
- Full-text search across all your transcripts (need something from a month ago? No problem)
- Integrations with work tools (see the list on their site)
- An MCP server for connecting it to AI assistants (on paid plans). MCP is a standard way to plug a tool into an assistant like Claude.

**Plans:** there's a Free plan with a monthly limit on minutes and paid plans with more minutes; current prices and limits are on otter.ai and the [What's current](https://aimayak.com/en/now/) page. Check the supported languages before you rely on it: if some of your meetings aren't in English, make sure your language is on Otter's list, or use a service with wider language coverage (for example, Fireflies).

🎨 **Picture this:** Otter.ai is a court stenographer who sits in on every meeting and types everything they hear in real time. Except this one never gets tired and doesn't cost much (you should still check the transcript for mistakes).

---

### Fireflies.ai: transcription + analytics + CRM integration

Fireflies goes further than Otter: it doesn't just record, it digs into what was said.

**On top of transcription** (according to the service's own description; check what your plan includes):

- **AI Summary**: a structured recap of what you discussed, what you decided and what's still open
- **Speaker Analytics**: who talked for how long, who dominated the conversation
- **Sentiment Analysis**: the tone of the conversation (positive / neutral / concerned)
- **Topic Tracker**: tracks mentions of key topics (budget, competitors, timelines)
- **CRM Push**: automatically sends the summary to HubSpot, Salesforce or Pipedrive
- **Webhooks**: sends data to any endpoint (a web address your own code listens on) after the meeting ends

Webhooks are exactly what make Fireflies the hub of our pipeline.

**Plans (as of October 2026):** Free, Pro, Business and Enterprise; see fireflies.ai for limits and prices. Whether you get API and webhook access depends on the plan. It supports 60+ languages and detects the language automatically.

**Recording consent:** recording a meeting requires the participants' consent, and in the US the rules vary by state: some states require everyone on the call to agree. Check the law in your state, and tell people you're recording at the start of every call.

---

### Zoom AI Companion vs Fireflies: which one to pick

| Feature | Zoom AI Companion | Fireflies.ai |
|---|---|---|
| Cost | Included in paid Zoom plans at no extra charge (check your plan) | Separate subscription (there's a free plan) |
| Integration | Built into Zoom | Works with Zoom, Meet, Teams |
| CRM sync | Limited | HubSpot, Salesforce, Pipedrive |
| Webhooks | Through the Zoom API (separate setup) | ✅ a core feature (depends on the plan) |
| Custom prompts | Limited | ✅ one for each meeting type |
| Tracking competitor mentions | — | ✅ Topic Tracker |
| Best for | Teams that live in Zoom | A custom pipeline + CRM |

**Bottom line:** Zoom AI Companion is enough if all you need is a summary. You need Fireflies when you're building an automatic pipeline: tasks → CRM → notifications.

---

### Microsoft Teams: the corporate setting

If your clients are large companies, they're probably on Teams. You have two options:

**Copilot in Teams** (built in): summaries, action items and answers to questions about what was said in the meeting. It requires a Microsoft 365 Copilot license (prices as of October 2026: Copilot Business from $18 per user per month billed yearly, a price listed through December 31, 2026, or $25.20 month to month). As a freelancer, you'd only have this if you pay for the license yourself.

**Fireflies + Teams**: Fireflies joins Teams as an outside bot. You keep every Fireflies feature, webhooks included. It's the best choice if you work with corporate clients on Teams but want to keep your own pipeline.

---

### Local Whisper: for confidential meetings

For full privacy, when the data must not leave your computer, run OpenAI Whisper locally. It's open source and works offline.

```bash
pip install openai-whisper
# Faster on Apple Silicon Macs:
pip install mlx-whisper
```

```python
import whisper

# small/medium/large: a trade-off between speed, quality and RAM
model = whisper.load_model("medium")

result = model.transcribe(
    "meeting_recording.mp3",
    language="en",          # force the language (more accurate); "es" for Spanish
    word_timestamps=True    # a timestamp for every word
)

print(result["text"])
```

**When to use Local Whisper:**

- Legal negotiations
- Meetings under an NDA
- Clients' financial data
- Any meeting that involves sensitive data

The quality is a bit below Otter or Fireflies, but it's good enough for most business tasks.

No code: MacWhisper runs locally on a Mac using Whisper and Parakeet models and supports 100+ languages.

If you're an employee, check your company's AI and recording policy before you connect any of these tools to work meetings.

---

### Prompt templates for different kinds of meetings

One prompt doesn't fit everything. A discovery call and a technical review are different jobs.

**Discovery call (your first meeting with a potential client):**

```
Analyze this discovery call transcript. Extract:
1. The client's pain points and problems (quotes from the conversation)
2. Budget and timeline (if mentioned)
3. The decision-maker
4. Objections and doubts
5. Next steps for both sides
6. Likelihood of closing the deal (Low/Medium/High), with your reasoning

Format: JSON with these fields.
```

**Client review (ongoing work with a current client):**

```
Analyze this transcript of a client meeting. Extract:
1. Project status: what's done and what isn't
2. The client's comments and requested changes (word for word)
3. Priorities for the next period
4. Risks and blockers
5. Tasks for our team (owner + deadline)
6. Tasks for the client (owner + deadline)
```

**Team standup:**

```
Analyze this standup. For each participant:
- What they did yesterday
- What they plan to do today
- Blockers and questions for the team

Then list the shared action items with owners.
```

---

### The webhook pipeline: from meeting to ClickUp task

🎨 **Picture this:** if the meeting is the factory floor, the webhook is the assembly line that comes after it. The part (the transcript) rolls off one machine → goes through quality control (Claude) → arrives at the warehouse (ClickUp) → and the floor supervisor gets a message (Slack).

```
Zoom/Meet meeting
      ↓
Fireflies records and transcribes
      ↓
Fireflies sends a webhook to your server (just the meeting id)
      ↓
Python Flask fetches the transcript through the Fireflies GraphQL API
      ↓
Claude API analyzes it with your template and returns JSON
      ↓
ClickUp API creates the tasks automatically
      ↓
Slack posts the summary to your channel
```

**Webhook server code (check the Fireflies request format against docs.fireflies.ai):**

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
SLACK_WEBHOOK_URL = os.environ["SLACK_WEBHOOK_URL"]

MEETING_PROMPT = """
You are an assistant that analyzes business meeting transcripts.

Transcript:
{transcript}

Meeting title: {meeting_title}
Participants: {participants}

Extract structured information as JSON:
{{
  "summary": "A short summary in 3-5 sentences",
  "decisions": ["decision 1", "decision 2"],
  "action_items": [
    {{
      "description": "What needs to be done",
      "assignee": "Owner's name or 'Unassigned'",
      "deadline": "Due date or 'Not specified'",
      "priority": "High|Medium|Low"
    }}
  ],
  "open_questions": ["question 1", "question 2"]
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
    """The Fireflies webhook sends only the meeting id: we fetch the text through the GraphQL API."""
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
    """Analyze the transcript with Claude."""
    participants_str = ", ".join(participants) if participants else "Unknown"

    message = claude_client.messages.create(
        model="claude-sonnet-5-5",  # for current model IDs, see the Anthropic docs
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
    # Strip markdown code fences if Claude added them
    if "```json" in response_text:
        start = response_text.find("```json") + 7
        end = response_text.find("```", start)
        response_text = response_text[start:end].strip()

    return json.loads(response_text)


def create_clickup_task(task_data: dict, meeting_title: str) -> str:
    """Create a task in ClickUp."""
    priority_map = {"High": 1, "Medium": 2, "Low": 3}

    payload = {
        "name": task_data["description"],
        "description": f"Source: meeting '{meeting_title}'\n"
                       f"Owner: {task_data['assignee']}",
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


def send_slack_summary(analysis: dict, meeting_title: str,
                       task_urls: list) -> None:
    """Post the summary to a Slack channel through an incoming webhook."""
    tasks_text = ""
    priority_emoji = {"High": "🔴", "Medium": "🟡", "Low": "🟢"}

    for item, url in zip(analysis["action_items"], task_urls):
        emoji = priority_emoji.get(item["priority"], "⚪")
        tasks_text += f"{emoji} {item['description']}\n"
        tasks_text += f"   → {item['assignee']} | {item['deadline']}"
        if url:
            tasks_text += f" | <{url}|Task>"
        tasks_text += "\n\n"

    open_q = "\n".join(f"• {q}" for q in analysis["open_questions"])

    message = f"""📋 *{meeting_title}*

📝 *Summary:*
{analysis['summary']}

✅ *Action items ({len(analysis['action_items'])}):*
{tasks_text}
❓ *Open questions:*
{open_q}""".strip()

    requests.post(
        SLACK_WEBHOOK_URL,
        json={"text": message},
        timeout=30,
    )


@app.route("/webhook/fireflies", methods=["POST"])
def fireflies_webhook():
    """Receive the webhook from Fireflies after a meeting ends."""
    data = request.json or {}

    # The webhook carries only metadata: meetingId and eventType
    if data.get("eventType") != "Transcription completed":
        return jsonify({"status": "skip", "reason": "other event"}), 200

    meeting = fetch_transcript(data["meetingId"])
    title = meeting["title"] or "Untitled meeting"
    transcript = meeting["text"]
    participants = meeting["participants"] or []

    if not transcript:
        return jsonify({"status": "skip", "reason": "no transcript"}), 200

    # 1. Analyze with Claude
    analysis = analyze_meeting(transcript, title, participants)

    # 2. Create tasks in ClickUp
    task_urls = [
        create_clickup_task(item, title)
        for item in analysis.get("action_items", [])
    ]

    # 3. Post the summary to Slack
    send_slack_summary(analysis, title, task_urls)

    return jsonify({
        "status": "processed",
        "tasks_created": len(task_urls),
        "meeting": title
    }), 200


if __name__ == "__main__":
    app.run(port=5000, debug=False)
```

**Where the summary goes:** this version posts to a Slack channel through an incoming webhook: a private URL that Slack gives you, and anything sent to it shows up in that channel. Prefer email? Swap `send_slack_summary` for a function that sends the same text through your email service. The rest of the pipeline stays the same.

**Deploying:** Railway, Render or another Python host (see the providers' sites for pricing). Make sure requests to your webhook really come from Fireflies (check the Fireflies documentation to see whether it supports signed requests).

---

### ROI: the math of automating meetings

| Task | Before automation | After |
|---|---|---|
| Meeting notes | 20–40 min | 0 min |
| Sending tasks to the team | 10–15 min | 0 min |
| Updating the CRM | 5–10 min | 0 min |
| Total per meeting | 35–65 min | 2 min (review) |
| At 5 meetings a week | 3–5 hours/week | 10 min/week |

Plug in your own rate: hours saved per month × what an hour of your time is worth. That's the amount that goes back into productive work. The numbers in the table are illustrative.

What the system costs: a subscription to a meeting service (there are free plans) + Claude API usage. At Sonnet 5.5 prices as of October 2026 ($2 per million input tokens and $10 per million output tokens), an hour-long meeting comes to roughly 15,000–20,000 input tokens, which works out to a few cents per meeting (an estimate; check it against your own recordings). Tokens are the units AI usage is billed in. Current prices: [What's current](https://aimayak.com/en/now/).

🎨 **Picture this:** you're hiring an assistant for the price of a subscription. It works around the clock, never asks for vacation and does one thing well: it turns meetings into concrete tasks. But checking its work is still your job.

---

## Practice

### Step 1: Connect Fireflies to your meetings (5 min)

1. Sign up at [fireflies.ai](https://fireflies.ai). The Free plan is enough to start
2. In Settings → Integrations, connect Google Calendar or Outlook
3. Fireflies will automatically join your meetings as a bot
4. Hold a test meeting in Zoom or Meet (even just with yourself)
5. Check that a transcript and an AI Summary showed up in your Fireflies dashboard

**Success looks like:** Fireflies recorded the meeting on its own and generated a summary.

### Step 2: Set up the webhook (10 min)

1. In Fireflies, open the developer section (Developer settings) and add a webhook (check on their site whether your plan includes webhooks)
2. For testing, use [webhook.site](https://webhook.site) as a temporary endpoint
3. Event: `Transcription completed`
4. Hold a test meeting (5–10 min)
5. Open webhook.site and look at the structure of the JSON that arrived

**Success looks like:** you see JSON with the fields `meetingId` and `eventType` (the transcript text itself comes through a separate request to the GraphQL API).

### Step 3: Run the Python server (10 min)

```bash
pip install flask anthropic requests
```

Save the code from the theory section as `meeting_pipeline.py`. Then get a Slack webhook URL: in Slack, create an app for your workspace, turn on Incoming Webhooks, add a webhook for the channel where you want the summaries, and copy its URL. (On a company Slack, an admin may need to approve the app.) Now set the environment variables:

```bash
export ANTHROPIC_API_KEY="sk-ant-..."
export FIREFLIES_API_KEY="..."
export CLICKUP_API_KEY="pk_..."
export CLICKUP_LIST_ID="..."
export SLACK_WEBHOOK_URL="https://hooks.slack.com/services/..."

python meeting_pipeline.py
```

To get a public URL while you're developing:

```bash
ngrok http 5000
# Copy the HTTPS URL, add /webhook/fireflies at the end → paste it into the Fireflies webhook settings
```

### Step 4: Test the whole pipeline (5 min)

Hold a 10-minute test meeting. Talk through a few tasks with deadlines and owners. Wait 5–10 minutes after it ends. Check that the tasks showed up in ClickUp and the summary arrived in Slack.

**Success looks like:** the whole cycle runs automatically, with no manual steps.

### Step 5: Tailor the prompt to your meetings (5 min)

Replace `MEETING_PROMPT` with whichever template from the theory section fits your kind of meetings. Or write your own. Keep the `{transcript}`, `{meeting_title}` and `{participants}` placeholders and the JSON fields the code reads (`summary`, `action_items`, `open_questions`), or update the code to match. Test it on a real meeting and make sure the output looks the way you expect.

---

## Tools and resources

- **[Fireflies](https://fireflies.ai)**: transcription + webhooks, 60+ languages, free plan available (API and webhook access depends on the plan)
- **[Otter.ai](https://otter.ai)**: real-time transcription, free plan available; check the supported languages if not all your meetings are in English
- **[tl;dv](https://tldv.io)**: records meetings in Zoom, Meet and Teams, free plan available
- **[Granola](https://www.granola.ai)**: a meeting notepad with no bot joining the call; macOS, Windows, iOS and Android (as of October 2026)
- **[OpenAI Whisper](https://github.com/openai/whisper)**: private offline transcription, free
- **[mlx-whisper](https://github.com/ml-explore/mlx-examples)**: fast Whisper on Apple Silicon
- **[MacWhisper](https://www.macwhisper.com)**: local transcription on a Mac, no code needed
- **[Claude API](https://platform.claude.com/docs)**: analyzing transcripts; estimate the cost by tokens ([What's current](https://aimayak.com/en/now/))
- **[ClickUp API v2](https://clickup.com/api)**: creating tasks
- **[ngrok](https://ngrok.com)**: a tunnel for development, free
- **[Railway](https://railway.app)**: hosting for the Python server, prices on the provider's site

---

## Key takeaways

> A meeting without automatic notes wastes your money twice: first you spend the time in the meeting, then you spend it again writing down what happened.

> The difference between Otter/Fireflies and Local Whisper is the difference between convenience and privacy. For most meetings, the cloud is safe enough. For negotiations under an NDA, run Whisper locally.

> A webhook pipeline changes how people work. When tasks show up in ClickUp automatically after every meeting, people start taking their commitments more seriously: what's said instantly becomes a record.

---

## Next lesson

→ [Translation and localization: DeepL MCP and an i18n pipeline](75-ai-translation.md)

We'll build a system that takes one piece of content in English and automatically turns it into Spanish, Portuguese and other languages, with cultural adaptation, a glossary of terms and SEO metadata for each market.
