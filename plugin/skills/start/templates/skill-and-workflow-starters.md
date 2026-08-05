# Skill and workflow starters

Use these in the Execute step (Step 3 of `guide.md`) when the work calls for a reusable task or a documented process. Most setups do not need either at first. Add them only when a process has proven itself.

## Workflow starter

A workflow is an end-to-end process written down so anyone, or the agent, can run it the same way. Save as `workflows/{{name}}/guide.md`.

```markdown
# Workflow: {{name}}

**What it does:** {{one line}}
**When to run it:** {{trigger}}

## Inputs

- {{what the person provides}}

## Steps

1. {{step}}
2. {{step, with any human review gate called out}}

## Output

- {{what gets produced, and where it is saved}}

## Notes

- {{gotchas, things that have gone wrong before}}
```

## Skill starter

A skill is a reusable task the agent runs on command (Claude products; ChatGPT/Codex saves reusable instructions its own way). It lives in `.claude/skills/{{name}}/SKILL.md` (works in that folder only) or in `~/.claude/skills/{{name}}/SKILL.md` in the hidden global folder (works in every folder). A skill goes global when it should be available everywhere; it stays in the project when it is specific to that work. When the same skill name exists in both places, the project one wins. Either way it must start with YAML frontmatter.

```markdown
---
name: {{skill-name}}
description: {{one line on what it does and when to use it}}
---

# {{Skill name}}

## What this does

{{short description}}

## Steps

1. {{step}}
2. {{step}}

## Output

{{what the person gets back}}
```

> A workflow usually calls several skills. Build the workflow first, then pull out skills when a step repeats.
