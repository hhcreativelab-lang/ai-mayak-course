# AI video generation: Runway, Kling, Luma and more

**Time:** about 25 min reading + 35 min practice

---

## The gist

A short video used to take a camera operator, an editor and a studio. Today you open a browser tab, write a few sentences, and a few minutes later you have a clip. It isn't Hollywood, but for social media, a landing page or an ad it's often good enough. In this lesson we go through the platforms as of October 2026 and build a working pipeline: Claude writes the script and the prompts (a prompt is your request to the AI) → Runway generates the video → FFmpeg assembles the final cut. Kling plugs in the same way.

🎨 **Picture this:** every video used to be handmade pottery: slow, expensive, started from scratch every time. Now it's more like a 3D printer: you enter the settings and get the finished piece. The quality is a notch below handmade, but it's hundreds of times faster.

---

## Key concepts

- **Text-to-Video**: a video generated from a written description of a scene
- **Image-to-Video**: animating a still photo or a render (bringing it to life)
- **Video-to-Video**: changing the style or the setting of an existing video
- **Motion Brush**: a tool from earlier versions of Runway for controlling exactly how each area of the frame moves
- **Keyframe animation**: you set the first and the last frame, and the AI builds the transition between them
- **The consistency problem**: characters can "drift" from one scene to the next, and how to deal with it
- **Commercial licensing**: what you can and can't do with generated videos

---

## Theory

### The 2026 platforms: who's who

Until 2024, AI video was a demo toy: blurry faces, unnatural movement, legs with extra joints. Runway, Kling, Luma and other platforms changed the equation, and in 2026 the market is moving fast: Sora has been shut down, and Runway and Kling have released new generations of their models. Small businesses already use AI video in their ads.

🎨 **Picture this:** the first digital cameras in 2001 took worse pictures than film, but they were perfectly fine for a birthday snapshot, and they kept getting better. AI video is at a similar point now: imperfect, but already useful for everyday jobs.

---

### Runway: the workhorse with an API

Runway is a US startup and one of the market leaders, with a strong API. That's exactly what makes it convenient for automation. As of October 2026, its flagship model is Gen-4.5; paid plans also give you partner models (for example, Kling 3.0, Seedance 2.0, Nano Banana Pro), and Aleph 2.0 edits video you already have.

**What it can do:**

**Text-to-Video.** You write a prompt and get a 5-10 second clip. Runway understands camera language very well: "slow dolly in", "aerial establishing shot", "rack focus from foreground to background". Write like a director, and you get a director's shot.

**Image-to-Video.** You upload a photo of a product or an interior, and Runway animates it while keeping the style. This is the standout feature for real estate and online stores: still photos come to life for ads.

**Motion Brush** (a tool from earlier versions of Runway; check whether the current models still have it). You paint over the frame and set a direction of movement for each area. The water flows, the leaves sway, and everything else stays still: full control.

**Pricing (as of October 2026):**

