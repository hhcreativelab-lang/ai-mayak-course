# How to find a niche with Google Trends and Reddit

**Time:** about 25 min reading + 35 min practice

---

## The gist

🎨 **Picture this:** one angler heads out onto a lake, fishes where everyone else is fishing and catches nothing. Another angler has a fish finder. She can see schools of fish a couple of hundred yards away, gets there two hours ahead of everyone else and goes home with a full bucket. Trends in niches work the same way. Most entrepreneurs go where the crowd already is. Whoever can read market signals early gets into position before the competition. That doesn't guarantee success, but it improves the odds.

Claude, paired with trend analysis tools, is your fish finder. You see what's just starting to grow while others haven't noticed it yet.

---

## Key concepts

- **Exploding Topics**: a service that finds topics in their early growth stage (according to the service itself, long before they peak)
- **Google Trends API** (an API is a way for one program to request data from another): real search demand data over time, by region and with related searches
- **pytrends**: an unofficial Python wrapper for Google Trends that doesn't need an API key (the repository has been archived since April 2025, and it works unreliably)
- **Reddit as a signal**: the total volume of discussion in a niche's subreddits is an indicator of how fast that niche's audience is growing
- **Twitter/X**: viral topics in real time (data access is paid, and the terms keep changing)
- **A "wave" vs "noise"**: the difference between a real trend and short-lived hype
- **Whitespace analysis**: looking for unclaimed niches where growing trends intersect
- **A trend-based content plan**: how to turn data into an editorial calendar
- **SEO** (search engine optimization): getting your pages to rank in search engines

---

## Theory

### Why trend analysis is useful

The market for online products often moves in waves. Getting in at the start of a wave is easier: there's little competition, and demand is just beginning to grow. People who noticed the buzz around ChatGPT in late 2022 had time to stake out a position in that niche before a crowd of competitors showed up. But many early signals go nowhere, so a trend doesn't mean success yet: you have to check it against data and a small experiment.

And "reading trends" doesn't mean reading TechCrunch headlines. By the time a trend makes the headlines, the wave is usually well underway. The real signals are in search demand data, in the rhythm of discussions on Reddit, in subreddits that are growing. That's where services like Exploding Topics look, and that's what you'll learn to do yourself in this lesson.

🎨 **Picture this:** a trend is a direction, a slope. You're not looking for what's already popular (the summit) but for what's just starting to tilt upward (the bottom of the climb). The summit is crowded. On the slope, you'll only meet the people who know how to read the terrain.

---

### Exploding Topics: finding growing topics

**What it is.** Exploding Topics is a platform for spotting growing topics. Its algorithm pulls together data from search engines, social media, news and professional communities, finds topics with steady growth and shows them before they go mainstream.

**How it works.** Each topic has a status:

- **Exploding**: sharp growth over the last few weeks or months; risk of a bubble
- **Regular**: steady, linear growth; less risk, more reliable
- **Peaked**: the peak has passed, and the audience has started to shrink

For a business, people usually look for **Regular** topics with noticeable but not huge search volume. That's a niche that has already proven itself (it isn't a bubble) but isn't overcrowded yet.

**Practical filters on Exploding Topics:**

- Category: AI, Productivity, Health & Wellness, Finance
- Period: growth over the last 2 years
- Volume: enough for the demand to be noticeable (pick the threshold that fits your project)

**An example of how to use it (hypothetical).** Say the service shows steady growth for "AI meeting notes" while the niche still has few players. The first ones into a niche like that usually arrive with SEO content and an audience. A year or two later it may get crowded, so check your own niche against fresh data, not against an example from a lesson.

