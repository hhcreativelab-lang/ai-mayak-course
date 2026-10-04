# The history of AI: from Turing to Claude, and why now

**Time:** about 40 min reading + 15 min practice

> *Imagine you're standing by a lighthouse on a foggy night. You know the lighthouse was shining yesterday, and the day before, and ten years ago. But tonight something has changed: the light is so bright you could see it from another continent. That's what happened to AI (artificial intelligence) between 2022 and 2026. The technology had been around for decades. But something happened, and suddenly the light was visible to everyone.*

---

## The gist

AI has been developing for more than 70 years. It has lived through two long stretches of disappointment, and today we're in a third wave. This wave is different from the earlier ones because AI is now cheap, easy to access, and able to act on its own. To use AI tools with confidence, it helps to understand where all of this came from and why the moment is happening now.

## Key ideas

- AI isn't magic and it isn't conscious. It's math trained on enormous amounts of human-written text
- The history of AI is a history of waves: a rise → inflated expectations → disappointment → a breakthrough
- The Transformer (a breakthrough neural network architecture, 2017) + ChatGPT (2022) = the point of no return
- The turning point isn't happening because AI got "smarter." It's happening because AI became cheap, accessible and autonomous

---

## Theory

### Part 1: What AI even is

Before we get into the history, let's agree on our terms.

In everyday conversation, AI (artificial intelligence) means different things to different people. To a Hollywood director, it's the Terminator. To a scientist, it's mathematical models. To a business owner, it's a tool that takes over part of the work.

In this course we use a practical definition:

**AI is a program trained on a huge amount of human text, code and knowledge that can answer questions, write, analyze data and carry out tasks, much the way a well-trained human assistant would.**

Picture this: you've gathered the best specialists in the world in one room (writers, programmers, lawyers, doctors, designers), and every one of them is ready to answer your question at the same time. That's roughly what modern AI is. Not because it "thinks" like a person, but because it was trained on billions of texts written by people like them.

**An important distinction people often get wrong:**

AI isn't conscious. AI doesn't "think" in the human sense of the word. AI is a mirror of the human mind. It doesn't create meaning; it reflects patterns (regularities, structures that repeat) from an enormous body of human knowledge.

That doesn't make it any less valuable. A mirror that can write code, analyze business plans and answer questions around the clock is a tool that can change how a business works.

---

### Part 2: 1950: Alan Turing asks the big question

It all starts with one question, asked in 1950.

**Alan Turing** was a British mathematician, logician and codebreaker. In 1936 he came up with the idea of a universal computing machine, what we now call a computer. During World War II he played a central role in cracking the German Enigma cipher, which, by historians' estimates, shortened the war by 2 to 4 years. One person, a few mathematical insights, and history changed.

In 1950 Turing published a paper called "Computing Machinery and Intelligence." Its first line became legendary:

> *"I propose to consider the question, 'Can machines think?'"*

To answer that question, Turing proposed an experiment: the Turing Test.

**Picture the Turing Test:** an examiner sits alone in a separate room and can't see who's on the other end. They type questions into a terminal and get answers back, either from a person or from a machine. If the examiner can't tell which one is the human, the machine has passed the test.

In 1950, no computer could come anywhere close to passing this test. All Turing had was the question. But the question turned out to be so deep that it set the direction of an entire field of science for more than 70 years.

Turing died in 1954 at the age of 41. He didn't live to see any of the revolutions his ideas set off. But without his question there would be no neural networks, no ChatGPT and no Claude.

---

### Part 3: 1956: The Dartmouth Conference and the birth of a name

Six years after Turing's paper, in the summer of 1956, an event took place in the small town of Hanover, New Hampshire, that gave all of this its name.

**The Dartmouth Conference** was the first conference in history devoted specifically to artificial intelligence. It was organized by **John McCarthy**, a young mathematician at Dartmouth College.

It was McCarthy who came up with the term "artificial intelligence" and used it for the first time. Before that, scientists talked about "machine thinking," "cybernetics" (the science of control and communication in systems) and "automata." McCarthy gave the new field a precise name.

The conference brought together about 10 scientists. They planned to solve the main problems of building thinking machines in a single summer. The enthusiasm was enormous.

**Picture the moment:** it was like the early days of aviation at the start of the 20th century. The Wright brothers had just flown, and engineers around the world were sure that within 20 years everyone would be getting around in their own personal aircraft. Reality turned out to be more complicated, but the direction was right.

