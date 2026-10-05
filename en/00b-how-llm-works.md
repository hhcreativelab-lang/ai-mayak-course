# How an LLM works inside, explained without math

**Time:** about 35 min reading + 15 min practice

> You talk to Claude, and it answers in clear, natural, well-organized English. It seems to understand you. But what is actually going on inside? It isn't magic, and it isn't a "real mind." It's math working with small building blocks of text. Once you understand that, you'll start using AI more effectively.

---

## The gist

Most people use an LLM (Large Language Model) as a black box: you ask a question, you get an answer. That works. But knowing how the box works inside gives you practical advantages: you save money, you get better answers, and you understand why AI sometimes gets things wrong and how to work around it.

This lesson is an X-ray of a language model. No formulas. Just pictures.

---

## Key concepts

- Token: the smallest unit of text AI works with
- Pre-training: how a model learns from enormous amounts of text
- Embedding: how AI turns words into numbers and meaning
- Transformer and attention: the design that changed everything
- Context window: AI's memory within a single conversation
- Temperature: the dial for "creative randomness"
- Hallucination: why AI sometimes says false things with total confidence

---

## Theory

---

### 1. What a token is: the atoms of language

First things first: AI doesn't read words. It sees tokens, the smallest units of text AI works with (think of arcade tokens: small, standard pieces the machine counts one by one).

A token isn't a word. It's a chunk of text that the language model treats as one piece it can't split further. Sometimes a token is a whole word. Sometimes it's part of a word. Sometimes it's a single character.

**Examples (rough numbers: every model splits text its own way):**
- The word `cat` = 1 token (short and common)
- The word `catastrophe` can split into 3 tokens: `cat` + `ast` + `rophe`
- A long, rare word like `anthropomorphism` = several tokens
- Words in other languages often split into more pieces than English words do

An important detail: **English is the "cheapest" language in tokens.** Many other languages need noticeably more tokens to say the same thing (the exact ratio depends on the model and the text). That matters because tokens are what your chat limits are counted in, and what developers pay for in the API (the connection programs use to talk to AI).

A rough rule of thumb from Anthropic: **1,000 tokens ≈ 750 words** in English. The newest Claude models split text into smaller pieces, so for them 1,000 tokens hold closer to 555 words. Text in other languages usually takes more tokens for the same amount of meaning.

🎨 **Picture this:** a token is a Lego brick. AI doesn't see words as single objects. It sees bricks of different sizes that words are built from. The word "cat" is one brick. The word "catastrophe" is three: "cat," "ast" and "rophe." When AI writes text, it lays down brick after brick. Left to right. One at a time. Each new brick depends on all the ones before it.

**Why this matters in practice:**
- Usage is counted in tokens, not words: in the chat app, tokens use up your limit; in the API, developers pay for them. The shorter and more specific your prompt (your request to the AI), the less you use
- Long texts in other languages can use more tokens than the same text in English
- A tight prompt with no filler can noticeably cut usage without hurting quality

---

### 2. How AI learns: pre-training

How does Claude know what the word "cat" means? How does it know that "The sun is shining in the" is followed by "sky"? How does it know history, physics, programming?

The answer: pre-training (the first stage of training a language model).

Imagine the model's developers gathering a giant library of text. Not just big: unimaginably big. Encyclopedias in many languages, books, scientific papers, computer code, news, forums, legal documents. This is called a corpus (from the Latin word for "body": a large collection of text used for training).

Then the model trains on that corpus: trillions of tokens, months of computing on thousands of specialized chips.

**The training task is almost absurdly simple:** guess the next token.

Concretely: the model sees the text `"The Earth revolves around the"` and has to predict what comes next. The right answer: `"Sun"`. The model predicted `"stars"`: wrong. Adjust the parameters. Again. And again. Trillions of times.

Sounds primitive? But everything grows out of this one simple task. To get good at guessing the next word in a medical article, you have to understand medicine. To guess well in code, you have to understand the logic of programming. To guess well in poetry, you have to feel the rhythm.

🎨 **Picture this:** a kid who has read absolutely EVERY book in the world. Every newspaper, every textbook, every novel, every refrigerator manual. They didn't memorize any of it word for word; they absorbed the patterns. How a sentence is built. How facts connect. Which words tend to show up next to which. Claude went through this same process, only not over 18 years of childhood but in a few months, on trillions of tokens of text.

