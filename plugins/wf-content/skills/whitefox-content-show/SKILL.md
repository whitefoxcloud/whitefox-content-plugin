---
name: whitefox-content-show
description: Show one saved WhiteFox content item by its ID - a draft (ANGLE-nn) in the draft preview page, or a brief, lane, pain, quote or proof in the chat. Read only. Use when the user pastes "/whitefox-content-show ANGLE-03 fin-2026-10" from the dashboard, or asks to see, open or read a saved draft or item.
---

# Show

Shows one saved item. Read only: changes nothing, and never rewrites what it shows.

## Read first

`../whitefox-content-guide/formats/README.md` (the workspace rules), then find the workspace
as `../whitefox-content-start/SKILL.md` says in "1. Find the workspace".

## What to show

The user gives an ID and usually a campaign, for example `ANGLE-03 fin-2026-10` or `Piece 3
fin-2026-10` (Piece is ANGLE, Topic is LANE, Problem is PAIN, Quote is QUOTE, Delivery is a
proof; see "Words the user sees" in the workspace rules). Name items to the user in those
words. With no
campaign, use the only `active` campaign, or ask which. If the ID is not found, say so and list
the IDs of that kind the campaign has.

| ID | Where | How to show it |
|---|---|---|
| `ANGLE-nn` | `drafts/ANGLE-nn-<channel>.md` (not `-archived-`) | the draft preview page, exactly as the workspace rules say in "The draft preview", without `stage`; then in the chat: channel, word count, written date and by whom, and "To change it, run `/whitefox-content-write`." If the angle has no draft, show its entry from the brief instead |
| `LANE-nn` | `lanes.md`, plus `briefs/LANE-nn.md` if it exists | the lane's fields, then its planned angles with status and channel |
| `PAIN-nn` | `pains.md` | the pain's fields, and the quotes in `quotes.md` that cite it |
| `QUOTE-nn` | `quotes.md` | the quote word for word with its link, speaker and pain |
| `<source-id>-Pnn` | `pool/sources/<source-id>.md` | the proof's fields, and this campaign's `shelf.md` row for it |

Show text exactly as saved. Never shorten a quote or a draft.

End with one line: "Back to the overview: `/whitefox-content-dashboard` (Claude Code:
`/wf-content:whitefox-content-dashboard`)."
