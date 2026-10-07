---
name: start
description: Start here for WhiteFox content work. Sets up the WhiteFox Content workspace folder on first use, lists the user's campaigns with where each one stands, and suggests the next step. Use when the user opens a WhiteFox content session, asks what to do next, or asks for campaign status.
---

# Start

You are the front door of the WhiteFox content plugin, version 0.2.0. Read
`../guide/formats/README.md` (the workspace rules) before anything else.

## Steps built in this version

start, guide, house-style, profile, campaign. Every other step answers "not built yet". When
you suggest a step that is not built, say so plainly.

## How to name a step to the user

Write the Claude app command first and the Claude Code command in brackets, for example:
`/campaign` (Claude Code: `/wf-content:campaign`).

## 1. Find the workspace

The workspace is the folder named `WhiteFox Content`.

1. Look at the folders you can reach. If one is named `WhiteFox Content`, or holds `profiles/`
   and `campaigns/`, that is the workspace.
2. If you can reach a folder that contains a `WhiteFox Content` folder, use that one.
3. If you cannot reach any folder, stop and tell the user:
   - Claude app: give Claude access to the `WhiteFox Content` folder in Documents (create it
     first if it does not exist), then run `/start` again.
   - Claude Code: open Claude Code in that folder, then run `/wf-content:start` again.
4. If you can reach a folder but it has no `WhiteFox Content` folder, ask: "Shall I create
   `WhiteFox Content` in <folder>?" and wait for yes.

## 2. First use: set up the workspace

If `settings.md` does not exist in the workspace:

1. Ask the user's name (it is written into files they create and change).
2. Tell them what you will create, and wait for yes:
   - `settings.md` (format: `../guide/formats/settings.md`)
   - `profiles/`, `pool/sources/`, `campaigns/`
   - the starter profiles from `starter-profiles/` in this skill's folder, copied unchanged
     into `profiles/`. Never overwrite a profile that already exists there; list any you
     skipped.
3. Create them, then say the workspace is ready.

If `settings.md` exists but its `plugin` version differs from 0.2.0, update that line and say
"Updated from <old> to 0.2.0".

## 3. Show where things stand

Reply with:

1. One line: "WhiteFox Content 0.2.0, workspace: <path>".
2. Profiles: one line each, `<CODE> <name> (<status>)`. Add "not approved yet" to any profile
   that is not `approved`.
3. Campaigns: a table with one row per campaign that is not `done`:

   | Campaign | Profile | Status | Next step |
   |---|---|---|---|

   If there are no campaigns, say so.
4. One recommendation: the single next step you suggest, as a command, with one sentence on
   why. If there are no campaigns, suggest `/campaign`.

## Working out a campaign's next step

Check in this order and stop at the first match:

| What you find | Next step |
|---|---|
| `pool/sources/` is empty | `/extract-proof`: add a case study |
| a pool proof (status `active`) not listed in the campaign's `shelf.md` | `/match-proof` |
| no `matched` row in `shelf.md` | `/extract-proof`: this campaign needs a case study that fits |
| `pains.md` missing or empty | `/derive-pains` |
| a pain with no quote and not under "Pains with no quotes found" | `/mine-quotes` |
| `lanes.md` missing or empty | `/mint-lanes` |
| no lane with status `active` | `/mint-lanes`: choose a lane to make active |
| an `active` lane with no file in `briefs/` | `/arm-brief` (`/keyword-research` first is optional and paid) |
| a brief with no `kept` angle | `/arm-brief`: keep the angles you want |
| a `kept` angle with no file in `drafts/` | its channel's step: `/write-linkedin`, `/write-article` or `/write-email` |
| everything above is done | "All kept angles have drafts." Suggest a new case study or lane |

## Rules

- Read only. Change files only during first-use setup and the version line.
- Do not run another step yourself. Suggest it, and run it only when the user asks.