---

### 3. Embeddings: how AI sees meaning

A computer only understands numbers. So how does it work with text?

The answer: every token is turned into a vector of numbers.

An embedding (a word's position in a space made of numbers) is a way to turn any word into a list of numbers so that words with similar meanings end up with similar numbers.

A vector (an ordered list of numbers) for the word "cat" might look like `[0.32, -0.71, 0.15, 0.88, -0.03, ...]`: thousands of numbers in one list. The word "kitten" gets a very similar list. The word "banana" gets a completely different one.

These vectors live in a mathematical space with a huge number of dimensions. Words with similar meanings sit close together in that space. Words with different meanings sit far apart.

**A remarkable property of embeddings:** math on them actually makes sense.

There's a famous example: vector("king") - vector("man") + vector("woman") ≈ vector("queen"). Doing math on text gave the right answer about how the ideas relate. That's not a coincidence; it's how the space of meaning is organized.

🎨 **Picture this:** a huge map, but a map of meaning, not geography. Every word is a city on it. "Dallas" and "Houston" sit close together: both are big Texas cities. "Dallas" and "Tokyo" are far apart. "Cat" and "kitten" are neighboring towns. "Cat" and "quantum physics" are on different continents. Embeddings are the GPS coordinates of each word on this map of meaning. When AI processes text, it navigates this map and finds the relationships between ideas.

---

### 4. The transformer and the attention mechanism

In 2017, researchers at Google published a paper called "Attention Is All You Need." That paper changed the history of AI.

The transformer (a neural network architecture invented at Google in 2017) is the type of design that became the foundation of every modern language model: GPT, Claude, Gemini, Llama.

Before transformers, AI read text the way a person reads a dull book: left to right, word by word, forgetting the beginning by the time it reached the end. Long texts were hard for it.

The transformer solved this in a radical way: it sees the WHOLE text at once.

**The key mechanism is attention: the model's ability to take every part of the text into account while it processes each word.**

When a transformer processes the word "he" in a sentence, the attention mechanism asks: which other words in this text do I need to pay attention to in order to figure out who "he" is?

Example: `"The river bank was steep"` vs `"The bank approved a loan at 12%"`.

The word "bank" is the same. But in the first case, the attention mechanism notices the word "river" and understands: this is the edge of a river. In the second, it notices the word "loan" and understands: this is a financial institution. One word, two different meanings, told apart correctly by paying attention to context.

🎨 **Picture this:** the conductor of a symphony orchestra. In front of them sit 80 musicians. At every moment of the concert, the conductor hears all of them at once. But depending on the piece and the measure, they bring some players up (the violins matter more right now) and bring others down (the drums can wait). The attention mechanism is the conductor of the text. It hears every word at once and decides, moment by moment, which ones deserve the most attention right now.

---

### 5. The context window: AI's desk

The context window (the maximum amount of text AI can keep in view during one conversation) is probably the single most important setting in practice when you work with AI.

Everything inside the context window, AI "sees" and takes into account. Everything outside it doesn't exist for AI at that moment.

**Context window sizes (as of October 2026, for Claude in the API):**
- Claude Fable 5.1, Opus 5.5, Sonnet 5.5: **1,000,000 tokens** ≈ 555,000 English words (these models split text into smaller tokens than earlier ones did) ≈ 1,800 book pages
- Claude Haiku 4.5: 200,000 tokens ≈ 150,000 English words ≈ 500 pages

ChatGPT, Gemini and other assistants also have windows measured in hundreds of thousands or millions of tokens, but the exact numbers depend on the model and the plan: check the provider's documentation and the [What's current](https://aimayak.com/en/now/) page. In a regular app (for example, the chat at claude.ai), the amount available to you may differ from the API.

These are big numbers. But in real work, context gets used up faster than you'd think: the system prompt (the background instructions the app gives the model), the conversation history, uploaded documents and AI's own answers all take up room in the context window.

**What happens when the context fills up:**
Earlier parts of the conversation get "pushed out," and AI stops taking them into account. You'll notice it: AI "forgets" what was said at the start of a long chat. That isn't stupidity; it's a limit built into how the model works.

🎨 **Picture this:** a desk. Everything on the desk, you can see and grab right away. That's AI's context window. Whatever is in the drawer, you'd have to pull out (that's long-term memory, which basic AI doesn't have). Whatever you left at home is out of reach entirely. When the desk gets too full, old papers slide onto the floor and drop out of sight. A context window of hundreds of thousands of tokens, or a million, is a very big desk. But it still has edges.

**Practical takeaways:**
- A big context is convenient. But it costs more: in the API you pay for every token in the request, and in the chat app a long conversation uses up your limit faster
- For later, when you get to Claude Code (the coding agent near the end of the course): on long projects, its `/compact` command compresses the conversation history while keeping the essentials
- Organize your conversations: start a new chat for a new task instead of dragging everything into one

---

### 6. How AI generates an answer, step by step

You wrote: `"Explain quantum mechanics in plain English"`. What happens next?

**Step 1: Tokenization**
Your text gets split into tokens: "Explain," "quantum," "mechanics" and so on. Longer or rarer words can be split into several tokens.

**Step 2: Embeddings**
Each token is turned into a vector of numbers. Now your request exists as a set of points in a mathematical space.

**Step 3: The transformer processes it**
The attention mechanism goes over all the tokens, builds connections between them and works out the context. "Quantum" + "mechanics" + "in plain English": three parts, and each one matters for understanding the task.

**Step 4: Calculating probabilities**
The model looks at everything in the context and calculates: which next token is most likely? Not just one option, but a probability distribution across its whole vocabulary (tens of thousands of tokens). "Quantum": 12%, "Let's": 8%, "Imagine": 15%...

**Step 5: Sampling (choosing the next token from the probability distribution)**
The model picks a token. Exactly how it picks depends on temperature (more on that below).

**Step 6: Repeat**
The chosen token is added to the context. Steps 4 and 5 repeat for the next token. And again. And again, until the answer is complete.

🎨 **Picture this:** a jazz musician improvising on stage. They hear everything that's been played up to this moment: every instrument, the whole rhythm, the whole theme. Based on that, they choose the next note. Not at random, but not from a fixed script either. Each note grows out of everything that came before. Each token in Claude's answer is a "note" born from the whole context. That's why AI can't "go back and fix" the beginning of its answer: it only plays forward, one note at a time.

---

### 7. Temperature: the randomness dial

Temperature (a setting that controls how much "randomness" goes into choosing the next token; the range differs between services, most often 0 to 1 or 0 to 2) is an important idea for understanding why answers vary.

⚠️ **A caveat, as of October 2026.** In the API for the newest Claude models (Opus 4.7 and newer, including Opus 5.5), manual temperature control has been removed: any value other than the default returns an error, and you steer the behavior through how you word your request. Regular chat apps don't have this setting at all. Some other models and services still offer it, so the principle below is worth knowing, but check the documentation for your model.

Remember: at the token-choosing step, the model has a probability distribution. Temperature decides how to pick from it.

**Temperature = 0:**
The model always picks the token with the highest probability. A fully deterministic mode (deterministic means predictable: the same input gives the same output). Ask the same question 10 times and you'll get the same answer. Predictable. Reliable. Boring. (Even at zero temperature, an identical answer isn't always guaranteed.)

