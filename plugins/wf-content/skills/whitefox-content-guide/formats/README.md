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

## Asking for approval

There are no buttons: the user approves or changes a result by typing. End every approval
question with one line that says so, with two or three examples that fit the result shown, for
example:

> Reply **save**, or tell me what to change, for example: *drop 3*, *make 7 a gap*, *add a
> pain: ...*

Number the items you show, so the user can refer to them. After a change, show the changed
items and ask again; save only after a clear yes ("save", "yes", "go ahead").

### The review page (Claude app)

When a result has 3 or more items and you can show an artifact (the Claude app can; Claude
Code cannot), also show the review page, so the user can keep, drop, edit and add rows with
buttons:

1. Copy `review.html` from this folder unchanged, except the `DATA` object between
   `/* DATA` and `/* end DATA */`. Fill it with the result: `title`, `item` (what one row is,
   for example "pain"), `fields` (one per field you show), `rows` (one per item, `id` = the
   number you show in the chat).
2. Fields holding text copied from a source (a customer quote, a case study sentence, a link)
   get `"edit": false`. Fields the user may reword get `"edit": true`; long text also gets
   `"long": true`.
3. For a judgement between two values, set `choice` (for example `["matched", "rejected"]` in
   `/whitefox-content-match-proof`). The default is keep and drop.
4. Set the page's `<title>` to `Review: <title>` (for example "Review: quotes for
   fin-2026-10") so the artifact card says what it is for. Show it as an HTML artifact, and
   still write the numbered result in the chat.
5. Start your reply with one line, before the result: "Click the **Review: <title>** card
   below to keep, drop or edit with buttons, then press Copy my choices and paste them here.
   Or just type your changes." The card does not look clickable, so always say this.
6. The user pastes back lines starting `Decisions for`. Apply each line exactly: `keep`, `drop`
   (or the two `choice` values), `edited: <field> = <text>`, and `new <item>: ...` rows. Show
   the result once more as a short list and save on yes. A new or edited item still follows
   the step's rules (for example a quote must stay word for word with a link); say so if it
   does not.

When a step names another step to the user, it gives the Claude app command and the Claude Code
command in brackets, for example `/whitefox-content-match-proof` (Claude Code:
`/wf-content:whitefox-content-match-proof`).

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
