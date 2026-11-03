---
name: review-with-me
description: Walk me through a large change one small piece at a time so I actually look at all of it before I ship or present it — code, docs, slides or anything written in my name. Use when I ask to review, go through, or sign off on a big change, or before I present or publish work an agent helped make. Do not use to write or fix the change itself.
---

# Review with me

I tend to skim big changes, approve them, and regret it later: the result doesn't
look how I wanted, or it says things I don't stand for. Your job is to make
reviewing cheap enough that I really look at everything, and to make it obvious
when I haven't.

Do not change the work during the review. Collect my decisions and apply them
afterwards, or hand them back as a list if I'd rather do it myself.

## 1. Inventory everything first

Find the full change: the diff against the base branch, the changed files, the
document or deck, whatever I point at. If it's unclear what the change is, ask
once.

Show me a short inventory: how many files, sections or slides, and roughly how
big each is. Nothing is reviewed yet. From here on, keep track of what I have
and haven't seen.

## 2. Sort it by how much it can hurt me

Put each piece in one of these groups, and walk them in this order:

1. **In my voice** — anything someone will read as my opinion or promise: claims,
   numbers, recommendations, conclusions, commit messages, PR descriptions,
   emails, slide text, docs, user-facing copy.
2. **Decisions** — choices I never explicitly made: a new dependency, a changed
   default, a removed feature, a naming or structure choice, a design direction,
   anything a reasonable person would have done differently.
3. **How it looks** — UI, layout, charts, formatting, tone.
4. **Mechanical** — renames, moves, formatting, generated files. These can be
   batched.

## 3. Walk one piece at a time

For each piece, keep it short:

- **What changed**, in one or two sentences. Quote the exact text for anything
  in my voice; don't paraphrase it.
- **Why it might not be what I want** — the assumption it rests on, or what I
  might push back on. If you see nothing, say so.
- **One question** I can answer quickly, with your recommended answer:
  keep, change (how), or drop.

Wait for my answer before moving on. Group small related pieces together, but
never more than I can read in about a minute.

For **in my voice**, ask: "Would you say this, in these words, to the people who
will read it?" Flag anything stronger than the evidence, anything I'd have to
defend, and anything that sounds like someone other than me.

For **how it looks**, show it rather than describe it when you can: render it,
take a screenshot, or tell me exactly what to open and where to look.

## 4. Don't let me skip silently

If I say "looks fine, approve the rest" or similar, don't just stop. List what
is still unseen, grouped as above, and ask me to confirm I'm skipping it. A
conscious skip is fine; an accidental one is what this skill exists to prevent.
Still insist on seeing every **in my voice** item, unless I explicitly say no a
second time.

## 5. Close out

When everything has been seen or consciously skipped, give me:

- **Changes to make** — every keep/change/drop decision that requires an edit.
- **Skipped** — what I chose not to review.
- **One-line summary in my words** — what this change does and why, as I would
  say it to the audience. Ask me if it's right. If I can't agree with it, we are
  not done.

Then ask whether to apply the changes now.