Good for: precise instructions, pulling data out of documents, structured tasks, code.

**Temperature = 1 (the default):**
A balance between predictability and variety. This is Claude's default setting. Answers are coherent but not mechanical.

**Temperature = 1.5 to 2:**
The model takes lower-probability tokens: "unexpected" choices. Answers become creative, surprising, sometimes strange. At very high temperatures, they turn into nonsense.

🎨 **Picture this:** a chef's spice dial. Temperature 0 is a dish with no salt or pepper: predictable, always the same, safe. Temperature 1 is the standard recipe: tasty and familiar. Temperature 2 is the chef throwing in everything on the spice rack in random amounts: sometimes brilliant, often inedible. For Claude, Anthropic chose the "kitchen temperature" itself: on the newest Claude models in the API you can no longer change it, while on a number of other models you still can.

**Practical guidelines (where your tool lets you set the temperature):**
- Writing code / extracting data → temperature 0 to 0.3
- Regular conversation / analysis → temperature 0.7 to 1.0
- Brainstorming / creative writing → temperature 1.0 to 1.3
- Above 1.5: for experiments only

---

### 8. Model parameters: what they are

A parameter (a numeric value the model learned during training) is one of the numbers inside a neural network that determine how it "thinks."

Put simply: a neural network is a math function with billions of variables. Training is the process of finding the right values for those variables so that the function gets good at predicting the next token.

