# AI video generation: Runway, Kling, Luma and more

**Time:** about 25 min reading + 60 min practice

---

## The gist

A short video used to take a camera operator, an editor and a studio. Today you open a browser tab, write a few sentences, and a few minutes later you have a clip. It isn't Hollywood, but for social media, a landing page or an ad it's often good enough. In this lesson we go through the platforms as of October 2026 and put a video together two ways. Without code: Claude writes the script and the prompts (a prompt is your request to the AI), you paste them into the Kling or Runway website and join the clips in a video editor. With code (optional, for people who program): the same pipeline runs by itself through an API, a way to plug the service into your own program.

🎨 **Picture this:** every video used to be handmade pottery: slow, expensive, started from scratch every time. Now it's more like a 3D printer: you enter the settings and get the finished piece. The quality is a notch below handmade, but it's far faster.

---

## Key concepts

- **Text-to-Video**: a video generated from a written description of a scene
- **Image-to-Video**: animating a still photo or a render (bringing it to life)
- **Video-to-Video**: changing the style or the setting of an existing video
- **Motion Brush**: a tool from earlier versions of Runway for controlling exactly how each area of the frame moves
- **Keyframe animation**: you set the first and the last frame, and the AI builds the transition between them
- **The consistency problem**: characters can "drift" from one scene to the next. What helps: the same starting image for every scene (Image-to-Video mode) and the same description of the character in every prompt
- **Commercial licensing**: what you can and can't do with generated videos

---

## Theory

### The 2026 platforms: who's who

Until 2024, AI video was a demo toy: blurry faces, unnatural movement, legs with extra joints. Runway, Kling, Luma and other platforms changed the equation, and in 2026 the market is moving fast: Sora has been shut down, and Runway and Kling have released new generations of their models. Small businesses already use AI video in their ads.

🎨 **Picture this:** the first digital cameras in 2001 took worse pictures than film, but they were perfectly fine for a birthday snapshot, and they kept getting better. AI video is at a similar point now: imperfect, but already useful for everyday jobs.

---

### Runway: the workhorse with an API

Runway is a US company and one of the best-known AI video services. It has a convenient API, which is why people often pick it for automation. As of October 2026, its flagship model is Gen-4.5; paid plans also give you partner models (for example, Kling 3.0, Seedance 2.0, Nano Banana Pro), and Aleph 2.0 edits video you already have.

**What it can do:**

**Text-to-Video.** You write a prompt and get a clip of up to 10 seconds. Runway understands camera language: "slow dolly in" (the camera slowly moves closer), "aerial establishing shot" (a wide view from above), "rack focus from foreground to background" (the focus shifts from the front of the scene to the back). The more precisely you describe the shot, the closer the result is to what you had in mind.

**Image-to-Video.** You upload a photo of a product or an interior, and Runway animates it while keeping the style. This is useful for real estate and online stores: still photos turn into clips for ads.

**Motion Brush** (a tool from earlier versions of Runway; check whether the current models still have it). You paint over the frame and set a direction of movement for each area. The water flows, the leaves sway, and everything else stays still: full control.

**Pricing (as of October 2026):**

