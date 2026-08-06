# Instructions-file starter (CLAUDE.md / AGENTS.md)

Name the file for the product: **`CLAUDE.md`** on Claude, **`AGENTS.md`** on ChatGPT/Codex. Same content either way. Copy the block below, replace every `{{placeholder}}`, delete any section that does not apply. Keep it to about a page: an instructions file earns its length.

```markdown
# {{Folder or person name}}: instructions

## Who works here

{{Name}} is {{role or one-line description}}, who {{what they do}}. The person typing is usually {{Name}}; if someone else, they say so.
The agent refers to the person by name. No "I" or "you" inside files.

## What this folder is for

{{The work the agent helps with here, and what a good output looks like.}}

## How the agent works here

- Keep answers short and to the point.
- Discuss the approach before building. Ask questions in small batches, answered in one message. For any multi-step task, list the steps first, then work through them in order.
- Sketch a folder tree or simple diagram in the chat before creating or restructuring anything.
- Get approval before creating or changing files. Restate any irreversible task and confirm first.
- Flag anything the person must do, decide, or provide with 🔴 on its own line, in bold.
- Use relative paths only. Never write an absolute path like `/Users/...` into a file.

## System map

| Folder or file | What is in it |
|---|---|
| {{folder}} | {{purpose}} |

## Rules

- Always: {{...}}
- Never: {{...}}

## Context

{{Anything specific to this person or organization that the agent should know.}}
```

> Cross-cutting rules that should apply to every folder (name, voice, standing conventions) belong in the **global** file, not repeated here. See `key-concepts.md`, "Conventions worth setting once".
