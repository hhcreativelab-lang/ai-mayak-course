# Claude Code desktop: start without the terminal

**Time:** about 30 min reading + 30 min practice

---

## The gist

There are two ways to work with Claude Code: through the VS Code extension (VS Code is a popular code editor from Microsoft; see the previous lesson) and through the native desktop app, a program you install on your computer like any other app. The desktop app is a tool for everyday work: three tabs, parallel sessions, a built-in terminal (a terminal is a program where you type text commands), a task scheduler, and switching models with a single click.

For non-programmers, this is usually the easiest way into Claude Code: you install an app, click around, and type your requests in plain English. You don't have to open a terminal to get started.

🎨 **Picture this:** VS Code with the extension is like hiring a chef to work in your restaurant's kitchen. The desktop app is like opening your own restaurant: kitchen, dining room and register, all in one place, under one roof.

---

## Key concepts

- **Claude Code Desktop**: a native app (macOS / Windows) with three tabs: Chat, Cowork, Code
- **The Code tab**: the main one; hands-on work with code and files on your computer
- **The Chat tab**: a regular conversation with Claude (no access to your files), the same as claude.ai in your browser
- **The Cowork tab**: Dispatch (an ongoing conversation with Claude that you can send tasks to, including from your phone) and longer agent work (an agent is a program that carries out tasks on its own): research, documents, spreadsheets
- **Permission modes**: how much freedom you give the agent (from "ask me about everything" to "go ahead on your own")
- **Models**: Haiku (fast), Sonnet (faster and cheaper than Opus), Opus (the default), Fable (the longest and hardest tasks); you can switch between them in the middle of a session. Current names and versions: [What's current](https://aimayak.com/now/)
- **Parallel sessions**: several agents working at the same time, each in its own tab
- **Scheduled tasks**: a scheduler; the agent starts on its own, on a schedule

---

## Theory

### Installing the desktop app

🎨 **Picture this:** installing Claude Code Desktop is like installing Word or Photoshop. Download it, open it, sign in. No Node.js, no npm commands (npm is the package manager for Node.js), no terminal to get started.

**System requirements:**

- **macOS 13.0+** (Ventura or later), Intel or Apple Silicon
- **Windows 10 1809+** or Windows Server 2019+
- Linux: the app is in **beta** (Ubuntu and Debian, installed through apt or a .deb package); the terminal version (the CLI, or command-line interface) runs on Linux with no restrictions
- 4 GB of RAM, an internet connection, and Git (a version control system that keeps track of changes to code): you need it for isolated sessions (worktrees)

**Option 1: download it directly**

| Platform | Link |
|---|---|
| **macOS Universal** (Intel + Apple Silicon) | [claude.ai/api/desktop/darwin/universal/dmg/latest/redirect](https://claude.ai/api/desktop/darwin/universal/dmg/latest/redirect) |
| **Windows x64** | [claude.ai/api/desktop/win32/x64/setup/latest/redirect](https://claude.ai/api/desktop/win32/x64/setup/latest/redirect) |
| **Windows ARM64** | [claude.ai/api/desktop/win32/arm64/setup/latest/redirect](https://claude.ai/api/desktop/win32/arm64/setup/latest/redirect) |

**Option 2: Linux (beta):** install it through apt or a .deb package for Ubuntu and Debian. Instructions: [Claude Desktop on Linux](https://code.claude.com/docs/en/desktop-linux).

> The `brew install --cask claude-code` command installs the terminal version of Claude Code, not this app. The terminal version is covered in the lesson [CLI launch modes](08-work-modes.md).

After downloading: open the DMG (macOS) or Setup.exe (Windows) → install it like any other app → launch it → sign in to your Anthropic account (the same one you use on claude.ai) → open the Code tab.

**You need a paid plan:** Pro, Max, Team or Enterprise. Claude's free plan doesn't include Claude Code. Current plan prices: [What's current](https://aimayak.com/now/).

---

### Three tabs: Chat, Cowork, Code

🎨 **Picture this:** the three tabs are like three floors of one building. The first floor (Chat) is a meeting room where you can just talk. The second floor (Cowork) is the workshop, where you can send a job even from your phone. The third floor (Code) is your private office with a computer: here you and the agent work on files together.

| Tab | What it does | What it's for |
|---|---|---|
| **Chat** | A conversation with Claude with no access to your files | Questions, analysis, explanations, no code |
| **Cowork** | Dispatch and longer agent work | Research, documents, spreadsheets; tasks sent from your phone (Dispatch requires a Pro or Max plan) |
| **Code** | Works with the local files on your computer | Programming, automation, projects |

**The main tab for this course is Code.** This is where the agent reads your files, writes code and runs commands in the terminal.

---

### The Code tab interface

🎨 **Picture this:** the Code tab is like an airplane cockpit. The sidebar on the left (your list of sessions) is the GPS and the maps. The center is the windshield you look through to see what you're doing. Down at the bottom are the pedals and levers (models, modes, the input box).

**The sidebar:**

- A list of all your sessions; each session is a separate conversation with the agent
- The `+ New session` button (Cmd+N / Ctrl+N): a fresh, clean conversation
- The **Scheduled** section: sessions from scheduled tasks
- The **Dispatch** section: tasks sent from your phone
- The **Routines** button: create and manage schedules
- The **Customize** button: connect MCP (Model Context Protocol, a standard way to plug outside tools and data into Claude), plugins and connectors

**The input box (at the bottom):**

- The text of your request
- The `+` button: attach a file, an image or a PDF
- The **Environment** dropdown: Local / Cloud / SSH (on Windows, also WSL)
- The **Model** dropdown: choose the model (Haiku / Sonnet / Opus / Fable)
- The **Mode** dropdown: the permission mode
- The send / stop button (Esc)

**Panels (you can open and hide them):**

| Panel | What it shows | Keyboard shortcut |
|---|---|---|
| Chat | Your conversation with Claude | — |
| Diff | Changes to the code (+/-) | Cmd+Shift+D |
| Browser | A built-in browser: your running app and any website | Cmd+Shift+B |
| Terminal | The built-in terminal | Ctrl+` |
| Tasks | Background tasks and subagents | — |
| Plan | Claude's plan of action | — |

**Transcript views:**

A "tool call" below is a single action Claude takes, such as reading a file or running a command.

- **Normal**: tool calls are collapsed into short summaries
- **Verbose**: you see every step and every tool call
- **Thinking**: tool calls are collapsed, but you can see Claude's reasoning
- To switch: `Ctrl+O`

---

### Choosing a model

🎨 **Picture this:** choosing a model is like choosing a tool on a construction site. Haiku is a hammer for small jobs. Sonnet is a hammer drill: faster and cheaper. Opus is a construction crane, and on subscriptions it's the one you get by default. Fable is the heavy equipment for the longest, toughest jobs. You switch right in the middle of the work, without shutting down the site.

To switch models: the dropdown next to the send button. It works **during a session**; you don't have to start over.

Models as of October 2026 (current list: [What's current](https://aimayak.com/now/)):

| Model | Alias | What it's for | Speed / cost |
|---|---|---|---|
| **Haiku 4.5** | `haiku` | Simple, quick tasks | Fastest / cheapest |
| **Sonnet 5.5** | `sonnet` | Everyday work | Faster and cheaper than Opus |
| **Opus 5.5** | `opus` | Complex reasoning, architecture decisions | The default model |
| **Fable 5.1** | `fable` | The longest and hardest tasks | Powerful / on subscriptions it may draw from usage credits |
| **OpusPlan** | `opusplan` | Opus plans, Sonnet carries out the plan | Hybrid |

Fable 5.1, Opus 5.5 and Sonnet 5.5 have a context window of 1 million tokens (context is everything in the conversation that the AI can see at once; tokens are the small chunks of text AI reads and writes), so they don't need a separate version with `[1m]`.

**Default model** (the one that's set unless you change it): on every subscription (Pro, Max, Team, Enterprise) and in the API, the default is Opus 5.5. The Pro plan used to default to Sonnet; that's no longer the case.

**Effort levels:**

You can choose how hard Claude thinks: `low`, `medium`, `high`, `xhigh`, `max`. The set of levels depends on the model, so check what the menu offers for the one you've picked.

- Menu: `Cmd+Shift+E`
- Or type `ultrathink` in your prompt (a prompt is the text request you give the AI), and Claude will think more deeply about that request

**Extended thinking:**

- Opus 5.5, Sonnet 5.5 and Fable always have extended thinking on; there's no separate button for it
- You can see Claude's reasoning in Thinking or Verbose view (switch with `Ctrl+O`)

---

### Permission modes

🎨 **Picture this:** permission modes are how far you trust a contractor with the keys to your home. Manual: the worker asks before every step. Accept edits: the worker makes changes on their own but asks before turning on the gas. Auto: the worker does everything while a security camera watches. Bypass: complete trust, no camera, and only for isolated test setups.

To choose: the dropdown next to the send button. Keyboard shortcut: `Cmd+Shift+M`.

| Mode | What it does | When to use it |
|---|---|---|
| **Manual** (the setting value is `default`; it used to be called Ask permissions) | Asks before every file and every command | Learning, unfamiliar tasks |
| **Accept edits** (formerly Auto accept edits) | Edits files on its own, asks before running commands | You're confident about the task and want speed |
| **Plan** (formerly Plan Mode) | Only analyzes, changes nothing | To see what Claude plans to do |
| **Auto** | Works without the usual questions, while a separate checker model compares each action against what you asked for | Experienced users, trusted tasks |
| **Bypass permissions** | No questions at all | **Only** in isolated containers (a sealed-off test environment with nothing important in it) |

Auto mode isn't available everywhere; it depends on the model and your plan. Check the dropdown in your version of the app for the exact names and the list of modes.

💡 **If you're just starting:** use Manual. It asks a lot of questions, and that's the point: you see what the agent is about to do with your files before it does it. Move to Accept edits once you're confident about the task.

---

### Parallel sessions

🎨 **Picture this:** parallel sessions are like several construction crews on different floors. The first crew does the roof, the second does the wiring, the third does the finishing work. You, as the general contractor, walk around and check on each one. Nobody gets in anyone else's way.

Each session gets an **isolated Git worktree** (a separate working copy of your project): the agent works in its own copy of the repository (the project folder Git keeps track of) and doesn't cross paths with the others.

**Managing sessions:**

| Action | Mac | Windows |
|---|---|---|
| New session | `Cmd+N` | `Ctrl+N` |
| Close session | `Cmd+W` | `Ctrl+W` |
| Next session | `Ctrl+Tab` | `Ctrl+Tab` |
| Previous session | `Ctrl+Shift+Tab` | `Ctrl+Shift+Tab` |
| Open side by side | `Cmd+click` on a session | `Ctrl+click` on a session |

**Side chat**: a side question that doesn't interrupt the main conversation:

- `Cmd+;` (macOS) / `Ctrl+;` (Windows)
- Or type `/btw` in your prompt

---

### Environments

🎨 **Picture this:** the environment is where your agent works. Local: the agent is in your office. Cloud: the agent works in the cloud (and keeps going even after you've gone home). SSH: the agent is on a remote server.

| Environment | Where the agent works | Advantages |
|---|---|---|
| **Local** | On your computer | Direct access to your files, top speed |
| **Cloud** | In Anthropic's cloud (a cloud session) | Keeps working with the app closed, several repositories |
| **SSH** | On a remote machine | Working with a production server (the live server your real users rely on), a VPS, a Dev Container |

**Setting up an SSH connection:**

1. Environment dropdown → `+ Add SSH connection`
2. Fill in: Name, SSH Host (`user@hostname`), Port (22 by default), Identity File
3. Claude Code installs itself on the remote machine automatically

---

### Scheduled tasks

🎨 **Picture this:** a scheduled task is like setting an alarm clock for the agent. You go to sleep, the agent wakes up, does the work and goes back to sleep until next time. In the morning, the result is waiting for you.

To create one: the Code tab → **Routines** in the sidebar → **New routine** → Local.

**Fields:**

- **Name**: a name (for example, `morning-report`)
- **Instructions**: what Claude should do (ordinary text, in plain English)
- **Schedule**: when it runs

**Schedule options:**

| Type | Example |
|---|---|
| Manual | Run by hand only |
| Hourly | Every hour |
| Daily | Every day at 9:00 AM |
| Weekdays | Weekdays at 8:30 AM |
| Weekly | Mondays at 10:00 AM |

Minimum interval: **1 minute**.

**Local vs. cloud:**

- Local: run while the app is open, with access to your files
- Cloud (routines): run even when your computer is off, can be triggered through the API (an API is a way for programs to talk to each other) or a GitHub event; minimum interval of 1 hour

**Tip:** local tasks only run while the app is running and your computer isn't asleep. Turn on **Keep computer awake** (`Settings → This computer → System`) if you use overnight tasks.

---

### Computer use

🎨 **Picture this:** computer use is like letting the agent see your screen and use your mouse and keyboard. It sees what's going on and can click, type and scroll. It's like remote desktop, except the agent decides what to do.

- Requires a **Pro or Max** plan (not available on Team and Enterprise); the feature is a research preview (an early version that's still being tested)
- To turn it on: `Settings → This computer → System → Computer use`
- macOS: it needs the Accessibility and Screen Recording permissions

⚠️ This lets the agent act inside your apps, so try it on something harmless first, and keep sensitive windows (banking, email) closed while you experiment.

**Three levels of access to apps:**

| Level | Apps |
|---|---|
| View only | Browsers (Safari, Chrome) |
| Click only | Terminals, IDEs (integrated development environments, the programs developers write code in) |
| Full control | Everything else |

---

### Key desktop keyboard shortcuts (full list)

> `Cmd+/` shows every keyboard shortcut right inside the app

| Shortcut (Mac) | What it does |
|---|---|
| `Cmd+N` | New session |
| `Cmd+W` | Close session |
| `Esc` | Stop Claude's reply |
| `Cmd+Shift+D` | Diff panel (see the changes) |
| `Cmd+Shift+B` | Browser (with your app and websites) |
| `` Ctrl+` `` | Built-in terminal |
| `Cmd+;` | Side chat (ask something without interrupting the main thread) |
| `Ctrl+O` | Transcript view (Normal / Thinking / Verbose) |
| `Cmd+Shift+M` | Permission modes menu |
| `Cmd+Shift+I` | Model menu |
| `Cmd+Shift+E` | Effort menu (how hard Claude thinks) |
| `Cmd+/` | Show all keyboard shortcuts |

---

### Desktop vs. VS Code extension vs. CLI: a comparison

🎨 **Picture this:** three tools for the same job. The CLI is a scalpel: precise and flexible in practiced hands. VS Code is a Swiss Army knife: editor and agent in one. Desktop is your own surgical center: several operating rooms (sessions), its own equipment (panels), an on-call schedule (scheduled tasks).

| Feature | CLI | Desktop | VS Code |
|---|---|---|---|
| Parallel sessions | Separate terminals | ✅ Built-in sidebar | ❌ |
| Built-in terminal | ❌ | ✅ | ✅ (in VS Code) |
| Visual diff | ❌ | ✅ | ✅ |
| Attaching files/photos | ❌ | ✅ | ❌ |
| Scheduled tasks screen | ❌ (through cron, a system tool that runs tasks on a schedule) | ✅ | ❌ |
| Computer use | ❌ | ✅ | ❌ |
| SSH environment | ❌ | ✅ | ❌ |
| Cloud (cloud sessions) | ❌ | ✅ | ❌ |
| Agent Teams (experimental, off by default) | ✅ | ❌ | ❌ |
| Automation/scripts | ✅ (`--print`) | ❌ | ❌ |
| Linux | ✅ | beta | ✅ |

**Bottom line:** Desktop is the best choice for everyday hands-on work. The CLI is for automation and scripts. VS Code is for when you want everything in one editor.

---

## Common mistakes

❌ **Mistake:** You opened the desktop app and got stuck in the Chat tab, thinking Chat is Claude Code.

✅ **Instead:** Chat is just a conversation, with no access to your files. To work with code, you need the **Code** tab.

❌ **Mistake:** Turning on Fable for every task "to make it better."

✅ **Instead:** For most everyday tasks the default model is plenty, and Sonnet is faster and cheaper. Fable is for truly long and complex tasks, and on subscriptions it may draw from usage credits. Haiku is for quick, simple requests. Don't burn tokens (the small units of text AI works in) for nothing.

❌ **Mistake:** Working in Bypass permissions mode on real projects with important data.

✅ **Instead:** Bypass permissions is only for isolated test environments. On real projects, use Auto or Accept edits.

❌ **Mistake:** Not knowing that sessions are isolated, so you're afraid to run tasks in parallel.

✅ **Instead:** Each session gets its own Git worktree. They don't interfere with each other. Go ahead and run 3-4 sessions in parallel.

❌ **Mistake:** Starting isolated sessions without Git installed.

✅ **Instead:** Sessions in a separate worktree need Git. On Windows, install [Git for Windows](https://git-scm.com/download/win) and start the session again.

---

## Practice

**Exercise: your first day in the desktop app**

The steps use Mac shortcuts; on Windows, press Ctrl where you see Cmd.

**Step 1: Install it (10 min)**

1. Download the desktop app using the link for your operating system (above)
2. Install it like any other app
3. Launch it → sign in to your Anthropic account

**Step 2: Explore the interface (5 min)**

1. Open the Code tab
2. Press `Cmd+/` and look over the list of keyboard shortcuts
3. Open the model dropdown and see what's available
4. Open the permission modes dropdown and read about each mode

**Step 3: Your first session (10 min)**

1. Press `Cmd+N` for a new session
2. Pick a project folder (or create a test folder)
3. Type: `What do you see in this folder? Describe its structure.`
4. Watch how the agent explores the files

💡 For your very first try, use a test folder rather than one with important documents, and keep the mode on Manual so Claude asks before it changes anything.

**Step 4: Parallel sessions (5 min)**

1. Press `Cmd+N` again to create a second session
2. Ask one thing in the first session and something else in the second
3. Switch between them with `Ctrl+Tab`
4. Make sure they don't get in each other's way

**Step 5: Create your first scheduled task (10 min)**

1. Click **Routines** in the sidebar
2. Create a new task: `morning-check`
3. Instructions: `Check all the .md files in this folder and tell me what's new.`
4. Schedule: Manual (runs by hand only, for now)
5. Run it by hand and watch how it works

---

## Tools and resources

- **[Claude Code Desktop: download (macOS)](https://claude.ai/api/desktop/darwin/universal/dmg/latest/redirect)**: Universal DMG (Intel + Apple Silicon)
- **[Claude Code Desktop: download (Windows x64)](https://claude.ai/api/desktop/win32/x64/setup/latest/redirect)**: Setup EXE
- **[Official guide: Desktop Quickstart](https://code.claude.com/docs/en/desktop-quickstart)**: Anthropic's quick start
- **[Full Desktop Reference](https://code.claude.com/docs/en/desktop)**: every feature of the interface
- **[Model Configuration](https://code.claude.com/docs/en/model-config)**: managing models and effort levels
- **[Desktop Scheduled Tasks](https://code.claude.com/docs/en/desktop-scheduled-tasks)**: scheduled tasks
- **[Git for Windows](https://git-scm.com/download/win)**: needed on Windows for isolated sessions

→ See the lesson [Installing VS Code and the extension](05-setup.md): the alternative route through VS Code

→ See the lesson [CLI launch modes](08-work-modes.md): if you want to work in the terminal

→ See the lesson [Loop and scheduled tasks](35-loop-scheduled-tasks.md): a deeper look at scheduling tasks

---

## Key takeaways

> Claude Code Desktop is a native app with three tabs. For programming, you need the Code tab. Chat is just a conversation, with no files.

> You can switch models right in the middle of your work. Opus is the default, Sonnet is faster and cheaper, Haiku is for quick tasks, and Fable is for the hardest ones.

> Parallel sessions are isolated through Git worktrees, so they don't interfere with each other. Run them without worrying.

> Scheduled tasks are an agent on a schedule. Set it up once, and it runs on its own every day.

---

## Next lesson

→ [How to write a good prompt for Claude Code](06-prompting-fundamentals.md): how to give the agent clear instructions
