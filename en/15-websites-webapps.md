# Build websites and web apps with Claude Code

**Time:** about 25 min reading + 45 min practice

---

## The gist

Building a website used to be like building a house: you needed an architect (a designer), a foreman (a front-end developer who turns the design into a working page), a crew (developers), and several weeks of work. With Claude Code, it's like having a skilled builder on call: you describe in words what you want, it builds it, and you make adjustments as you go.

You don't need to know how to code for this lesson. You'll be describing, looking and asking for changes. It's also the first step if you later want to build an app with Claude Code.

---

## Key concepts

- Claude Code builds a complete HTML/CSS/JS website (the three building blocks of a web page: structure, styling and behavior) from a plain-language description
- You iterate by talking: "make the background darker" instead of editing the CSS by hand
- A local server (localhost) lets you check the site before you deploy it (deploying means putting it live on the internet)
- Deploying to Vercel, Cloudflare Pages or GitHub Pages is free for personal projects (terms for commercial sites below)

---

## Theory

### What Claude Code actually builds

🎨 **Picture this:** Claude Code builds a website the way an experienced carpenter builds custom furniture. You say "I want a table with drawers, in dark wood," and they make a real table, not a cardboard mockup. You can set a plate on it right away.

When you ask for a website, the agent generates real code. Not a template, not a placeholder: complete, working HTML, CSS and JavaScript. You can open these files in any browser, and they'll work.

**Sample prompt:** "Build a website for a fitness coach. Name: Mike Carter. Specialty: 90-day body transformation. Needed: a home page with a call to action, a section with 3 programs (Weight Loss, Muscle Gain, Challenge), client testimonials, a contact form. Style: dark background, orange accents, modern minimalism."

**What the agent builds:**
- `index.html`: the structure of the page
- `styles.css`: all the styles, colors, fonts and the responsive layout (the page adapts to the screen size)
- `script.js`: animations, forms, interactive elements
- Optimized for phones
- Proper HTML semantics (headings, sections, meta tags)

The first draft appears in minutes, not weeks.

---

### A worked example: a fitness coach's website

Let's walk through a real workflow for building a website, from start to finish.

#### Stage 1: The first prompt

```
Build a one-page website for a personal trainer.
Client details:
- Name: Mike Carter
- Specialty: body transformation, works with busy professionals
- Key promise: visible results in 90 days or your money back
- Three programs: "Lose 20 Pounds" ($200/month), "Lean & Strong" ($250/month), "VIP Coaching" ($500/month)
- Style: dark (#1a1a1a), orange accents (#f5813f), a modern font
- Needs a form to book a free consultation
```

#### Stage 2: Iterate by talking

🎨 **Picture this:** iterating on a website by talking is like a suit fitting at the tailor. "A little wider in the shoulders," "narrower lapels," "darker buttons." The tailor makes the changes and shows you again. You don't sew anything yourself.

You've opened the site in your browser and taken a look. Now you make adjustments:

- "Make the headline bigger, it gets lost"
- "Add a stats bar: 3 years of experience / 200+ clients / 94% satisfied"
- "The programs section looks cramped, give it more breathing room"
- "Add a video cover to the home page (a placeholder with a play button)"
- "In the booking form, add a field for choosing a program"

Each change is one sentence in plain English. The agent finds the right spot in the code and changes it. You don't look at the code or edit anything by hand.

#### Stage 3: Check it on different devices

The agent has already made the design responsive, but it's worth checking:

```
Check how the site looks on a phone screen 375px wide.
If anything breaks, fix it.
```

---

### A local server: check before you deploy

🎨 **Picture this:** a local server is like a dress rehearsal in an empty theater. Everything is real: the lights, the costumes, the lines. But there's no audience. You find the problems and fix them before opening night.

Before you show the site to a client or deploy it, you test it locally. Claude Code starts a local server:

```bash
# The agent runs this for you (the --bind 127.0.0.1 option keeps the server reachable only from your own computer)
python3 -m http.server 3000 --bind 127.0.0.1
# or
npx serve .
```

