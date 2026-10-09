# WhiteFox Content: user manual

This guide is for WhiteFox colleagues. It shows how to turn a WhiteFox case study into
LinkedIn posts, website articles and outbound emails, with Claude doing the legwork and you
approving each result.

You need a Claude subscription (Pro or Max) and one of these:

- **Claude desktop app** (recommended): review pages, draft previews and the dashboard open as
  pages beside the chat.
- **Claude Code**: the same steps in the terminal. Each review happens in the chat, by typing.

Contents:

1. [Install the plugin](#1-install-the-plugin)
2. [Choose your workspace folder](#2-choose-your-workspace-folder)
3. [Connect DataForSEO (optional)](#3-connect-dataforseo-optional)
4. [Start a campaign](#4-start-a-campaign)
5. [Stage 1: add a case study](#5-stage-1-add-a-case-study)
6. [Stage 2: find topics](#6-stage-2-find-topics)
7. [Stage 3: write](#7-stage-3-write)
8. [Review pages: how to approve](#8-review-pages-how-to-approve)
9. [The dashboard](#9-the-dashboard)
10. [Getting a new version](#10-getting-a-new-version)
11. [Commands and words](#11-commands-and-words)
12. [Problems and fixes](#12-problems-and-fixes)

---

## 1. Install the plugin

You do this once.

### Claude desktop app

1. Open **Customize** (left menu), then the **Plugins** tab.
2. Click **+ Add** (top right), then **Add marketplace**.
3. Choose **Add from a repository**. In **URL**, paste `whitefoxcloud/whitefox-content-plugin`,
   leave **Sync automatically** on, and click **Sync**. The red trust warning is shown for every
   plugin outside Anthropic's own list; this one is WhiteFox's.
4. The **Discover** tab opens with **WhiteFox Content**. Click **Add** on its row (not
   *Try in chat*).
5. The plugin's page opens: the switch on the right is on and the version shows under the
   name. Start a new chat.

![Where to add a marketplace: Customize, Plugins, +](images/01-app-plugins-add-button.png)

![Add marketplace: choose Add from a repository](images/02-app-marketplace-from-repository.png)

![Adding the WhiteFox marketplace in the Claude app](images/03-app-add-marketplace.png)

![Adding WhiteFox Content from Discover](images/04-app-install-plugin.png)

![WhiteFox Content added: version shown, switch on](images/05-app-plugin-added.png)

### Claude Code

Type these two commands:

```
/plugin marketplace add whitefoxcloud/whitefox-content-plugin
/plugin install wf-content@whitefox
```

Then start a new session. In Claude Code every command begins with `wf-content:`. For example,
`/whitefox-content-start` in the app is `/wf-content:whitefox-content-start` in Claude Code.

![Installing the plugin in Claude Code](images/06-code-install-plugin.png)

---

## 2. Choose your workspace folder

Everything you make (industries, case studies, campaigns, drafts) lives in one folder on your
laptop, called your workspace. You choose its name and place, for example
`Documents\WhiteFox Content`. The plugin itself holds no data.

1. In a new chat, type `/whitefox-content-start`, but do not send it yet.
2. Click **Project or folder** under the message box, then **Add folder**, and pick your
   workspace folder (or create an empty one with **New folder**), then **Select Folder**.
   The folder's name now shows under the message box. Then send.
   (Forgot? Claude asks which folder to use: paste the folder's path in your reply.)
3. Claude checks GitHub for a newer version of the plugin, and the app asks *Claude wants to
   fetch a web page* (raw.githubusercontent.com). Click **Always allow for this website**, so
   it does not ask again. (If you pasted a folder path instead, the app may also ask for folder
   access: tick **Don't ask again for this folder on this device**, then **Allow**.)
4. The first time, Claude lists what it will set up in the empty folder and asks your name (it
   goes into the files you create). Reply with your name and yes, for example *Sam, yes*.

![Project or folder, then Add folder](images/07-app-add-folder.png)

![Picking the workspace folder, then Select Folder](images/08-app-pick-folder.png)

![The folder shows under the message box, ready to send](images/09-app-folder-chosen.png)

![Allowing the version check: Always allow for this website](images/10-app-allow-version-check.png)

![First-time setup: what Claude will create](images/11-app-first-setup.png)

The workspace comes with four starter industries: financial services (FIN), insurance (INS),
healthcare (HC) and AI (AI).

---

## 3. Connect DataForSEO (optional)

DataForSEO gives real monthly search numbers for your topics. It is **only for people with the
company DataForSEO login**, and every call costs money (a few cents per topic). Everyone else
skips this section and uses the free check (questions and phrasing from web search, without
numbers).

Rules, whichever app you use:

- Never paste the DataForSEO login into a chat or a file. You sign in on DataForSEO's own page.
- The plugin only ever uses three DataForSEO tools: **Keyword Overview**, **Related Keywords**
  and **SERP Organic Live Advanced**. It shows the price first, and it spends only when you
  reply **paid** (at most $1.00 per topic).

### Claude desktop app

1. Open **Customize**, then **Connectors**, and click **+**.
2. Choose **Add custom connector**. Name: `DataForSEO`. URL: `https://mcp.dataforseo.com/mcp`.
3. Click **Connect**, and sign in on DataForSEO's page with the company login.
4. Open the connector's tool permissions. Turn off every tool except these three, and set each
   of them to **ask before use**:
   - DataForSEO Labs Google Keyword Overview
   - DataForSEO Labs Google Related Keywords
   - SERP Organic Live Advanced

   The connector marks many tools "read-only". That only means they change nothing at
   DataForSEO; they still cost money.

![Adding the DataForSEO custom connector](images/12-app-dataforseo-add.png)

![DataForSEO tool permissions: three tools on, set to ask](images/13-app-dataforseo-permissions.png)

### Claude Code

Claude Code signed in with your Claude account already has the connectors you added in the
Claude app.

1. Set up the connector in the Claude app first (above).
2. In Claude Code, type `/mcp`. You should see **claude.ai DataForSEO** with the status
   *connected*. If it says it needs signing in, select it and sign in with the company login.
3. Claude Code asks before each DataForSEO call. Answer **Yes** for one call at a time, and
   never pick "don't ask again" for a DataForSEO tool.

![claude.ai DataForSEO in the /mcp list](images/14-code-dataforseo-mcp.png)

If you use Claude Code without the Claude app, add the connector in the terminal instead:

```
claude mcp add --transport http dataforseo https://mcp.dataforseo.com/mcp
```

Then type `/mcp`, select **dataforseo** and sign in with the company login.

---

## 4. Start a campaign

A campaign is one push of content for one industry, with one goal, for example "insurance
leaders, October, systems integration".

1. Type `/whitefox-content-start`. Claude shows your industries and campaigns, and the
   dashboard opens on the right (section 9). Reply *start a new campaign*, or type
   `/whitefox-content-campaign`.
2. Claude asks which industry and what goal. Reply in one message, for example *FIN, start
   conversations with fintech founders and payments product leaders in Australia about
   building reliable real-time payments integrations*. No goal yet? Just give the industry.
3. Claude names the campaign (for example `ins-2026-10`) and asks for its case study. Go on to
   stage 1.

![Start: your industries and campaigns](images/15-start.png)

![Creating a campaign: industry and goal](images/16-new-campaign.png)

![Campaign created; the dashboard shows it with the suggested next step](images/17-app-campaign-created.png)

After the campaign exists, everything runs in three stages, one command each. Each stage runs
straight through, stops only when there is something for you to review, and then carries on
into the next stage. From a new campaign to the first drafts takes about seven replies:

| # | Your reply |
|---|---|
| 1 | industry and goal |
| 2 | the case study |
| 3 | review: what we delivered, and your audience's problems |
| 4 | review: the topics |
| 5 | free or paid search interest check |
| 6 | review: the content plan |
| 7 | review: the drafts |

Type **stop** any time. The same command carries on from where you stopped.

---

## 5. Stage 1: add a case study

Command: `/whitefox-content-add-case-study`

1. Right after creating a campaign, Claude already asks for the case study, so just answer.
   Later, type the command, or click **Copy command** on the dashboard and paste it. Claude
   says what the stage does and asks for the case study.
2. Attach the case study (PDF or Word file), paste its text, or paste its link. With a link,
   Claude opens the page in the app's browser. The first time, the app asks to allow
   whitefox.cloud: click **Always allow**.
3. Claude lists **what we delivered**: each piece of work WhiteFox really did, in whole
   sentences from the case study, and checks which ones fit your campaign's audience.
4. Claude names your **audience's problems** that this work solves, in your buyers' words.
5. Review both on the review page (section 8). Each delivery has **fits** (use it in this
   campaign), **doesn't fit** (keep it in the library, not for this campaign) or **drop** (do not
   save it). Each problem has **keep** or **drop**. Then **Copy my choices**, paste, send.

![Starting stage 1 from the dashboard's command](images/18-app-stage1-start.png)

![Stage 1 asks for the case study; the link is pasted](images/19-add-case-study.png)

![Review: what we delivered](images/20-review-deliveries.png)

Delivered work goes into your case study library, so later campaigns can use it too.

---

## 6. Stage 2: find topics

Command: `/whitefox-content-find-topics`

1. Claude searches the public web (forums, interviews, reviews) for **audience quotes**: real
   buyers voicing the problems, word for word, each with its link. You see progress lines while
   it searches.
2. Claude proposes **topics**: one audience problem, plus what we delivered and the quotes
   behind it, framed as a position WhiteFox can own.
3. One review page holds the topics and the quotes. Mark each topic **chosen**, **idea** or
   **drop**, and each quote **keep** or **drop**. Chosen topics go on to stage 3. A topic needs
   something behind it: if you drop the only quote behind a topic with no delivery, that topic
   is not saved.

![Topics review: topics and their quotes in the chat, the review page on the right](images/21-review-topics.png)

![Quotes on the same page (keep or drop), and the copied choices pasted](images/22-topics-quotes-choices.png)

---

## 7. Stage 3: write

Command: `/whitefox-content-write`

For one chosen topic at a time:

1. **Search interest.** Claude asks one question: free or paid.
   - **free**: questions and phrasing from web search, no numbers, no cost.
   - **paid** (only with DataForSEO connected): real monthly searches. The question shows the
     number of calls and the price, and replying **paid** approves that spend. The app then
     asks before each DataForSEO call (about five): click **Allow once** each time, never
     Always allow.
2. **Content plan.** Claude plans the pieces for the topic: channel (LinkedIn, email or
   article), headline, who posts it (company, founder or engineer) and the keyword. Mark each
   piece **planned**, **later** or **drop**.
3. **Drafts.** Claude writes every planned piece and opens them in one preview page, one tab per
   draft, as they will look. Approve, or type what to change.
4. Claude saves the drafts and offers the next chosen topic. Reply **next** to plan it.

![Topics saved, dashboard updated, then the free or paid question](images/23-free-or-paid.png)

![Stage 3 on its own: /whitefox-content-write asks free or paid; the answer typed](images/24-app-write-paid.png)

![Paid: the app asks before each DataForSEO call; click Allow once](images/25-app-dataforseo-allow.png)

![Review: content plan](images/26-review-content-plan.png)

![Draft preview with one tab per draft](images/27-draft-preview.png)

Drafts are saved in your campaign's `drafts` folder. Copy the text from the preview page with
its copy button, or open the file.

---

## 8. Review pages: how to approve

When a result has three or more items, a review page opens on the right of the chat (closed
it? click its card above your reply).

1. For each row, pick a choice with the buttons (for example keep or drop), or edit the text.
   Text copied from a source, such as a quote or a case study sentence, cannot be edited.
2. Add a row with the **Add** button at the bottom of the page if something is missing.
3. Press **Copy my choices**, paste into the chat and send.
4. Claude shows the result once more. Reply **yes** to save.

You can always skip the page and just type your changes, for example *drop 3, keep the rest*.
Nothing is saved before you approve.

In Claude Code there are no pages: Claude lists the items in the chat and you type your
choices.

![A review page with keep and drop buttons](images/28-review-page.png)

![Pasting the copied choices back into the chat](images/29-paste-choices.png)

---

## 9. The dashboard

Command: `/whitefox-content-dashboard` (it also opens with `/whitefox-content-start`)

The dashboard shows every campaign, newest first:

- what has been made so far (case studies, problems, quotes, topics, drafts): click a count to
  see the list,
- topics in progress: click one to expand it,
- **Open** on a draft shows it on the page as it will look, with copy buttons,
- the next actions, one of them suggested, and **+ New campaign**.

While it is open, Claude refreshes it after each milestone (a campaign created, a review
saved, drafts saved). The dashboard only shows; it never changes anything. To see one saved item in the chat, use
`/whitefox-content-show`, for example `/whitefox-content-show Topic 3 ins-2026-10`.

![The dashboard](images/30-dashboard.png)

![A draft opened inside the dashboard](images/31-dashboard-draft.png)

---

## 10. Getting a new version

`/whitefox-content-start` tells you when a newer version exists.

- **Claude app:** Customize, Plugins, WhiteFox Content, the **⋯** menu, **Check for updates**,
  then **Update**. Start a new chat afterwards (open chats keep the old version).
- **Claude Code:** `/plugin marketplace update whitefox`, then start a new session.

![Updating the plugin in the Claude app: ⋯ menu, Check for updates, Update](images/32-app-update.png)

---

## 11. Commands and words

| Claude app | Claude Code | What it does |
|---|---|---|
| `/whitefox-content-start` | `/wf-content:whitefox-content-start` | where each campaign stands, and the next step |
| `/whitefox-content-campaign` | `/wf-content:whitefox-content-campaign` | create, pause, resume or finish a campaign |
| `/whitefox-content-add-case-study` | `/wf-content:whitefox-content-add-case-study` | stage 1 |
| `/whitefox-content-find-topics` | `/wf-content:whitefox-content-find-topics` | stage 2 |
| `/whitefox-content-write` | `/wf-content:whitefox-content-write` | stage 3 |
| `/whitefox-content-dashboard` | `/wf-content:whitefox-content-dashboard` | the dashboard page |
| `/whitefox-content-show` | `/wf-content:whitefox-content-show` | one saved item |
| `/whitefox-content-guide` | `/wf-content:whitefox-content-guide` | how the workflow works |

Words the plugin uses:

- **What we delivered:** one piece of work WhiteFox really did, from a case study.
- **Audience problem:** a problem your campaign's audience has, that this work solves.
- **Audience quote:** a real buyer saying it, word for word, with its link.
- **Topic:** one audience problem, plus what we delivered and the quotes behind it.
- **Content plan:** the pieces planned for one topic.
- **Piece:** one LinkedIn post, email or article.
- **Industry:** who a campaign is for, how WhiteFox is positioned there, and which words to use
  or avoid.

---

## 12. Problems and fixes

| What you see | What to do |
|---|---|
| "This marketplace is already added" | It is installed already. Go to Plugins, Discover, and click **Add** on WhiteFox Content (or update it, section 10). |
| A command is not found | Start a new chat (or session). In Claude Code, add `wf-content:` in front. |
| Claude asks for the folder every time | Pick it with **Project or folder** before sending (section 2). |
| The page on the right is gone | Click the page's card above Claude's reply. |
| "DataForSEO is not connected" | Expected without the company login: choose free. With the login, see section 3. |
| A DataForSEO call fails or the balance is empty | Nothing is retried without your yes. Choose free, and tell the DataForSEO account owner. |
| A new version does not show | Check for updates (section 10), then start a new chat. |

If something else goes wrong, take a screenshot and send it to the plugin owner.

---

## Screenshots to add

Save each image in `docs/images/` with this name:

| File | Shows |
|---|---|
| `01-app-plugins-add-button.png` | Claude app, Customize, Plugins, with the + (Add marketplace) button visible |
| `02-app-marketplace-from-repository.png` | the Add marketplace window: Browse Anthropic sources or Add from a repository |
| `03-app-add-marketplace.png` | Add from a repository: URL pasted, Sync automatically on, Sync button |
| `04-app-install-plugin.png` | Plugins, Discover: WhiteFox Content with its Add button |
| `05-app-plugin-added.png` | the WhiteFox Content page after Add: version, switch on, Try in chat |
| `06-code-install-plugin.png` | Claude Code after `/plugin install wf-content@whitefox` |
| `07-app-add-folder.png` | Project or folder menu under the message box, with Add folder |
| `08-app-pick-folder.png` | the Windows folder picker with WhiteFox Content selected |
| `09-app-folder-chosen.png` | /whitefox-content-start typed, WhiteFox Content shown under the message box |
| `10-app-allow-version-check.png` | "Claude wants to fetch a web page" for the version check |
| `11-app-first-setup.png` | first-time setup in an empty folder: what Claude will create, asks name and yes |
| `12-app-dataforseo-add.png` | Add custom connector with name and URL filled in |
| `13-app-dataforseo-permissions.png` | DataForSEO tool permissions, three tools on and set to ask |
| `14-code-dataforseo-mcp.png` | Claude Code `/mcp` list with claude.ai DataForSEO connected |
| `15-start.png` | the start reply with the dashboard open on the right |
| `16-new-campaign.png` | /whitefox-content-campaign: the industry and goal question, with the answer typed |
| `17-app-campaign-created.png` | campaign created in the chat, dashboard showing it with Add a case study suggested |
| `18-app-stage1-start.png` | the start reply, with /whitefox-content-add-case-study typed (or copied from the dashboard) |
| `19-add-case-study.png` | the stage 1 opener asking for the case study, with the link pasted |
| `20-review-deliveries.png` | stage 1 review page: one row per delivery with fits, doesn't fit, drop |
| `21-review-topics.png` | stage 2 review: topics with their quotes in the chat, topics page on the right |
| `22-topics-quotes-choices.png` | quote rows (keep, drop) on the topics page, choices pasted |
| `23-free-or-paid.png` | topics saved, dashboard updated, the free or paid question with the price |
| `24-app-write-paid.png` | /whitefox-content-write run on its own: the free or paid question, answer typed |
| `25-app-dataforseo-allow.png` | "Claude wants to use DataForSEO ..." with Allow once |
| `26-review-content-plan.png` | search interest results in the chat, content plan review page (planned, later, drop) |
| `27-draft-preview.png` | draft preview page with tabs |
| `28-review-page.png` | any review page, buttons and Copy my choices visible |
| `29-paste-choices.png` | the copied "Decisions for" lines pasted in the chat |
| `30-dashboard.png` | the dashboard with a campaign expanded |
| `31-dashboard-draft.png` | a draft opened inside the dashboard |
| `32-app-update.png` | the plugin's ⋯ menu with Check for updates (and Update, if it shows) |

Use test data only (for example the fin-2026-10 campaign), and crop out names, emails and
other chats.
