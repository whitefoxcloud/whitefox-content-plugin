---
name: whitefox-content-write-email
description: Write a WhiteFox outbound email for a kept email angle of a lane's brief - subject options, preview text, a short body and one call to action - following house style and the lane's evidence, and save it as a draft. Use when the user wants an outbound or sales email written.
---

# Write email

Writes one outbound email for one kept `email` angle. The goal is to invite a qualified buyer
into a low-effort next step (a short workflow review, a case study, or a reply), sounding like
a useful specialist, not an automated sequence.

## Read first

- `../whitefox-content-guide/formats/README.md`, then begin as it says (workspace, settings,
  campaign, profile).
- `../whitefox-content-guide/formats/draft.md` (the format).
- `../whitefox-content-writing-rules/SKILL.md`, all of it: rules, evidence use, checklist.
- The campaign's `briefs/`, `lanes.md`, `quotes.md`, `shelf.md` and `drafts/`; the pool files of
  the proofs the angle uses.

## 1. Pick the angle

Kept `email` angles with no live draft in `drafts/`. If the user names an angle, use it. With
several and none named, list them (ID, headline) and ask which. If the chosen angle already has
a live draft, ask whether to write a new take; on yes, the old file is archived when the new
one is saved.

Ask which lead route fits, from the profile's lead routes (for example the case study, or a
workflow review), unless the angle makes it obvious.

## 2. Write

- Subject options: 2 or 3, short, specific to the pain, no clickbait.
- Preview text: one line that adds to the subject, not a repeat.
- Body: 80 to 150 words, never over 170. Short, direct paragraphs. The reason for writing is
  clear in the first two lines.
- Personalise only with placeholders (`[first name]`, `[company]`). Never pretend to know the
  recipient, and never say they have a problem: use conditional wording ("if your team...").
- One call to action, easy to say yes or no to, tied to the pain and the proof.
- Evidence, claim level, quotes and flags: as in house style, "Using evidence in a draft".
  Never invent metrics, outcomes, compliance guarantees or AI capabilities.
- Sign-off: `[sender name]`, `[role]`. The sender is the user's choice, not a persona.
- Never use: hope this email finds you well, just checking in, bumping this to the top of your
  inbox (house style lists the rest).
- Run the writing-rules checklist. Fix what fails.

## 3. Show and approve

1. If the profile is not `approved`, say so first (checklist). In the Claude app, show the
   draft preview page (workspace rules, "The draft preview").
2. Subject options, preview text, body, sign-off; the body's word count; "Built from"; the
   checklist.
3. Ask: "Reply **save**, or tell me what to change, for example: *softer ask*, *lead with the
   case study*, *third subject line*." Apply changes and show the email again.
4. On yes: if this is a new take, rename the old file to
   `ANGLE-nn-email-archived-<YYYY-MM-DD>.md`. Save `drafts/ANGLE-nn-email.md` in the format,
   status `draft`, `written_by` the user's name.

## Change a draft's status

If the user asks to mark a draft `approved`, `published` or `archived` (for example "mark
ANGLE-03 published"), show its current status, change the `status` line after a yes, and stop.

## Next

Other kept angles of the brief, or `/whitefox-content-start` to see where things stand.

## Rules

- Nothing is saved before the user's yes.
- No claim beyond the angle's proofs and claim level.
