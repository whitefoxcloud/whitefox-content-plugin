---
name: whitefox-content-write
description: Stage 3 of 3 of the WhiteFox content workflow. Plans the pieces for an active topic (the brief) and writes the drafts - LinkedIn posts, emails and articles - one after the other in one conversation. Use when the user wants content written, drafts, posts, emails or articles for a campaign.
---

# Write (stage 3 of 3)

Plans the pieces for one active topic (lane), then writes the drafts the user keeps, one after
the other in this conversation. Each plan and each draft still waits for approval before
saving.

| Step | What it does | What the user decides |
|---|---|---|
| 1 of 2, plan the pieces | proposes 5 to 8 pieces for the topic (the content plan): channel, headline, voice, evidence | plan, later or drop each piece |
| 2 of 2, write the drafts | writes each planned piece in its channel | approve or change each draft; articles get their plan approved first |

## Before you start

1. Read `../whitefox-content-guide/formats/README.md` and begin as it says (workspace,
   settings, campaign, profile).
2. If the campaign has no `active` lane, say stage 2 comes first and offer
   `/whitefox-content-find-topics` (Claude Code: `/wf-content:whitefox-content-find-topics`).
   Stop.
3. Lane: if the user named one, use it. With exactly one active lane, use it and say so. With
   several, list them (Topic N, label, whether it has a content plan and how many drafts) and ask which.
4. Work out where to start:
   - The lane has no brief, or the user asks for more pieces: step 1.
   - The brief has kept pieces without drafts: step 2.
   - Every kept piece has a draft: say so; offer more pieces (step 1) or another lane.
5. Show the plan in at most four lines, including the limits: "LinkedIn posts are 110 to 180
   words, emails 80 to 150, articles usually 1200 to 1800 and are planned before they are
   written. Each article aims at one main keyword."

## Step 1: plan the pieces

Read `../whitefox-content-arm-brief/SKILL.md` and follow it exactly, with the stage line
**Stage 3 of 3, Write: step 1 of 2, plan the pieces.** and without its "Next" section.

## Step 2: write the drafts

List the planned pieces without drafts (Piece N, channel, headline) and ask which to write: one, several
or **all**. Then write them one at a time, in the order the user gave (or LinkedIn posts, then
emails, then articles). For each, open with **Stage 3 of 3, Write: step 2 of 2, draft <n> of
<total>, <channel>.** and follow its file exactly, without its "Next" section:

| Channel | File |
|---|---|
| linkedin-post | `../whitefox-content-write-linkedin/SKILL.md` |
| email | `../whitefox-content-write-email/SKILL.md` |
| website-article | `../whitefox-content-write-article/SKILL.md` |

After each save, say in one line what was saved, then: "Next: draft <n+1>, <channel>. Reply
**go**, or **stop** to pause here."

## End of the stage

Say: "Done for Topic <N>, <label>: <N> drafts saved in `drafts/`." List them (Piece N, channel, word
count). Then offer: more pieces for this topic, another chosen topic, or `/whitefox-content-start`
to see the whole campaign.

## Rules

- Every step's own rules apply in full, including the house-style checklist on every draft;
  this file only joins them.
- Never skip an approval. Nothing is saved before the user's yes.
