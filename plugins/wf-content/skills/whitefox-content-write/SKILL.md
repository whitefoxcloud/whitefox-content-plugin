---
name: whitefox-content-write
description: Stage 3 of 3 of the WhiteFox content workflow. Plans the pieces for a chosen topic (the content plan) and writes all the drafts - LinkedIn posts, emails and articles - with one review for the plan and one for the drafts. Use when the user wants content written, drafts, posts, emails or articles for a campaign.
---

# Write (stage 3 of 3)

Plans the pieces for one chosen topic, then writes every planned piece, as the workspace rules
say in "Running straight through". The user replies three times: free or paid search interest,
the content plan, and the drafts.

| Step | What it does |
|---|---|
| 1 of 2, plan the pieces | checks search interest for the topic (free or paid, the user chooses), then proposes 5 to 8 pieces (the content plan): channel, headline, voice, evidence |
| 2 of 2, write the drafts | writes every planned piece in its channel |

## Before you start

1. Read `../whitefox-content-guide/formats/README.md` and begin as it says (workspace,
   settings, campaign, profile).
2. If the campaign has no chosen (`active`) topic, say stage 2 comes first and carry on with
   `../whitefox-content-find-topics/SKILL.md`.
3. Topic: if the user named one, use it. Otherwise the first chosen topic without a content
   plan, or with planned pieces still to write; say which in one line.
4. Work out where to start:
   - The topic has no content plan, or the user asks for more pieces: step 1.
   - The content plan has planned pieces without drafts: step 2.
   - Every planned piece has a draft: say so, and carry on with the next chosen topic, or end.
5. One line with the limits: "LinkedIn posts are 110 to 180 words, emails 80 to 150, articles
   1200 to 1800 and each aims at one main keyword. Type **stop** any time."

## Step 1: plan the pieces

1. If the topic has no section in `keywords.md`, check its search interest first with
   `../whitefox-content-search-interest/SKILL.md`, asking free or paid in one question:
   - With the DataForSEO connector: work out the paid plan and price as that file says, then
     ask: "Search interest for Topic <n> (<country>): **free** (web search: the questions and
     phrasing people use, no numbers) or **paid** (DataForSEO: <N> calls, about $<X>, real
     monthly searches; an estimate from list prices, not a hard limit)? Replying **paid**
     approves that spend." This is the paid mode's price question: **paid** is its explicit
     yes, and the $1.00 cap still applies. The user may name another market in the reply.
   - Without the connector, still ask, so the user knows the choice exists: "Search interest
     for Topic <n>: I can do the **free** check (questions and phrasing, no numbers). The paid
     DataForSEO check needs the company login connected in your Claude app (see the README,
     one-time setup). Reply **free**, or **skip**."
   Keep the result for the plan. On **skip**, plan without keywords.
2. Follow `../whitefox-content-plan-pieces/SKILL.md`, using that result, without its "Next".

Its review is the first of the two: **Stage 3 of 3, Write: review the content plan.** Show the
search interest found (main and extra keywords, top questions) in two or three lines above the
pieces. The review page holds the pieces with `choice` `["planned", "later", "drop"]`. On save,
write the keywords section to `keywords.md`, then the content plan to `briefs/LANE-nn.md`.

## Step 2: write the drafts

Write every planned piece without a draft, straight through, LinkedIn posts first, then
emails, then articles. Follow each channel's file exactly, except: skip its "which piece"
question, its own "Show and approve" and "Next", and (for articles) the separate plan
approval. Use the defaults in "Running straight through". One progress line per draft: "Wrote
Piece 3, LinkedIn post (164 words)."

| Channel | File |
|---|---|
| linkedin-post | `../whitefox-content-write-linkedin/SKILL.md` |
| email | `../whitefox-content-write-email/SKILL.md` |
| website-article | `../whitefox-content-write-article/SKILL.md` |

Then the second review: **Stage 3 of 3, Write: review the drafts.** One preview page with every
draft as a tab (the preview's `drafts` list; an article's SEO title, meta description and slug
go in its `seo`). In the chat, per draft: Piece N, channel, word count, and any writing-rules
check that did not pass. Reply line: "Reply **save** for all, or tell me what to change, for
example: *Piece 3: shorter*, *Piece 5: softer ask*, *drop Piece 1*." Apply changes, show the
changed drafts again, and save every draft on yes.

## Then

One line: "Done for Topic <n>, <label>: <N> drafts saved in `drafts/`." If another chosen topic
has no content plan, carry on with it ("Next: Topic <m>, <label>."). Otherwise end with
`/whitefox-content-dashboard` to see everything.

## Rules

- Every step's own rules apply in full, including the writing-rules checklist on every draft;
  this file only joins them.
- Nothing is saved before its review's yes.
