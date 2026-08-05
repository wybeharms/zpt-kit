# Key concepts (the agent teaches these as they come up)

> Part of the **ZPT Kit** by ZPT Partners. The agent explains each idea below in plain language at the moment it becomes relevant: one 💡 at a time, with a small sketch in the chat where it helps, never a lecture. Never assume the person already knows any of this, and never explain what they clearly already know. Patterns specific to the improve path are marked **When improving:**.

## The ground floor: files and folders

A computer stores everything as **files** (a document, a photo, a note) inside **folders**, which can hold other folders. Every file has an address, called a **path**:

```
📁 Documents
└── 📁 my-work
    └── plan.md   ←  its path is Documents/my-work/plan.md
```

Folders whose names start with a dot (like `.claude`) are **hidden** by default. That is why some folders below are hard to find; the reveal tricks are further down.

## Chat vs agent

- **Chat** (the claude.ai or chatgpt.com website, the plain app): you ask, it answers, and when the chat closes, the context is gone. It cannot touch your files.
- **Agent:** the same AI, but working inside your files. It reads them, creates them, edits them, and asks permission along the way.

Where the agent mode lives:

| Product | Chat | Agent mode |
|---|---|---|
| Claude | claude.ai, the Claude app | **Claude Code** (terminal or app) and **Cowork** (inside the Claude desktop app) |
| ChatGPT | chatgpt.com, the ChatGPT app | **Codex** (terminal) and the app's work mode (**GPT Work**) |

This kit needs the agent mode. If the AI says it cannot read files, the person is in plain chat: the fix is to reopen in the agent mode from the table above, mounted to the right folder.

## Prompting: how to talk to an agent

There is no magic syntax. A prompt is an instruction in plain language, everyone phrases them differently, and all of it is valid input. The agent's job is to understand, ask when unsure, and act.

What makes a prompt land better, taught in passing rather than as a lesson:

- **Say the outcome, not the method.** "Draft a thank-you note to the coach" beats "write some text".
- **Context does the heavy lifting.** That is the whole point of the folder: the more the agent can read, the less the person has to type.
- **Correcting is normal.** "Shorter", "warmer", "not like that" are excellent prompts. Nobody nails it first try.
- **Vague is allowed.** "Help me with this" works; the agent asks what "this" is.

**When improving:** how the person prompts is part of the setup. If they report the agent "never gets it", weak context files are the usual culprit, not their phrasing; fix the folder before coaching the person.

## The mounted folder (the most important idea for trust)

Think of the agent as sitting inside one filing drawer: the folder it was opened in.

- It reads **that folder first** and works inside it.
- It does **not** roam the computer. Photos, messages, and other folders stay invisible to it.
- With **permission**, it can step outside: read another folder, or connect to a service. Improving uses exactly this: the agent asks permission to look at the folders it is improving.
- The **permission prompts** are exactly that: the agent asking before it touches anything. Saying yes to a specific request is how you let it work; no is always available.

A sketch worth drawing when teaching this:

```
your computer
├── 📁 photos          (invisible to the agent)
├── 📁 other stuff     (invisible to the agent)
└── 📁 my-folder   ←   the agent lives here
```

## Folder-first

Instead of treating AI as a throwaway chat (ask, answer, lose everything on close), you keep a folder that holds structured context about your work or life: who you know, what you are working on, your standards, your voice, examples of good output. You point the agent at the folder, it reads the folder first, and then it helps you as if it had worked with you for months. That is the whole idea this kit builds.

**When improving:** the journey measures how well the existing setup delivers on this idea.

## Markdown (.md files)

Nearly everything this kit builds or improves is a `.md` (markdown) file: ordinary text with a little formatting (`#` for headings, `-` for lists). Any notes or text app opens it (TextEdit on Mac, Notepad on Windows), and the person can read and change every file the agent creates. `CLAUDE.md` and `AGENTS.md` are not special formats, just agreed filenames the products look for.

## Two layers: global and local

- **Local:** an instructions file inside a specific folder. Rules and context for that one project ("this folder is for client X, here is their tone, never share these notes").
- **Global:** one instructions file that applies to **every** folder on the computer: your name, how you like to write, rules you never want to repeat.