(By the way, you'll run into a few terms in this lesson. **Ahrefs** is a brand of SEO analysis tools. **Conversion** is the percentage of people who take the action you want. A **funnel** is a marketing funnel, the path from first contact to purchase. An **agent** is an AI that carries out tasks on its own. A **prompt** is your request to an AI. A **workflow** is a sequence of work steps. A **dashboard** is a panel with your key metrics. A **token** is a unit of text for AI. To **deploy** means to put your code live.)

**Free plan.** It gives you a list of trends without the details. For serious analysis you need a paid plan with full access to the history and to niche search (prices and terms are on the service's website). For a one-time strategy session, the free plan plus some manual analysis may be enough.

---

### Google Trends API: real search demand data

**What it shows.** Google Trends shows the relative popularity of a search term over time and by region. Important: it doesn't show the absolute number of searches but an index from 0 to 100 (100 = peak).

**pytrends: Python without an official key.** For a long time there was no official API, and developers used the pytrends library, which imitates a browser's requests to Google Trends. It's an unofficial method: the pytrends repository has been archived since April 2025, Google often answers with error 429 (too many requests), and scripts break whenever the site changes. In July 2025, Google opened an alpha test of the official Google Trends API (access by application, limited quotas): [developers.google.com/search/apis/trends](https://developers.google.com/search/apis/trends). The examples below work as learning exercises; for serious work, look at the official API.

```python
# Installation
# pip install pytrends pandas matplotlib

from pytrends.request import TrendReq
import pandas as pd

# Setup
pytrends = TrendReq(hl='en-US', tz=360)

# Compare competitors in an AI niche
keywords = ["claude code", "cursor ai", "github copilot", "bolt.new"]

pytrends.build_payload(
    keywords,
    timeframe='today 12-m',   # last 12 months
    geo='US'                   # US, or '' for worldwide
)

# Data over time
interest_over_time = pytrends.interest_over_time()
print(interest_over_time.tail(10))

# Related queries (the key technique!)
related = pytrends.related_queries()
for kw in keywords:
    print(f"\n--- {kw} rising queries ---")
    if related[kw]['rising'] is not None:
        print(related[kw]['rising'].head(5))
```

**Related queries are a goldmine for content planning.** Rising queries show related searches that are growing along with the main one. Those are ready-made topics for articles, videos and products.

**Example analysis: looking for an unclaimed niche in AI tools:**

```python
from pytrends.request import TrendReq
import pandas as pd
import time

pytrends = TrendReq()

# Step 1: check the growth of several niches
niches = [
    ["ai video editor", "ai image generator", "ai music generator"],
    ["ai for lawyers", "ai for doctors", "ai for teachers"],
    ["local llm", "ollama", "self hosted ai"]
]

results = {}
for group in niches:
    pytrends.build_payload(group, timeframe='today 5-y')
    df = pytrends.interest_over_time()
    for kw in group:
        if kw in df.columns:
            # Growth over the last year vs the year before
            last_year = df[kw].tail(52).mean()
            prev_year = df[kw].iloc[-104:-52].mean()
            growth = ((last_year - prev_year) / (prev_year + 1)) * 100
            results[kw] = round(growth, 1)
    time.sleep(2)  # pause so you don't get blocked

# Top growing niches
sorted_results = sorted(results.items(), key=lambda x: x[1], reverse=True)
print("Top growing niches:")
for kw, growth in sorted_results[:10]:
    print(f"  {kw}: +{growth}%")
```

This script gives you a ready list of niches with their growth percentages. Send it straight to Claude for analysis.

---

### Reddit as an early-warning system

Reddit is where professionals and enthusiasts discuss topics before they reach mainstream media. A growing subreddit = a growing audience for the niche.

**What to track:**

1. The **number of members** in a subreddit over 6-12 months
2. **Post activity** (views, comments)
3. **Frequent questions** (what is / how to / best X for Y): these are requests for content

**Tools:**

- **Reddit Stats** (subredditstats.com): growth history for subreddits (check that the service still works)
- **PRAW (Python Reddit API Wrapper)**: programmatic access to posts and comments

```python
# pip install praw

import praw
from collections import Counter
import re

reddit = praw.Reddit(
    client_id="YOUR_CLIENT_ID",
    client_secret="YOUR_CLIENT_SECRET",
    user_agent="trend-analyzer/1.0"
)

def analyze_subreddit_trends(subreddit_name, limit=200):
    """Analyzes a subreddit's top posts to find trending topics"""
    
    subreddit = reddit.subreddit(subreddit_name)
    
    titles = []
    for post in subreddit.hot(limit=limit):
        titles.append(post.title.lower())
    
    # Extract keywords (simplified)
    all_words = ' '.join(titles)
    words = re.findall(r'\b[a-z]{4,}\b', all_words)
    
    # Stop words
    stopwords = {'that', 'this', 'with', 'from', 'have', 'been', 'will', 'your', 'what'}
    filtered = [w for w in words if w not in stopwords]
    
    counter = Counter(filtered)
    
    print(f"\nTop topics in r/{subreddit_name}:")
    for word, count in counter.most_common(20):
        print(f"  {word}: {count} mentions")
    
    return counter

# Analyze a few niche subreddits
for sub in ['ClaudeAI', 'LocalLLaMA', 'AIToolsDirectory']:
    analyze_subreddit_trends(sub)
```

**Setting up PRAW:**

1. Go to reddit.com/prefs/apps
2. Create a new app and choose the "script" type
3. Get your client_id and client_secret

Important: under its Responsible Builder Policy (updated in November 2025), Reddit requires you to request and receive approval for API access in advance, so getting working keys may be harder than it used to be. Check the terms in Reddit's Data API rules. If you don't get access, check subreddits by hand, as in step 5 of the practice.

---

### Claude analyzes the trend data: the full workflow

Collecting the data is half the job. The other half is making sense of it. This is where Claude earns its place as an analyst.

**Sample prompt for analyzing Google Trends data:**

```python
import anthropic
import json

client = anthropic.Anthropic()

# Hypothetical sample data (not real numbers): swap in the results of your own scripts
trend_data = {
    "period": "last 12 months",
    "keywords_growth": {
        "ai meeting notes": 340,
        "local llm": 280,
        "ai for lawyers": 195,
        "cursor ai": 450,
        "ai video editor": 120
    },
    "reddit_growing_subreddits": [
        {"name": "LocalLLaMA", "members_12m_ago": 45000, "members_now": 180000},
        {"name": "ClaudeAI", "members_12m_ago": 8000, "members_now": 95000}
    ],
    "exploding_topics": [
        "agentic ai", "ai coding assistant", "rag pipeline", "model context protocol"
    ]
}

message = client.messages.create(
    model="claude-opus-5-5",   # current models: see the What's current page
    max_tokens=2000,
    messages=[
        {
            "role": "user",
            "content": f"""Analyze this trend data and give me strategic recommendations:

{json.dumps(trend_data, ensure_ascii=False, indent=2)}

My situation: I'm a solo developer, I know how to work with Claude Code, and I want to launch a micro-SaaS or a content project in the AI space. Starting budget: up to $500.

Answer these questions:
1. Which 3 niches are the most promising to enter right now, and why?
2. Which niches are already overheated (too late to get in)?
3. What unclaimed angle is there where two growing trends intersect?
4. A concrete plan: what to build, what content to create, how to make money from it?

Be specific, but rely only on the data above. If the data isn't enough to draw a conclusion, say so and don't make up numbers."""
        }
    ]
)

print(message.content[0].text)
```

🎨 **Picture this:** trend data is a map covered in pins. You see the dots, but you can't see the route. Claude is an experienced guide who looks at the same map and says: "Here's a mountain trail with hardly any traffic that goes straight to the top. And over there is a beautiful road, but it's already jammed with tourists."

---

### Twitter/X trends: a real-time viral signal

Twitter/X gives you a different kind of data: not steady growth but viral spikes. It's useful for planning content on "hot" topics, but be careful: trends on X fizzle out fast.

**How to get the data:**

- The official X API is paid; check the terms and pricing on X's developer page (they've changed several times)
- Third-party APIs on marketplaces like RapidAPI are cheaper, but check their reliability and whether they comply with X's rules yourself
- The free way: monitor accounts by hand with Feedly or RSS

**When X trends are useful:**

- Niches around current events (a new AI release, an industry scandal)
- Content strategy for an X/Twitter audience
- Quick validation: "are people talking about this right now?"

**Tip.** For most business analysis, Google Trends + Reddit is more reliable than X. X gives you the "temperature" of the moment; Google Trends gives you real search demand that turns into traffic.

---

### Whitespace analysis: finding the unclaimed spot

The most valuable skill isn't finding a growing trend. It's finding an unclaimed intersection of two trends.

**Intersection matrix:**

| | AI Tools | Automation | Local First |
|---|---|---|---|
| **Lawyers** | Some competitors | Few | Almost none |
| **Teachers** | Some competitors | Moderate competition | Few |
| **Architects** | Almost none | Almost none | None |

In this hypothetical table, the "AI tools for architects, local-first" cell looks like a niche with minimal competition. That makes it a whitespace candidate: you still need to check demand and competitors against real data. The table only illustrates the method.

**How to check whitespace with Claude:**

```
Check the following niche intersections to see whether they're still open.
For each cell, estimate:
- Are there existing products (1-5, where 5 = many competitors)?
- What is the search demand (Google Trends data attached)?
- Are there communities on Reddit or forums?
- How feasible is it to build a micro-SaaS here in 30 days?

Niches to analyze:
[paste the Google Trends data + a list of competitors from a quick search]
```

---

## Practice

### Exercise: build a trend dashboard for your niche in 35 minutes

**Scenario:** you want to find a promising niche for a micro-SaaS (a small software product run by one person or a tiny team) or a content project in the AI space.

---

**Step 1: Install the dependencies (3 minutes)**

```bash
mkdir trend-analyzer && cd trend-analyzer
python3 -m venv venv && source venv/bin/activate
pip install pytrends pandas matplotlib anthropic python-dotenv
```

---

**Step 2: The data collection script (10 minutes)**

Create a file called `trend_collector.py`:

```python
from pytrends.request import TrendReq
import pandas as pd
import json
import time

def collect_trend_data(keyword_groups, timeframe='today 5-y', geo=''):
    """
    Collects trend data for groups of keywords.
    keyword_groups: a list of lists (max 5 keywords per group because of Google's limit)
    """
    pytrends = TrendReq(hl='en-US', tz=360)
    all_results = {}
    
    for group in keyword_groups:
        print(f"Processing: {group}")
        pytrends.build_payload(group, timeframe=timeframe, geo=geo)
        
        df = pytrends.interest_over_time()
        if not df.empty:
            for kw in group:
                if kw in df.columns:
                    # Growth: average of the recent half of the period vs the earlier half
                    vals = df[kw].values
                    half = len(vals) // 2
                    recent_avg = vals[half:].mean()
                    old_avg = vals[:half].mean()
                    growth_pct = ((recent_avg - old_avg) / (old_avg + 0.001)) * 100
                    
                    all_results[kw] = {
                        'current_avg': round(float(recent_avg), 1),
                        'growth_pct': round(float(growth_pct), 1),
                        'peak': int(df[kw].max()),
                        'trend': 'growing' if growth_pct > 20 else 
                                 'stable' if growth_pct > -10 else 'declining'
                    }
        
        time.sleep(3)  # required pause between requests
    
    return all_results

# Choose the niches to analyze (change these to fit your field)
keyword_groups = [
    ["claude code", "cursor ai", "github copilot"],
    ["ai for small business", "ai automation tools", "no code ai"],
    ["local llm", "ollama", "private ai"],
    ["ai meeting assistant", "ai note taker", "ai transcription"],
]

print("Collecting trend data...")
results = collect_trend_data(keyword_groups, timeframe='today 3-y')

# Save the results
with open('trend_data.json', 'w', encoding='utf-8') as f:
    json.dump(results, f, ensure_ascii=False, indent=2)

print("\nResults:")
sorted_r = sorted(results.items(), key=lambda x: x[1]['growth_pct'], reverse=True)
for kw, data in sorted_r:
    symbol = '📈' if data['trend'] == 'growing' else '➡️' if data['trend'] == 'stable' else '📉'
    print(f"{symbol} {kw}: growth {data['growth_pct']}%, peak {data['peak']}")
```

Run it: `python trend_collector.py`

---

**Step 3: Claude analyzes the results (10 minutes)**

Create `analyze_with_claude.py`:

```python
import anthropic
import json
from dotenv import load_dotenv

load_dotenv()
client = anthropic.Anthropic()

# Load the trend data
with open('trend_data.json') as f:
    trend_data = json.load(f)

# Top 10 growing
growing = sorted(
    [(k, v) for k, v in trend_data.items() if v['trend'] == 'growing'],
    key=lambda x: x[1]['growth_pct'],
    reverse=True
)[:10]

analysis_prompt = f"""I'm a solo developer, and I know how to work with Python and Claude Code.
I want to launch a micro-SaaS or an educational content project in AI/automation.
Budget: up to $500. Time available: 10-15 hours a week.

Google Trends data (growth over the last 1.5 years):
{json.dumps(dict(growing), ensure_ascii=False, indent=2)}

Give me:
1. The TOP 3 niches to enter right now, with your reasoning
2. Which niche to avoid (too late, or a bubble)
3. A concrete product or content format for each of the TOP 3
4. The first 3 actions to take this week
5. Where to look for the first customers or readers

Keep the answer structured and specific. If the data isn't enough to draw a conclusion, say so."""

message = client.messages.create(
    model="claude-opus-5-5",   # current models: see the What's current page
    max_tokens=2500,
    messages=[{"role": "user", "content": analysis_prompt}]
)

print("=== NICHE ANALYSIS ===\n")
print(message.content[0].text)

# Save the analysis
with open('niche_analysis.md', 'w', encoding='utf-8') as f:
    f.write("# Niche analysis - " + __import__('datetime').date.today().isoformat() + "\n\n")
    f.write(message.content[0].text)

print("\nAnalysis saved to niche_analysis.md")
```

---

**Step 4: A quick chart (5 minutes)**

```python
import matplotlib.pyplot as plt
import json

with open('trend_data.json') as f:
    data = json.load(f)

# Growing niches only
growing = {k: v for k, v in data.items() if v['trend'] == 'growing'}
sorted_g = sorted(growing.items(), key=lambda x: x[1]['growth_pct'], reverse=True)

keywords = [x[0] for x in sorted_g]
growths = [x[1]['growth_pct'] for x in sorted_g]

plt.figure(figsize=(12, 6))
colors = ['#2ecc71' if g > 100 else '#f39c12' if g > 30 else '#3498db' for g in growths]
bars = plt.barh(keywords, growths, color=colors)
plt.xlabel('Growth (%)')
plt.title('Growing niches: Google Trends analysis')
plt.tight_layout()
plt.savefig('trends_chart.png', dpi=150)
print("Chart saved: trends_chart.png")
```

---

**Step 5: Check on Reddit (5 minutes, by hand)**

For each of your top 3 niches:

1. Open reddit.com/search and type in the keyword
2. Check: is there an active subreddit?
3. Open the subreddit, go to About and look at the member count and how it's growing
4. Jot down the name, size and activity

This gives you context that Claude will use for the final conclusion.

---

## Tools and resources

- **[Exploding Topics](https://explodingtopics.com)**: finds growing topics. There's a free plan; paid plans are listed on the website
- **[Google Trends](https://trends.google.com)**: the basic tool, free
- **[pytrends](https://github.com/GeneralMills/pytrends)**: an unofficial Python library for Google Trends, free; the repository is archived
- **[Google Trends API (alpha)](https://developers.google.com/search/apis/trends)**: the official API, by application, with limited quotas
- **[SubredditStats](https://subredditstats.com)**: growth history for subreddits (check that the service still works)
- **[PRAW](https://praw.readthedocs.io)**: the Python Reddit API wrapper (you need a Reddit app and approved access)
- **[Ahrefs Free Tools](https://ahrefs.com/free-seo-tools)**: search volume for keywords, partly free
- **[Semrush Keyword Gap](https://www.semrush.com)**: compares niches by search volume; trial terms are on the website (Semrush was bought by Adobe in April 2026, and the product still works)
- **[Anthropic API](https://console.claude.com)**: Claude for data analysis, billed per token (prices: [What's current](https://aimayak.com/en/now/))

---

## Key takeaways

> "Trends aren't hype. They're measurable data about search demand. People who can read that data and test it with a small experiment make decisions based on facts, not gut feelings."

> "Google Trends gives you demand, Reddit gives you the audience, Exploding Topics gives you early signals. Claude helps you pull it all into a draft strategy quickly and cheaply, but the decision and the checking stay with you: the model can be wrong, and it only works with the data you gave it."

> "Whitespace, the intersection of two growing trends in an unclaimed vertical, is the most valuable find. Don't look where it's noisy. Look where it's quiet but the direction is clear."

---

## Next lesson

→ [AI competitive intelligence](89-competitive-intelligence.md): automated market monitoring

We move from trend analysis to tracking competitors systematically: Ahrefs MCP, Playwright for scraping, ChangeDetection.io and weekly reports from Claude, all on autopilot.
