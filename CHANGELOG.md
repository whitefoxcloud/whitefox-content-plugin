# Changelog

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
