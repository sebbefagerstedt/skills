# Agent Instructions

This repo hosts agent skills following the [Agent Skills specification](https://agentskills.io), installable via the [vercel-labs/skills](https://github.com/vercel-labs/skills) CLI (`npx skills`).

## Compatibility Requirement

Every skill pushed to this repo must be **compatible with all AI coding assistants**, not just Claude Code. Do not rely on assistant-specific features (e.g. Claude-only frontmatter fields like `context: fork`, or Claude-only hooks).

When writing or reviewing a skill's `SKILL.md`:

- Stick to the required frontmatter fields: `name` and `description`.
- Write instructions in plain Markdown that any agent can follow — avoid assuming a specific tool's syntax, file layout, or command set unless the skill is explicitly about that tool.
- Avoid features flagged as agent-specific in the [vercel-labs/skills compatibility table](https://github.com/vercel-labs/skills#compatibility) (e.g. `allowed-tools` support and hooks vary by agent).
- If a skill genuinely only makes sense for one assistant, say so explicitly in its `description` rather than assuming compatibility.
