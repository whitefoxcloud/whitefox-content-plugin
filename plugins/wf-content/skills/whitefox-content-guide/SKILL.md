---
name: whitefox-content-guide
description: Explains how the WhiteFox content workflow works, what each step does, where files live in the WhiteFox Content folder, and what the IDs (proof, PAIN, QUOTE, LANE, ANGLE) mean. Use when the user asks how the plugin, workflow, folders or IDs work.
---

# Guide

Answer the user's question about the WhiteFox content workflow. The workspace rules are in
`formats/README.md` in this skill's folder; the template for each file is next to it. Read
them before answering a question about files, IDs or statuses.

If the user asked nothing specific, give the overview below, short, then ask what they want to
know more about.

## The workflow

A case study goes in; LinkedIn posts, articles and emails come out. Every piece of content can
be traced back to something WhiteFox really delivered.

| # | Step | What it does | Writes |
|---|---|---|---|
| 1 | `/whitefox-content-profile` | describes an industry: audience, positioning, words to use and avoid | `profiles/<CODE>.md` |
| 2 | `/whitefox-content-campaign` | starts a campaign on one profile | `campaigns/<name>/campaign.md` |
| 3 | `/whitefox-content-extract-proof` | reads a case study once and lists what WhiteFox really did (proofs) | `pool/sources/<id>.md` |
| 4 | `/whitefox-content-match-proof` | judges which pool proofs fit this campaign | `shelf.md` |
| 5 | `/whitefox-content-derive-pains` | names the buyer problems those proofs solve | `pains.md` |
| 6 | `/whitefox-content-mine-quotes` | finds real buyers saying those problems in public, word for word | `quotes.md` |
| 7 | `/whitefox-content-mint-lanes` | turns pains, proofs and quotes into topics to publish about (lanes) | `lanes.md` |
| 8 | `/whitefox-content-keyword-research` | optional and paid: what people search for on a lane | `keywords.md`, `costs.md` |
| 9 | `/whitefox-content-arm-brief` | plans the pieces for one lane (angles: channel, headline, persona) | `briefs/LANE-nn.md` |
| 10 | `/whitefox-content-write-linkedin`, `/whitefox-content-write-article`, `/whitefox-content-write-email` | writes one piece for a kept angle | `drafts/` |

`/whitefox-content-start` shows where every campaign stands and suggests the next step. `/whitefox-content-house-style` shows the
writing rules every draft follows.

In Claude Code every command starts with `wf-content:`, for example `/wf-content:whitefox-content-start`.

## Things people ask

- **Is anything saved without me?** No. Each step shows its result and waits for your approval.
- **Does it spend money?** Only keyword research, and only after it shows the price and you say
  yes. Every paid call is logged in the campaign's `costs.md`.
- **Why a pool?** A case study is extracted once; every campaign you run reuses its proofs.
- **Can I edit the files myself?** Yes, they are plain text. Keep the headings and IDs as they
  are, or the next step may not find them.
- **What is a profile status?** `draft` was written but not checked; `unconfirmed` came from
  somewhere but nobody confirmed it; `approved` was confirmed by a person. Writing steps warn
  when a profile is not approved.

## Rules

- Read only. Never change a workspace file from this skill.
- Answer from the rules and templates; do not invent behaviour a step does not have.