| Product | Local file (in the folder) | Global file |
|---|---|---|
| Claude | `CLAUDE.md` | `~/.claude/CLAUDE.md` |
| ChatGPT / Codex | `AGENTS.md` | `~/.codex/AGENTS.md` |

The global layer saves repeating yourself; the local layer keeps each folder specific.

### Conventions worth setting once, in the global file

Cross-cutting rules belong in the global file, set once. Good defaults to offer (personal taste, so offer, never force):

- Refer to people by name and to the agent by its name. Avoid "I" and "you" inside files.
- Keep answers short and to the point.
- Discuss the approach before building. Ask questions in small batches the person answers in one message. List the steps of a multi-step task first, then work through them in order.
- Sketch a folder tree or simple diagram in the chat before creating or restructuring anything.
- Restate any irreversible task and confirm before running it.
- Flag anything the person must do, decide, or provide with 🔴 on its own line, in bold.
- Use relative paths inside files; never hardcode a path like `/Users/...`, so folders survive being moved or shared.
- Use descriptive, lowercase, hyphenated filenames a non-technical person understands. Avoid `README.md`, `INDEX.md`, and the like.
- A preferred date style (such as "May 8th, 2026"), or punctuation the agent should never use.

**When improving:** the same rules repeated across several local instructions files are the classic sign they should be lifted into the global file once, and removed from the copies.

## The hidden global folder (people always struggle to find this)

The global settings live in a **hidden** folder in the home directory: `.claude` for Claude, `.codex` for ChatGPT/Codex.