- There's a free plan with a one-time batch of credits, and several paid plans
- How fast credits go depends on the model: each model uses a set number of credits per second of video
- Current prices and credit rates: [runway.com/pricing](https://runway.com/pricing), [What's current](https://aimayak.com/now/)

**What matters most for us:** the official API (application programming interface, a way for your own programs to talk to the service). You can automate the whole thing: Claude generates the prompts → a script (a small program that runs the steps for you) sends them to Runway → the videos download on their own.

**Commercial license:** according to Runway's pricing page, commercial use is allowed on paid plans. Reread the terms before you deliver work to a client.

```python
from runwayml import RunwayML, TaskFailedError  # pip install runwayml

# The API key is read from the RUNWAYML_API_SECRET environment variable
client = RunwayML()


def generate_video(prompt: str, duration: int = 5) -> str:
    """
    Generates a video from text through the Runway API.
    Returns the URL of the finished video.
    Model names and allowed parameters change: check docs.dev.runwayml.com.
    If the model you pick only accepts a starting image, use
    client.image_to_video.create(...) with the prompt_image parameter.
    """
    try:
        task = client.text_to_video.create(
            model="gen4.5",         # flagship model as of October 2026
            prompt_text=prompt,
            ratio="1280:720",       # 16:9 landscape
            duration=duration,
        ).wait_for_task_output()    # the SDK polls the task status for you
    except TaskFailedError as error:
        raise RuntimeError(f"Generation failed: {error.task_details}")

    return task.output[0]
```

---

### Kling: strong at human movement

Kling is a platform from Kuaishou (China). Its working lineup as of October 2026 is Kling VIDEO 3.0: clips from 3 to 15 seconds, native 4K, sound with lip sync, and several shots in a single request. In late September 2026, Kling 4.0 was announced (up to 30 seconds in one pass, up to 10 keyframes, stereo sound); a wide launch is expected in October.

**Strengths:**

- Human movement: gestures, facial expressions, the way people walk (according to user reviews; test it on your own prompts)
- Clips up to 15 seconds on VIDEO 3.0; version 4.0 is announced at up to 30
- Sound with lip sync right inside the video
- An API is available (documentation: [kling.ai/document-api](https://kling.ai/document-api))

**Limitations:**

- Generation speed depends on load and on your plan: time it on your own tasks
- Data storage questions for EU and US clients (check the terms of your agreement)

**Pricing:** there's a free Basic plan and several paid plans. Current prices: [What's current](https://aimayak.com/now/).

🎨 **Picture this:** Kling is a documentary camera operator. It films movement that looks lived-in, not staged.

**How to connect the API:** you sign in to the Kling API with a JWT, a token built from your Access Key and Secret Key that stays valid for 30 minutes. The API address and model names change between versions, so this lesson doesn't hard-code them: take the current ones from the Kling documentation.

```python
import time
import jwt  # pip install pyjwt


def kling_token(access_key: str, secret_key: str) -> str:
    """Token for the Kling API: a JWT (HS256) signed with the Secret Key, valid for 30 minutes."""
    now = int(time.time())
    payload = {"iss": access_key, "exp": now + 1800, "nbf": now - 5}
    return jwt.encode(payload, secret_key, algorithm="HS256")
```

The token goes in the `Authorization: Bearer <token>` header. After that, you send a request to create a task and check its status following the steps in the Kling documentation: the same "send the task → wait → download the clip" loop as in the Runway example.

---

### Luma: cinematic look and control over the frame

Luma AI makes the Ray video models (as of October 2026, Ray 3.2: cinematic quality and frame-by-frame control of direction) and Creative Agent, which creates and refines video, images, audio and text in your brand's style. There's an API. You can try it for free in the app at app.lumalabs.ai.

**What sets it apart:**

- Frame-by-frame control: you set the first and the last frame → the AI builds the story in between
- Loop videos: endless loops for website backgrounds (check whether the current model supports them)
- Creative Agent, which keeps to your brand's style

**Weak spots:** faces and people, so check them on your own prompts. For products, interiors, nature and architecture, try it first.

**Pricing:** there's a free start; paid plans are listed on the website.

**Commercial license:** read the terms of your plan on the website before you deliver work to a client.

---

### Sora (OpenAI): shut down

OpenAI shut down the Sora app and website on April 26, 2026, and the Sora API was turned off on September 24, 2026; there's no replacement for video in the OpenAI API ([OpenAI's page](https://help.openai.com/en/articles/20001152-what-to-know-about-the-sora-discontinuation)). If older material tells you to build a pipeline on Sora, that advice is out of date.

**Nearby options:** Google Flow (since May 2026, video in Gemini and Flow is made by the Gemini Omni model: short clips with sound; without a subscription, Flow gives you a small number of free daily credits, and the current limits are on Google's site) and Pika ([pika.art](https://pika.art), there's a free tier). Build your pipeline on a platform with an API: Runway, Kling, Luma.

---

### Platform comparison table

| | Runway | Kling | Luma |
|---|---|---|---|
| Model (October 2026) | Gen-4.5 | VIDEO 3.0 (4.0 announced) | Ray 3.2 |
| Max length | see the documentation | up to 15 sec (4.0 announced at up to 30) | see the website |
| Best for | Any content + API | Human movement, sound with lip sync | Cinematic look, frame-by-frame control |
| Free start | one-time credits | Basic plan | free in the app |
| Paid plans | see [What's current](https://aimayak.com/now/) | see [What's current](https://aimayak.com/now/) | see the website |
| API | ✅ | ✅ | ✅ |
| Commercial use | paid plans | check the terms | check the terms |

This table reflects the data as of October 2026; for anything that changes quickly, check each service's own pages.

---

### Workflow: Claude as the scriptwriter + Kling/Runway as the camera crew

🎨 **Picture this:** a Ford assembly line. Each station does one thing, does it fast and passes it on. You're the engineer who set up the line, not the worker standing at it.

```
The client's task
      ↓
Claude (scriptwriter): splits it into 5-8 scenes
      ↓
Claude: writes a prompt for each scene (in English, in camera language)
      ↓
Kling / Runway API: generates the clips in parallel
      ↓
FFmpeg: stitches the clips into one video
      ↓
ElevenLabs: adds a voiceover (optional)
      ↓
A finished 30-second promo video
```

**The full Python pipeline:**

```python
import anthropic
import requests
import subprocess
import json
import os
from pathlib import Path
from runwayml import RunwayML, TaskFailedError  # pip install runwayml

claude = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])
runway = RunwayML()  # key from the RUNWAYML_API_SECRET environment variable


def create_video_scenes(business_info: str) -> list[dict]:
    """Claude writes the script: the theme + a prompt for each scene."""
    response = claude.messages.create(
        model="claude-sonnet-5-5",  # current model IDs: see the Anthropic documentation
        max_tokens=2000,
        messages=[{
            "role": "user",
            "content": f"""
Write a script for a 30-second promo video for this business:

{business_info}

Return JSON: a list of 6 objects:
{{
  "scene_number": 1,
  "duration": 5,
  "description": "What we show (in plain words, for reference)",
  "video_prompt": "A detailed prompt in English for a video generation platform. Include:
                   the type of shot (close-up / wide shot / aerial),
                   the camera movement (dolly in / pan right / static),
                   the lighting (golden hour / soft natural / studio),
                   the mood (warm and inviting / professional / energetic).
                   At least 40 words."
}}

Return only the JSON array, with no other words.
"""
        }]
    )
    return json.loads(response.content[0].text)


def generate_clip(prompt: str, duration: int = 5) -> str:
    """
    Generates a clip through the Runway API and returns the video URL.
    To use Kling instead, rewrite the body of this function following the Kling API documentation:
    the rest of the pipeline stays the same.
    """
    try:
        task = runway.text_to_video.create(
            model="gen4.5",
            prompt_text=prompt,
            ratio="1280:720",
            duration=duration,
        ).wait_for_task_output()
    except TaskFailedError as error:
        raise RuntimeError(f"Runway: generation failed: {error.task_details}")
    return task.output[0]


def download_video(url: str, path: str) -> str:
    """Downloads a video from a URL."""
    r = requests.get(url, stream=True)
    r.raise_for_status()
    with open(path, "wb") as f:
        for chunk in r.iter_content(chunk_size=8192):
            f.write(chunk)
    return path


def concat_with_ffmpeg(video_files: list[str], output: str) -> str:
    """FFmpeg stitches the clips into one video."""
    list_path = "/tmp/ffmpeg_list.txt"
    with open(list_path, "w") as f:
        for vf in video_files:
            f.write(f"file '{os.path.abspath(vf)}'\n")

    subprocess.run([
        "ffmpeg", "-y", "-f", "concat", "-safe", "0",
        "-i", list_path, "-c", "copy", output
    ], check=True, capture_output=True)
    return output


def create_promo_video(business_info: str, output_dir: str = "/tmp/promo") -> str:
    """
    The full pipeline: business description → promo video.
    """
    Path(output_dir).mkdir(parents=True, exist_ok=True)

    print("Claude is writing the script...")
    scenes = create_video_scenes(business_info)
    print(f"Done: {len(scenes)} scenes")

    clip_files = []
    for scene in scenes:
        n = scene["scene_number"]
        print(f"Generating scene {n}/{len(scenes)}: {scene['description']}")

        try:
            video_url = generate_clip(
                scene["video_prompt"],
                scene.get("duration", 5)
            )
            clip_path = f"{output_dir}/scene_{n:02d}.mp4"
            download_video(video_url, clip_path)
            clip_files.append(clip_path)
            print(f"  ✅ Scene {n} is ready")
        except Exception as e:
            print(f"  ❌ Scene {n} failed: {e}")

    if not clip_files:
        raise RuntimeError("Could not create a single clip")

    final_path = f"{output_dir}/promo_final.mp4"
    concat_with_ffmpeg(clip_files, final_path)
    print(f"\n🎬 Final video: {final_path}")
    return final_path


# Run it
if __name__ == "__main__":
    business = """
    "Acme Realty", a real estate agency in Cuenca, Ecuador (a made-up example for this lesson).
    Specialty: selling apartments to buyers relocating from the US.
    Mood: professional, trustworthy, warm.
    Unique selling point: full service in English.
    Key listings: apartments in the historic center.
    """
    create_promo_video(business)
```

---

### Commercial restrictions and licenses

License terms differ from service to service, and they change. The general picture as of October 2026:

- **Paid plans** usually allow commercial use (according to Runway's pricing page, that's the case there)
- **Free plans** usually restrict commercial use or add a watermark
- Who owns the result, and the restrictions on real people's faces and other companies' brands, are spelled out in each service's terms

**The main rule:** before you deliver work to a client, check the terms of your specific plan on the service's website and save a screenshot of them. Don't promise a client more than the license allows.

---

### Your costs: what it costs you to make a video

There are no client prices here: they depend on the market, the niche and the location, and nobody can guarantee income. We only count what it costs you:

- **Platform credits:** number of clips × seconds per clip × credits used per second × the price of a credit on your plan (each Runway model has its own per-second rate; see Runway's pricing page)
- **Voice and editing:** ElevenLabs, CapCut and others, at their own plan prices
- **Your time:** the script, checking every clip, revisions

Those lines add up to the price of your service: [How to set a price](d02-pricing-simple.md), [What a customer costs you and what they bring in](d01-unit-economics-simple.md). Typical formats: short videos for social media, a monthly package of videos, a video tour of a property.

🎨 **Picture this:** you're selling a video, not hours. The client doesn't care whether it took you 2 hours or 2 days. They need a result that does the job.

---

## Practice

### Step 1: Set up accounts and keys (5 min)

1. Go to [kling.ai](https://kling.ai), the international version of the platform; it has a free Basic plan
2. For a working pipeline, create a Runway account and get an API key in the developer portal (the link is in the documentation at [docs.dev.runwayml.com](https://docs.dev.runwayml.com))
3. Save it: `export RUNWAYML_API_SECRET="your_key"`

### Step 2: Your first video by hand (10 min)

Open Kling → Text to Video. Test this prompt:

```
A modern apartment interior in South America. Cuenca, Ecuador.
Warm golden hour sunlight streaming through large windows.
Slow cinematic dolly shot revealing open living room with mountain views.
Contemporary design, plants, wooden floors, white walls.
Real estate advertisement quality. Professional photography style.
```

Look at the result. Try swapping 2-3 words and compare, so you get a feel for how the prompt changes the picture.

### Step 3: Automate it through the API (10 min)

Install the dependencies:

```bash
pip install anthropic requests runwayml
```

Run the `create_promo_video()` script with a description of a real business in your town. Watch Claude write the script → Runway generate the scenes → FFmpeg stitch the final video together.

### Step 4: Compare the tools (5 min)

Send the same prompt to Runway, Kling and Luma. Compare:

- Image quality
- How realistic the movement looks
- Total wait time

Write down for yourself which tool works best for which tasks. That becomes the basis of what you offer clients.

### Step 5: Put together a sample for a small business (5 min)

Find a small business in your town that has no video content (a restaurant, an agency, a hair salon). Prepare:

- A 15-second demo video for their niche
- A short description: what exactly you do and what you don't promise (for example, you don't guarantee higher sales)

Work out your price and terms with the lessons on pricing and unit economics (links above). This is a portfolio piece, not a promise of income.

---

## Tools and resources

- **[Runway](https://runway.com)**: strong API, professional control
- **[Kling AI](https://kling.ai)**: human movement, sound with lip sync
- **[Luma](https://lumalabs.ai)**: Ray video models, frame-by-frame control
- **[Google Flow](https://flow.google.com)**: video from Google, with free daily credits
- **[Pika](https://pika.art)**: a set of apps for styles and effects, free tier
- **[FFmpeg](https://ffmpeg.org)**: stitching and processing video from the command line, free
- **[CapCut](https://www.capcut.com)**: final editing with captions and music
- **[ElevenLabs](https://elevenlabs.io)**: voiceover
- **Prices and versions:** [What's current](https://aimayak.com/now/)

---

## Key takeaways

> The client doesn't care how you made the video: in 2 hours with AI or in 2 days with a videographer. They need a video that solves their problem. AI tools speed up production, but checking every clip is still your job.

> A platform's API is the difference between handwork and a production line. By hand, you make videos one at a time; a pipeline runs a whole series of scenes while you're busy with something else.

> Platforms change fast: Sora was shut down, and Runway and Kling released new generations. Build your pipeline so you can swap the platform by changing one function.

---

## Next lesson

→ [The complete content pipeline: from idea to publishing](72-content-pipeline-complete.md)

We'll put it all together: text (Claude) + voice (ElevenLabs) + video (Runway/Kling) + automatic posting (n8n/Buffer).
