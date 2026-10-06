# AI presentations with Gamma, Beautiful.ai and Claude

**Time:** about 25 min reading + 35 min practice

---

## The gist

Making a good presentation used to take a full day in PowerPoint. With AI, a solid draft comes together in about half an hour, and you focus on your ideas instead of pushing boxes around a slide.

The main part of this lesson is done in a browser, with no code. The sections on python-pptx and the Google Slides API are for people who build their own tools; everyone else can skip them.

🎨 **Picture this:** regular PowerPoint is like putting together IKEA furniture yourself: the parts are right, but it takes all day and half the bolts are left over. Gamma is furniture that arrives already assembled. You say what you want, and five minutes later it's standing in the room. Then you move whatever isn't quite right.

---

## Key concepts

- Gamma: a complete presentation from one prompt (your request to the AI), with a layout that adapts to the content
- Beautiful.ai: AI slide design with smart templates (a template is a ready-made layout)
- Claude + python-pptx: generating PowerPoint files with code (full control; for builders)
- Claude + the Google Slides API (an API is a way for one program to talk to another service): presentations in the cloud, built with code
- The workflow: idea → structure with Claude → design in Gamma → final edits
- A pitch deck (a presentation for investors) with AI: from concept to a solid draft in a few hours

---

## Theory

### Gamma: a presentation from one prompt

