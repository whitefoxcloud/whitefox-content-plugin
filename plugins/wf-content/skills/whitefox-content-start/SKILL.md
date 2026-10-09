---
name: whitefox-content-start
description: Start here for WhiteFox content work. Sets up the WhiteFox Content workspace folder on first use, lists the user's campaigns with where each one stands, and suggests the next step. Use when the user opens a WhiteFox content session, asks what to do next, or asks for campaign status.
---

# Start

You are the front door of the WhiteFox content plugin, version 0.15.1. Read
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

If `settings.md` exists but its `plugin` version differs from 0.15.1, update that line and say
"Updated from <old> to 0.15.1".

## 3. Show where things stand

Reply with:

1. One line: "WhiteFox Content 0.15.1, workspace: <path>".
2. Only if a newer version exists (see "Checking for a newer version"), one line:
   "A newer version (<latest>) is available. To update: Claude app, Customize, Plugins,
   WhiteFox Content, the ⋯ menu, Check for updates, Update, then start a new chat. Claude
   Code: `/plugin marketplace update whitefox`."
3. Under the heading **Profiles**, one line each, `<CODE> <name> (<status>)`. Add "not approved yet" to any profile
   that is not `approved`.
4. If there are no campaigns, explain the path once, in this shape, then suggest
   `/whitefox-content-campaign`:

   > How it works: set up a campaign, then three stages, each one command.
   > 1. **Add a case study**: what WhiteFox delivered, checked against your campaign, and the
   >    problems it solves for your audience.
   > 2. **Find topics**: real quotes from your audience, then the topics to write about
   >    (checking search interest is optional).
   > 3. **Write**: a content plan for a topic, then LinkedIn posts, emails and articles.
   > It runs straight through and stops only when there is something for you to review.
   > You can come back to any stage at any time: add another case study, find more topics, or
   > start a new campaign.

5. Under the heading **Your campaigns**, for each campaign that is not `done`, what has been
   made and what is in progress, in this shape (lead with finished work, never hide it behind
   a count):

   > **Your campaigns**
   >
   > **acme-2026-10** (ACME)
   > Made so far: 2 case studies · 11 audience problems · 10 quotes · 8 topics · 3 drafts
   > - Topic 3, *Payment gateway switching costs*: 3 drafts (LinkedIn post, email, article) ✓
   > - Topic 1, *Chargeback handling at scale*: no plan yet

   List the active lanes and any lane with a brief or drafts, with its label from `lanes.md`
   and what it has (see "What the user can do").
6. What the user can do, in one line, with the suggested action first:

   > You can: **write for Topic 1** (suggested), add another case study, find more topics, or
   > start a new campaign.

   Then the suggested command with its Claude Code form, for example
   `/whitefox-content-write` (Claude Code: `/wf-content:whitefox-content-write`).
7. In the Claude app, also show the dashboard page (workspace rules, "The dashboard"), and say
   in one line at the top: "Your **WhiteFox Content dashboard** is open on the right (closed
   it? click its card above). Click a count or a topic to see the list." The page is a
   snapshot; `/whitefox-content-dashboard` (Claude Code: `/wf-content:whitefox-content-dashboard`)
   shows a fresh one any time.

## Checking for a newer version

If you can fetch web pages, fetch
`https://raw.githubusercontent.com/whitefoxcloud/whitefox-content-plugin/main/plugins/wf-content/.claude-plugin/plugin.json`
and read its `version`. If it is higher than 0.15.1 (compare each number in turn), show the
update line. If the fetch fails or you cannot fetch pages, skip the check silently; never
delay or block the rest of `start` for it.

## What the user can do

The three stages are not a one-way road: a campaign can take another case study or more topics
at any time, and the user can start a new campaign whenever they like. So always offer all
three stage commands and "start a new campaign", and mark one as suggested.

What a topic has, for the list in step 5 and the dashboard: count its drafts (files in
`drafts/` whose `lane` is the lane, leaving out `-archived-` files) and name their channels
(LinkedIn post, email, article). Otherwise "plan ready, N kept pieces to write" when it has a
brief, or "no plan yet". A topic is finished (✓) when every kept piece in its brief has a draft.

To pick the suggested action, check in this order; the first match wins.

| What you find | Suggested action | Short reason |
|---|---|---|
| `pool/sources/` is empty | Add a case study | add a case study (attach, paste or link) |
| no `matched` row in `shelf.md` (for example a new campaign) | Add a case study | add a case study for this campaign |
| a pool proof (status `active`) not listed in the campaign's `shelf.md` | Add a case study | N new proofs to check for fit |
| `pains.md` missing or empty | Add a case study | derive the buyer pains |
| a pain with no quote and not under "Pains with no quotes found" | Find topics | N pains still need quotes |
| `lanes.md` missing or empty | Find topics | turn pains and quotes into topics |
| no lane with status `active` | Find topics | choose a topic to work on |
| a brief with a `kept` angle without a file in `drafts/` | Write for Topic <N> | N planned pieces without drafts |
| an `active` lane with no file in `briefs/` | Write for Topic <N> | no plan yet |
| everything above is done | Add another case study | every active topic has its drafts |

The dashboard's `actions` list the suggested one first, then the other stage commands as "Add
another case study" (or "Add a case study" when there is none), "Find more topics" (or "Find
topics") and "Write" (or "Write for Topic <N>").

Stage commands: `/whitefox-content-add-case-study`, `/whitefox-content-find-topics`,
`/whitefox-content-write`. Mention a single step's own command only if the user asks for it.

## Rules

- Read only. Change files only during first-use setup and the version line.
- Do not run another step yourself. Suggest it, and run it only when the user asks.
