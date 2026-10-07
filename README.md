# WhiteFox Content plugin

Turns case studies into proof-backed LinkedIn posts, articles and emails, one approved step at
a time. Runs in the Claude desktop app and in Claude Code, on your own Claude subscription (Pro
or Max).

Status: 0.4.1. Built: start, guide, house-style, profile, campaign, and the evidence steps
(extract-proof, match-proof, derive-pains, mine-quotes, mint-lanes). The keyword, brief and
writing steps are not built yet.

## How it works

| Layer | Holds | Lives in |
|---|---|---|
| This plugin | how each step works | this repo |
| Your workspace folder | your profiles, proof pool and campaigns | `WhiteFox Content` on your laptop |

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
3. **Keyword research only:** add the DataForSEO login when the plugin asks for it.

## Each time you work

1. Type `/whitefox-content-start` (in Claude Code: `/wf-content:whitefox-content-start`).
2. If Claude asks which folder to use, add your workspace folder with **+** in the message box
   and send a short message such as "use this folder" (a folder alone does not send), or paste
   its path. When Claude asks for folder access, tick "Don't ask again for this folder
   on this device", then click Allow. Claude lists your campaigns, or offers to create one.
3. New campaign: pick a profile, or create a new one.
4. Add a case study: attach the file or paste the link. Claude extracts its proofs into your
   pool, or reuses them if you extracted it before.
5. Follow the steps Claude suggests: match proofs, derive pains, mine quotes, mint lanes,
   keyword research (price shown first, runs only on your yes), build a brief, write the
   LinkedIn post, article or email.
6. At each step Claude shows the result; approve or correct it. Nothing is saved before you
   approve.
7. Take the post from the chat, or open the saved draft in your campaign folder.

Next time, `/whitefox-content-start` shows where each campaign stands and what to do next.

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