In the 1950s and '60s, AI researchers believed that full human-level AI would arrive within 20 years. It was a sincere belief, based on what they were seeing: the first computers could calculate, play chess and translate simple sentences. It felt like just the beginning.

They got the timing wrong. But they set in motion a process that eventually led to exactly what they had dreamed of.

---

### Part 4: AI winter: why progress stalled twice

The history of AI isn't a straight line going up. It moves in waves.

**AI winter** is the term for the periods when excitement about AI suddenly turned into disappointment, funding was cut, and progress nearly stopped.

There were two of these "winters."

**The first AI winter: 1974 to 1980**

In the early 1970s it became clear that the computers of the day were far too weak for such ambitious goals. Early AI programs could play chess at a basic level, solve algebra equations and imitate a simple conversation. But scaling up didn't work: the harder the problem, the worse the algorithms did.

In 1973 the British government commissioned a report on the state of AI research. The **Lighthill Report** was scathing: researchers had promised too much and delivered too little. Funding in the UK was almost completely shut off.

The US agency DARPA (the Defense Advanced Research Projects Agency) cut its grants too. A period began that historians would later call the first AI winter.

**The second AI winter: 1987 to 1993**

In the 1980s AI found a new direction: expert systems. The idea seemed brilliant: write down the knowledge of the best specialists as a set of rules, and the computer would give the same advice they would.

The XCON system, which configured computers for DEC (Digital Equipment Corporation), saved the company $25 million a year. The medical system MYCIN made diagnoses better than many doctors. It looked as though expert systems were the way forward.

But then it turned out that these systems cost millions of dollars to build and maintain. They couldn't learn: every new rule had to be written by hand. They broke down in unusual situations. They couldn't scale.

In 1987 the market for AI computers collapsed almost overnight. The second winter began.

**Picture the two winters:** waves on a beach. Every wave rolls back, and it looks as if nothing happened. But each new wave reaches a little farther up the sand. The AI winters didn't wipe out progress. They weeded out ideas that weren't ready yet and bought time to build up strength for the next breakthrough.

---

### Part 5: 1986 to 1989: Neural networks come back

While some researchers were building expert systems, others kept working on an idea inspired by biology.

A **neural network** is a mathematical model inspired by the structure of the human brain. The idea is simple: the brain has billions of neurons (nerve cells) connected to one another. When a neuron receives enough signals, it fires and passes a signal along. Thinking is patterns of activity across this network.

Can you build something like that with math? Yes. An artificial neuron is just a number. A network of such numbers is a model. When the model sees data, it adjusts its weights (the numbers that set how strongly the neurons are connected) so that it gives the right answers.

**Machine learning** is exactly this tuning process: the computer learns from examples instead of from rules someone wrote out by hand.

The key learning algorithm is **backpropagation** (short for "backward propagation of errors"). The network makes a prediction, compares it with the right answer, calculates the error, and then sends information about that error backward through the network, adjusting each weight a little at a time.

**Geoffrey Hinton** is a Canadian scientist and one of the three "founding fathers" of modern neural networks. In 1986, together with colleagues, he published a key paper on backpropagation that showed how to train networks with many layers (in 2024 Hinton received the Nobel Prize in Physics for his work on neural networks). The other two founders are **Yann LeCun**, who created convolutional neural networks for recognizing images, and **Yoshua Bengio**, who helped systematize the approaches to deep learning. In 2018 all three received the Turing Award, the most prestigious award in computer science.

**Picture a neural network:** it's like training your muscles. When you learn to ride a bike, you fall, your brain adjusts the commands it sends to your muscles, and you try again. With each attempt, the connections in your brain get tuned more precisely. A neural network does the same thing, except that instead of falling off a bike, it calculates its errors mathematically.

But in the late 1980s neural networks were still too small, and there wasn't enough computing power. They had to wait.

---

### Part 6: 2012: The deep learning breakthrough

The breakthrough didn't come from a new theory. It came from two things: big data and powerful GPUs.

**Deep learning** is machine learning with neural networks that have many layers. "Deep" means many-layered. The more layers, the more complex the patterns a network can learn. The first layer notices simple lines. The second, geometric shapes. The third, parts of objects. The fourth, the objects themselves.

Every year starting in 2010, a contest called **ImageNet** was held: a competition in image recognition. The task: show a program a photo, and it has to say what's in it. The database: 1.2 million photos in 1,000 categories.

In 2012 Geoffrey Hinton's team entered the contest with a program called **AlexNet**, named after Hinton's student Alex Krizhevsky. AlexNet's error rate: 15.3%. The best previous result: 26.2%. A huge gap.

