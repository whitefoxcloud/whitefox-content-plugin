---
name: whitefox-content-find-topics
description: Stage 2 of 3 of the WhiteFox content workflow. Finds what to write about, straight through with one review - real audience quotes for each problem, then the topics, with the user choosing which to work on. Use when a campaign has audience problems and the user wants topics or quotes.
---

# Find topics (stage 2 of 3)

Runs two steps straight through and shows one review at the end, as the workspace rules say in
"Running straight through". The user replies once: to approve the topics and choose which to
work on.

| Step | What it does |
|---|---|
| 1 of 2, find audience quotes | searches the web for real people from your audience voicing each problem, word for word with links |
| 2 of 2, choose topics | turns problems, deliveries and quotes into topics WhiteFox can own |

Checking search interest is not part of this stage: stage 3 runs the free check for each topic
before planning it. Paid keyword research runs only when the user asks for it
(`/whitefox-content-search-interest`).

## Before you start

1. Read `../whitefox-content-guide/formats/README.md` and begin as it says (workspace,
   settings, campaign, profile).
2. If the campaign has no `pains.md`, say stage 1 comes first and carry on with
   `../whitefox-content-add-case-study/SKILL.md`.
3. Work out where to start:
   - Problems without quotes and not under "Pains with no quotes found": step 1.
   - Every problem covered, no topics (or new problems since the last topics): step 2.
   - Topics exist and at least one is chosen (`active`): say so and carry on with stage 3.
   - Topics exist and none is chosen: show the topics review (below) to choose.
4. One line: "Working through it: find audience quotes, then choose topics. You'll see one
   review at the end; type **stop** any time."

## Running the steps

Follow each step's file exactly, except: no "continue?" questions, and skip each step's own
"Show and approve" and "Next". Write short progress lines while searching (the quote step says
how).

| Step | File |
|---|---|
| 1 | `../whitefox-content-find-quotes/SKILL.md` |
| 2 | `../whitefox-content-choose-topics/SKILL.md`, using step 1's quotes |

## The review

Open with **Stage 2 of 3, Find topics: review.** Then, in the chat:

1. **Topics**, numbered: each with its label, our point of view, what backs it (deliveries
   and quotes), and its quotes underneath, short, with their links.
2. One line with the quote count and any problems with no quotes found.

The review page holds the topics as rows with `choice` `["idea", "chosen", "drop"]`, and your
suggestion for the 1 to 3 strongest set as `pick: "chosen"`.

Reply line: "Reply **save** to keep these with my picks chosen, or tell me what to change, for
example: *choose 2 and 5*, *drop 4*, *drop quote 3*."

On save, write `quotes.md`, then `lanes.md` (chosen topics `active`, ideas `candidate`). One
line: "Saved: <N> quotes, <M> topics, <K> chosen."

## Then

Carry straight on with stage 3 for the first chosen topic: follow
`../whitefox-content-write/SKILL.md`, with one line first: "On to stage 3, Write: planning
the pieces for Topic <n>, <label>. The other chosen topics come after."

## Rules

- Every step's own rules apply in full; this file only joins them.
- Nothing is saved before the review's yes.
