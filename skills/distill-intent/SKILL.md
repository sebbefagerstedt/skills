---
name: distill-intent
description: Distill the current conversation into a short intent brief a fresh session can act on. Use when the user asks to turn a chat into an intent, prompt, handoff or brief, or is done reasoning and wants something to paste into a new session.
---

# Distill intent

Turn this conversation into the shortest brief that lets an agent who hasn't seen the chat do the right work. That agent can read the code and make sensible choices, so the brief only carries what it can't work out for itself.

## How to work

1. **Read the whole conversation in order.** Later messages override earlier ones, so keep only the final state of each decision.
2. **Keep what the agent can't recover:**
   - The goal and why it matters
   - Decisions the user made, with the reason when the agent might otherwise reopen them
   - Constraints and boundaries
   - How to tell the work is done
   - Non-obvious facts and gotchas
   - Pointers to key files or findings that took real effort to uncover, such as "The retry logic is in `queue/worker.py`, not the API layer"
3. **Keep the results of a deepen round.** If the conversation includes methods, raw material or checks from the deepen skill and the user didn't reject them, carry over the ones that would change the result or how it is checked. Without this, the rigor added before the handoff is lost. Items the user accepted go in the normal sections. Items the user never accepted go only under **Optional**, never in Decisions, Guardrails or Done when. Drop any item that conflicts with, narrows or overrides something the user decided (for example, a cap on a value the user said to honour); a proposal must never quietly change a decision.
4. **Drop everything else:**
   - The history of how the discussion got here
   - Rejected options, unless the agent is likely to suggest them again. Then add one guardrail line: "Not X, because Y."
   - Other suggestions from the assistant that the user never accepted
   - Implementation steps, unless the user required them or they came from a deepen round
   - Anything the agent would find quickly in the code, and standard practice
   - Rules already covered by the project's instruction files, since the agent loads those itself. Include a rule only if this task needs an exception to it.
5. **Don't fill gaps by guessing.** List anything essential that the chat left unsettled under Open. If the chat has no done criteria, propose them and mark each one "(proposed)" so the user can see it didn't come from them.
6. **Cut before you deliver.** Remove any line the agent could do the right work without. Aim for under 150 words, counting every section, Optional included.
   - One fact per line, one short sentence each. Say each fact once: don't repeat a decision as a guardrail or a done criterion.
   - Give a reason only where the agent would otherwise reopen the decision.
   - Optional holds at most three items: the ones most likely to catch a wrong result.
   - If still over, cut in this order: Context, then Optional, then reasons. Keep decisions and done criteria even if that means going over.
   - Always keep the instruction line under the Optional heading.

Don't start the work. Write in the language of the conversation unless asked otherwise. Reply with the brief in one copyable code block and at most one line pointing out open items or proposed items.

## Format

Leave out empty sections.

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
- Facts and pointers the agent can't quickly work out from the code or files.

## Optional
Not agreed with the user. Use only where it doesn't conflict with anything above; skip any item you don't need.
- Methods, checks or limits proposed during a deepen round.

## Open
- Questions the chat left unsettled.
```