What did Hinton have that the others didn't? **GPUs (graphics processing units)**. Graphics cards built for video games turned out, almost by accident, to be ideal for training neural networks: they can run millions of calculations in parallel. Hinton's team used two consumer Nvidia GTX 580 graphics cards, and that turned out to be enough to start a revolution.

**Picture what GPUs did for AI:** think of the steam engine in the Industrial Revolution. Looms had existed for centuries. The steam engine gave them power they'd never had before, and work done by hand became work done by machines. The GPU gave neural networks the computing power they had been missing.

After 2012, deep learning took over everything. Image recognition. Speech recognition. Translation. Playing Go and chess. Spotting cancer on medical scans. It seemed neural networks could do anything, as long as you gave them enough data and computing power.

But there was one thing they still couldn't do: hold a conversation.

---

### Part 7: 2017: Transformers change everything

In 2017 a group of Google researchers published a paper with a simple title:

**"Attention Is All You Need"**

This paper changed the history of AI the way the steam engine changed the history of industry.

The authors proposed a new neural network architecture: the **Transformer**. Before transformers, language models (programs that work with text) processed text sequentially: word by word, left to right, the way you're reading this right now. That worked, but it was slow and ran into trouble with long texts.

The transformer uses an **attention mechanism**: the ability to "look at" all the words in a text at once and figure out which of them matter for understanding each particular word.

**Picture this:** a translator is translating the sentence "The bank raised the interest rate on my loan" into Spanish. A bad translator handles the word "bank" without knowing what comes next and might pick the Spanish word for a riverbank. A good translator reads the whole sentence first and understands from the context ("interest rate," "loan") that this is the kind of bank that handles money. The attention mechanism does the same thing: before it handles each word, the transformer "looks at" the whole sentence.

Transformers turned out to be ideal for language. They learn quickly from huge amounts of text. They scale well: the more parameters (a parameter is an adjustable number inside a neural network, the same idea as a "weight"), the smarter the model. And they can work in parallel, which makes training dozens of times faster.

An **LLM (large language model)** is exactly this: a neural network built on the transformer architecture and trained on an enormous body of text. The first "L," for Large, is the key part. Large means billions or hundreds of billions of parameters.

All of today's AI assistants (ChatGPT, Claude, Gemini, Llama) are LLMs built on the transformer architecture. They're all descendants of that 2017 paper.

---

### Part 8: 2020: GPT-3 and the first shock

In June 2020 the company **OpenAI** released **GPT-3**.

GPT stands for Generative (it creates new content), Pre-trained (trained on a large body of text before anyone starts using it) and Transformer (the architecture).

The third version of GPT had 175 billion parameters. For comparison, the human brain has roughly 86 billion neurons. GPT-3 isn't smarter than a person, but the scale was already in the same range.

What could GPT-3 do? An incredible amount by 2020 standards. Write essays. Compose poems. Write working code. Answer questions. Translate. Imitate the style of famous authors. Solve math problems.

When researchers first got access to GPT-3 through its API (application programming interface, a way for programs to talk to each other), hundreds of amazed posts appeared online. People were doing things that had seemed impossible: AI was writing short stories, coming up with business plans, reasoning about philosophy.

**Picture this:** the first iPhone in 2007. Phones with internet and music had existed before. But the iPhone brought it all together, made it easy to use, and showed what the future could look like. GPT-3 was just like that: not perfect, often wrong, sometimes hallucinating (a hallucination is when AI confidently makes something up and presents it as fact). But it was clear the world was going to change.

---

### Part 9: 2022: ChatGPT and the mass explosion

Earlier AI breakthroughs were known only to scientists and tech people. November 30, 2022, changed that for good.

On that day OpenAI launched **ChatGPT**, a chat interface on top of the GPT-3.5 model. It was a chatbot that anyone with an internet connection could talk to, no technical knowledge needed.