- **Mac:** `~/.claude/` means `/Users/<your-name>/.claude/`. To see hidden folders in Finder, press **Cmd + Shift + . (period)**.
- **Windows:** `%USERPROFILE%\.claude\` means `C:\Users\<your-name>\.claude\`. In File Explorer: **View, then Show, then Hidden items**.

Inside Claude's `.claude`, worth one look: `CLAUDE.md` (global instructions), `skills/` (skills that work everywhere), `memory/` or a `projects/.../memory/` area (what the agent remembers), `settings.json` and `plugins/` (configuration, usually leave alone). ChatGPT's `.codex` similarly holds `AGENTS.md` plus configuration.

Most people have never opened this folder, so an old, forgotten global file can quietly shape every session. The agent opens it, recaps what is there in plain language, and asks whether it is still correct before relying on it.

**When improving:** an old global file can even contradict the local folders being looked at, so the confirmation matters double. Bonus census trick: the subfolder names inside `~/.claude/projects/` encode every folder the person has ever mounted an agent in, which makes it a ready-made map of the sprawl worth cross-checking against what the person remembers.

## Where files end up: Cowork's own folder

Claude Code and Codex work in the folder they are pointed at. **Claude Cowork can be different: unless a folder is chosen, it saves work into its own separate folder**, whose location differs per person and per platform. This is one of the most common ways people "lose" files: they were saved somewhere unexpected.

**When improving:** this is a common reason a setup looks emptier than it is. Half the person's real work may be sitting in the Cowork folder, unexamined. Hunt it down before judging anything.

Finding that folder, or any folder's real path:

- **Mac:** in Finder, hold **Option**, right-click the folder, choose **Copy "(folder)" as Pathname**, and paste it.
- **Windows:** in File Explorer, hold **Shift**, right-click the folder, choose **Copy as path**, or read the address bar.

## Where your real files live: cloud storage

Most people keep their work in a cloud-synced folder, and the real location on disk is not obvious.

- **Mac:** most cloud folders live under `~/Library/CloudStorage/` (for example `OneDrive-<Company>` or `GoogleDrive-<email>`). iCloud Drive is at `~/Library/Mobile Documents/com~apple~CloudDocs`. Dropbox is usually `~/Dropbox` or under `~/Library/CloudStorage/`.
- **Windows:** OneDrive and SharePoint usually sync to `C:\Users\<your-name>\OneDrive` or `C:\Users\<your-name>\<Company Name>`. Dropbox is usually `C:\Users\<your-name>\Dropbox`.
- The path tricks above (Option-right-click on Mac, Shift-right-click on Windows) give the exact answer.

Two gotchas:

- A cloud folder is fine as the home for an agent folder **as long as it is synced to this computer**.
- Cloud apps sometimes keep a file **online-only** (a placeholder on disk). If the agent cannot read a file that is clearly there, make the folder available offline: OneDrive "Always keep on this device", Google Drive "Available offline", iCloud "Keep Downloaded".

## Keeping your work safe

- A folder inside iCloud, OneDrive, Dropbox, or Google Drive is **already backed up**. For a first folder, that is enough. Confirm this instead of demanding tools the person does not have.
- **Git** is a power tool for saving labeled versions of a folder and sharing it with others (think version history you control). Optional. A first folder does not need it; when the folder starts to matter, ask the agent to set it up and explain it then.

**When improving:** if the person already uses git, commit before changing anything. If not, a simple copy of the folder before the Execute step does the job; git can come later.

## Connectors: when the agent reaches beyond the folder

With permission, the agent can also connect to services the person already uses, through their official interfaces. The words to recognize are **connector** and **MCP**; they mean roughly the same thing here.

- Common ones: **Gmail and Google Calendar**, and **Microsoft 365** (Outlook, OneDrive, SharePoint).
- What that unlocks from a folder: the agent reads your email and answers questions from it, turns messages into updates to your files, drafts replies for you to review and send.
- Setup lives in the product's settings (usually called Connectors), and each connection is authorized once by the person.

This is the natural **second week** step: first the folder works, then it gets connected. The agent offers it as an outlook, and walks through it in a later chat when the person asks.

**When improving:** note which connectors are already wired up and whether they are actually used. A connector nobody uses is clutter; a workflow that would sing with one is an opportunity worth naming.

## Skills: saved workflows you can run on command

A **skill** is a reusable task saved as a small instructions file, run on command ("draft my weekly update"). On Claude, a skill lives in two possible places:

- **Project skill:** inside a folder, at `.claude/skills/<name>/SKILL.md`. Works only in that folder.
- **Global skill:** at `~/.claude/skills/<name>/SKILL.md`. Works in every folder.

The project skill wins when names collide. Put a skill globally when it should work everywhere (how you like emails written); keep it in the project when it is specific to that work. ChatGPT/Codex has its own way of saving reusable instructions; the agent running this kit can set that up when the need appears.

Skills come **after** the folder: first live with the setup, notice what repeats, then save it as a skill.

**When improving:** watch for the same skill copied into several folders (it probably belongs in the global folder once) and for a local skill silently shadowing a global one of the same name.

## Memory: how a setup remembers across sessions

By default, each chat forgets the last one. A healthy setup fixes this two ways:

- **Working memory:** the instructions file the agent reads at the start of every session.
- **A knowledge base:** small note files the agent writes over time (preferences, decisions, durable facts), plus a short index file that points to them rather than copying them.

The discipline: one fact per note, check for an existing note before adding a new one (no duplicates), keep the index pointing rather than repeating. The agent offers to record durable facts as they come up, not passing chatter.

**When improving:** a setup with no memory at all is a maturity gap worth naming; a memory store full of duplicates or stale facts is worth tidying.

## One area or many: umbrella vs separate folders

- **One coherent area** (your personal life, or a single business): one folder.
- **Several areas** (for example a holding company over a few brands, or work plus a rich personal setup): two sensible options.
  - **Umbrella:** one top-level folder with a subfolder per area, plus shared context at the root. Best when the areas share contacts, voice, or processes.
  - **Separate folders:** one folder per area, with truly-global rules in the global file. Best when the areas are genuinely independent.
- Avoid one giant "everything" folder with no structure.
- **One folder per person.** Family members or teammates each build their own; sharing one folder as a first setup ends in a mess.

**When improving:** when the right move is consolidating scattered folders into an umbrella, follow the safe method in `what-good-looks-like.md` ("Consolidating scattered folders") before moving anything.

## What never goes in the folder

Worth saying out loud during the interview:

- **Passwords, banking credentials, and identity numbers: never.** The folder is not a vault.
- Sensitive material (medical, financial, other people's private information) only when the person consciously decides it belongs there, knowing the folder lives on this computer and its cloud sync.

**When improving:** if any of this is already sitting in the setup, flag it 🔴 and propose moving it out.

## Mac vs Windows

The agent detects the platform rather than asking. It matters for paths, the hidden-folder reveal, and the cloud storage locations above; use the right variant without making a topic of it.