Open your browser at `http://localhost:3000` and you'll see the site as if it were already on the internet, except only you can see it.

**Why this matters:** some things don't work when you simply open the HTML file (API requests, fonts from Google Fonts). A local server reproduces real-world conditions.

---

### Deploying: putting your site on the internet

🎨 **Picture this:** deploying to Vercel is like using an espresso machine. Inside there's complex machinery: pressure, temperature, grind. You press one button, and your coffee is ready.

#### Vercel (recommended to start)

**Cost:** the Hobby plan is free, but only for personal, non-commercial projects. For a client's site or any commercial site, you need the paid Pro plan (as of October 2026: $20 a month per developer, which includes $20 of credit for usage). Check the current terms at vercel.com/pricing. If you need a free option for a client's site, look at Cloudflare Pages (the lesson [24/7 deployment: Cloudflare Workers](18-deployment-cloudflare.md)) and check the terms on its pricing page.

**How to deploy:**
1. Upload your code to GitHub, a website that stores code projects (you can ask the agent to do this)
2. Connect the repository (your project's folder on GitHub) to Vercel (vercel.com)
3. Click Deploy
4. Get a URL like `fitness-carter.vercel.app`
5. You can connect your own domain

**Automatic updates:** every time the agent makes changes and you commit them to GitHub (a commit is a saved snapshot of your changes), Vercel updates the site automatically. A deploy takes 30-60 seconds.

#### GitHub Pages

**Cost:** free, as long as the code is public

**When to choose it:** static sites with no server-side code, when you don't mind everyone being able to see your code.

**How to deploy:** repository → Settings → Pages → choose a branch → Save.

---

### Adding more features

#### Contact forms

A static site can't receive form submissions on its own (it has no server side). Your options:

- **Formspree**: has a free plan with a monthly limit on submissions (check the current limit on their pricing page); you just point the form's action at their URL
- **Netlify Forms**: if you deploy on Netlify, forms work out of the box
- **EmailJS**: sends the form straight from the browser through their API

The agent knows all of these services and will set one up if you ask.

#### A CMS for content

If the client wants to edit the text on their own, without a programmer, they need a CMS (content management system, an editing dashboard for the site):

- **Decap CMS** (formerly Netlify CMS): open source, free
- **Sanity**: more powerful, has a free plan
- **Contentful**: a popular option

The agent can connect any of them to a static site.

#### Payments

To sell services right from the site:

- **Stripe**: accepts cards from around the world (availability depends on the country where your business is registered)
- **PayPal**: the widget takes a few lines of code

---

### What clients order most often

🎨 **Picture this:** a simple website is like a photographer who does a professional shoot in a single day. That used to take a studio, lighting and a crew. Now it's one person with the right tool.

Websites are one of the services you can offer with Claude Code. Here's what clients order most often:

**A simple site for a local business:** a hair salon, a restaurant, a dental office.

**A landing page for a product or service:** one screen that clearly explains the value, with a sign-up form.

**A portfolio for a freelancer:** the client wants to show off their work.

**An event site:** a conference, a party, a company event.

Price and timing depend on the market, the niche and how many rounds of revisions there are; there are no universal numbers. How to work out your own price is covered in the lessons [Value-based pricing](39-monetization-pricing.md) and [How to set your price](d02-pricing-simple.md).

---

### Limits: what Claude Code doesn't do on its own

**The honest limits:**

- Complex web apps (user logins, databases, real-time features) need more than HTML/CSS/JS: they need a backend (the server side that stores data and runs the logic). Claude Code can handle it, but it's considerably harder and takes longer
- The design won't always come out "wow" on the first try; it takes iteration
- The agent doesn't draw unique illustrations and icons (it uses stock images or emoji)
- You need to supply original photos yourself

**Practical takeaway:** for landing pages and simple business sites, it's an excellent tool. For complex web apps with users, payments and real data, you need more knowledge of architecture (the lessons [APIs and integrations](16-apis-integration.md) and [24/7 deployment: Cloudflare Workers](18-deployment-cloudflare.md)).

---

## Practice

**Exercise: build a one-page website**

Pick one option:
- **Option A:** A site about you (who you are, what you do, how to reach you)
- **Option B:** A practice site for a made-up business (invent your own)
- **Option C:** If you already have a real client, start their site

The process:
1. Describe what you need in one prompt (topic, sections, style, colors)
2. Look at the result in your browser through the local server
3. Make at least 5 changes by talking
4. Deploy to Vercel or GitHub Pages
5. Share the link: you have a live website

⚠️ If it's a real client's site (Option C), remember that Vercel's free Hobby plan is for non-commercial projects only (see the deploy section above). And GitHub Pages needs the code to be public, so keep any private details out of it.

---

## Tools and resources

- **Claude Code**: builds HTML/CSS/JS from a description
- **[Vercel](https://vercel.com)**: deployment; the free plan is for non-commercial projects only
- **[GitHub Pages](https://pages.github.com/)**: an alternative for public repositories
- **[Cloudflare Pages](https://pages.cloudflare.com/)**: fast deployment, has a free plan, a global CDN (a network of servers around the world that delivers your site quickly). As of October 2026, Cloudflare recommends Workers with static assets for new projects; Pages keeps working
- **[Formspree](https://formspree.io)**: form handling, has a free plan with a limit
- **[EmailJS](https://www.emailjs.com/)**: sends forms straight from the browser
- **[Playwright](https://playwright.dev/)**: automated testing of web apps (across browsers)
- **[Puppeteer](https://pptr.dev/)**: automates Chrome for testing and screenshots
- **[Google Fonts](https://fonts.google.com/)**: free fonts; the agent knows how to add them
- **[Unsplash](https://unsplash.com)**: free photos (the agent can pull images from there)
- **[Coolors](https://coolors.co)**: a color palette generator, if you don't know what to pick
- **[Lighthouse](https://developer.chrome.com/docs/lighthouse)**: audits a site's performance and accessibility (built into Chrome DevTools)

Current prices and versions: [What's current](https://aimayak.com/en/now/).

---

## Common mistakes

**Mistake 1: Not testing on phone screens**
The site looks perfect on a desktop, but on a phone the text runs off the screen and the buttons are too small. Always check: "Check how it looks on a screen 375px wide" (that's the width of the iPhone SE, the narrowest popular screen).

**Mistake 2: Forgetting the meta viewport tag**
Without `<meta name="viewport" content="width=device-width, initial-scale=1.0">` the site looks like a shrunken desktop version on a phone. Claude usually adds it, but check.

**Mistake 3: Not checking how fast it loads**
Huge images, unoptimized fonts, heavy animations, and the site takes 8 seconds to load. Ask the agent: "Optimize all the images and make sure the site loads in under 3 seconds." Or use Lighthouse in Chrome DevTools.

---

## Related lessons

- **[API keys and .env setup](11-api-keys-env.md)**: setting up a `.env` file (where secret keys live, so they stay out of your site's code) for API integrations on your site (Stripe, Formspree)
- **[24/7 deployment: Cloudflare Workers](18-deployment-cloudflare.md)**: deploying to Cloudflare Workers and Pages in detail
- **[RAG: Retrieval Augmented Generation](14-rag.md)**: if your site needs a chatbot with a knowledge base

---

## Key takeaways

> A simple site that used to take a week of work can now take a few hours. That isn't just a bit more efficiency; it's a different kind of work. Projects that used to require a team are now within reach of one person.

> Iterating in plain language is the biggest advantage. You're not learning CSS; you're describing what you want. That fundamentally changes who can build websites.

> Deploying your first site is a skill that will come in handy at work and in personal projects. Don't put off the practice.

---

## Next lesson

→ [APIs and integrations](16-apis-integration.md): how programs talk to each other and how to use that
