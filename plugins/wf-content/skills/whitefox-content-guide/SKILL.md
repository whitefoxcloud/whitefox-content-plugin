---
name: whitefox-content-guide
description: Explains how the WhiteFox content workflow works, what each step does, where files live in the WhiteFox folder, and what words and IDs mean (deliveries, audience problems, quotes, topics, pieces). Use when the user asks how the plugin, workflow, folders, words or IDs work.
---

# Guide

Answer the user's question about the WhiteFox content workflow. The workspace rules are in
`formats/README.md` in this skill's folder; the template for each file is next to it. Read
them before answering a question about files, IDs or statuses, and answer in the words from
"Words the user sees" there.

If the user asked nothing specific, give the overview below, short, then ask what they want to
know more about.

## The workflow

A case study goes in; LinkedIn posts, articles and emails come out. Every piece of content can
be traced back to something WhiteFox really delivered.

You only need four commands:

| Command | What happens |
|---|---|
| `/whitefox-content-start` | sets up your folder, shows every campaign and what to do next |
| `/whitefox-content-add-case-study` | stage 1: a case study goes in; what we delivered is checked against your campaign and your audience's problems are named |
| `/whitefox-content-find-topics` | stage 2: real audience quotes, then the topics to write about, then an optional search interest check |
| `/whitefox-content-write` | stage 3: a content plan for a topic, then the LinkedIn posts, emails and articles |

Each stage runs its steps one after the other and waits for your yes at each one. You can stop
any time; the same command carries on from where you stopped.

Two more for looking around, they change nothing:

| Command | What happens |
|---|---|
| `/whitefox-content-dashboard` | shows the dashboard page: click a count or a topic to see its problems, quotes, topics and drafts |
| `/whitefox-content-show <ID>` | shows one saved item, for example `/whitefox-content-show Piece 3 fin-2026-10` opens that draft in the preview page |

The detailed steps behind the stages, each also a command of its own:

| # | Step | What it does | Writes |
|---|---|---|---|
| 1 | `/whitefox-content-industry` | describes an industry: audience, how we position WhiteFox, words to use and avoid | `profiles/<CODE>.md` |
| 2 | `/whitefox-content-campaign` | starts a campaign for one industry | `campaigns/<name>/campaign.md` |
| 3 | `/whitefox-content-list-deliveries` | list what we delivered: reads a case study once and lists what WhiteFox really did | `pool/sources/<id>.md` |
| 4 | `/whitefox-content-check-fit` | check what fits: which deliveries in your case study library fit this campaign | `shelf.md` |
| 5 | `/whitefox-content-name-problems` | name audience problems: the problems those deliveries solve | `pains.md` |
| 6 | `/whitefox-content-find-quotes` | find audience quotes: real people saying those problems in public, word for word | `quotes.md` |
| 7 | `/whitefox-content-choose-topics` | choose topics: turns problems, deliveries and quotes into topics to publish about | `lanes.md` |
| 8 | `/whitefox-content-search-interest` | check search interest, optional: what people search for on a topic; paid with DataForSEO (real numbers) or free with web search (questions and phrasing) | `keywords.md`, `costs.md` |
| 9 | `/whitefox-content-plan-pieces` | plan the pieces: the content plan for one topic (channel, headline, who posts it) | `briefs/LANE-nn.md` |
| 10 | `/whitefox-content-write-linkedin`, `/whitefox-content-write-article`, `/whitefox-content-write-email` | writes one planned piece | `drafts/` |

`/whitefox-content-writing-rules` shows the writing rules every draft follows.

In Claude Code every command starts with `wf-content:`, for example `/wf-content:whitefox-content-start`.

## Words we use

| Word | What it means |
|---|---|
| Industry | who we sell to in one sector, and how we talk to them (for example INS, Insurance / insurtech) |
| Case study library | every case study you have added, read once and reused by every campaign |
| What we delivered (a delivery) | one piece of work WhiteFox did for a client: their problem, what we built, the outcome |
| Audience problem | a problem your audience has that our work solves |
| Audience quote | a real person from your audience saying that problem in public, word for word, with its link |
| Topic | a subject to publish about, with our point of view |
| Content plan | the pieces planned for one topic |
| Piece | one planned LinkedIn post, email or article |
| Draft | a written piece, ready to copy |

IDs: Problem 3, Quote 4, Topic 3, Piece 3, Delivery 2 (Loot). In the files they are written
PAIN-03, QUOTE-04, LANE-03, ANGLE-03 and loot-P02; either form works when you type them.

## Things people ask

- **Is anything saved without me?** No. Each step shows its result and waits for your approval.
- **Does it spend money?** Only keyword research in paid mode (DataForSEO), and only after it
  shows the price and you say yes. Its free mode spends nothing. Every paid call is logged in
  the campaign's `costs.md`.
- **Why a case study library?** A case study is read once; every campaign you run reuses what
  we delivered in it.
- **Can I edit the files myself?** Yes, they are plain text. Keep the headings and IDs as they
  are, or the next step may not find them.
- **What does an industry's status mean?** `draft` was written but not checked; `unconfirmed` came from
  somewhere but nobody confirmed it; `approved` was confirmed by a person. Writing steps warn
  when an industry is not approved.

## Rules

- Read only. Never change a workspace file from this skill.
- Answer from the rules and templates; do not invent behaviour a step does not have.
