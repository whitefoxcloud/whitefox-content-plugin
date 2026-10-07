---
name: whitefox-content-start
description: Start here for WhiteFox content work. Sets up the WhiteFox Content workspace folder on first use, lists the user's campaigns with where each one stands, and suggests the next step. Use when the user opens a WhiteFox content session, asks what to do next, or asks for campaign status.
---

# Start

You are the front door of the WhiteFox content plugin, version 0.7.0. Read
`../whitefox-content-guide/formats/README.md` (the workspace rules) before anything else.

## Steps built in this version

All steps are built.

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

If `settings.md` exists but its `plugin` version differs from 0.7.0, update that line and say
"Updated from <old> to 0.7.0".

## 3. Show where things stand

Reply with:

1. One line: "WhiteFox Content 0.7.0, workspace: <path>".
2. Only if a newer version exists (see "Checking for a newer version"), one line:
   "A newer version (<latest>) is available. To update: Claude app, Customize, Plugins,
   WhiteFox Content, the ⋯ menu, Check for updates, Update, then start a new chat. Claude
   Code: `/plugin marketplace update whitefox`."
3. Profiles: one line each, `<CODE> <name> (<status>)`. Add "not approved yet" to any profile
   that is not `approved`.
4. If there are no campaigns, explain the path once, in this shape, then suggest
   `/whitefox-content-campaign`:

   > How it works: set up a campaign, then three stages, each one command.
   > 1. **Add a case study**: what WhiteFox delivered, matched to your campaign, and the buyer
   >    problems it solves.
   > 2. **Find topics**: real buyer quotes, then the topics to write about (keyword research
   >    optional).
   > 3. **Write**: a plan of pieces for a topic, then LinkedIn posts, emails and articles.
   > Every step shows its result and waits for your yes before saving.

5. For each campaign that is not `done`, a map of the stages with where it stands:

   > **acme-2026-10** (ACME)
   > Setup ✓ · 1 Add a case study ✓ · 2 Find topics ✓ · **3 Write ← you are here**
   > Next: `/whitefox-content-write`, LANE-03 has 2 kept pieces without drafts.

   ✓ marks a finished stage; the arrow marks the stage to work on (see "Where a campaign
   stands"). The Next line gives the stage command and one short reason.
6. One recommendation: the single next command you suggest, with its Claude Code form.

## Checking for a newer version

If you can fetch web pages, fetch
`https://raw.githubusercontent.com/whitefoxcloud/whitefox-content-plugin/main/plugins/wf-content/.claude-plugin/plugin.json`
and read its `version`. If it is higher than 0.7.0 (compare each number in turn), show the
update line. If the fetch fails or you cannot fetch pages, skip the check silently; never
delay or block the rest of `start` for it.

## Where a campaign stands

Check in this order; the first match is the stage to work on, every stage before it is ✓.

| What you find | Stage | Next line says |
|---|---|---|
| `pool/sources/` is empty | 1 Add a case study | add a case study (attach, paste or link) |
| a pool proof (status `active`) not listed in the campaign's `shelf.md` | 1 Add a case study | N new proofs to match |
| no `matched` row in `shelf.md` | 1 Add a case study | this campaign needs a case study that fits |
| `pains.md` missing or empty | 1 Add a case study | derive the buyer pains |
| a pain with no quote and not under "Pains with no quotes found" | 2 Find topics | N pains still need quotes |
| `lanes.md` missing or empty | 2 Find topics | turn pains and quotes into topics |
| no lane with status `active` | 2 Find topics | choose a topic to work on |
| an `active` lane with no file in `briefs/` | 3 Write | plan the pieces for <lane> |
| a brief with a `kept` angle without a file in `drafts/` | 3 Write | <lane> has N kept pieces without drafts |
| everything above is done | all ✓ | all kept pieces have drafts; add a case study or plan more pieces |

Stage commands: `/whitefox-content-add-case-study`, `/whitefox-content-find-topics`,
`/whitefox-content-write`. Mention a single step's own command only if the user asks for it.

## Rules

- Read only. Change files only during first-use setup and the version line.
- Do not run another step yourself. Suggest it, and run it only when the user asks.
