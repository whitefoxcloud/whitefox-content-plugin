---
name: whitefox-content-find-topics
description: Stage 2 of 3 of the WhiteFox content workflow. Finds what to write about, in one conversation - real buyer quotes for each pain, then the topics (lanes) with the ones to work on made active, then optional keyword research. Use when a campaign has pains and the user wants topics, lanes or quotes.
---

# Find topics (stage 2 of 3)

Runs up to three steps one after the other in this conversation. Each step still shows its
result and waits for approval before saving.

| Step | What it does | What the user decides |
|---|---|---|
| 1 of 3, mine quotes | searches the web for real buyers voicing each pain, word for word with links | keep or drop quotes (at most 3 per pain) |
| 2 of 3, mint lanes | turns pains, proofs and quotes into topics WhiteFox can own | keep, drop or edit topics, and which are active |
| 3 of 3, keyword research (optional) | what buyers search for on an active topic | free, paid (price shown first) or skip; which keywords to target |

## Before you start

1. Read `../whitefox-content-guide/formats/README.md` and begin as it says (workspace,
   settings, campaign, profile).
2. If the campaign has no `pains.md`, say stage 1 comes first and offer
   `/whitefox-content-add-case-study` (Claude Code: `/wf-content:whitefox-content-add-case-study`).
   Stop.
3. Work out where to start, and skip steps that are already done, one line each:
   - Pains without quotes and not under "Pains with no quotes found": step 1.
   - Every pain covered, no lanes (or new pains since the last lanes): step 2.
   - Lanes exist and at least one is `active`: offer step 3, or end the stage.
   - Lanes exist and none is `active`: step 2, to choose the active ones.
4. Show the plan in at most four lines: the steps you will run, that keyword research is
   optional, and "You can stop after any step; running this command again carries on from
   there."

## Running each step

For each step, read its file and follow it exactly, with two changes:

- Open with the stage line, for example **Stage 2 of 3, Find topics: step 1 of 3, mine
  quotes.**
- Skip the step's own "Next" section. After it saves, say in one line what was saved, then ask:
  "Continue to step N, <name>? Reply **go**, or **stop** to pause here." Mine quotes may need
  more than one round: offer the next round before moving on.

| Step | File |
|---|---|
| 1 | `../whitefox-content-mine-quotes/SKILL.md` |
| 2 | `../whitefox-content-mint-lanes/SKILL.md` (make sure the user chooses at least one `active` lane before moving on) |
| 3 | `../whitefox-content-keyword-research/SKILL.md`, only on the user's choice |

Before step 3, ask: "Keyword research for <active lane>? **free** (questions and phrasing from
web search, no numbers), **paid** (real search numbers from DataForSEO, price shown first), or
**skip** (LinkedIn posts and emails do not need it; articles are better with it)." Run it once
per active lane the user picks. Paid mode keeps all its own rules: price question, explicit
yes, $1.00 cap.

## End of the stage

Say: "Stage 2 done for <campaign>: <N> quotes, <M> topics, <K> active: <labels>." Then: "Next
is stage 3, Write: a plan of pieces for an active topic, then the drafts. Reply **go** to start
it now, or run `/whitefox-content-write` (Claude Code: `/wf-content:whitefox-content-write`)
later." On go, follow `../whitefox-content-write/SKILL.md`.

## Rules

- Every step's own rules apply in full; this file only joins them.
- Never skip a step's approval. Nothing is saved before the user's yes, and nothing is spent
  without the paid step's own price question and yes.