The results beat every expectation:
- 1 million users in the first 5 days (Instagram took 75 days)
- 100 million users in about 2 months (by analysts' estimates at the time, the fastest-growing consumer app up to then)
- OpenAI's servers went down under the load several times

ChatGPT became the first AI tool to break out of tech circles and become a mass cultural phenomenon.

What made ChatGPT special, apart from the quality of the model? Two things:

**1. The interface.** Just a chat. Like texting a friend. No programming, no technical knowledge.

**2. RLHF (reinforcement learning from human feedback)**, a special training method. After the model is trained on text from the internet, human raters train it further. They show the model two possible answers and say which one is better. This makes AI not just smart but also easy to talk to: it answers the way a person expects.

**Picture this:** the first McDonald's in 1955. Hamburgers and French fries were sold in America long before that. But McDonald's came up with a system: a standard recipe, fast preparation, an affordable price, the same everywhere. AI existed before; ChatGPT made it available to everyone. That changed everything.

---

### Part 10: 2023 to 2024: The model race

After ChatGPT's success came a period the industry calls "the model race." Every few months a new, more powerful version came out.

**GPT-4** came out in March 2023. It's multimodal (able to work with different kinds of data): it understands not only text but also images. According to OpenAI, it scored in the top 10% of human test takers on the bar exam, and it passed the USMLE (the US medical licensing exam).

**Claude 1, 2 and 3**: a series of models from Anthropic. Each version was smarter than the one before. In 2024, Claude 3 Opus became one of the best AI assistants on many benchmarks (standard performance tests).

**Gemini**: Google's answer. The company that invented the transformer in 2017 took a long time to release a competing product. According to Google, Gemini Ultra beat the level of human experts on MMLU (Massive Multitask Language Understanding, a test of language understanding across many subjects).

**Llama**: a series of open-weight models (the numbers that make up the trained model are published) from Meta, the company behind Facebook and Instagram. Unlike GPT and Claude, Llama's weights are public. Anyone can download the model and run it on their own computer (under the terms of its license). That gave rise to a whole ecosystem of AI that runs locally, on your own machine.

**Picture this period:** something like the space race, except between companies and out in the open. Every major tech company poured billions of dollars into AI research. Google, Microsoft, Amazon, Meta and Apple all declared AI their top strategic priority.

The race hasn't ended: over 2025 and 2026 the Claude, ChatGPT, Gemini and other model lineups were replaced several times. For the current list, see the [What's current](https://aimayak.com/now/) page. In this lesson we're looking at the history, not at the latest version.

---

### Part 11: 2025 to 2026: Why this is the turning point

You've reached the most important section. Why now, and not in 2020, or 2022, or 2030?

Three signs set the current moment apart from all the earlier ones:

**Sign 1: AI is getting cheaper faster than it's getting more capable**

A token is the smallest unit of text that AI "processes." In English, a token is about 0.75 of a word. The API charges per million tokens.

In just a few years, the price of a model at the same level of quality has dropped several times over, while the top-tier models have become noticeably stronger. For example, Claude Opus 4.1 cost $15 per million input tokens, while Claude Opus 5.5 costs $4 as of October 2026 (current prices: [What's current](https://aimayak.com/now/)). That puts AI automation within reach of small businesses too. But the strongest models are still expensive, and the bill grows with how much you use, so work out the cost in advance.

**Sign 2: APIs are open to everyone**

Until 2023, using AI in a business meant hiring ML (machine learning) engineers and building expensive infrastructure (the technical foundation: servers, networks, storage). That took months and cost hundreds of thousands of dollars.

Now you sign up in Anthropic's developer console, get an API key (a unique code that gives you access to the service), write 10 lines of code, and you have working AI automation. One person can put together a simple version over a weekend.

**Sign 3: Agentic AI, or AI that acts instead of just answering**

This is the most important shift. Until 2024, AI was reactive: you asked, it answered. You made a request, it generated something. A powerful tool, but a limited one.

**Agentic AI** is AI that can plan tasks on its own, use tools (read files, send requests to services, write and run code) and carry out multi-step tasks without a person constantly watching over it.

**Reasoning models**, such as today's Claude models with a thinking mode (in the newer models, the model decides for itself how much to think, and you set the level of effort), can "think before they answer." They break a complex task into steps, check their own conclusions and adjust their approach. That makes them much more accurate on hard tasks: programming, analysis, strategic decisions.

And this is where **Claude Code** comes in, the tool this course is built around. Claude Code is Anthropic's coding agent. It's not just a chat with AI. It's an AI agent that can read your project, edit files, run commands, fix errors and deploy apps (put them live in production, where real users can reach them). It acts instead of only giving advice. As of October 2026 it works in the terminal, in VS Code and JetBrains, in the Claude desktop app, in the browser and on your phone.

**Picture the moment:** like the internet in 1995. The technology already existed: web browsers (programs for viewing web pages), email, the first websites. But most people didn't see why they needed it. A few people who got it early founded Amazon, Google, Yahoo; most people simply learned to use it over the following years, at their own pace. We're now in the early period of mass AI, and a lot is still taking shape.

---

### Part 12: Anthropic and Claude: who's behind it

This course is built around Claude and Claude Code. It's worth understanding what kind of company is behind them and why that matters.

**Anthropic** is an American AI company founded in 2021 in San Francisco.

How it started: most of Anthropic's founders previously worked at OpenAI. In 2021 **Dario Amodei**, then OpenAI's vice president of research, and his sister **Daniela Amodei**, then vice president of operations, decided to start a new company. Several key researchers left with them.

The main disagreement was about speed. The Amodeis felt OpenAI was moving too fast without paying enough attention to safety. Anthropic was founded with a different focus: "responsible AI development."

Anthropic developed a training method called **Constitutional AI**. Instead of only showing the model what's "good" and what's "bad" through human ratings, Constitutional AI gives the model a set of principles, a "constitution," and teaches it to judge its own answers against those principles. This makes Claude more consistent in following its values.

**Claude** is Anthropic's flagship family of models. According to a widely repeated account, it's named after Claude Shannon, the American mathematician who created information theory, the foundation of the entire digital world.

Why Claude, and Anthropic specifically, matter for this course:

1. Claude Code is Anthropic's official development tool, built to work natively with Claude
2. Anthropic has one of the strongest APIs in the industry for building agents
3. Anthropic puts an emphasis on honest and safe answers, and for reliable business processes it's important that a model can say "I don't know"

---

## Practice

Three exercises, light and practical:

### Exercise 1: Your first conversation with Claude

Open **claude.ai** in your browser. If you don't have an account, sign up; the basic plan is free. If Claude isn't available where you are, for example while you're traveling abroad (the list of supported countries is on [Anthropic's page](https://www.anthropic.com/supported-countries)), use any other AI assistant: you'll find options in the [Tools](https://aimayak.com/tools/) section.

Ask this:
```
Hi! I'm just starting to learn about AI.
In 3-4 sentences, tell me who Alan Turing was
and why he matters in the history of AI.
```

Look at the answer. Notice that Claude didn't read your question the way a person would. It generated the most likely answer based on patterns from the texts about Turing that were in its training data. The result reads like something written by a well-read person, because that's exactly the kind of text it was trained on.

### Exercise 2: Ask Claude to explain itself

Ask Claude this:
```
Are you a transformer? Explain how you work
for a complete beginner, using everyday images and analogies,
with no technical terms.
```

Compare its explanation with what you read in this lesson. Where do they match? What new things did Claude add?

### Exercise 3: Look it up (5 minutes)

Google "Dartmouth Conference 1956 AI". Find any article about it. Read 2 or 3 paragraphs.

A question to answer for yourself: what surprised you most about the history of AI in this lesson? Write it down in one sentence. That will help you hold on to your own "aha moment."

---

## Key takeaways

> **AI isn't magic.** It's math trained on human writing. A mirror that reflects patterns. A useful tool, as long as you understand how it works.

> **The history of AI is a story of waves.** Two rises, two letdowns, and now a third wave. None of the earlier waves was "fake": each one laid the foundation for the next.

> **2017 + 2022 = the point of no return.** Transformers provided the architecture; ChatGPT provided the access. After that, AI stopped being a lab experiment.

> **The turning point is happening now for three reasons:** AI is getting cheaper faster than it's getting more capable, APIs are available to everyone without specialized technical knowledge, and agentic AI has started acting on its own instead of only answering questions.

> **Anthropic and Claude are this course's choice** because Claude Code makes it easy to show agentic work in practice. The principles in this lesson apply to other assistants too.

---

## Further reading (if you're curious)

**Books worth reading:**
- *The Alignment Problem* by Brian Christian, on why AI safety is hard
- *Human Compatible* by Stuart Russell, on the future of AI from one of the leading scientists in the field

**Movies:**
- *The Imitation Game* (2014), a biopic about Alan Turing starring Benedict Cumberbatch. It takes liberties with the history, but it captures the atmosphere.
- *Ex Machina* (2014), about the Turing test. It does a good job of showing how psychologically tricky the question "can you trust AI?" really is.

**Articles:**
- "Attention Is All You Need" (2017), the original paper on transformers. The introduction and conclusion are readable even without a math background.
- The Anthropic blog (anthropic.com/research), on how the company thinks about safe AI

---

## Next lesson

**→ [How an LLM works inside](00b-how-llm-works.md): no math, just plain pictures**

In the next lesson we'll cover what a token really is, how exactly an LLM generates text word by word, what a model's "temperature" is and why the same question sometimes gets different answers, and what "200,000 tokens of context" means in practical terms.

---

*The history of AI | Updated: October 2026*
