---
name: whitefox-content-add-case-study
description: Stage 1 of 3 of the WhiteFox content workflow. Adds a case study and gets a campaign ready for topics, straight through with one review - lists what WhiteFox delivered, checks what fits the campaign, names the audience problems. Use when the user has a case study (file, text or link) to add, or wants to start a campaign's content.
---

# Add a case study (stage 1 of 3)

Runs three steps straight through and shows one review at the end, as the workspace rules say
in "Running straight through". The user replies once: to approve or change the review.

| Step | What it does |
|---|---|
| 1 of 3, list what we delivered | reads the case study and lists, word for word, what WhiteFox delivered |
| 2 of 3, check what fits | checks which deliveries in the case study library fit this campaign's audience |
| 3 of 3, name audience problems | names the audience problems those deliveries solve |

## Before you start

1. Read `../whitefox-content-guide/formats/README.md` and begin as it says (workspace,
   settings).
2. Campaign: if the user named one, use it. With exactly one `active` campaign, use it and say
   so. With several, ask which. With none, run `../whitefox-content-campaign/SKILL.md` first
   (it is part of setup), then come back here.
3. Work out where to start, and skip steps that are already done:
   - The user gave a case study (file, text or link): start at step 1.
   - No new case study and the campaign has nothing that fits yet (a new campaign): ask for
     its case study: "Attach the case study for <campaign>, paste its text, or paste its link.
     Or reply **library** to check the <N> deliveries already in your case study library."
     Start at step 1 with the case study, or at step 2 on **library**.
   - No new case study, the campaign already has deliveries that fit, and the library has
     deliveries not checked for this campaign: start at step 2.
   - Everything checked, at least one fits, no `pains.md`: start at step 3.
   - All done: say "Stage 1 is done for <campaign>" and carry on with stage 2.
4. One line: "Working through it: list what we delivered, check what fits, name audience
   problems. You'll see one review at the end; type **stop** any time."

## Running the steps

Follow each step's file exactly, except: no "continue?" questions, small questions take the
defaults in "Running straight through", and skip each step's own "Show and approve" and
"Next". Write a one-line progress note after each step.

| Step | File |
|---|---|
| 1 | `../whitefox-content-list-deliveries/SKILL.md` (if the case study is already in the library, say so and go to step 2) |
| 2 | `../whitefox-content-check-fit/SKILL.md`, using step 1's deliveries |
| 3 | `../whitefox-content-name-problems/SKILL.md`, using the deliveries that fit from step 2 |

## The review

Open with **Stage 1 of 3, Add a case study: review.** Then three numbered sections in the chat,
and the review page with all of them as rows (`choice` keep/drop for deliveries, fits/doesn't
fit for the fit check, keep/drop for problems):

1. **What we delivered** (step 1): each delivery, short.
2. **What fits this campaign** (step 2): fits or doesn't fit, with the one-line wording.
3. **Audience problems** (step 3): each problem, what backs it, its search angle.

Then "Check before saving" if anything needs a look, and the reply line: "Reply **save**, or
tell me what to change, for example: *drop delivery 4*, *delivery 2 doesn't fit*, *reword
problem 3: ...*". If a change affects a later section (a dropped delivery backed a problem),
update that section too and show what changed.

On save, write in this order: `pool/sources/<source-id>.md`, the campaign's `shelf.md`,
`pains.md`, each as its step's file describes. One line: "Saved: <N> deliveries, <M> fit,
<K> audience problems."

## Then

Carry straight on with stage 2: follow `../whitefox-content-find-topics/SKILL.md`, with one line
first: "On to stage 2, Find topics: finding audience quotes for the <K> problems."

## Rules

- Every step's own rules apply in full; this file only joins them.
- Nothing is saved before the review's yes.
