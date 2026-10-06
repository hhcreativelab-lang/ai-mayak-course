# No-code AI for non-programmers: v0, Webflow, Framer

**Time:** about 25 min reading + 60 min practice

---

## The gist

🎨 **Picture this:** imagine working with an architect without needing a drafter. You describe what you want in words, "a three-bedroom house with floor-to-ceiling windows and a heated garage," and a few minutes later a finished design is sitting in front of you. You never picked up a pencil, you don't know the building code, and the house still comes out looking professional. That's how no-code AI tools work: you describe what you want, and they build it. Claude Code, in this picture, is the general contractor you call in when you need custom wiring or plumbing that the standard plan didn't account for.

This lesson is about building websites and apps for yourself and for clients without writing a single line of code by hand. It's also about when no-code is enough, and when it's time to bring in Claude.

---

## Key concepts

- **No-code AI** (building software without writing code): tools that generate an app's interface, content and logic from a plain-language text description
- **v0** (v0.app, formerly v0.dev): a Vercel service that builds React interfaces and whole apps from a prompt (your request to the AI); you can look at the code it produces, take it out and keep working on it in Claude Code
- **Webflow AI**: AI built into Webflow that helps you build pages, write copy and fill in the CMS (the system that manages a site's content) right in the editor
- **Framer AI**: Framer's agents, which create pages, copy and images in your project from a description in words
- **The hybrid approach**: v0 or Framer generates the visual part, and Claude Code adds the business logic, the API integrations (an API, or application programming interface, is how programs talk to each other) and the database
- **The "builder for hire" niche**: a service where you take orders for websites, build them quickly with the tools from this lesson, and hand them over to the client as a finished product
- **Speed vs flexibility**: no-code is faster for standard jobs; Claude Code is irreplaceable for custom logic and long-term growth
- **Lovable and Bolt.new**: Claude Code's competitors for non-coders. They generate full-stack apps from a description, but there's a ceiling on how far you can customize them

---

## Theory

### Why no-code AI became a professional tool

"Building a site without code" used to mean a Squarespace or Wix template with fixed blocks and limited animation. Today, no-code AI tools generate production-ready React components, make the layout adapt to phones and computers, set up CMS fields and publish to a CDN (content delivery network). The gap between "I made it myself" and "I hired a developer" has shrunk so much that a business owner with no technical background can quickly put together a simple site that used to take a team weeks.

That creates a concrete business opportunity: becoming a "builder for hire," someone who knows these tools better than the client and gets paid for expertise in choosing the right set of tools and for speed of delivery, not for writing code.

---

### v0 (Vercel): from text to a React interface

**What it is.** v0 (at v0.app, formerly v0.dev) is a service from Vercel, the company behind Next.js. It's now an agent that builds interfaces and full-stack apps. You write a prompt ("make a product card with an image, a price, an add-to-cart button and a discount badge") and get ready-made React code with Tailwind CSS and shadcn/ui. There's a free plan with a daily message limit; paid plans run on credits that are used up based on how much text goes into and out of v0 (terms at [v0.app/pricing](https://v0.app/pricing)).

**How it works.** v0 understands not just "a button" but "a Stripe-style button with a hover effect and a loading state." The output is a regular React/Next.js project: you can look at it in the Code tab, take it out through GitHub (a service that stores code) or publish it straight to Vercel. It usually needs a little fine-tuning to fit your project.

**The standout feature for the hybrid approach.** You paste the generated code into Claude Code and say: "connect this component to my /products/:id API, add skeleton loading and error handling." Claude Code writes the logic on top of v0's visuals.

**A practical workflow:**

1. Describe the screen or component you need in v0
2. Iterate with prompts ("make the headline bigger," "add a dark mode")
3. Take out the final code: from the Code tab or by connecting the project to GitHub
4. Hand it to Claude Code and describe the business logic
5. Claude Code connects the data, adds validation and deploys

🎨 **Picture this:** v0 is a designer who sketches a layout in 30 seconds. Claude Code is the developer who takes the sketch and turns it into a working product. You're the manager who gives both of them their assignments.

---

### Webflow AI: content and CMS without the busywork

**What it is.** Webflow is a visual website editor with its own built-in hosting. Webflow has AI features: help building and designing pages, writing copy, filling in the CMS, translating the site. The feature set and the plans change, so check the current details on Webflow's site.

**AI in the CMS.** You create a CMS collection called "Services" with three fields: name, description, price. Then you ask the AI to create items in that collection, one at a time or in bulk, and it fills in the fields, descriptions included. For an agency with a long list of services, that speeds up first drafts noticeably, but every text still needs a human read and edit.

**Localization in Webflow.** The paid Webflow Localization add-on can translate your site into other languages with AI: for example, Spanish and French versions of your English site. For international clients this saves translation time, but machine translation still needs a human read-through.

**Limitations.** To publish a site on your own domain, you need a paid Site plan. There's a free Workspace plan; a paid one is for working as a team. For clients with a simple site, Webflow can be overkill. But for businesses with a blog, a team and regularly updated content, it's a great fit.

---

### Framer AI: a landing page from one prompt

**What it is.** Framer is a design tool that has learned to generate complete landing pages from a text description. You write: "A landing page for a yoga studio in Austin. Modern minimalist style, warm tones, sections: hero, about us, class schedule, reviews, book a trial class," and shortly after you get a page with copy and images that you can keep editing. The agent can also set up phone and tablet versions: ask it to, and check the result.

**Strengths.** Framer is known for beautiful animation and polished layouts, and the AI works in the same editor. On the free plan, your site is published on a Framer subdomain; connecting your own domain takes a paid plan (terms on Framer's site).

**Framer vs Webflow.** For a landing page for a single product, people usually pick Framer. For a company site with a big catalog and a blog, Webflow and its CMS. Compare the plans on the official pricing pages before you choose.

**Limitation.** Framer is first and foremost a tool for websites and marketing pages, not for complex web apps. If the client wants a customer account area or a CRM integration, look at an app builder (Bubble, Lovable) or a hybrid with Claude Code.

---

### Bubble.io + AI plugins: full web apps

**What it is.** Bubble is a no-code platform for building full web apps: with a database, user accounts, logic and payment integrations. Add AI features or connect models through an API (OpenAI, Claude), and the app can read, summarize and write on its own.

**Typical Bubble projects.** Marketplaces (like Airbnb, without code), SaaS dashboards, online course platforms, CRMs for small businesses. All of it without writing server code.

**Bubble + the Claude API.** Through a plugin or direct API calls, you connect Claude (an LLM, a large language model). For example: a user uploads a document → Bubble sends the text to the Claude API → Claude returns a summary → Bubble saves it to the database and shows it to the user. That's a working AI product without a single line of server code.

**The downside of Bubble.** A steep learning curve: you won't master the basics in one evening. To launch your app on your own domain you need a paid plan, and the price depends on how much load your app puts on the platform (plans on Bubble's site). It's a good fit for an MVP (a first, minimal version of a product) and a small number of users; if the product grows a lot, it may eventually need to move to its own code.

---

### Lovable: Claude Code's competitor for non-programmers

**What it is.** Lovable (formerly GPT Engineer) is a tool that generates an app from a description. It's similar to Claude Code, but it works through a web interface, with no terminal. You describe the app in a chat, Lovable builds the interface and the logic, and it comes with a built-in backend, Lovable Cloud (a database, sign-up and log-in), plus publishing.

**About client data.** Since September 9, 2026, Lovable may use data from its Free and Pro plans (prompts, files, code) to train its models. You can opt out at any time: Account settings → Preferences → AI model training, then turn off "Use my Lovable content for model training." For client projects, turn it off right away. On the Business and Enterprise plans, data is excluded from training by default.

**Lovable vs Claude Code.** Lovable is easier to start with: there's nothing to install. Claude Code is more flexible and more capable: it works with any tech stack and any cloud, and it gives you full control over the code. For a beginner who needs an MVP fast, Lovable. For a serious product that's meant to last, Claude Code.

**Hybrid.** Some developers use Lovable for a quick prototype, then export the code and keep refining it with Claude Code. That approach works well.

---

### Bolt.new: StackBlitz AI in the browser

**What it is.** Bolt.new from StackBlitz is an app generator that runs right in your browser. You don't need to install anything: everything runs in the cloud. You write a prompt and get a working project with a frontend and a backend. Hosting, a database and domains are part of the service itself (Bolt Cloud): a free address on bolt.host, your own domain on paid plans.

**Strengths.** Bolt is very fast for simple jobs: a landing page, a contact form, a simple dashboard. Because it's built on StackBlitz, the code runs right in the browser, so you can show the client the result right away, without a separate deploy.

**Limitations.** Complex business logic and connections to unusual services require either moving to Claude Code or a lot of manual edits.

---

### When to use no-code vs Claude Code

| Criterion | No-code (v0/Framer/Webflow) | Claude Code |
|---|---|---|
| **Time to launch** | hours | days |
| **Customization** | Medium | Full |
| **Cost of the tools** | depends on each service's plans | a Claude subscription (Pro and up) or pay-per-token through the API |
| **Hosting** | Included in the plan or paid separately | You handle it (Cloudflare, Vercel) |
| **Standard jobs** | ✅ Excellent | Overkill |
| **Custom logic** | ❌ Hard or impossible | ✅ Full control |
| **Scaling** | Limited by the plan | Depends on your hosting |
| **Long-term maintenance** | You depend on the platform | Full control |
| **API integrations** | Through plugins or Zapier (a platform that connects different apps to each other) | Any of them, natively |
| **Best for** | Landing pages, MVPs, small businesses | SaaS, complex products |

**Rule of thumb:** if the project is standard (a landing page, a simple business site, a basic catalog) and doesn't need custom logic, go no-code. If it has a customer account area, integrations or unusual requirements, go hybrid or pure Claude Code. Current prices and versions: [What's current](https://aimayak.com/en/now/).

---

### The hybrid approach: a no-code UI + a Claude Code backend

🎨 **Picture this:** restaurants often buy prepared basics like dough and sauces, but the final cooking is up to the chef. No-code tools are the prepared basics of the interface. Claude Code is the chef who brings the dish up to restaurant quality.

**The workflow of a hybrid project:**

```
[STAGE 1: Design (v0 / Framer)]
Prompt → UI components / landing page
Iterate → final design approved
↓
[STAGE 2: Customization (Claude Code)]
Paste in the code from v0
Connect APIs (Stripe, Slack, a CRM)
Add user log-in
Add form validation
Set up the business logic
↓
[STAGE 3: Deploy (Cloudflare / Vercel)]
One command through Claude Code
CDN and SSL (a secure connection): set up automatically
Your own domain: in the hosting settings
↓
[HANDOFF TO THE CLIENT]
Training (15 min): how to edit the content
Support: 1 month, per the contract
```

---

### The "builder for hire" business model

This is a concrete niche for the more business-minded people taking this course. You're not a developer and you're not a designer: you're an expert at putting things together. You know which tool fits which job, you can assemble a result quickly, and you charge for speed and expertise.

**What you can offer:**

- A landing page (Framer + customization)
- A company website with a CMS (Webflow)
- An app MVP (Bubble, or a hybrid with Claude Code)
- A redesign of an existing site (components from v0 + Claude Code)

**Why clients pay.** They could try Framer themselves, but they'd spend time learning it and on revisions. You do it faster. The difference in price is their time multiplied by their hourly rate. Prices are set by the market and by your own costs; income isn't guaranteed. To work out your price, see the lesson [How to price AI services](39-monetization-pricing.md).

**How to find clients.** Small businesses with no website, or with an outdated one, are everywhere: local restaurants, hair salons, law offices, medical practices, tailors, travel agencies. They don't need a complex product. They need a decent website with a contact form at a reasonable price.

---

## Practice

### Exercise: build a landing page with v0 + Claude Code

**Scenario:** a client asks you to build a landing page for an online English school for adult learners. They need a hero section (the first screen a visitor sees), the benefits, pricing plans, and a sign-up form that sends each request to the school's Slack channel.

**When to do it.** Step 1 happens in v0 only, so you can do it now. Steps 2-5 happen in Claude Code: it comes with a paid subscription (the lesson [Claude Code pricing](05c-access-levels-pricing.md)), and the lesson [Claude Code desktop](05b-claude-code-desktop.md) helps you install it. Both lessons come later in this module, so come back to steps 2-5 after them. For now you can publish the page straight from v0 with the Publish button; that's enough for a practice run.

**Time to set aside:** about 35 minutes for the steps themselves, plus time to sign up for v0 and Vercel and to set up the Slack webhook.

---

**Step 1: Generate the design in v0 (10 minutes)**

Go to [v0.app](https://v0.app), sign in (signing up is free) and enter this prompt. The free plan limits how many messages you can send per day, so batch your edits into one message when you can.

```
Create a landing page for an online English school for adults. Style: modern,
professional, blue color scheme. Sections:
1. Hero: the headline "Start speaking English in 3 months", a subheadline,
   and a "Book a trial lesson" button
2. Three benefits: live lessons, a flexible schedule, a certificate
3. Pricing: Basic ($49/month), Standard ($89/month), Premium ($149/month),
   shown as cards with features and a button
4. Sign-up form: name, email, phone, preferred time, a submit button
Use Tailwind CSS; the component should be in React.
Put all of the page's code in one file, app/page.tsx, with no separate components.
```

Iterate if you need to ("make the hero section taller," "show the pricing side by side," "add icons to the benefits"). When you're happy with the final version, open the **Code** tab in the preview toolbar, select the file app/page.tsx and copy all of its text.

---

**Step 2: Set up the project in Claude Code (5 minutes)**

A Next.js project needs Node.js on your computer (the software that runs projects like this; you download it from nodejs.org). If it's missing, Claude Code will tell you; ask it to walk you through installing it.

Create an empty folder called english-school-landing, in Finder or File Explorer or with these commands in the terminal:

```bash
# In the terminal:
mkdir english-school-landing
cd english-school-landing
```

Open this folder in Claude Code (in the desktop app: the Code tab → Select folder) and type:

```
Create a new Next.js project with Tailwind CSS.
Structure: app/page.tsx for the home page.
Install the dependencies and check that everything runs.
```

---

**Step 3: Paste in the code from v0 (5 minutes)**

Tell Claude Code:

```
Here's a React component I generated in v0.
Put it in app/page.tsx and make sure all the imports are correct,
Tailwind works, and the component renders without errors.

[paste the code from v0 here]
```

Claude Code will sort out the imports, fix any conflicts and start the project. If something is missing, it will tell you what to install.

---

**Step 4: Send sign-ups to Slack (10 minutes)**

An incoming webhook is a private link that posts whatever is sent to it into one Slack channel; Slack's help pages show how to create one. Treat the link as a secret: don't paste it into a chat with AI or share it publicly.

```
Add handling for the sign-up form. When a visitor clicks "Book a trial lesson",
the data should be sent to our Slack channel through an incoming webhook.

I'll add the webhook URL myself: create a .env.local file
with an empty SLACK_WEBHOOK_URL variable and tell me where to paste it.

Message format in Slack:
🎓 New trial lesson request
Name: {name}
Email: {email}
Phone: {phone}
Preferred time: {time}

Add:
1. An API route app/api/contact/route.ts to handle the form
2. Field validation (name at least 2 letters, a valid email, a phone number)
3. A loading state on the button
4. A success / error message for the visitor
5. An environment variable for the webhook URL
```

The sign-ups contain people's names and phone numbers: handle them with care, and let the client know the form sends this data to Slack.

---

**Step 5: Deploy to Vercel (5 minutes)**

You'll need a free Vercel account. The first time you deploy, Vercel asks you to log in; you do that yourself, in the browser.

```
Get the project ready to deploy on Vercel:
1. Create a .env.example with the required variables
2. Add a vercel.json if any special settings are needed
3. Make sure .gitignore ignores .env
4. Initialize git and make the first commit

Then deploy with the command: npx vercel --prod
```

The .env.local file doesn't go to Vercel, so add the webhook URL in your project's settings on Vercel (Settings → Environment Variables), or ask Claude Code to help with that. Without it, the form on the live site won't send anything.

After the deploy, Claude Code will show you the URL. Send it to the client for approval.

**About free plans.** Vercel's Hobby plan is only for personal, non-commercial projects. For a client's (commercial) site you need a paid Vercel plan (Pro, from $20/month per developer as of October 2026; see [What's current](https://aimayak.com/en/now/)) or a different host, such as Cloudflare Pages.

---

## Tools and resources

| Tool | What it's for | Price | Link |
|---|---|---|---|
| **v0** | React interfaces and apps from a prompt | Free plan available; paid plans run on credits | v0.app |
| **Webflow** | Visual site editor with AI features | Free Starter plan (a webflow.io address); your own domain on a paid Site plan | webflow.com |
| **Framer** | Landing pages and animations from a prompt | Free plan available; your own domain on a paid plan | framer.com |
| **Bubble.io** | Full-stack web apps without code | Free plan for building; paid plans to launch | bubble.io |
| **Lovable** | AI app building for non-coders | Free plan with a credit limit | lovable.dev |
| **Bolt.new** | Apps in the browser, from StackBlitz | Free plan with limits | bolt.new |
| **Vercel** | Next.js deploys, custom domains | Hobby (non-commercial) is free; Pro for business | vercel.com |
| **Zapier / Make** | Connecting no-code tools to each other | Free plans with limits | zapier.com / make.com |

**A low-cost starter kit for a builder for hire:**

- v0 (free plan) + Claude Code (included in a paid Claude subscription, not available on the free plan) + Cloudflare Pages or Vercel + Framer (free plan)
- For client (commercial) projects, free plans often won't do: read the terms of each service

---

## Key takeaways

> "No-code AI isn't about fooling the client. It's about getting them a result faster. The tool doesn't matter; the result and the speed do."

> "The v0 + Claude Code hybrid is the best of both worlds: a good-looking interface without the busywork, plus complete freedom in the logic, with no platform limits."

> "Your first real project will teach you more than 10 lessons of theory. Find a small business near you, offer to build them a landing page, and get started whenever you're ready."

---

## Next lesson

→ [Zapier AI](79-zapier-ai.md): thousands of apps and smart Zaps with AI, your first automation without code

In the library, optional: [n8n + AI](78-n8n-ai-workflows.md): how n8n (a Zapier alternative you can run on your own server) becomes an AI orchestrator, connecting the Claude API to real business processes in "trigger → AI → action" chains without server code.
