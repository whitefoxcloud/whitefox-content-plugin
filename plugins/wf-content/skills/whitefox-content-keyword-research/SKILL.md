---
name: whitefox-content-keyword-research
description: Keyword research for one active WhiteFox content lane. Paid mode uses the DataForSEO connector for monthly searches, difficulty, intent and "people also ask" questions, with the price approved first and every call logged in costs.md. Free mode uses web search for the questions and phrasing buyers use, without search numbers. Use when the user wants keyword data, search demand or SEO research for a lane.
disable-model-invocation: true
---

# Keyword research

For one active lane, finds what the campaign's buyers search for and ask, so briefs can plan
articles around real searches. Two modes:

- **Paid** (DataForSEO connector): real monthly searches, difficulty and intent, from the
  company DataForSEO account. Costs money; nothing is called before the user approves the
  price.
- **Free** (web search): the questions buyers ask and the phrasing they use, with links. No
  search numbers, so the verdict stays `unknown`. Costs nothing beyond the user's Claude plan.

## Read first

- `../whitefox-content-guide/formats/README.md`, then begin as it says (workspace, settings,
  campaign, profile).
- `../whitefox-content-guide/formats/keywords.md` and `../whitefox-content-guide/formats/costs.md`
  (the formats).
- The campaign's `lanes.md`, `keywords.md` and `costs.md` (if they exist).

Never ask for, accept, repeat or save a DataForSEO login. If the user pastes a password or key,
tell them to remove it from the chat and change it, and do not use it.

## 1. Pick the lane, country and mode

- The lane must have status `active`. If the user names a lane that is not, say so and suggest
  making it active with `/whitefox-content-mint-lanes`. With several active lanes and none
  named, ask which.
- If `keywords.md` already has a section for this lane, show its date, mode and verdict, and
  ask whether to run again.
- Country: one per run, from the profile's Markets. With several, ask which.
- Phrases: the lane's search phrases that are not skipped (at most 3). If all are skipped, say
  the lane has no search phrases and stop.
- Mode: if you have the DataForSEO connector (its tools are named after DataForSEO services,
  for example "DataForSEO Labs Google Keyword Overview"), offer both: "Paid
  (DataForSEO, about $X, real search numbers) or free (web search, questions and phrasing, no
  numbers)?" If you do not have it, say: "DataForSEO is not connected in your Claude app (it is
  limited to the people with the company login). I can do the free version: the questions and
  phrasing buyers use, without search numbers." Run free mode on yes.

## 2. Paid mode

### Plan and price

Only these three connector tools may be called. Call no other DataForSEO tool, even if it
looks useful: every one of them costs money ("read-only" in the connector only means it changes
nothing). Prices are DataForSEO's list prices as checked on 2026-10-07; the real cost is logged
after each call.

| # | Connector tool | DataForSEO service | What to send | Estimate |
|---|---|---|---|---|
| 1 | DataForSEO Labs Google Keyword Overview, once | `dataforseo_labs/google/keyword_overview/live` | the phrases, the country, English | $0.012 + $0.00012 per phrase |
| 2 | DataForSEO Labs Google Related Keywords, once per phrase | `dataforseo_labs/google/related_keywords/live` | the phrase, the country, English, depth 1, limit 20 | up to $0.0144 per call |
| 3 | SERP Organic Live Advanced, once, for the primary keyword | `serp/google/organic/live/advanced` | the primary keyword, the country, English, depth 10 | $0.002 |

Fill each tool's parameters from its own description (names such as `keyword` or `keywords`,
`location_name`, `language_code` or `language_name`, `depth`, `limit`). Send the country name
as written (for example "Australia", "United States"). If the connector instead offers a single
`api_request` tool, call the same three services through it and nothing else.

Add up the estimate (three phrases come to about $0.06). If it is above **$1.00**, do not run:
say so, and offer a smaller plan. Never exceed $1.00 per lane per run, even if the user says
yes.

