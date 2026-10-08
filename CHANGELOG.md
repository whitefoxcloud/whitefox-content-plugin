# Changelog

## 0.9.2

- Starter profile INS is approved (by Charlotte, 2026-10-08). Its keyword "insurance portal"
  is now "insurance systems integration", since "broker portal" is on its never-position-as
  list. Existing workspaces keep their own copy; update it with `whitefox-content-profile`.

## 0.9.1

- Pages: the reply now says the page is open on the right and its card is above (it said
  "click the card below", but the panel opens on its own and the card sits above the reply).
- `whitefox-content-start` and the dashboard put the campaigns under a **Your campaigns**
  heading.

## 0.9.0

- `whitefox-content-start` and the dashboard show what has been made first: counts, then each
  topic in progress with its drafts (for example "3 drafts: LinkedIn post, email, article") or
  "no plan yet". The one-way "you are here" stage strip is gone.
- Every campaign now offers all three stage commands (add another case study, find more
  topics, write), with one marked suggested, and the dashboard has a "+ New campaign" button.
- Started drafts come before planning a new topic when choosing the suggestion.
- Dark mode pages: a darker page background so cards and topic rows stand out; lighter page
  background in light mode too.

## 0.8.1

- Pages carry the real whitefox.cloud logo (its text black on light backgrounds, white on
  dark; the fox always brand blue) and the brand colours from the WhiteFox Figma: primary
  `#005DE5`, background navy `#152D51`, black and white. Dark mode uses the brand navy.

## 0.8.0

- One chat style for every step: stage banner, result card with numbered items, notes to
  check, and the reply line last.
- Pages in WhiteFox's colours and font (Bai Jamjuree, brand blue): the review page gains a
  stage header; new draft preview page (LinkedIn post, email or article as it will look, with
  copy buttons and a search-result preview with title and description lengths); new campaign
  dashboard from `whitefox-content-start` (stages, counts, next command). Pages never save;
  saving stays in the chat.

## 0.7.0

- Three stage commands, so users need four commands in all: `whitefox-content-add-case-study`
  (extract, match, pains), `whitefox-content-find-topics` (quotes, lanes, optional keywords)
  and `whitefox-content-write` (brief, then drafts). Each runs its steps in one conversation,
  skips what is done, and carries on where the user stopped. The detailed steps still work on
  their own.
- `whitefox-content-start` shows each campaign as a stage map with "you are here" and the next
  command, and explains the path to new users.
- Every step opens with where the user is, what it does, what they decide and its limits.
- Keywords: `target` (several per lane; each article aims at one) and `supporting` replace
  primary and secondary; older files still read. The review page can start each row on a
  suggested choice.

## 0.6.1

- house-style: a draft says what the case study says WhiteFox did, and never presents a
  checklist, order of checks or method as what WhiteFox used unless the case study states it;
  the checklist tests this.
- LinkedIn and email drafts get a label heading, so the copyable text does not repeat the hook.

## 0.6.0

- The brief and writing steps are built: arm-brief (5 to 8 angles per lane within the lane's
  claim ceiling, keyword only on articles, persona only on LinkedIn, review page with keep,
  later and drop), write-linkedin, write-email and write-article (plan approved first, then the
  article). Each draft lists the proofs and quotes it relies on and passes the house-style
  checklist before it is shown.
- house-style: how drafts use proofs, quotes, claim levels and flags; article length 1200 to
  1800 words usually, never over 2200.

## 0.5.2

- mint-lanes: search phrases are short search terms people type, not sentences from complaints;
  the category phrase is the broad term most likely to have search data.
- keyword-research: says where real spend is visible (the DataForSEO dashboard; the connector
  reports no costs) and explains an all-empty result as phrases too narrow, offering broader
  phrases or free mode.

## 0.5.1

- keyword-research uses the DataForSEO connector's own tools (DataForSEO Labs Google Keyword
  Overview, DataForSEO Labs Google Related Keywords, SERP Organic Live Advanced); the connector
  in the Claude app has one tool per service, not a single `api_request` tool.
- Colleague guide: set the connector's tools to ask first, and turn off all but those three.

## 0.5.0

- keyword-research is built: for one active lane, three DataForSEO services through the
  DataForSEO connector (keyword overview, related keywords, one Google results page), price
  shown and approved first, never more than $1.00 per lane per run, every call logged in
  `costs.md` with the actual cost or `unknown`. The verdict (none, some, strong) updates the
  lane's Demand. No login is ever stored in the plugin or the workspace.
- keyword-research free mode: without DataForSEO (or by choice), web search collects the
  phrasing and questions buyers use, with links; search numbers stay `unknown`.
- Price table uses DataForSEO's list prices of 2026-10-07 (about $0.06 per lane).

## 0.4.3

- Review page: the card is named after what it reviews ("Review: lanes for ..."), and Claude
  says to click it. Rows can have more than two choices: lanes offer keep, active and drop.
- mine-quotes: a quote read through a copy keeps the original page's link.
- mint-lanes: a quote variant is the whole quote with only names replaced, never a fragment.

## 0.4.2

- Review page: in the Claude app, results with 3 or more items also open as a page with keep,
  drop, edit and add on each row; copy your choices back into the chat.
- Every approval question says how to save or change, with examples.
- extract-proof: fields are whole sentences copied from the case study; no spliced fragments,
  no summary of its own; marketing and future-work sentences left out.
- derive-pains: a passing mention in a proof does not count as backing.
- start: says that a folder added with + needs a short message to send.

## 0.4.1

- The workspace can be any folder, with any name. When no workspace is attached,
  `whitefox-content-start` asks which folder to use (add it with + or paste its path) and
  requests access to it.

## 0.4.0

- The evidence steps are built: extract-proof, match-proof, derive-pains, mine-quotes and
  mint-lanes, carrying the WhiteFox content app's rules.
- `whitefox-content-start` says when a newer version is on GitHub and how to update.
- Formats: a proof keeps the case study's own words; the campaign wording for it moves to the
  shelf. A pain may be backed by `gap`. Quotes gain a tier; lanes gain quote variants and flags.
  Every step begins the same way (see `formats/README.md`).

## 0.3.0

- Every step is renamed with the `whitefox-content-` prefix, so WhiteFox commands are easy to
  find and cannot clash with other plugins: `/whitefox-content-start` in the Claude app,
  `/wf-content:whitefox-content-start` in Claude Code.

## 0.2.0

- `start` sets up the workspace folder on first use (settings, folders, starter profiles),
  lists profiles and campaigns, and suggests each campaign's next step.
- `guide`, `house-style`, `profile` and `campaign` are built.
- Workspace formats: rules and one template per file in `skills/guide/formats/`.
- Starter profiles gained `changed_by` and `changed`.

## 0.1.0

- Skeleton: marketplace, the `wf-content` plugin, a working `start` skill, and placeholders for
  every workflow step.
- Starter profiles FIN, INS, HC and AI, transcribed from the WhiteFox content app.
