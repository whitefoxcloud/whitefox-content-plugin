---
name: whitefox-content-profile
description: Create a new WhiteFox industry profile or change an existing one (audience, positioning, never-position-as, lead routes, brand and exclude terms, quote and keyword vocabulary) in the WhiteFox Content workspace. Use when the user wants to add, edit, approve or look at a profile.
---

# Profile

A profile describes one industry WhiteFox sells into. Campaigns use one profile each. Any user
may create or change a profile.

## Read first

- `../whitefox-content-guide/formats/README.md` (workspace rules) and `../whitefox-content-guide/formats/profile.md` (the
  format).
- `settings.md` in the workspace, for the user's name. If the workspace is not set up, tell the
  user to run `/whitefox-content-start` (Claude Code: `/wf-content:whitefox-content-start`) first, and stop.
- Every file in `profiles/`.

## Look at a profile

If the user only wants to see one, show it in full and stop.

## Create a profile

1. Ask for the industry name and a code (2 to 5 capital letters). Refuse a code that already
   exists in `profiles/`; offer to change that profile instead.
2. Ask what the user already has: a case study link, the WhiteFox site, notes, or nothing.
3. Fill the fields from what they gave you. Where they gave nothing, you may draft a field
   from the case study or the site (read them with web access if you have it). Never invent
   facts about WhiteFox, its clients or its results. A field you cannot fill is `unknown`.
4. Show the whole profile in the format and list which fields you drafted and which came from
   the user.
5. Ask the user to correct anything, then ask: "Save as draft?" Save on yes as
   `profiles/<CODE>.md` with status `draft`, `changed_by` the user's name, `changed` today.

## Change a profile

1. Show the fields the user wants to change, as they are now.
2. Write the new version of those fields only. Show before and after, side by side or as two
   short lists.
3. Save on yes. Update `changed_by` and `changed`. Leave every other field exactly as it was.
4. If the profile was `approved` and a field other than the approval note changed, set status
   back to `unconfirmed` and say so, unless the user says the change is approved too.

## Approve a profile

Only when the user says the profile is approved (by them or by a named person):

1. Set status `approved`.
2. Add to the approval note: who approved, which fields, today's date.
3. Show the changed lines and save on yes.

Never set `approved` on your own judgement.

## Rules

- Show the result and wait for approval before saving.
- One profile per file; never touch another profile's file.
- Warn if a field still reads `[placeholder]` or `unknown`: writing steps cannot use it.
