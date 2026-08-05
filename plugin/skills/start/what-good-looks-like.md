# What good looks like

The standard a healthy agent setup is measured against. Read it whenever the path includes improving. The agent uses it twice: in Orient to judge what is already there, and in Propose to shape the target.

## A healthy setup at a glance

- A clear **instructions file** (`CLAUDE.md` on Claude, `AGENTS.md` on ChatGPT/Codex) that says who the person is, what the work is, and the rules.
- A **folder structure** that matches the work, no bigger than it needs to be.
- **Context files** that hold the business knowledge the agent needs to stay useful.
- A **global layer** in the hidden global folder (`.claude` on Claude, `.codex` on ChatGPT/Codex) holding cross-cutting identity and rules, so they are not repeated in every folder.
- **Memory** that persists useful facts across sessions, indexed so it does not duplicate.
- **Readable filenames** a non-technical teammate understands at a glance.
- **Relative paths** everywhere, so the folder survives being moved or shared.
- A few **conventions** that make the agent predictable.

## The instructions file

The agent reads it first every session. A good one covers:

- **Who the person is** and what they do, so the agent does not answer as the wrong person.
- **What the work is** and what good output looks like.
- **A folder map**: what lives where and when to read it.
- **Rules**: what the agent must always do and never do.
- **Context**: anything specific to this person or organization.

## Folder structure

Sensible, optional building blocks. Use only what the work needs:

- `company-context/` (or `context/`): business knowledge the agent reads to stay aware.
- `workflows/`: end-to-end processes, documented.
- `output/`: what the agent produces.
- `templates/`: reusable skeletons.
- `example-docs/`: real reference documents, used but not changed.
- `_archived/`: retired material, kept for reference, never deleted in place.

### One business or many

- **One coherent area** (personal life, or a single business): one folder.
- **Several businesses** (for example a holding company over a few brands): either an **umbrella** (one top-level folder, a subfolder per business, shared context and skills at the root) when they share contacts, voice, or process; or **separate folders** with the truly-global rules in the hidden global `.claude` folder when they are genuinely independent. Full guidance in `key-concepts.md`.
- A giant "everything" folder with no structure is a smell, not a target.

### Consolidating scattered folders into an umbrella

When the right move is to pull several scattered folders into one umbrella, do it safely so a non-technical user does not break paths or lose work:

- **Copy, do not move.** Bring a copy into the new structure and verify it before touching the original.
- **Keep originals** in `_archived/` (or untouched) until the new layout is confirmed working.
- **One area at a time.** Migrate, verify, then move to the next; no big-bang move.
- **Re-check relative paths** after each move, since files that referenced each other may now sit at a different depth.

### The global layer

A healthy setup uses the **hidden global folder** (`.claude` on Claude, `.codex` on ChatGPT/Codex) for cross-cutting identity and rules (the person's name, voice, standing rules) so they are not repeated in every local instructions file. A full review opens that folder and reports what is inside: the global instructions file, `skills/`, `memory/`, and configuration. If everything lives only in one local folder and nothing is global, if the same rules are copied across several local files, or if the person does not know the global folder exists, that is worth raising. `key-concepts.md` explains where it is on Mac and Windows.

## Memory

A mature setup remembers across sessions instead of starting cold each time:

- **Working memory** is the instructions file read at the start of every session.
- **A knowledge base** is small note files written over time, kept in the memory area of the hidden global folder, with a `MEMORY.md` index that points to them rather than copying their contents.

What good looks like: one fact per note, no duplicates, an index that points rather than repeats, and durable facts captured (not passing chatter). A setup with no memory at all is a maturity gap worth naming; a memory store full of duplicates or stale facts is worth tidying.

## Skills vs workflows vs plain docs

- **Plain doc**: reference knowledge the agent reads. Most setups need these first.
- **Workflow**: an end-to-end process written down (for example, "monthly reporting").
- **Skill**: a reusable task the agent can run on command. These come later, once the process is clear.

Start with a strong instructions file and a few plain docs. Add workflows and skills only when a process has proven itself.

**Where a skill lives matters.** A project skill (`.claude/skills/`) works only in that folder; a global skill (`~/.claude/skills/`) works everywhere. The agent resolves a skill name project-first, then global, then plugins, first match wins. So the same skill copied into several folders usually belongs in the global folder once, and a local skill can silently shadow a global one of the same name.

## Naming

- Descriptive, lowercase, hyphenated: `meeting-notes.md`, `deal-pipeline.md`.
- Must pass the non-technical-reader test: the name alone says what the file holds.
- No `README.md`, `INDEX.md`, `MAIN.md`, `NOTES.md`. `overview.md` only when it truly is an overview.

## Paths

- Relative only. Never write absolute `/Users/...` paths into a file. Folders move between machines, clones, and shared drives, and hardcoded paths break the moment they do.

## Conventions worth having

These conventions are cross-cutting: they should hold in every folder, so the healthy home for them is the **global instructions file**, set once, rather than re-typed into each local file. When the improve path finds them only in local files (or repeated across several), the fix is to lift them up to the global layer.

- **No pronouns in files**: names and the agent's name, never "I" or "you".
- **Short answers**: punchy and to the point, never an essay.
- **Planning protocol**: discuss before building, ask questions in small batches, list steps first, get approval before implementing.
- **Sketch before restructuring**: a folder tree or simple diagram in the chat before anything is created or moved.
- **Confirm before executing**: restate a task and confirm before anything multi-step or irreversible.
- **🔴 to flag what the person must do**, on its own line, in bold.
- **Relative paths only** inside files.
- **Descriptive, readable filenames**: no `README.md` or `INDEX.md` (see Naming).

Personal writing preferences belong in the global file too, offered as examples rather than imposed: a preferred date style (such as "May 8th, 2026"), or punctuation the person never wants the agent to use. Project-specific rules (a client's confidentiality terms, a folder's output format) stay in that folder's local instructions file.

## Intentional exceptions (when to leave it alone)

Some of the rules above are defaults, not laws. The most common reason to keep something that looks wrong is that it deliberately mirrors a system the person already uses.

- **Mirroring an external system of record.** If a folder structure or naming scheme matches the organization's existing SharePoint, shared drive, VDR, or CRM taxonomy (for example numbered, spaced deal folders like `1. Legal`, `3. Model & Analysis`), that is a feature, not a defect. Matching what the team already knows beats imposing the generic convention. Leave it.
- **A scheme the team has standardized on.** An established internal convention the whole team reads fluently is worth more than the "ideal" one.

The test is intent and consistency: a deliberate, consistent mirror of how the organization already works is correct. A one-off `README.md` or a stray `/Users/...` path mirrors nothing, so it still gets flagged. When unsure whether something is deliberate, ask the person rather than changing it.

## Signs a setup needs work

- No instructions file, or one that never says who the person is.
- An empty or unexamined global layer: nothing in the hidden global folder, or a global instructions file the person has never read.
- The same cross-cutting rules copied across several local instructions files instead of set once globally.
- No memory at all (every session starts cold), or a memory store full of duplicates and stale facts.
- The same skill duplicated into several folders, or a local skill shadowing a global one of the same name.
- Skills and notes scattered with no map tying them together.
- Duplicate or orphaned files.
- Hardcoded `/Users/...` paths.
- Tech-convention filenames a non-technical teammate cannot read.
- A workflow that automates a bad process. Automating a bad workflow only makes it faster, so fix the process first.