Show the plan as a short list of the calls, then ask:

"Run these N DataForSEO calls for about $X? This is an estimate from DataForSEO's list
prices, not a hard limit; the real cost is logged after each call. Reply **yes** to spend, or
**no**."

Wait for an explicit yes in reply to this question. A yes to anything earlier does not count.

### Run

1. Call tools 1 and 2. Then choose the primary keyword: the keyword with the most monthly
   searches that the profile's audience would type (see "Read the results"), then call tool 3
   for it. The user's Claude app may ask them to approve each call; that is expected.
2. After every call, add a row to `costs.md` straight away (create it with the heading if
   missing): date, `keyword-research`, what was called (lane, tool, phrase, country), the
   estimate, the actual cost from the response's `cost` field (or `unknown` if the response has
   none), and the user's name. Never write $0 for an unknown cost.
3. If a call fails or returns an error (including an empty balance), stop. Log it with what the
   response says about cost, tell the user what failed, and do not retry without a new yes.
   On an empty balance, offer free mode.

### Read the results

- From tools 1 and 2, list each keyword with its monthly searches (`search_volume`),
  difficulty (`keyword_difficulty`), and main intent (`search_intent_info.main_intent`). A
  missing value is `unknown`, never 0.
- Use: `primary` for the chosen keyword, `secondary` for others a buyer in the profile's
  audience would type, `skip: <reason>` for the rest. Skip keywords in the voice of the
  buyer's end users or consumers ("where is my money"), job searches, other countries' brands
  and products, anything on the profile's exclude terms, and keywords off the lane's topic.
- From tool 3, copy the "people also ask" questions word for word (items of type
  `people_also_ask`). None found: `(none)`.
- Verdict, from the total monthly searches of the primary and secondary keywords: 1000 or more
  `strong`, 10 or more `some`, less than 10 `none`. If nothing came back measured, `unknown`.

## 3. Free mode

Use web search only. No DataForSEO call, no `costs.md` row.

1. Search each phrase (with the country where it helps) and read the results.
2. Keywords: collect the phrasings buyers use for this topic, from page titles, headings and
   forum thread titles that match the lane, at most 15. Monthly searches and difficulty are
   `unknown` for every one. Intent is your judgement from the results (informational,
   commercial, navigational, transactional), marked `(judged)`. Use: `primary` for the phrasing
   that appears most often in buyer-facing results, `secondary` for others a buyer would type,
   `skip: <reason>` as in paid mode.
3. Questions: real questions buyers ask about the topic, word for word from forum threads, Q&A
   sites and FAQ sections you opened, each with its link, at most 10. Never write a question
   yourself.
4. Verdict: always `unknown` (no numbers). In "Why", say it came from free web search.

## 4. Show and approve

1. Lead with the mode, the verdict and, for paid mode, the actual total cost (or "unknown").
   When the cost is unknown, add: "The DataForSEO connector does not report costs; the real
   spend is in your DataForSEO account at app.dataforseo.com."
   When every phrase came back empty, say the phrases are too narrow for search data (not a
   fault), and offer broader phrases (a new price question) or free mode.
2. The keyword table and the questions, in the format.
3. The user may change Use values (for example "make 4 secondary", "skip 7").
4. On yes, add the section to `keywords.md` (create it with the heading if missing). In paid
   mode, update the lane's `Demand` line in `lanes.md` to the verdict; free mode leaves Demand
   as it is. Paid `costs.md` rows are already written and stay, even if the user does not save
   the keywords.

## Next

Suggest `/whitefox-content-arm-brief` for this lane.

## Rules

- Paid: no call before an explicit yes to the price question, never more than $1.00 per lane
  per run, only the three tools above, every call logged in `costs.md` with the user's
  name.
- Search numbers come only from DataForSEO responses. Never estimate, round or invent them; in
  free mode they are `unknown`.
