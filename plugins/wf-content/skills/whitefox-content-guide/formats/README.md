# Workspace formats

The rules every step follows when it reads or writes the workspace folder. Each file in this
folder is the template for one kind of workspace file.

## Layout

The workspace is any folder the user chooses (`WhiteFox Content` below is only an example name).

```
WhiteFox Content/
  settings.md                       settings.md
  profiles/
    <CODE>.md                       profile.md
  pool/
    sources/
      <source-id>.md                source.md
  campaigns/
    <campaign-name>/
      campaign.md                   campaign.md
      shelf.md                      shelf.md
      pains.md                      pains.md
      quotes.md                     quotes.md
      lanes.md                      lanes.md
      keywords.md                   keywords.md
      briefs/LANE-nn.md             brief.md
      drafts/ANGLE-nn-<channel>.md  draft.md
      costs.md                      costs.md
```

## Every step begins the same way

1. Find the workspace as `whitefox-content-start` does (its section 1 in
   `../../whitefox-content-start/SKILL.md`): any folder the user chose, recognised by a
   `settings.md` headed `# WhiteFox Content workspace`, or by `profiles/` and `campaigns/`. If
   no workspace is reachable, ask the user for the folder the same way. If the chosen folder
   has no `settings.md`, tell the user to run `/whitefox-content-start` (Claude Code:
   `/wf-content:whitefox-content-start`) first, and stop.
2. Read `settings.md` for the user's name.
3. Steps that work on a campaign: if the user named one, use it. Otherwise list the campaigns
   with status `active`; with exactly one, use it and say so; with several, ask which.
4. Read the campaign's `campaign.md` and its profile in `profiles/`.
5. Open your first reply with where the user is and what this step asks of them, in at most
   three short lines, before any work or question:

   > **Stage 1 of 3, Add a case study: step 2 of 3, check what fits.**
   > What it does: checks which of the things we delivered, in your case study library, fit
   > this campaign's audience.
   > What you'll decide: keep or reject each one, and its one-line wording.

   Name the step's limits here when it has any (for example "each article aims at one target
   keyword", "at most 3 quotes per pain", "never more than $1.00 per lane"), so the user is
   never surprised by a rule later. The stages are in "The stages".

## Words the user sees

Users are not technical. In every chat reply and on every page, use the words in the right
column, never the left. The left column stays inside the files (headings, field names, file
and folder names, IDs on disk) so existing workspaces keep working. Read the user's words both
ways: "Topic 3", "LANE-03" and "lane 3" are the same thing.