**Size comparison:**
- GPT-3 (2020): 175 billion parameters
- Today's flagship models from OpenAI, Anthropic and Google: the companies don't disclose their sizes, and any numbers you find online are guesses
- Llama 3.1 (Meta, open weights, meaning anyone can download the model itself): versions with 8, 70 and 405 billion

More parameters ≠ a better model. That's a common misconception. What matters isn't the count; it's the quality of the training, the data and the architecture. Newer, smaller models often outperform larger predecessors.

🎨 **Picture this:** parameters are like the synapses in a human brain (a synapse is a connection point between nerve cells, where signals pass from one to the next). In the first few years of life, a child's brain builds a huge number of new connections and then prunes them: unused connections are cleared away, and the brain's circuits become more efficient. An adult is smarter than a toddler not because there are more connections, but because the ones that remain are tuned the right way. Number of synapses ≠ intelligence. Number of parameters ≠ the power of a model. What decides everything is how they're tuned.

---

### 9. Fine-tuning: how an assistant is born

After basic pre-training, you have a powerful but "raw" language model. It can predict tokens. But it doesn't know how to be a helpful assistant: it might quote Nazi propaganda or give instructions for self-harm, simply because "that was text in the training data too."

To turn a "text predictor" into a "helpful assistant," developers use fine-tuning (additional training of an already-trained model on specific data for a specific goal).

**RLHF: the key method behind ChatGPT, GPT-4 and most commercial models**

RLHF (Reinforcement Learning from Human Feedback) works like this:
1. The model generates several possible answers to the same question
2. Human reviewers rank them: this one is better, that one is worse
3. Those rankings are used to train a separate reward model (a model that scores answers)
4. The main model learns to produce answers that the reward model will score highly

**Constitutional AI: Anthropic's method for Claude**

Constitutional AI (a training method in which the model is guided by a set of principles) is the approach Anthropic uses at the core of Claude's training.

Instead of relying only on human ratings (people make mistakes and have biases), Claude is trained to follow a set of explicit principles, a "constitution": be helpful, be honest, avoid harm. The model learns to critique its own answers against those principles and improve them.

🎨 **Picture this:** two kids who've read exactly the same books. The first one (RLHF) was raised by parents who simply praised or scolded: "good" or "bad," with no explanation. The second one (Constitutional AI) was raised by parents who explained the principles: "That's not okay, because it hurts someone else. Let's think about how to say it differently." The second kid understands better why they do what they do, and applies those principles in new situations. That's the idea Anthropic builds Claude's behavior on.

---

### 10. Why AI hallucinates

