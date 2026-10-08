---
name: whitefox-content-add-case-study
description: Stage 1 of 3 of the WhiteFox content workflow. Adds a case study and gets a campaign ready for topics, in one conversation - extract its proofs, match them to the campaign, derive the buyer pains. Use when the user has a case study (file, text or link) to add, or wants to start a campaign's content.
---

# Add a case study (stage 1 of 3)

Runs three steps one after the other in this conversation, so the user never needs to know the
next command. Each step still shows its result and waits for approval before saving.

| Step | What it does | What the user decides |
|---|---|---|
| 1 of 3, list what we delivered | reads the case study and lists, word for word, what WhiteFox delivered | correct, merge or drop each delivery |
| 2 of 3, check what fits | checks which deliveries in the case study library fit this campaign's audience | keep or reject each, and its wording |
| 3 of 3, name audience problems | names the audience problems those deliveries solve | keep, edit, drop or add problems |

## Before you start

1. Read `../whitefox-content-guide/formats/README.md` and begin as it says (workspace,
   settings).
2. Campaign: if the user named one, use it. With exactly one `active` campaign, use it and say
   so. With several, ask which. With none, run `../whitefox-content-campaign/SKILL.md` first
   (it is part of setup), then come back here.
3. Work out where to start, and skip steps that are already done, one line each:
   - The user gave a case study (file, text or link): start at step 1.
   - No new case study and the campaign has no `matched` proof yet (a new campaign): ask for
     its case study first: "Do you have a case study for <campaign>? Attach a file, paste the
     text, or paste a link. Or reply **pool** to check the <N> proofs already in the pool (from
     <sources>) for fit." Start at step 1 with the case study, or at step 2 on **pool**.
   - No new case study, the campaign already has matched proofs, and the pool has active
     proofs not judged for this campaign: start at step 2.
   - Every proof judged, at least one matched, no `pains.md`: start at step 3.
   - All done: say "Stage 1 is done for <campaign>" and offer stage 2.
   - The pool is empty and no case study was given: ask for one (attach a file, paste the
     text, or paste a link).
4. Show the plan in at most four lines: the table's steps you will run, and "You can stop after
   any step; what you approved is saved, and running this command again carries on from there."

## Running each step

For each step, read its file and follow it exactly, with two changes:

- Open with the stage line from the workspace rules, for example **Stage 1 of 3, Add a case
  study: step 2 of 3, check what fits.**
- Skip the step's own "Next" section. After it saves, say in one line what was saved, then ask:
  "Continue to step N, <name>? Reply **go**, or **stop** to pause here."

| Step | File |
|---|---|
| 1 | `../whitefox-content-list-deliveries/SKILL.md` (if the case study is already in the pool, say so and go to step 2) |
| 2 | `../whitefox-content-check-fit/SKILL.md` |
| 3 | `../whitefox-content-name-problems/SKILL.md` |

## End of the stage

Say: "Stage 1 done for <campaign>: <N> deliveries in your case study library, <M> fit this campaign, <K> audience problems." Then:
"Next is stage 2, Find topics: real audience quotes, then the topics to write about. Reply
**go** to start it now, or run `/whitefox-content-find-topics` (Claude Code:
`/wf-content:whitefox-content-find-topics`) later." On go, follow
`../whitefox-content-find-topics/SKILL.md`.

## Rules

- Every step's own rules apply in full; this file only joins them.
- Never skip a step's approval. Nothing is saved before the user's yes.