- There's a free plan with a one-time batch of credits, and several paid plans
- How fast credits go depends on the model: each model uses a set number of credits per second of video
- Current prices and credit rates: [runway.com/pricing](https://runway.com/pricing), [What's current](https://aimayak.com/en/now/)

**For people who program:** Runway has an official API (application programming interface, a way for your own programs to talk to the service). With it the pipeline runs by itself: Claude generates the prompts → a script (a small program that runs the steps for you) sends them to Runway → the videos download on their own.

**Commercial license:** according to Runway's help center, you keep the rights to what you create and commercial use is allowed; on the free plan, videos carry a watermark. Reread the terms before you deliver work to a client.

An example API call (optional, for people who program):

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

Kling is a platform from Kuaishou (China). Its working lineup as of October 2026 is Kling VIDEO 3.0: clips from 3 to 15 seconds, native 4K, sound with lip sync, and several shots in a single request. In late September 2026, Kling 4.0 was introduced (up to 30 seconds in one generation, up to 10 keyframes, stereo sound): access is opening gradually, and a wide launch is promised for October.

**Strengths:**

- Human movement: gestures, facial expressions, the way people walk (according to user reviews; test it on your own prompts)
- Clips up to 15 seconds on VIDEO 3.0; version 4.0 is announced at up to 30
- Sound with lip sync right inside the video
- An API is available (documentation: [kling.ai/document-api](https://kling.ai/document-api))

**Limitations:**

- Generation speed depends on load and on your plan: time it on your own tasks
- Where data from EU and US clients is stored: check the service's terms

**Pricing:** there's a free Basic plan and several paid plans. Current prices are on Kling's website; what has changed on the market is collected on the [What's current](https://aimayak.com/en/now/) page.

🎨 **Picture this:** Kling is a documentary camera operator. It films movement that looks lived-in, not staged.

**How to connect the API** (for people who program): in Kling's developer console you create an API key and send it in the `Authorization: Bearer <key>` header. Sign-in used to go through a JWT token built from an Access Key and a Secret Key; that scheme remains in the previous version of the API. Request addresses and model names change between versions, so this lesson doesn't hard-code them: take the current ones from the Kling documentation.

```python
import os


def kling_headers() -> dict:
    """Headers for Kling API requests: the key is read from the KLING_API_KEY environment variable."""
    return {
        "Authorization": f"Bearer {os.environ['KLING_API_KEY']}",
        "Content-Type": "application/json",
    }
```

After that, you send a request to create a task and check its status following the steps in the Kling documentation: the same "send the task → wait → download the clip" loop as in the Runway example.

---

### Luma: cinematic look and control over the frame

Luma AI makes the Ray video models (as of October 2026, Ray 3.2: cinematic quality and keyframe control over the clip) and Luma Agents, which create and refine video, images, audio and text. There's an API. You work in the app at app.lumalabs.ai.

**What sets it apart:**

- Keyframe control: you set the first and the last frame → the AI builds the story in between
- Luma Agents, which take a task from the idea to the finished material

**Weak spots:** faces and people, so check them on your own prompts. For products, interiors, nature and architecture, try it first.

**Pricing:** the pricing page has no free plan: plans are paid, starting with Plus. According to Luma, every plan includes free trial credits. Details: [lumalabs.ai/pricing](https://lumalabs.ai/pricing)

**Commercial license:** on the pricing page, commercial use is listed starting with the Plus plan. Reread the terms before you deliver work to a client.

---

### Sora (OpenAI): shut down

OpenAI shut down the Sora app and website on April 26, 2026, and the Sora API was turned off on September 24, 2026; there's no replacement for video in the OpenAI API ([OpenAI's page](https://help.openai.com/en/articles/20001152-what-to-know-about-the-sora-discontinuation)). If older material tells you to build a pipeline on Sora, that advice is out of date.

**Nearby options:** Google Flow (Google's video studio: it runs the Gemini Omni models, released in May 2026, and Veo 3.1; clips of up to 10 seconds; without a subscription you get free credits every day, and the current number is on Google's site) and Pika ([pika.art](https://pika.art); there's a free plan, but it has no monthly credits: you buy them in packs). If you're building the pipeline with a script, you need a platform with an API: Runway, Kling, Luma.

---

### Platform comparison table

| | Runway | Kling | Luma |
|---|---|---|---|
| Model (October 2026) | Gen-4.5 | VIDEO 3.0 (4.0 is rolling out gradually) | Ray 3.2 |
| Max length | see the documentation | up to 15 sec (4.0 announced at up to 30) | see the website |
| Best for | General-purpose work, convenient API | Human movement, sound with lip sync | Cinematic look, keyframe control |
| Free start | one-time credits | Basic plan | no free plan; trial credits |
| Paid plans | [runway.com/pricing](https://runway.com/pricing) | see Kling's website | [lumalabs.ai/pricing](https://lumalabs.ai/pricing) |
| API | ✅ | ✅ | ✅ |
| Commercial use | allowed; watermark on the free plan | check the terms | from the Plus plan |

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
Kling or Runway: generates the clips (by hand on the website or through the API)
      ↓
A video editor (for example, CapCut) or FFmpeg: joins the clips into one video
      ↓
ElevenLabs: adds a voiceover (optional)
      ↓
A finished 30-second promo video
```

Without code, you walk this path by hand: you ask Claude in a regular chat to write the script and the prompts, paste each prompt into the Kling or Runway website, download the clips and put them one after another in a video editor. That's how Step 5 of the practice works.

**The same pipeline as a Python script (optional, for people who program):**

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
        max_tokens=8000,  # the limit also covers the model's thinking, so leave headroom
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
    # The response may contain thinking blocks: take only the text
    text = "".join(block.text for block in response.content if block.type == "text")
    return json.loads(text)


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

- **Paid plans** usually allow commercial use. Examples: Luma lists it starting with the Plus plan, and Pika includes a commercial license starting with the Creator plan
- **Free plans** usually restrict commercial use or add a watermark. According to Runway's help center, you keep the rights to what you create on any plan, but videos made on the free plan carry a watermark
- Who owns the result, and the restrictions on real people's faces and other companies' brands, are spelled out in each service's terms

**The main rule:** before you deliver work to a client, check the terms of your specific plan on the service's website and save a screenshot of them. Don't promise a client more than the license allows.

---

### Your costs: what it costs you to make a video

There are no client prices here: they depend on the market, the niche and the location, and nobody can guarantee income. We only count what it costs you:

- **Platform credits:** number of clips × seconds per clip × credits used per second × the price of a credit on your plan (each Runway model has its own per-second rate; see Runway's pricing page)
- **Voice and editing:** ElevenLabs, CapCut and others, at their own plan prices
- **Your time:** the script, checking every clip, revisions

How to turn those lines into the price of your service comes later, in the module on money: [How to set a price](d02-pricing-simple.md), [What a customer costs you and what they bring in](d01-unit-economics-simple.md). Typical formats: short videos for social media, a monthly package of videos, a video tour of a property.

🎨 **Picture this:** you're selling a video, not hours. The client doesn't care whether it took you 2 hours or 2 days. They need a result that does the job.

---

## Practice

Steps 1, 2, 4 and 5 need no code: together they're the full path from an idea to a finished video. Step 3 is optional; it's for people who program.

### Step 1: Set up an account (5 min)

1. Go to [kling.ai](https://kling.ai), the international version of the platform; it has a free Basic plan
2. Sign up (an email address is enough) and sign in
3. Find the video creation section and the Text to Video mode

### Step 2: Your first video by hand (15 min)

In Kling, open Text to Video and paste this prompt:

```
A modern apartment interior in South America. Cuenca, Ecuador.
Warm golden hour sunlight streaming through large windows.
Slow cinematic dolly shot revealing open living room with mountain views.
Contemporary design, plants, wooden floors, white walls.
Real estate advertisement quality. Professional photography style.
```

Wait for the result: on the free plan, generation can take several minutes or longer. Watch the clip. Then swap 2-3 words in the prompt and compare, so you get a feel for how the prompt changes the picture.

### Step 3 (optional, for people who program): Automate it through the API

1. Create a Runway account and get an API key in the developer portal (the link is in the documentation at [docs.dev.runwayml.com](https://docs.dev.runwayml.com)). Generating through the API uses credits; the terms are in the same place
2. Save the keys as environment variables: `export RUNWAYML_API_SECRET="your_key"` and `export ANTHROPIC_API_KEY="your_key"`
3. Install FFmpeg (a program for joining video, [ffmpeg.org](https://ffmpeg.org)) and the Python libraries:

```bash
pip install anthropic requests runwayml
```

4. Save the pipeline code from the "Workflow" section to a file called `promo.py`, replace the business description with your own and run it with `python promo.py`. Watch Claude write the script → Runway generate the scenes → FFmpeg join the final video

### Step 4: Compare the tools (10 min)

Send the same prompt to one more service you have access to: for example, Runway (the free plan has a one-time batch of credits; you can see which models it covers after you sign in) or Google Flow, if it works in your country. Luma has no free plan. Compare:

- Image quality
- How realistic the movement looks
- Total wait time

Write down for yourself which tool works best for which tasks. It will help when you choose a service for a task or for a client.

### Step 5: Put together a demo video for a small business (30 min)

Without code, a video comes together like this: Claude writes the script, you make the clips on the Kling website, and you join them in a video editor.

1. Pick a small business in your town that has no video (a restaurant, an agency, a hair salon), or make one up
2. Ask Claude, in a regular chat, to write the script:

```
Write a script for a 15-second promo video for this business: [describe the business in two or three sentences].
Split the video into 3 scenes of 5 seconds each. For each scene, give me:
1) what we show, in plain words;
2) a prompt for a video generator: the type of shot (close-up or wide), the camera movement, the lighting, the mood.
```

3. Paste each scene's prompt into Kling and download the three clips. If you run out of free credits for the day, finish tomorrow or settle for two scenes
4. Open a video editor, for example [CapCut](https://www.capcut.com): start a new project, put the clips one after another and save the video to your device
5. Write a short description: what exactly you do and what you don't promise (for example, you don't guarantee higher sales)

**Check yourself:** you have a 10-15 second video file made of two or three scenes, and a paragraph describing it. If the video is going into an ad or to a client, check your plan's terms first: free plans usually come with a watermark and limits on commercial use. This is a portfolio piece, not a promise of income.

---

## Tools and resources

- **[Runway](https://runway.com)**: convenient API, lots of settings
- **[Kling AI](https://kling.ai)**: human movement, sound with lip sync
- **[Luma](https://lumalabs.ai)**: Ray video models, keyframe control
- **[Google Flow](https://flow.google.com)**: video from Google, with free daily credits
- **[Pika](https://pika.art)**: a set of apps for styles and effects; on the free plan you buy credits in packs
- **[FFmpeg](https://ffmpeg.org)**: joining and processing video from the command line, free (for people who program)
- **[CapCut](https://www.capcut.com)**: no-code editing: joining clips, captions, music
- **[ElevenLabs](https://elevenlabs.io)**: voiceover
- **Prices and versions:** [What's current](https://aimayak.com/en/now/)

---

## Key takeaways

> The client doesn't care how you made the video: in 2 hours with AI or in 2 days with a videographer. They need a video that solves their problem. AI tools speed up production, but checking every clip is still your job.

> You can put a video together without code: the script in Claude, the clips on the service's website, the joining in a video editor. An API matters when there are many videos: a script runs a whole series of scenes while you're busy with something else.

> Platforms change fast: Sora was shut down, and Runway and Kling released new generations. Don't tie yourself to one service: keep your scripts and prompts on your side so it's easy to move to another.

---

## Next lesson

→ [AI music with Suno and sound design](69-music-ai-suno.md): background music and short sounds for your videos.

How to join text, voice, video and publishing into one flow comes later, in the lesson [The complete content pipeline: from idea to publishing](72-content-pipeline-complete.md).