Gamma ([gamma.app](https://gamma.app)) is one of the fastest ways to get from an idea to a good-looking presentation.

**How it works:**

1. You type one sentence or paste in a chunk of text
2. Gamma suggests a structure (you edit it)
3. Gamma generates the design
4. You fine-tune the details

**What it can create:**

- Presentations (slides)
- Documents (nicely formatted docs)
- Web pages (public landing pages)

**Pricing (as of October 2026):** Gamma lets you start for free, generation uses credits, and limits and export options depend on the plan. According to Gamma's help center, the starting credits on the free plan don't refill on their own, so spend them on a real task. Gamma's prices: [gamma.app/pricing](https://gamma.app/pricing). Prices of the AI assistants: [What's current](https://aimayak.com/en/now/).

**What Gamma does well:**

- A layout that adapts to any content
- Automatic typography
- Built-in images that match the topic
- Interactive elements (charts, embeds)
- Gamma Agent: in a chat, it changes the style, text and tone across the whole deck at once
- Smart Diagrams: draws diagrams from a description
- Languages: according to Gamma's help center, you can write your prompt in your own language, and the interface language list includes Spanish. Still check the quality of the text on your own topic

🎨 **Picture this:** Gamma is like a good freelance layout designer. You say what you need, they make it look good; you say what to change, they change it. Not perfect, but most of the work is already done.

---

### Beautiful.ai: smart slide templates

Beautiful.ai ([beautiful.ai](https://beautiful.ai)) takes a different approach from Gamma: the priority is making slides look professional automatically. It also has a Create with AI mode: you give it a topic or an outline, refine the structure, and get a design.

**The key feature: Smart Slides.**
When you add an element (text, an image, an icon), the slide automatically rearranges itself so everything looks right. You can't make it look "off"; the system won't let you.

| | Gamma | Beautiful.ai |
|--|-------|--------------|
| Generate from a prompt | ✅ Yes | ✅ Yes (Create with AI) |
| Design control | Medium | High |
| Smart templates | Basic | Advanced |
| Collaboration | ✅ Yes | ✅ Yes |
| PPTX export | depends on the plan | depends on the plan |
| Price | see the pricing page | see the pricing page (trial terms are listed there) |

The "Design control" and "Smart templates" rows are the author's assessment, not the result of an independent comparison: test them on your own task.

**When to use Beautiful.ai instead of Gamma:**

- You need more control over the design
- A team is working on the presentation together
- You have corporate brand guidelines that must be followed exactly

**If you live in PowerPoint or Google Slides:** Copilot in PowerPoint (Agent Mode) and Gemini in Google Slides can also build a presentation from a request. You need the right subscriptions (Microsoft 365 with Copilot, or Google Workspace and Google AI plans), and the features are rolling out gradually. If you present in a language other than English, check language support first: at launch, Gemini in Slides worked only in English.

---

### For builders: Claude + python-pptx, PowerPoint with code

This section and the next one are optional: they're for people who write code. If you don't code, go on to the section called "The workflow." When you need full control, or need to generate lots of presentations automatically, Claude writes code that creates PPTX files (the PowerPoint file format).

**Install:**

```bash
pip install python-pptx
```

**A basic example: the code builds a presentation from a ready-made outline:**

```python
from pptx import Presentation
from pptx.util import Inches, Pt
from pptx.dml.color import RGBColor
from pptx.enum.text import PP_ALIGN

def create_presentation(title, slides_data):
    """
    slides_data = [
        {"title": "Slide title", "content": ["point 1", "point 2"]},
        ...
    ]
    """
    prs = Presentation()
    
    # Slide size (16:9 widescreen)
    prs.slide_width = Inches(13.33)
    prs.slide_height = Inches(7.5)
    
    # Title slide
    slide_layout = prs.slide_layouts[0]
    slide = prs.slides.add_slide(slide_layout)
    slide.shapes.title.text = title
    slide.placeholders[1].text = "Made with Claude + python-pptx"
    
    # Content slides
    for slide_data in slides_data:
        slide_layout = prs.slide_layouts[1]  # title + content
        slide = prs.slides.add_slide(slide_layout)
        
        # Title
        slide.shapes.title.text = slide_data["title"]
        
        # Content
        tf = slide.placeholders[1].text_frame
        tf.clear()
        for i, point in enumerate(slide_data["content"]):
            if i == 0:
                tf.text = point
            else:
                p = tf.add_paragraph()
                p.text = point
                p.level = 0
    
    return prs

# Usage
slides = [
    {"title": "The problem", "content": [
        "Problem 1: ...",
        "Problem 2: ...",
        "Problem 3: ..."
    ]},
    {"title": "Our solution", "content": [
        "How we solve problem 1",
        "How we solve problem 2"
    ]},
]

prs = create_presentation("Pitch Deck: Project Name", slides)
prs.save("presentation.pptx")
print("Done!")
```

**A prompt for Claude:** "Write a Python script that creates a professional pitch deck for [project description]. Use python-pptx. 10 slides: problem, solution, market, product, business model, team, traction, financials, roadmap, CTA."

---

### Claude + the Google Slides API: presentations in the cloud

For teamwork and automatic generation in the cloud, there's the Google Slides API. This section is for builders too.

**Why it's useful:**

- The presentation lands right in your Google Drive, and you share it with your team yourself
- It can be updated automatically (quarterly reports, for example)
- No dependence on PPTX files or anything stored on your computer

**Setup:**

```bash
pip install google-api-python-client google-auth-httplib2 google-auth-oauthlib
```

In Google Cloud Console, enable the Google Slides API, create an OAuth client of the "Desktop app" type and download its file as `credentials.json` (the Google Slides API documentation, linked at the end of this lesson, walks you through it).

**Basic code:**

```python
from google_auth_oauthlib.flow import InstalledAppFlow
from googleapiclient.discovery import build

# Set up authorization: a browser window opens, and you sign in to your Google account
SCOPES = ['https://www.googleapis.com/auth/presentations']
flow = InstalledAppFlow.from_client_secrets_file('credentials.json', SCOPES)
credentials = flow.run_local_server(port=0)

service = build('slides', 'v1', credentials=credentials)

# Create a new presentation
presentation = service.presentations().create(
    body={"title": "My AI presentation"}
).execute()

presentation_id = presentation['presentationId']
print(f"Created: https://docs.google.com/presentation/d/{presentation_id}")
```

From there, Claude helps you write batch requests that add slides, text and images.

⚠️ Treat the `credentials.json` file like a password: keep it out of shared folders, emails and public code repositories.

---

### The workflow: idea → Claude → Gamma → final

A convenient order for most presentations:

**Step 1: Structure with Claude (5 min)**

```
Task: a presentation on [topic] for [audience]
Goal: [what the audience should do afterward]
Length: [N slides]

Create the structure:
- A title for each slide
- 3-5 key points for each one
- Suggestions for visuals
```

**Step 2: Generate in Gamma (5 min)**

- Paste Claude's structure into Gamma
- Pick a theme
- Gamma generates the design

**Step 3: Edit in Gamma (10-15 min)**

- Fix the wording
- Swap images if needed
- Cut anything you don't need

**Step 4: Final review with Claude (5 min)**

```
[Paste the final key points from every slide]

Check:
1. Does the logic flow from slide to slide? Is there a story?
2. Does each slide make one point, or several?
3. Is the call to action on the last slide specific?
4. Do any slides contradict each other?
```

Total: 25-30 minutes for a solid draft of a presentation. Checking the facts and numbers on the slides is your job.

---

### A pitch deck for investors, built with AI

A pitch deck is a special format: a strict structure, very little text, as many numbers as possible.

**The standard structure (10-12 slides):**

```
1. Title: name, tagline, contact info
2. Problem: a specific pain point and how big it is
3. Solution: how you solve it, in 1 sentence
4. Product: screenshots, a demo, 3 key features
5. Market: TAM, SAM, SOM, with sources
6. Business model: how you make money
7. Traction: growth, metrics, customers
8. Competition: a comparison matrix
9. Team: photos + 1 line on why you
10. Financials: a 3-year P&L forecast
11. The ask: how much, what for, runway
12. Thank you: contact info + follow-up
```

A few terms, if they're new to you: TAM, SAM and SOM are three sizes of your market (the total market, the part you could serve, and the share you can realistically win). P&L means profit and loss. Runway is how many months the money will last.

Check every market figure against its source. AI can confidently make up numbers (a hallucination), and a wrong market size on slide 5 can cost you the whole meeting.

**A prompt for Claude:**

```
Create a pitch deck structure for [startup description].
Investors: [type of investors, stage].
Round: [pre-seed / seed / Series A], amount: [N].

For each slide:
- A title (5 words max)
- The 3 main points (specific numbers wherever possible)
- What data the slide needs
- What NOT to put on it (common mistakes on this slide)
```

🎨 **Picture this:** a pitch deck is a resume for investors. A good resume doesn't explain every job in detail; it shows the essentials fast. If an investor needs more than 3 minutes to get through your 12 slides, something's wrong.

---

## Practice

1. Create a Gamma account (it's free, and you can sign in with Google):

Go to [gamma.app](https://gamma.app) → Create new AI. You'll use two modes there: Generate (a presentation from a short prompt) and Paste in text (a presentation from ready-made text or an outline). Button names in the interface change from time to time

2. Ask Claude to create a structure for your presentation:

```
Topic: [pick something real: a description of your project,
course, service or idea]
Audience: [who will be watching]
Goal: [what they should do afterward]
Slides: 10

Create the structure: a title for each slide +
3-4 key points for each one.
```

3. In Gamma, choose Paste in text, paste the structure, choose Presentation and a theme, and generate the presentation

4. Ask Claude to improve the first 3 slides:

```
[Paste the text of the first 3 slides from Gamma]

For each slide:
- Suggest a stronger title (6 words max)
- Cut the generic wording and add specifics
- Make the first point the most important fact
```

You're done when you have a 10-slide presentation you could show someone, with the facts and numbers on the slides checked by you. That's the end of the no-code practice.

5. Optional, for builders: install python-pptx and create a simple presentation with code:

```bash
pip install python-pptx
```

```python
# Ask Claude to write a script for a 5-slide presentation
# about your project, using the code from this lesson as a starting point
```

6. Optional, for builders: an automatic weekly report generator:

```
Ask Claude to write a script that:
1. Reads data from a CSV file (the week's metrics)
2. Generates a PPTX file with 4 slides:
   - Key numbers
   - What we got done
   - What didn't work
   - Plans for next week
3. Saves it with the date in the file name
```

---

## Tools and resources

- **[Gamma](https://gamma.app)**: a fast route from an idea to slides
- **[Beautiful.ai](https://beautiful.ai)**: smart templates for design control
- **[python-pptx](https://python-pptx.readthedocs.io)**: a library for generating PPTX files with code
- **[Google Slides API](https://developers.google.com/slides)**: presentations in the cloud through an API
- **[Canva Presentations](https://www.canva.com)**: an alternative with a big template library
- **Prices and versions:** [What's current](https://aimayak.com/en/now/)

---

## Key takeaways

> Gamma plus a structure from Claude is the minimum combination that gets you a solid draft in half an hour: Claude handles the logic and the content, Gamma makes it look good, and you adjust the details and check the facts.

> You need python-pptx when presentations are generated automatically or from a template: weekly reports, custom proposals for clients, training materials, anything you need to reproduce many times.

> An AI-built pitch deck is a draft, not the final version. Investors have seen plenty of decks built on templates like these; they decide based on content and numbers, not on the design.

---

## Next lesson

→ [AI translation and localization: DeepL and Claude](75-ai-translation.md): translating emails and texts so they sound natural

Video comes in the next module: [AI video generation: Runway, Kling and more](71-ai-video-generation.md): bringing your ideas to life with video
