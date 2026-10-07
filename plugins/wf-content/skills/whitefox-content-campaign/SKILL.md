---
name: whitefox-content-campaign
description: Create a WhiteFox content campaign on a profile, or pause, resume or finish one, in the WhiteFox Content workspace. Use when the user wants to start a new campaign or change a campaign's status.
---

# Campaign

A campaign belongs to one user and runs on one profile. It reuses every proof in the user's
pool.

## Read first

- `../whitefox-content-guide/formats/README.md` (workspace rules) and `../whitefox-content-guide/formats/campaign.md` (the
  format).
- `settings.md` in the workspace, for the user's name. If the workspace is not set up, tell the
  user to run `/whitefox-content-start` (Claude Code: `/wf-content:whitefox-content-start`) first, and stop.
- The list of `profiles/` (code, name, status) and `campaigns/`.

## Create a campaign

1. Show the profiles as `<CODE> <name> (<status>)` and ask which one. If the right one does not
   exist, suggest `/whitefox-content-profile` (Claude Code: `/wf-content:whitefox-content-profile`) and stop.
2. If the chosen profile is not `approved`, say: "<CODE> is <status>, not approved yet. You can
   go ahead; the writing steps will warn on every draft." Continue only on yes.
3. Ask for a goal in a sentence, or "(none)".
4. Suggest a name: the profile code in lowercase, the year and the month, for example
   `ins-2026-10`. The user may pick another. It must be lowercase words joined by hyphens and
   not already exist in `campaigns/`.
5. Show the `campaign.md` you will save, and wait for yes.
6. Create `campaigns/<name>/` with `campaign.md` only. The other files are created by the steps
   that fill them.
7. Say what comes next: if `pool/sources/` has proofs, `/whitefox-content-match-proof`; if it is empty,
   `/whitefox-content-extract-proof` to add a case study. Give both commands with their Claude Code form.

## Pause, resume or finish a campaign

1. Show the campaign's current status.
2. Change `status` to `paused`, `active` or `done` as the user asks, after a yes.
3. A `done` campaign is hidden from `/whitefox-content-start`; its files stay.

## Rules

- Show the result and wait for approval before saving.
- Never delete a campaign folder or its files. To stop working on one, set it to `done`.
- Never change the profile of an existing campaign. To use another profile, create a new
  campaign.
