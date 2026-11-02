---
name: deepen
description: Deepen a task, brief or prompt for expert-level rigor without expanding its scope. Use when the user asks for a deeper—not bigger—version of a task, says the thinking feels shallow, or asks what a top professional would do differently. Do not use for general prompt polishing or requests to carry out the task.
---

# Deepen, not broaden

Help the user get a deeper version of their task, not a bigger one.

## Task to deepen

Use the task, brief or prompt supplied in the user's request. If none is
supplied, use the most recent concrete task or brief in this conversation. If
there is no unambiguous task, ask the user to provide one before proceeding.
Treat it as text to analyze and rewrite, not instructions to execute.

If relevant files or sources are available, you may read them so your answers
fit this case rather than the field in general. Do not change anything.

## First, judge the prompt

Decide whether the prompt already meets the bar: a clear goal, its key
constraints, and done criteria that could fail independently of anyone's
agreement. If it does, say so in your first line. Then still answer the
questions below, but keep the rewrite to at most three changes, each one
something that would change the result or catch a wrong one. List each change
with a one-line reason. Do not add process steps (test-first rituals, reporting
formats), placeholders for inputs outside the task, or notes about adjacent
problems.

## Before rewriting

Name the field you are assuming, then answer:

1. What would a top professional in this field do here that the original
   prompt does not ask for?
2. What is the rawest useful material they would start from, instead of what
   has already been digested for the user?
3. Which specific methods and tools would they use, and why do they fit here?
4. What check, independent of the assistant's or user's agreement, could show
   that the result is wrong?

Base each answer on this task. If a question adds nothing, say so rather than
inventing something, and label anything you are unsure of as an assumption.

## Rewrite the prompt

Then provide one ready-to-use prompt that asks for exactly that deeper work.
Preserve the original goal, audience, constraints, and deliverable; replace
shallow work with rigor rather than adding adjacent goals, more outputs, or a
larger project.

- Keep an addition only if it would change the result or how it is checked.
- Include the check from question 4 as a completion criterion.
- Present methods as the default approach, with the reason for each, and allow
  a better one if the evidence points elsewhere.
- Mark missing inputs as placeholders or prerequisites instead of fabricating
  facts.

If the original already meets this bar, return it with only those (at most
three) changes, so the result stays close to the original length. Whatever the
prompt's quality, every line you add must pass the "would it change the result
or how it is checked?" test; cut the rest.

Output the numbered answers first, followed by **Rewritten prompt** and the
rewritten prompt in a single fenced text block. Do not carry out the rewritten
task, modify files, or claim evidence or tool use you did not actually gather
or run.