| In the files | Say to the user |
|---|---|
| workspace | your WhiteFox folder |
| profile | industry (for example "the INS industry, Insurance / insurtech") |
| pool, source | case study library, case study |
| proof | what we delivered; one item: delivery |
| testimonial | testimonial |
| shelf; matched / rejected | fits this campaign / doesn't fit |
| transfer: direct / cross-industry | same industry / carries over from another industry |
| pain | audience problem (short: problem) |
| "Pains with no quotes found" | problems with no quotes found |
| quote | audience quote (short: quote) |
| domain: in-domain / adjacent | from this industry / from a nearby field |
| tier: tier1 / tier2 | anonymous person / named executive |
| lane | topic |
| lane status: candidate / active | idea / chosen |
| lane type: full-stack / silent-authority / commentary-only | backed by our work and audience quotes / backed by our work only / audience quotes only (we don't claim to solve it) |
| stance | our point of view |
| search phrases | search phrases |
| demand: none / some / strong / unknown | search interest: low / some / high / not checked |
| keyword use: target / supporting | main keyword / extra keyword |
| brief | content plan |
| angle | piece |
| angle status: proposed / kept / dropped | suggested / planned / dropped |
| section: pitch / talk | sales / expertise |
| claim level: pitch / soft / none | names WhiteFox / hints at WhiteFox / no mention |
| persona: company / founder / engineer | posted as the company / founder / engineer |
| house style | writing rules |

Step names, as the user sees them:

| Step | Say |
|---|---|
| list-deliveries | list what we delivered |
| check-fit | check what fits |
| name-problems | name audience problems |
| find-quotes | find audience quotes |
| choose-topics | choose topics |
| search-interest | check search interest |
| plan-pieces | plan the pieces |
| write-linkedin, write-email, write-article | write the drafts |

IDs, as the user sees them: `PAIN-03` is **Problem 3**, `QUOTE-04` is **Quote 4**, `LANE-03` is
**Topic 3**, `ANGLE-03` is **Piece 3**, and `loot-P02` is **Delivery 2 (Loot)** (the source's
`name` or `client`, shortened). File paths are the one exception: when you name a saved file,
show its real path.

## The stages

What the user sees is three stages after setup. Each stage command runs its steps one after the
other in the same conversation; each step can also be run on its own.

| Stage | Command | Steps, in order |
|---|---|---|
| Setup | `/whitefox-content-start` | workspace, then `profile` and `campaign` when needed |
| 1 of 3, Add a case study | `/whitefox-content-add-case-study` | list what we delivered (list-deliveries), check what fits (check-fit), name audience problems (name-problems) |
| 2 of 3, Find topics | `/whitefox-content-find-topics` | find audience quotes (find-quotes), choose topics (choose-topics), check search interest (search-interest, optional) |
| 3 of 3, Write | `/whitefox-content-write` | plan the pieces (plan-pieces), then write the drafts (write-linkedin, write-email or write-article) for each planned piece |

When a step runs on its own (not from its stage command), still name its stage and step
number in the opening lines.

## Chat style

Every step's replies look the same, so the plugin feels like one product:

1. **Banner**: the stage line in bold, then "What it does" and "What you'll decide" (see "Every
   step begins the same way"). Only in the first reply of a step.
2. **Result card**: a `###` heading naming the result ("### 8 topics for fin-2026-10"), one
   summary line with the counts, then the numbered items. Each item: its ID and name in bold
   on the first line, then its fields as short `Label: value` lines. Use a table only when
   every item has the same three to six short fields (a keyword table, what fits).
3. **Notes**: anything the user should check, as a short list under "Check before saving", never
   buried in the items.
4. **Reply line**: always last, as a quote block (see "Asking for approval").

Keep chat replies short: long results go on a page (see "Pages in the Claude app") and the chat
keeps the numbered summary. Use ✓ for done and → for next; no other symbols or emoji. After
saving, name the file once: "Saved to `drafts/ANGLE-03-linkedin-post.md`."

## Running straight through

Users should only reply when there is a real choice. From a new campaign to drafts takes about
eight replies: industry and goal, the case study, then one review each for what we delivered
and the audience problems, the topics, free or paid search interest, the content plan, and the
drafts.

When a stage command (add-case-study, find-topics, write) runs its steps:

- Never ask "continue?" or "go?" between steps or between stages (the one stop: after a
  topic's drafts are saved, the write stage ends and offers the next topic). Carry straight on, with a
  one-line progress note ("Listed 9 deliveries; checking what fits..."). The user can type
  **stop** at any time; what was approved is saved, and the same command carries on later.
- A step's own "Show and approve" is skipped when the stage says so: the stage collects the
  results and shows them in one review. On the user's yes, save every file of that review in
  order. Later steps work from the earlier results even before they are saved.
- A step's small questions take their default instead of asking:

| Step | Question | Default |
|---|---|---|
| list-deliveries | is the case study public? | `yes` for a public web page, otherwise `needs review` |
| choose-topics | which topics are chosen? | asked inside the topics review, not separately |
| search-interest | free or paid; which country | asked, in one question with the price (see the write stage); the first market unless the user names another |
| plan-pieces | which topic | the first chosen topic without a content plan |
| write | which pieces to write | every planned piece without a draft |
| write-email | which lead route | the profile's first lead route |
| write-article | approve the article plan first | skipped: the plan is shown as part of the drafts review |
| write-*, any step | a draft already exists | keep it and skip that piece; a new take only when the user asks |

Still always asked: free or paid search interest for each topic before its content plan (one
question that shows the price, so answering **paid** is the explicit yes), and the reviews
above. Nothing is saved before its review's yes.

## Asking for approval

There are no buttons: the user approves or changes a result by typing. End every approval
question with one line that says so, with two or three examples that fit the result shown, for
example:

> Reply **save**, or tell me what to change, for example: *drop 3*, *make 7 a gap*, *add a
> problem: ...*

Number the items you show, so the user can refer to them. After a change, show the changed
items and ask again; save only after a clear yes ("save", "yes", "go ahead").

## Reading web pages

Read a web page with web search and web fetch (fetch returns the page's text), never with the
browser. In the Claude app the browser asks the user to allow every new website; fetch does
not. Use the browser only when fetch cannot read a page that matters, and then say first, in
one line: "<site> blocks reading as text; I can open it in the browser (the app asks you to
allow the site once), or skip it." Skip it unless the user says open.

## Pages in the Claude app

Three pages in this folder, in WhiteFox's colours and font, show results next to the chat. Show
them only when you can show an artifact (the Claude app can; Claude Code cannot; then the chat
alone is enough). For each: copy the file unchanged except the `DATA` object between `/* DATA`
and `/* end DATA */`, set `stage` to the current stage line, and show it as an HTML artifact.
Pages never save anything: saving always happens in the chat.

| Page | When | What the user does on it |
|---|---|---|
| `review.html` | a result with 3 or more items to approve | keep, drop, edit, add; copy choices back |
| `preview.html` | drafts, before asking to save (several drafts: one tab each) | reads it as it will look; copies the clean text |
| `dashboard.html` | `whitefox-content-start`, once the workspace exists | sees what each campaign has made and what they can do next |

The page opens on its own in the panel on the right, and its card sits above your reply. Start
your reply with one line naming the page, for example: "**Draft: LinkedIn post, ANGLE-03** is
open on the right, as it will look (closed it? click its card above)."

### The review page

For a result with 3 or more items, show the review page so the user can keep, drop, edit and
add rows with buttons:

1. Copy `review.html` from this folder unchanged, except the `DATA` object between
   `/* DATA` and `/* end DATA */`. Fill it with the result: `title`, `item` (what one row is,
   for example "pain"), `fields` (one per field you show), `rows` (one per item, `id` = the
   number you show in the chat).
2. Fields holding text copied from a source (a customer quote, a case study sentence, a link)
   get `"edit": false`. Fields the user may reword get `"edit": true`; long text also gets
   `"long": true`.
3. For other choices per row, set `choice`: two or more values, the first is the default and
   the last dims the row (for example `["matched", "rejected"]` in
   `/whitefox-content-check-fit`, `["keep", "active", "drop"]` in
   `/whitefox-content-choose-topics`). The default is keep and drop. A row may set `pick` to start
   on another choice than the first (for example your suggestion).
4. Set the page's `<title>` to `Review: <title>` (for example "Review: quotes for
   fin-2026-10") so the artifact card says what it is for. Show it as an HTML artifact, and
   still write the numbered result in the chat.
5. Start your reply with one line, before the result: "**Review: <title>** is open on the
   right: keep, drop or edit with buttons, then press Copy my choices and paste them here
   (closed it? click its card above). Or just type your changes."
6. The user pastes back lines starting `Decisions for`. Apply each line exactly: `keep`, `drop`
   (or the `choice` values), `edited: <field> = <text>`, and `new <item>: ...` rows. Show
   the result once more as a short list and save on yes. A new or edited item still follows
   the step's rules (for example a quote must stay word for word with a link); say so if it
   does not.

### The draft preview

For every draft, before asking to save, show `preview.html` with `channel`, `title` (the
article's H1, or "LinkedIn post, ANGLE-nn" / "Email, ANGLE-nn"), `persona` (LinkedIn), `words`
and `range`, `body` (the ready-to-copy text; for articles the Markdown after the H1),
`subjects` and `previewText` (email) or `seo` (article). The page title is "Draft: <title>".
When several drafts are reviewed together, put each in the `drafts` list (with `piece`, for
example "Piece 3") and show one page; it gets a tab per draft.
In the chat keep the word count, "Built from" and the checklist; the draft text itself may be
left to the page when it is longer than about 200 words. After a change, show the page again.

### The dashboard

In `whitefox-content-start`, once the workspace exists, show `dashboard.html` with `version`,
`workspace`, `update` (the newer version, or null), `profiles` and one entry per campaign that
is not `done`, most recently worked on first (the newest file change in its folder; the page
opens the first and collapses the others): `made` (case studies, audience problems, quotes, topics, drafts), `topics` (the active
lanes and any lane with a plan or drafts, each with its label and what it has, for example "3
drafts: LinkedIn post, email, article" or "no plan yet") and `actions` (the three stage
commands, one marked suggested; see `whitefox-content-start`, "What the user can do"). The page
has its own "+ New campaign" button, so never add a new campaign to `actions`. In `made`, each
value is a plain number and each name agrees with it ("1 case study", "2 case studies"); leave
out zeros. The chat gives the same picture as short text.

Each campaign also gets `details`, which the page opens when a count or topic is clicked. The
page cannot read files, so put in everything it shows, copied from the files, never reworded:

- `sources`: each pool source with a proof judged for this campaign: `id`, `name`, `link` (or
  null), and its `proofs` with `id`, `solution`, `fit` (from `shelf.md`: matched, rejected, or
  "not judged") and `wording` (the shelf wording, or "(none)").
- `pains`: from `pains.md`: `id`, `text` (the Pain line), `audience`, `backed` (Backed by), and
  `quotes` (how many quotes cite it).
- `quotes`: from `quotes.md`: `id`, `text` (word for word, without the outer quote marks),
  `speaker`, `platform`, `link`, `pain`.
- `lanes`: every lane in `lanes.md`: `id`, `label`, `status`, `type`, `stance`, `demand`,
  `pains` and `quotes` (ID lists), `keywords` (the lane's `target` and `supporting` keywords from
  its latest `keywords.md` section, or empty), and `drafts`: each live file in `drafts/` for
  the lane, with `angle`, `channel`, `words`, `title` (an article's H1, an email's first
  subject option, or a LinkedIn post's first line), and its text exactly as in the draft
  preview: `body`, `persona` (LinkedIn), `subjects` and `previewText` (email), `seo` (article).

Leave out a list the campaign does not have yet. A draft's **Open** shows its text on the page
with copy buttons; a draft without `body` falls back to copying `/whitefox-content-show Piece <n>
<campaign>`. Keep IDs and statuses in `details` exactly as in the files (`PAIN-03`, `active`);
the page shows them in the user's words.

### Keeping the dashboard fresh

The dashboard is a snapshot: the page cannot read files. If it was shown earlier in this chat,
show it again, rebuilt from the files exactly as above, right after each of these saves:
a campaign created, paused, resumed or finished; a stage's review saved (deliveries and
problems, topics, a content plan); drafts saved. Not after smaller steps. Say nothing extra
about it beyond one line: "Dashboard updated." In Claude Code, where pages do not show, skip
this.

When a step names another step to the user, it gives the Claude app command and the Claude Code
command in brackets, for example `/whitefox-content-check-fit` (Claude Code:
`/wf-content:whitefox-content-check-fit`).

## IDs

| Item | Pattern | Example | Unique within |
|---|---|---|---|
| Profile | 2 to 5 capital letters | `INS` | `profiles/` |
| Campaign | lowercase words joined by hyphens | `ins-2026-q4` | `campaigns/` |
| Source | lowercase letters, digits, hyphens; short | `acme-claims` | `pool/sources/` |
| Proof | source ID, `-P`, two digits | `acme-claims-P03` | its source |
| Testimonial | source ID, `-T`, two digits | `acme-claims-T01` | its source |
| Pain | `PAIN-` and two digits | `PAIN-04` | the campaign |
| Quote | `QUOTE-` and two digits | `QUOTE-12` | the campaign |
| Lane | `LANE-` and two digits | `LANE-02` | the campaign |
| Angle | `ANGLE-` and two digits | `ANGLE-07` | the campaign |

- A new campaign ID is the next number after the highest one in that file (or folder), never
  a reused number. Removed items keep their number: mark them `archived`, do not delete them.
- Profile, source and proof IDs never use a counter shared across files, so `profiles/` and
  `pool/` can later move to a shared folder without renumbering.
- Before saving a new source, check `pool/sources/<source-id>.md` does not exist yet.

## Status values

| Item | Values | Starts as |
|---|---|---|
| Profile | `draft`, `unconfirmed`, `approved` | `draft` |
| Campaign | `active`, `paused`, `done` | `active` |
| Proof, testimonial | `active`, `archived` | `active` |
| Shelf fit | `matched`, `rejected` | (judged) |
| Lane | `candidate`, `active`, `paused`, `archived` | `candidate` |
| Angle | `proposed`, `kept`, `dropped` | `proposed` |
| Draft | `draft`, `approved`, `published`, `archived` | `draft` |

Only an `active` lane goes to keyword research or a brief. Only a `kept` angle gets a draft.
Writing steps warn when the campaign's profile is not `approved`.

## Lineage

Every item names the IDs it is built from, so any draft traces back to a case study:

```
draft -> angle -> brief -> lane -> pain + proofs + quotes -> source
```

- A shelf row names a proof ID from the pool.
- A pain names the matched proofs that back it, or `gap`.
- A quote names the pain it speaks to.
- A lane names its pain, proofs and quotes.
- A brief names its lane; each angle names the proofs and quotes it uses.
- A draft names its angle and lane.

A step never cites an ID it has not found in the workspace.

## Writing rules

- Dates are `YYYY-MM-DD`.
- Money is US dollars with cents (`$0.42`). An unknown price is written `unknown`, never `$0`.
- An empty field is written `(none)`; a field not yet known is written `unknown`.
- Text copied from a source (case study text, customer quotes) stays word for word.
- Each step shows its result and waits for approval before it saves. Saving adds or updates
  only the items that were approved; it never rewrites other items in the file.
- Lines starting with `<!--` in a template are instructions for the step and are not copied
  into the workspace file.
