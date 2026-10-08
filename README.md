# WhiteFox Content plugin

Turns case studies into proof-backed LinkedIn posts, articles and emails, one approved step at
a time. Runs in the Claude desktop app and in Claude Code, on your own Claude subscription (Pro
or Max).

Status: 0.14.1. Every step is built, grouped into three stage commands (add a case study, find
topics, write) after setup with `whitefox-content-start`.

The words it uses: **what we delivered** (one piece of work from a case study), **audience
problem**, **audience quote**, **topic**, **content plan** and **piece**. `/whitefox-content-guide`
explains each one.

## How it works

| Layer | Holds | Lives in |
|---|---|---|
| This plugin | how each step works | this repo |
| Your WhiteFox folder | your industries, case study library and campaigns | `WhiteFox Content` on your laptop |

The plugin holds no campaign data, case studies or logins.

## One-time setup

1. **Install the plugin:**
   - Claude desktop app: Customize, Plugins, "+", Add marketplace, paste
     `whitefoxcloud/whitefox-content-plugin`, then install `wf-content`.
   - Claude Code: `/plugin marketplace add whitefoxcloud/whitefox-content-plugin`, then
     `/plugin install wf-content@whitefox`.
2. **Workspace folder:** pick any folder for your WhiteFox content, with any name, anywhere
   (for example `Documents\WhiteFox Content`). The first time you run the plugin, Claude asks
   for it and sets it up.
3. **Keyword research (only people with the company DataForSEO login):** in the Claude app,
   Customize, Connectors, **+**, "Add custom connector", name it `DataForSEO`, URL
   `https://mcp.dataforseo.com/mcp`, then Connect and sign in on DataForSEO's page with the
   company login. In the connector's tool permissions, set the read-only tools to ask before
   each use (every DataForSEO tool costs money, "read-only" only means it changes nothing).
   Safest: allow only DataForSEO Labs Google Keyword Overview, DataForSEO Labs Google Related
   Keywords and SERP Organic Live Advanced (ask first), and turn the others off. Never paste the login into a chat or a file. Everyone else skips this step; keyword
   research then offers its free mode (questions and phrasing from web search, no numbers).

## Each time you work

1. Type `/whitefox-content-start` (in Claude Code: `/wf-content:whitefox-content-start`).
2. If Claude asks which folder to use, add your workspace folder with **+** in the message box
   and send a short message such as "use this folder" (a folder alone does not send), or paste
   its path. When Claude asks for folder access, tick "Don't ask again for this folder
   on this device", then click Allow. Claude shows each campaign's stage and the next command,
   or offers to create a campaign (pick an industry, or create one).
3. Run the three stages. Each runs straight through and stops only for a review, and each
   stage carries on into the next:
   - `/whitefox-content-add-case-study`: attach the case study or paste its link. What we
     delivered goes into your case study library, is checked against the campaign, and your
     audience's problems are named.
   - `/whitefox-content-find-topics`: real audience quotes, then the topics to write about
     (you choose which to work on).
   - `/whitefox-content-write`: a search interest check for a topic (you choose free, or paid
     with DataForSEO with the price shown), a content plan, then every LinkedIn post, email and
     article in it.
4. From a new campaign to drafts takes about eight replies: industry and goal, the case study,
   then one review each for what we delivered and the problems, the topics, free or paid
   search interest, the content plan and the drafts. Approve or correct each by typing, or with the page's buttons. Nothing is
   saved before you approve. You can stop any time; the same command
   carries on from where you stopped.
5. Take the draft from the chat, or open it in your campaign's `drafts` folder.

Next time, `/whitefox-content-start` shows where each campaign stands and what to do next.
`/whitefox-content-dashboard` shows the dashboard page any time: click a count or a topic to see
its problems, quotes, topics and drafts, and **Open** on a draft to read it in the preview.

### Getting a new version

- Claude app: Customize, Plugins, WhiteFox Content, the ⋯ menu, "Check for updates", then
  "Update". Start a new chat afterwards.
- Claude Code: `/plugin marketplace update whitefox`.

`/whitefox-content-start` shows the version you have.

## For maintainers

```
.claude-plugin/marketplace.json     the marketplace (name: whitefox)
plugins/wf-content/                 the plugin
  .claude-plugin/plugin.json        name and version
  skills/<step>/SKILL.md            one skill per step: /<step> in the app, /wf-content:<step> in Claude Code
.github/workflows/release.yml       on a version tag, builds the uploadable plugin file
```

Try it locally with Claude Code:

```
claude plugin validate .
claude --plugin-dir ./plugins/wf-content
```

Releasing: raise `version` in `plugin.json`, add a `CHANGELOG.md` entry, merge, then push a
tag `v<version>`. The release workflow attaches `wf-content-v<version>.zip` to the GitHub
release; that file is what Claude desktop app users upload if the repo is ever made private.
