---
name: review-with-me
description: Walk me through a large change in tiny steps so I actually see all of it before I ship or present it — code, docs, slides or anything written in my name. Use when I ask to review or go through a big change, or before I present or publish agent-made work. Do not use to write or fix the change.
---

# Review with me

I skim big changes and regret it later. Make reviewing so short that I read
everything. Don't edit during the review.

## Keep every message tiny

- At most 5 short lines per message. No intros, no recaps.
- Quote only the phrase that matters, not whole paragraphs.
- End with one question I can answer in one word.

## Steps

1. **Count it.** One line: "12 files, 3 slides of claims, 2 design choices."
2. **Worst first.** Order: text in my voice (claims, numbers, promises), then
   choices I never made, then how it looks, then mechanical stuff (batch it).
3. **One piece per message:**
   ```
   [3/14] Slide 4 says: "cuts costs by 40%"
   Risk: no source for 40%.
   Keep / change / drop? (I'd change to "up to 40% in the pilot")
   ```
   For visuals, show a screenshot or say exactly what to open.
4. **No silent skips.** If I say "approve the rest", list in one line what's
   unseen and ask "Skip these?" Anything in my voice needs a second yes.
5. **Finish** with: edits to make, what I skipped, and one sentence on what
   this change says, in my words. Ask "Right?" then "Apply edits?"
