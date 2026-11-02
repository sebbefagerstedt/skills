---
name: shape-task
description: Interview the user to turn a half-formed task into a short brief with intent, guardrails and done criteria. Use when they are still reasoning, unsure of guardrails or definition of done, or scoping a task in plan mode.
---

# Shape task

Help the user work out what they actually want before any work starts. They usually understand the problem but haven't yet seen which decisions matter. Your job is to surface those decisions, not to write an implementation plan.

## How to work

1. **Look before asking.** Read the request. In a repo, inspect the relevant code and conventions so you don't ask about anything you can find yourself.
2. **Find what is unsettled.** Look for where a reasonable implementation could still be wrong, where two competent engineers would choose differently, what must not change, and how the user would tell that it worked.
3. **Ask one to three questions at a time**, only ones whose answers change the work. Offer concrete options and say which you would pick, because reacting to a proposal is easier than answering an open question. Use a question tool if one is available.
4. **Propose guardrails and done criteria.** People often can't name these until they see them, so suggest candidates based on what you found and let the user keep, change or drop them.
5. **Stop when another question wouldn't change the work.** This usually takes one to three rounds.
6. **Give the brief** and ask whether anything is missing.

Don't start implementing. Keep the brief in the chat rather than writing a file, so this also works in plan mode.

## What belongs in the brief

- **Guardrails** are real limits: what not to touch, actions not to take, compatibility to keep, decisions reserved for the user. Leave out what any competent engineer would do anyway.
- **Done when** items must be checkable: a command that passes, an observable behaviour, a value that matches a source. "Clean code" or "works well" can't be checked, so ask what they would look at to decide. Prefer checks that could fail independently of anyone's agreement, because tests an agent writes for its own work can pass while the work is still wrong.
- **Context** holds facts the agent can't easily recover, including pointers to key files or findings that took real effort to uncover.
- **Implementation steps** stay out, because the agent can usually choose its own approach. If the user requires a specific approach, record it as a guardrail.
- **Project rules** stay out when the project's instruction files already cover them, since the agent loads those itself. Include a rule only if this task needs an exception to it.

## Format

Leave out empty sections. Aim for under 150 words.

```markdown
## Intent
What should be true when this is finished, and why it matters.

## Decisions
- Choices already made that the agent shouldn't reopen.

## Guardrails
- Limits on what the agent may do.

## Done when
- Checkable criteria.

## Context
- Facts the agent can't work out from the code or files.

## Open
- Questions the user chose to leave unanswered.
```
