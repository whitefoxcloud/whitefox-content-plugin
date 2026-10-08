---
name: whitefox-content-dashboard
description: Show the WhiteFox Content dashboard page for the current workspace - every campaign with its case studies, pains, quotes, topics and drafts, each clickable to see the list. Read only. Use when the user asks for the dashboard, wants to see or refresh it, or wants to browse what a campaign has made.
---

# Dashboard

Shows the dashboard page, fresh from the workspace. Read only: changes nothing.

1. Read `../whitefox-content-guide/formats/README.md` (the workspace rules) and find the
   workspace as `../whitefox-content-start/SKILL.md` says in "1. Find the workspace". If there
   is none, or `settings.md` is missing, say: "No workspace yet. Run `/whitefox-content-start`
   (Claude Code: `/wf-content:whitefox-content-start`) first." and stop.
2. Build the page exactly as the workspace rules say in "The dashboard", including `details`,
   with the suggested action from `../whitefox-content-start/SKILL.md`, "What the user can do".
   Skip the version check.
3. Reply with one line: "Your **WhiteFox Content dashboard** is open on the right (closed it?
   click its card above). Click a count or a topic to see the list; **Open** on a draft copies a
   command that shows it here." Then the "You can:" line from start, nothing else.

In Claude Code, where pages do not show, reply with start's text summary instead.
