# WhiteFox Content plugin

Turns case studies into proof-backed LinkedIn posts, articles and emails, one approved step at
a time. Runs in the Claude desktop app and in Claude Code, on your own Claude subscription (Pro
or Max).

Status: 0.2.0. Built: `start`, `guide`, `house-style`, `profile`, `campaign`. The evidence,
keyword, brief and writing steps are not built yet.

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
2. **Workspace folder:** create `WhiteFox Content` in your Documents folder. The plugin fills in
   the rest the first time you run it.
3. **Keyword research only:** add the DataForSEO login when the plugin asks for it.

## Each time you work

1. Open Claude and give it access to your `WhiteFox Content` folder.
2. Type `/start` (in Claude Code: `/wf-content:start`). Claude lists your campaigns, or offers
   to create one.
3. New campaign: pick a profile, or create a new one.
4. Add a case study: attach the file or paste the link. Claude extracts its proofs into your
   pool, or reuses them if you extracted it before.
5. Follow the steps Claude suggests: match proofs, derive pains, mine quotes, mint lanes,
   keyword research (price shown first, runs only on your yes), build a brief, write the
   LinkedIn post, article or email.
6. At each step Claude shows the result; approve or correct it. Nothing is saved before you
   approve.
7. Take the post from the chat, or open the saved draft in your campaign folder.

Next time, `/start` shows where each campaign stands and what to do next.

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
