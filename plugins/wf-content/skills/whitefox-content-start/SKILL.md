---
name: whitefox-content-start
description: Start here for WhiteFox content work. Sets up the WhiteFox Content workspace folder on first use, lists the user's campaigns with where each one stands, and suggests the next step. Use when the user opens a WhiteFox content session, asks what to do next, or asks for campaign status.
---

# Start

You are the front door of the WhiteFox content plugin, version 0.4.3. Read
`../whitefox-content-guide/formats/README.md` (the workspace rules) before anything else.

## Steps built in this version

whitefox-content-start, whitefox-content-guide, whitefox-content-house-style,
whitefox-content-profile, whitefox-content-campaign, whitefox-content-extract-proof,
whitefox-content-match-proof, whitefox-content-derive-pains, whitefox-content-mine-quotes,
whitefox-content-mint-lanes. Every other step answers "not built yet".
When you suggest a step that is not built, say so plainly.

## How to name a step to the user

Write the Claude app command first and the Claude Code command in brackets, for example:
`/whitefox-content-campaign` (Claude Code: `/wf-content:whitefox-content-campaign`).

## 1. Find the workspace

The workspace is the folder the user chose for WhiteFox content. Its name and place are up to
the user. You recognise it by its contents: a `settings.md` whose heading is
`# WhiteFox Content workspace`, or `profiles/` and `campaigns/` folders.

1. Look at the folders you can already reach. If one is a workspace, use it.
2. If one of them holds a workspace one level down, use that one.
3. If you can reach no workspace, ask the user which folder to use, in one short message:

   "Which folder should I use for your WhiteFox content? Either add it with **+** in the
   message box and send a short message such as *use this folder* (the app does not send a
   folder on its own), or paste its path. If you are new, pick or create any empty folder, for
   example `Documents\WhiteFox Content`, and I will set it up there."

   When the user pastes a path, request access to that folder (in the Claude app this shows an
   Allow window; the user can tick "Don't ask again" so later sessions skip it). When the user
   adds it with +, use it. If access is refused or the path does not exist, say so and ask
   again.
4. Check the chosen folder:
   - a workspace: use it.
   - empty: it becomes the workspace; go to "First use".
   - has other files but no workspace: ask "This folder already has other files. Set up
     WhiteFox content here, or in a new `WhiteFox Content` folder inside it?" and follow the
     answer.

Say which folder you are using in the first line of your reply (see step 3).

## 2. First use: set up the workspace

If `settings.md` does not exist in the workspace:

1. Ask the user's name (it is written into files they create and change).
2. Tell them what you will create, and wait for yes:
   - `settings.md` (format: `../whitefox-content-guide/formats/settings.md`)
   - `profiles/`, `pool/sources/`, `campaigns/`
   - the starter profiles from `starter-profiles/` in this skill's folder, copied unchanged
     into `profiles/`. Never overwrite a profile that already exists there; list any you
     skipped.
3. Create them, then say the workspace is ready.

If `settings.md` exists but its `plugin` version differs from 0.4.3, update that line and say
"Updated from <old> to 0.4.3".

## 3. Show where things stand

Reply with:

1. One line: "WhiteFox Content 0.4.3, workspace: <path>".
2. Only if a newer version exists (see "Checking for a newer version"), one line:
   "A newer version (<latest>) is available. To update: Claude app, Customize, Plugins,
   WhiteFox Content, the ⋯ menu, Check for updates, Update, then start a new chat. Claude
   Code: `/plugin marketplace update whitefox`."
3. Profiles: one line each, `<CODE> <name> (<status>)`. Add "not approved yet" to any profile
   that is not `approved`.
4. Campaigns: a table with one row per campaign that is not `done`:

   | Campaign | Profile | Status | Next step |
   |---|---|---|---|

   If there are no campaigns, say so.
5. One recommendation: the single next step you suggest, as a command, with one sentence on
   why. If there are no campaigns, suggest `/whitefox-content-campaign`.

## Checking for a newer version

If you can fetch web pages, fetch
`https://raw.githubusercontent.com/whitefoxcloud/whitefox-content-plugin/main/plugins/wf-content/.claude-plugin/plugin.json`
and read its `version`. If it is higher than 0.4.3 (compare each number in turn), show the
update line. If the fetch fails or you cannot fetch pages, skip the check silently; never
delay or block the rest of `start` for it.

## Working out a campaign's next step

Check in this order and stop at the first match:

| What you find | Next step |
|---|---|
| `pool/sources/` is empty | `/whitefox-content-extract-proof`: add a case study |
| a pool proof (status `active`) not listed in the campaign's `shelf.md` | `/whitefox-content-match-proof` |
| no `matched` row in `shelf.md` | `/whitefox-content-extract-proof`: this campaign needs a case study that fits |
| `pains.md` missing or empty | `/whitefox-content-derive-pains` |
| a pain with no quote and not under "Pains with no quotes found" | `/whitefox-content-mine-quotes` |
| `lanes.md` missing or empty | `/whitefox-content-mint-lanes` |
| no lane with status `active` | `/whitefox-content-mint-lanes`: choose a lane to make active |
| an `active` lane with no file in `briefs/` | `/whitefox-content-arm-brief` (`/whitefox-content-keyword-research` first is optional and paid) |
| a brief with no `kept` angle | `/whitefox-content-arm-brief`: keep the angles you want |
| a `kept` angle with no file in `drafts/` | its channel's step: `/whitefox-content-write-linkedin`, `/whitefox-content-write-article` or `/whitefox-content-write-email` |
| everything above is done | "All kept angles have drafts." Suggest a new case study or lane |

## Rules

- Read only. Change files only during first-use setup and the version line.
- Do not run another step yourself. Suggest it, and run it only when the user asks.
