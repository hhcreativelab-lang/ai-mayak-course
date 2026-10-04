# No-code AI for non-programmers: v0, Webflow, Framer

**Time:** about 25 min reading + 35 min practice

---

## The gist

🎨 **Picture this:** imagine working with an architect without needing a drafter. You describe what you want in words, "a three-bedroom house with floor-to-ceiling windows and a heated garage," and 30 seconds later a finished design is sitting in front of you. You never picked up a pencil, you don't know the building code, and the house still comes out looking professional. That's how no-code AI tools work: you describe what you want, and they build it. Claude Code, in this picture, is the general contractor you call in when you need custom wiring or plumbing that the standard plan didn't account for.

This lesson is about building websites and apps for yourself and for clients without writing a single line of code by hand. It's also about when no-code is enough, and when it's time to bring in Claude.

---

## Key concepts

- **No-code AI** (building software without writing code): tools that generate an app's interface, content and logic from a plain-language text description
- **v0** (v0.app, formerly v0.dev): a Vercel service that builds React interfaces and apps from a prompt (your request to the AI); you can copy the code it produces straight into Claude Code
- **Webflow AI**: AI built into Webflow that generates text, images and CMS content without you leaving the editor
- **Framer AI**: creates a landing page from a single sentence, automatically adapted for phones and tablets
- **The hybrid approach**: v0 or Framer generates the visual part, and Claude Code adds the business logic, the API integrations (an API, or application programming interface, is how programs talk to each other) and the database
- **The "builder for hire" niche**: a service where you take orders for websites, build them quickly with the tools from this lesson, and hand them over to the client as a finished product
- **Speed vs flexibility**: no-code is faster for standard jobs; Claude Code is irreplaceable for custom logic and long-term growth
- **Lovable and Bolt.new**: Claude Code's competitors for non-coders. They generate full-stack apps from a description, but there's a ceiling on how far you can customize them

---

## Theory

### Why no-code AI became a professional tool

"Building a site without code" used to mean a Squarespace or Wix template with fixed blocks and limited animation. Today, no-code AI tools generate production-ready React components, make the layout adapt to every screen size, set up CMS fields and deploy to a CDN (content delivery network). The gap between "I made it myself" and "I hired a developer" has shrunk so much that a business owner with no technical background can quickly put together a simple site that used to take a team weeks.

That creates a concrete business opportunity: becoming a "builder for hire," someone who knows these tools better than the client and gets paid for expertise in choosing the right set of tools and for speed of delivery, not for writing code.

---

### v0 (Vercel): from text to a React interface

