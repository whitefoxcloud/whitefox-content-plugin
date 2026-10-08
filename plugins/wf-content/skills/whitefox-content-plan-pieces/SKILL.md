---
name: whitefox-content-plan-pieces
description: Plan the content pieces for one chosen WhiteFox topic (the content plan): channel, type, headline, who posts it, main keyword, and the deliveries and quotes each piece uses. Use when the user wants a content plan, content ideas or pieces for a topic.
---

# Arm brief

A brief holds the planned pieces for one lane. Each piece is an angle: one channel (LinkedIn
post, website article or email), one type, one working headline, and the evidence it uses. This
step proposes angles from the lane's evidence only; it invents no proof, quote or keyword.

## Read first

- `../whitefox-content-guide/formats/README.md`, then begin as it says (workspace, settings,
  campaign, profile).
- `../whitefox-content-guide/formats/brief.md` (the format).
- `../whitefox-content-writing-rules/SKILL.md`, its "Posting personas" section.
- The campaign's `lanes.md`, `shelf.md`, `quotes.md`, `keywords.md` (if it exists) and
  `briefs/` (every brief, for angle numbering and earlier angles).
- For each proof the lane cites: its pool file (Problem, Solution, Outcome, Metric) and its
  shelf wording.

## 1. Pick the lane

The lane must be `active` and have a Type. If the user names a lane that is not active, say so
and suggest `/whitefox-content-choose-topics` to make it active. With several active lanes and
none named, list them and ask which.

If `briefs/LANE-nn.md` exists, this is a re-arm: show its angles in one line each and propose
only new angles that are clearly different from them.

## 2. What the lane allows

- **Claim ceiling.** `full-stack` and `silent-authority` lanes allow `pitch`; a
  `commentary-only` lane allows only `none`.
- A `pitch` section angle needs claim level `pitch` or `soft` AND at least one proof in Uses:
  no proof, no pitch. A `talk` section angle has claim level `none`.
- **Silent-authority** lanes: frame every angle as "what we learned shipping this", never
  "everyone is complaining".
- **Flags** on the lane (voice only, permission) carry into every angle: a voice-only idea is
  discussed through its quote, never claimed.
- **Adjacent quotes** are texture, never framed as this campaign's own buyers speaking. Prefer
  in-domain quotes for hooks.

## 3. Propose angles

Propose 5 to 8 angles: the strongest, most distinct pieces the evidence supports. Fewer is fine
when the evidence is thin; never pad.

1. **Could we build it.** Every angle's problem ends somewhere software-shaped: the reader
   should finish thinking "this is the kind of thing custom software fixes". No advice in
   someone else's profession (no accounting, legal or medical advice). An idea that fails this
   is skipped with a reason.
2. **Written to the buyer.** Every angle speaks to the profile's audience, the software
   decision maker. Quotes are evidence the pain is real, never the voice the piece is written
   in.
3. **Channels.** Mix channels where the evidence supports it. Without keyword data for this lane
   (no section in `keywords.md`, or a verdict of `none`), prefer LinkedIn posts and emails, and
   justify any article in its Why.
4. **Keyword** only on website-article angles: exactly one `target` keyword from this lane's
   `keywords.md` section, with its country, or `(none)`. Different articles may aim at
   different target keywords; no two articles in the campaign aim at the same one. **Supporting**:
   up to 3 `supporting` keywords from the same section that fit the piece. Never on LinkedIn or
   email. (Older `keywords.md` files say `primary` and `secondary`: read them as target and
   supporting.)
5. **Persona** required on LinkedIn angles: `company`, `founder` or `engineer`, chosen to fit the
   angle's voice (house style). Never on articles or emails.
6. **Answers** may only cite questions listed in this lane's `keywords.md` section, word for
   word.
7. **Uses** cites only proofs and quotes this lane cites. Mark a quote `(neutral)` when the
   piece must use the lane's neutral variant of it.
8. **Headline**: a working headline a person would click, true to the stance, with no number
   the evidence does not hold.
9. **Skips**: list ideas you considered and did not plan, with the reason. Skipping is a
   correct answer.

Number new angles after the highest ANGLE in any brief of this campaign.

## 4. Show and approve

1. One block per angle with every field, then the skipped ideas.
2. Review page: `choice` `["keep", "later", "drop"]`. `keep` saves the angle as `kept`,
   `later` as `proposed`, `drop` as `dropped`. Typed replies work too ("keep 1, 3 and 5, drop
   2").
3. On yes, save `briefs/LANE-nn.md` (create it, or add the new angles and skips to it), with
   `armed` set on first creation only.

## Next

For each kept angle, its writing step: `/whitefox-content-write-linkedin`,
`/whitefox-content-write-article` or `/whitefox-content-write-email`.

## Rules

- Nothing is saved before the user's yes.
- Cite only IDs, keywords and questions that exist in the workspace for this lane.
- Never change the lane, its evidence or another brief from this step.
