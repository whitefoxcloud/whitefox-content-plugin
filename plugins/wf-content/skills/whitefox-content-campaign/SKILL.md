---
name: whitefox-content-campaign
description: Create a WhiteFox content campaign for one industry, or pause, resume or finish one, in the WhiteFox folder. Use when the user wants to start a new campaign or change a campaign's status.
---

# Campaign

A campaign belongs to one user and runs on one industry (a profile in the files). It reuses
everything in the user's case study library.

## Read first

- `../whitefox-content-guide/formats/README.md` (workspace rules) and `../whitefox-content-guide/formats/campaign.md` (the
  format).
- `settings.md` in the workspace, for the user's name. If the workspace is not set up, tell the
  user to run `/whitefox-content-start` (Claude Code: `/wf-content:whitefox-content-start`) first, and stop.
- The list of `profiles/` (code, name, status) and `campaigns/`.

## Create a campaign

One question, one answer:

1. Ask in one message: "Which industry, and what's the goal? For example: *INS, start
   conversations with insurance operations leaders in Australia*." List the industries as
   `<CODE> <name>`, adding "(not approved yet)" where it applies. If the user already gave
   the industry or goal, do not ask for it again. If the right industry does not exist,
   suggest `/whitefox-content-industry` (Claude Code: `/wf-content:whitefox-content-industry`)
   and stop. The goal may be "(none)".
2. Name it yourself: the industry code in lowercase, the year and the month, for example
   `ins-2026-10`; add `-2`, `-3` if that name exists.
3. Save `campaigns/<name>/campaign.md` straight away (the reply was the approval). If the
   industry is not approved, add one line: "<CODE> is not approved yet; drafts will carry a
   warning."
4. Reply in one message: "✓ Campaign <name> created for <industry>. Saved to
   `campaigns/<name>/campaign.md`; to rename it or change the goal, just say so." Then ask for
   the case study (first refresh the dashboard if it is open in this chat; workspace rules,
   "Keeping the dashboard fresh"):

   > Next: attach the case study for <name>, paste its text, or paste its link, and I'll take
   > it from there.

   If the case study library already has deliveries, add: "Or reply **library** to check the
   <N> deliveries already in your case study library." When the user replies, follow
   `../whitefox-content-add-case-study/SKILL.md`.
   Never suggest or offer a case study yourself (not from the industry's links or lead routes);
   the user chooses it.

## Pause, resume or finish a campaign

1. Show the campaign's current status.
2. Change `status` to `paused`, `active` or `done` as the user asks.
3. A `done` campaign is hidden from `/whitefox-content-start`; its files stay.

## Rules

- Never delete a campaign folder or its files. To stop working on one, set it to `done`.
- Never change the industry of an existing campaign. To use another, create a new campaign.