**What it is.** v0 (at v0.app, formerly v0.dev) is a service from Vercel, the company behind Next.js. It's now an agent that builds interfaces and full-stack apps. You write a prompt ("make a product card with an image, a price, an add-to-cart button and a discount badge") and get ready-made React code with Tailwind CSS and shadcn/ui. There's a free plan; paid plans run on credits based on token usage (terms at [v0.app/pricing](https://v0.app/pricing)).

**How it works.** v0 understands not just "a button" but "a Stripe-style button with a hover effect and a loading state." The output is regular React/Next.js code that you copy into your project; it usually needs a little fine-tuning to fit.

**The standout feature for the hybrid approach.** You paste the generated code into Claude Code and say: "connect this component to my /products/:id API, add skeleton loading and error handling." Claude Code writes the logic on top of v0's visuals.

**A practical workflow:**

1. Describe the screen or component you need in v0
2. Iterate with prompts ("make the headline bigger," "add a dark mode")
3. Copy the final code
4. Paste it into Claude Code and describe the business logic
5. Claude Code connects the data, adds validation and deploys

🎨 **Picture this:** v0 is a designer who sketches a layout in 30 seconds. Claude Code is the developer who takes the sketch and turns it into a working product. You're the manager who gives both of them their assignments.

---

### Webflow AI: content and CMS without the busywork

**What it is.** Webflow is a visual website editor with its own built-in hosting. Webflow has AI features: generating text right in the editor, help with CMS content, translating the site. The feature set and the plans change, so check the current details on Webflow's site.

**AI in the CMS.** You create a CMS collection called "Services" with three fields: name, description, price. You turn on an AI field for "description," and Webflow writes the description itself based on the name and the context of the site. For an agency with 50 services, that saves a copywriter days of work.

**Localization in Webflow.** Built-in translation of the site into several languages: click a button and get, say, Spanish and French versions of your English site. For international clients this saves translation time, but machine translation still needs a human read-through.

**Limitations.** Webflow usually costs more than Framer: you pay for both a site plan and a workspace plan. For clients with a simple site, that can be overkill. But for businesses with a blog, a team and regularly updated content, it's a great fit.

---

### Framer AI: a landing page from one prompt

**What it is.** Framer is a design tool that has learned to generate complete landing pages from a text description. You write: "A landing page for a yoga studio in Austin. Modern minimalist style, warm tones, sections: hero, about us, class schedule, reviews, book a trial class," and shortly after you get a finished page with copy, images and a layout that adapts to any screen.

**Strengths.** Framer has long been known for beautiful animations that are hard to recreate in Webflow without knowing code. The AI keeps that level of visual quality. On the free plan, your site is published on a Framer subdomain; connecting your own domain takes a paid plan (terms on Framer's site).

**Framer vs Webflow.** Framer is usually faster at generating pages and better-looking out of the box. Webflow wins on CMS features and on scaling to large sites. For a landing page for a single product, use Framer. For a company site with a catalog, use Webflow.

**Limitation.** Framer is first and foremost a tool for websites and marketing pages, not for complex web apps. If the client wants a customer account area or a CRM integration, you need Webflow or a hybrid with Claude Code.

---

### Bubble.io + AI plugins: full web apps

**What it is.** Bubble is one of the most capable no-code tools for building full web apps: with a database, user accounts, logic and payment integrations. Add AI features or connect models through an API (OpenAI, Claude), and the app can read, summarize and write on its own.

**Typical Bubble projects.** Marketplaces (like Airbnb, without code), SaaS dashboards, online course platforms, CRMs for small businesses. All of it without writing server code.

**Bubble + the Claude API.** Through a plugin or direct API calls, you connect Claude (an LLM, a large language model). For example: a user uploads a document → Bubble sends the text to the Claude API → Claude returns a summary → Bubble saves it to the database and shows it to the user. That's a working AI product without a single line of server code.

**The downside of Bubble.** A steep learning curve: you won't master the basics in one evening. You need a paid plan to launch, and the price depends on how much load your app puts on the platform (plans on Bubble's site). Performance is lower than with hand-written code. It's great for an MVP and low traffic; a startup that's growing will eventually need to migrate to code.

---

### Lovable: Claude Code's competitor for non-programmers

**What it is.** Lovable (formerly GPT Engineer) is a tool that generates an app from a description. It's similar to Claude Code, but it works through a web interface, with no terminal. You describe the app in a chat, Lovable builds the interface and the logic, and it comes with a built-in backend, Lovable Cloud (a database, sign-up and log-in), plus publishing.

**About client data.** On some Lovable plans, your project data may be used to train models unless you turn on the opt-out setting ("Data collection opt out"). Check the current terms on Lovable's site, and for client projects, turn the opt-out on right away.

**Lovable vs Claude Code.** Lovable is easier to start with: there's nothing to install. Claude Code is more flexible and more capable: it works with any tech stack and any cloud, and it gives you full control over the code. For a beginner who needs an MVP fast, Lovable. For a serious product that's meant to last, Claude Code.

**Hybrid.** Some developers use Lovable for a quick prototype, then export the code and keep refining it with Claude Code. That approach works well.

---

### Bolt.new: StackBlitz AI in the browser

**What it is.** Bolt.new from StackBlitz is an app generator that runs right in your browser. You don't need to install anything: everything runs in the cloud. You write a prompt and get a working project with a frontend and a backend. Hosting and domains are part of the service itself (Bolt Cloud): a free address on bolt.host, your own domain on paid plans.

**Strengths.** Bolt is very fast for simple jobs: a landing page, a contact form, a simple dashboard. Because it's built on StackBlitz, the code runs right in the browser, so you can show the client the result right away, without a separate deploy.

**Limitations.** Complex business logic, custom integrations, working with databases: all of that requires either moving to Claude Code or a lot of manual edits.

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
| **Scaling** | Limited by the plan | Unlimited |
| **Long-term maintenance** | You depend on the platform | Full control |
| **API integrations** | Through plugins or Zapier (a platform that connects different apps to each other) | Any of them, natively |
| **Best for** | Landing pages, MVPs, small businesses | SaaS, complex products |

**Rule of thumb:** if the project is standard (a landing page, a simple business site, a basic catalog) and doesn't need custom logic, go no-code. If it has a customer account area, integrations or unusual requirements, go hybrid or pure Claude Code. Current prices and versions: [What's current](https://aimayak.com/now/).

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
CDN, SSL, custom domain: set up automatically
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

**Why clients pay.** They could try Framer themselves, but they'd spend a week learning it and another week on revisions. You do it faster. The difference in price is their time multiplied by their hourly rate. Prices are set by the market and by your own costs; income isn't guaranteed. To work out your price, see the lesson [How to price AI services](39-monetization-pricing.md).

**How to find clients.** Small businesses with no website, or with an outdated one, are everywhere: local restaurants, hair salons, law offices, medical practices, tailors, travel agencies. They don't need a complex product. They need a decent website with a contact form at a reasonable price.

---

## Practice

### Exercise: build a landing page in 35 minutes with v0 + Claude Code

**Scenario:** a client asks you to build a landing page for an online English school for adult learners. They need a hero section, the benefits, pricing plans, and a sign-up form that sends each request to the school's Slack channel.

---

**Step 1: Generate the design in v0 (10 minutes)**

Go to [v0.app](https://v0.app) and enter this prompt:

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
```

Iterate if you need to ("make the hero section taller," "show the pricing side by side," "add icons to the benefits"). When you're happy with the final version, copy all of the code.

---

**Step 2: Set up the project in Claude Code (5 minutes)**

```bash
# In the terminal:
mkdir english-school-landing
cd english-school-landing
```

Open Claude Code in this folder and type:

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

Claude Code will sort out the imports, fix any conflicts and start the project.

---

**Step 4: Send sign-ups to Slack (10 minutes)**

An incoming webhook is a private link that posts whatever is sent to it into one Slack channel; Slack's help pages show how to create one.

```
Add handling for the sign-up form. When a visitor clicks "Book a trial lesson",
the data should be sent to our Slack channel through an incoming webhook.

My Slack incoming webhook URL: [your webhook URL]

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

---

**Step 5: Deploy to Vercel (5 minutes)**

```
Get the project ready to deploy on Vercel:
1. Create a .env.example with the required variables
2. Add a vercel.json if any special settings are needed
3. Make sure .gitignore ignores .env
4. Initialize git and make the first commit

Then deploy with the command: npx vercel --prod
```

After the deploy, Claude Code will show you the URL. Send it to the client for approval.

**About free plans.** Vercel's Hobby plan is only for personal, non-commercial projects. For a client's (commercial) site you need a paid Vercel plan (Pro, from $20/month per developer as of October 2026; see [What's current](https://aimayak.com/now/)) or a different host, such as Cloudflare Pages.

---

## Tools and resources

| Tool | What it's for | Price | Link |
|---|---|---|---|
| **v0** | React interfaces and apps from a prompt | Free plan available; paid plans run on credits | v0.app |
| **Webflow** | Visual site editor with AI content | Paid site and workspace plans; prices on the site | webflow.com |
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

> "No-code AI isn't about fooling the client. It's about giving them a result in 2 days instead of 3 weeks. The tool doesn't matter; the result and the speed do."

> "The v0 + Claude Code hybrid is the best of both worlds: a good-looking interface without the busywork, plus complete freedom in the logic, with no platform limits."

> "Your first real project will teach you more than 10 lessons of theory. Find a small business near you, offer to build them a landing page, and get started whenever you're ready."

---

## Next lesson

→ [n8n + AI](78-n8n-ai-workflows.md): smart workflows with LLM nodes

We'll look at how n8n (a Zapier alternative you can run on your own server) becomes a capable AI orchestrator: we'll connect the Claude API to real business processes and build "trigger → AI → action" chains without a single line of server code.