A hallucination (when AI confidently states something that's false) is the most common problem you'll run into with language models.

AI will confidently cite scientific papers that don't exist. It attributes quotes to real people who never said them. It gives the wrong dates for historical events. And it does all of this in the same confident tone it uses when it's right.

**Why this happens:**

Remember: the model is optimized to "guess the next token so the text sounds plausible." Not to "tell the truth." Plausible and true are two different things.

If the training data contains lots of texts that mention someone like "Professor Miller from the University of Michigan," the model will produce a plausible "Professor Miller from the University of Michigan" even if no such person exists. Because it's a plausible pattern.

If a specific fact showed up rarely in the training data, or in contradictory contexts, the model fills the gap with the "most likely" option. Which may be false.

AI doesn't "know" facts the way a person knows something they read in a reliable source. AI has seen patterns in texts about facts, and it reproduces those patterns.

🎨 **Picture this:** a person with a photographic memory who has read absolutely everything people have ever written, but has never seen the real world. Only text. They know everything that was ever written down. But they have no way to check: "did this actually happen in real life?" When you ask them about a specific fact, they find the closest pattern in their memory and repeat it. If the pattern was wrong in the sources, they repeat the mistake. If there was no pattern at all, they create one that sounds plausible but doesn't exist.

**How to protect yourself:**
- Always verify important facts in an independent source
- Double-check dates, names and statistics
- For current information, ask Claude to search the web (it has web search built in) and look at the links it cites
- Ask Claude: "Are you sure about this? How likely is it that you're wrong?" Models trained to be honest often admit uncertainty

---

### 11. Why this matters in practice

This isn't an academic lecture. Every section has a direct use in your work.

**Tokens → saving your limit and your money:**
Tokens use up your limit in the chat app, and in the API they cost money. Once you understand what a token is, you:
- Write more compact prompts (less filler = fewer tokens = less usage)
- Know that English is usually the cheapest language in tokens, so a long document in another language uses up your limit faster
- Don't load entire documents into the context, only the parts you need

**Context window → working with big documents:**
Knowing that context has limits, you:
- Split big documents into parts and work through them one at a time
- Later, in Claude Code, use the `/compact` command when a conversation gets long
- Start a new chat for a new task instead of dragging everything into one

**Temperature → consistency or creativity:**
Knowing how temperature works, you:
- Set a low temperature for tasks that need repeatable results (generating code, extracting data), where your tool lets you change it
- Set a higher one for brainstorming and generating ideas
- Understand why the same prompt gives different results on different tries

**Hallucinations → critical thinking:**
Knowing where hallucinations come from, you:
- Don't trust AI blindly on factual questions
- Always verify what matters in primary sources
- Use AI to organize your thinking, not as a substitute for fact-checking

---

## Practice

**Exercise 1: A token experiment**

Go to [claude.ai](https://claude.ai) and type:

```
Here's a list of words. For each one, tell me roughly how many tokens it takes:
cat, catastrophe, computer, AI, internationalization, hello, hola, computadora, anthropomorphism, i18n
```

Look at the answer. It's a rough estimate: the number of tokens depends on the model, and an exact count is only available through the API (the interface developers use). Anthropic's documentation explains how that works: [Token counting](https://platform.claude.com/docs/en/build-with-claude/token-counting). You don't need to count anything yourself: it's enough to see that short, common words take one token, while long or rare ones take several.

Goal: get a feel for how token counts differ between languages and between words.

**Exercise 2: A temperature experiment through repetition**

Type the same prompt three times in a row without changing anything (start a new chat each time, so Claude doesn't see its earlier answers):

```
Come up with an unusual name for a coffee shop in the style of magical realism. Just the name, no explanation.
```

Did the answers match? Differ slightly? Differ a lot? That's temperature in action.

**Exercise 3: A context window test**

Take any long article from the internet (at least 5,000 words). Paste it into a chat with Claude and ask a question about details from the beginning of the article. Then ask about details from the end. Compare how accurate the answers are.

Then try splitting the same article into two requests and see whether the quality of the answers changes.

What to expect: an article this size fits into the context window whole, so Claude should answer about the beginning and the end equally well. "Forgetting" only starts in very long conversations.

**Exercise 4: A hallucination check**

Ask Claude about a specific, little-known fact: for example, the second-largest city in a little-known country, or the year a particular small college was founded. Write down the answer. Check it on Wikipedia. Did it match?

Goal: build the reflex of verifying important facts.

---

## Key takeaways

> AI isn't a thinking machine. It's a very advanced next-token predictor. That explains both its strengths (patterns, connections, speed) and its weaknesses (hallucinations, no "real" understanding).

> Tokens are the currency of working with AI. The fewer unnecessary tokens in your prompt, the cheaper the result, and often the more accurate.

> The context window is AI's desk. What's on the desk, it sees. What's off the desk, it doesn't. Manage what you put on the desk.

> Temperature sets the balance between predictability and creativity. Low for code. High for ideas.

> Hallucinations are a built-in property of the architecture. Not bad intent, not a random glitch. The model is optimized for plausibility, not truth. Verify what matters.

> Fine-tuning turned a "text predictor" into a "helpful assistant." Constitutional AI is Anthropic's approach, and Claude's behavior is built on it.

---

## Next lesson

→ [The history of AI](00-what-is-ai.md): from Turing to Claude, where all this came from and why the turning point is happening now.

A comparison of the assistants (Claude, ChatGPT, Gemini and others) comes in the next module, in the lesson [Comparing AI models](00c-ai-models-comparison.md).
