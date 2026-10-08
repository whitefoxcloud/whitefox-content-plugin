# Changelog

## 0.14.2

- The write stage stops after a topic's drafts are saved and offers the next chosen topic
  ("Reply **next** to plan it"), instead of starting it on its own.

## 0.14.1

- The write stage asks free or paid search interest for each topic again, in one question that
  shows the DataForSEO price, so replying **paid** also approves the spend ($1.00 cap
  unchanged). Without the DataForSEO connector it offers free or skip and says how to connect.

## 0.14.0

- Far fewer replies: from a new campaign to drafts takes about seven (industry and goal, the
  case study, then one review each for deliveries and problems, topics, the content plan, and
  the drafts), down from about 25.
- Stages run straight through: no "continue?" between steps or stages, and each stage carries
  on into the next. Type **stop** any time.
- Small questions take defaults (public case study, lead route, which pieces to write, free
  search interest check before each content plan). Paid keyword research only when asked, and
  still with its price question.
- Creating a campaign is one question (industry and goal); the name is automatic.
- The draft preview shows several drafts as tabs, so all drafts are reviewed at once.

## 0.13.0

- Dashboard: each campaign folds open and closed. Folded, it shows one line of counts and its
  next step. The most recently worked-on campaign opens first; the page remembers which ones
  you opened. The profiles list is headed "Industries".

## 0.12.2

- Finding audience quotes is one pass with one approval, however many problems there are (no
  more rounds of 6). It searches several problems at once, stops at 2 good quotes or after 2
  searches and 4 page reads per problem, and shows a short progress line every few problems.

## 0.12.1

- Web pages are read with web search and web fetch, not the browser, so the Claude app stops
  asking to allow every website while finding quotes or reading a case study link. The browser
  is used only when a page cannot be read as text and the user agrees.

## 0.12.0

- Step commands renamed to plain words, with plain descriptions in the skill list:
  `profile` is now `industry`, `extract-proof` is `list-deliveries`, `match-proof` is
  `check-fit`, `derive-pains` is `name-problems`, `mine-quotes` is `find-quotes`, `mint-lanes` is
  `choose-topics`, `keyword-research` is `search-interest`, `arm-brief` is `plan-pieces`,
  `house-style` is `writing-rules` (all with the `whitefox-content-` prefix). The main commands
  (start, campaign, add-case-study, find-topics, write, dashboard, show) are unchanged, and so
  are the workspace files.

## 0.11.1

- Starter profiles: plain source line ("WhiteFox starter profile") and shorter approval notes,
  without internal references.

## 0.11.0

- Plain words everywhere the user looks: what we delivered (was proof), audience problem (pain),
  audience quote, topic (lane), content plan (brief), piece (angle), industry (profile), case
  study library (pool), writing rules (house style). Statuses too: idea / chosen topics,
  suggested / planned pieces, "fits this campaign", "search interest". Step names: list what we
  delivered, check what fits, name audience problems, find audience quotes, choose topics, check
  search interest, plan the pieces.
- IDs read as Problem 3, Quote 4, Topic 3, Piece 3, Delivery 2 (Loot); the old IDs still work
  when typed. Files, folders and commands are unchanged, so existing workspaces keep working.
- The workspace rules hold the full word list ("Words the user sees"); the guide explains the
  words to users.

## 0.10.0

- Dashboard: every count opens its list (case studies with their proofs and fit, pains, quotes
  with links, all topics, drafts). Each topic opens to show its stance, the pains and quotes
  behind it, its keywords and its drafts.
- New `/whitefox-content-dashboard`: shows a fresh dashboard any time, read only.
- New `/whitefox-content-show <ID> <campaign>`: shows one saved item; a draft opens in the
  preview page. The dashboard's **Open** button on a draft copies this command.

## 0.9.6

- A new campaign now leads to its own case study first. `whitefox-content-campaign` ends by
  asking for the case study and starts stage 1 in the same chat; it no longer suggests
  matching the pool's existing proofs or single-step commands.
- `whitefox-content-add-case-study`: for a campaign with nothing matched yet, it asks for a
  case study before matching the pool (reply **pool** to check the existing proofs instead).
- `whitefox-content-start`: a campaign with nothing matched suggests "add a case study for
  this campaign" rather than "N new proofs to match".

## 0.9.5

- New look for all pages: neutral surfaces (white and soft grey in light mode, near black in
  dark mode) instead of blue on blue; blue is kept for actions only.
- One colour per stage everywhere: violet for Add a case study, amber for Find topics, green
  for Write. The dashboard's counts carry stage dots with a legend, and the review and preview
  pages' stage pill takes its stage's colour.
- Dashboard: counts as a stat strip; topics with status pills (done in green, in progress in
  blue, no plan yet dashed); the suggested action as a highlighted card with "Copy command",
  other actions as smaller cards with stage icons; approved profiles carry a tick.

## 0.9.4

- Dashboard: topic and action rows get their own lighter background so they stand out from
  the campaign card; each action shows its name and command on two lines with the Copy button
  beside them, so nothing wraps awkwardly in the side panel.
- Workspace rules: the dashboard section now describes the 0.9 data (made, topics, actions);
  it still described the old stage strip, which gave counts like "8 (3 active) topics". Counts
  read "1 case study", "2 case studies", and "+ New campaign" is never repeated as an action.

## 0.9.3

- Starter profiles HC and AI are approved (by Charlotte, 2026-10-08), with industry and
  audience filled in and a specific case study each: Touchstone for HC, RACAS for AI. All four
  starter profiles are now approved. Existing workspaces keep their own copies.

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
