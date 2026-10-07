---
name: whitefox-content-keyword-research
description: Paid keyword research for one active WhiteFox content lane through the DataForSEO connector - monthly searches, difficulty, intent and "people also ask" questions - with the price shown and approved first and every call logged in costs.md. Use when the user wants keyword data, search demand or SEO research for a lane.
disable-model-invocation: true
---

# Keyword research

For one active lane, finds what the campaign's buyers actually search for, so briefs can plan
articles around real searches. This step spends real money from the company DataForSEO
account. Nothing is called before the user approves the price.

## Read first

- `../whitefox-content-guide/formats/README.md`, then begin as it says (workspace, settings,
  campaign, profile).
- `../whitefox-content-guide/formats/keywords.md` and `../whitefox-content-guide/formats/costs.md`
  (the formats).
- The campaign's `lanes.md`, `keywords.md` and `costs.md` (if they exist).

## 1. Check the connector

This step needs the DataForSEO connector (its `api_request` tool). If you do not have it, say:
"DataForSEO is not connected in your Claude app. Keyword research uses the company DataForSEO
account and is limited to the people who have its login; ask the WhiteFox content owner if you
need it." Then stop. Never suggest another account, another tool, or guessing numbers.

Never ask for, accept, repeat or save a DataForSEO login. If the user pastes a password or key,
tell them to remove it from the chat and change it, and do not use it.

## 2. Pick the lane and country

- The lane must have status `active`. If the user names a lane that is not, say so and suggest
  making it active with `/whitefox-content-mint-lanes`. With several active lanes and none
  named, ask which.
- If `keywords.md` already has a section for this lane, show its date and verdict and ask
  whether to run again (a new run is paid again).
- Country: one per run, from the profile's Markets. With several, ask which. Send the country
  name as written (for example "Australia", "United States"), language "English".
- Phrases: the lane's search phrases that are not skipped (at most 3). If all are skipped, say
  the lane has no search phrases and stop.

## 3. Plan and price

Only these three DataForSEO services may be called, through `api_request`, with POST bodies
shaped like these. Call no other service, even if it looks useful.

| # | Service | Body | Estimate |
|---|---|---|---|
| 1 | `/v3/dataforseo_labs/google/keyword_overview/live` | `[{"keywords": [<the phrases>], "location_name": "<country>", "language_name": "English"}]` | $0.01 per phrase |
| 2 | `/v3/dataforseo_labs/google/related_keywords/live`, once per phrase | `[{"keyword": "<phrase>", "location_name": "<country>", "language_name": "English", "depth": 1, "limit": 20}]` | $0.015 per call |
| 3 | `/v3/serp/google/organic/live/advanced`, once, for the primary keyword | `[{"keyword": "<primary keyword>", "location_name": "<country>", "language_name": "English", "depth": 10}]` | $0.01 |

Add up the estimate for this lane. If it is above **$1.00**, do not run: say so, and offer a
smaller plan (fewer phrases). Never exceed $1.00 per lane per run, even if the user says yes.

Show the plan as a short list of the calls, then ask:

"Run these N DataForSEO calls for about $X? This is an estimate from the WhiteFox app's
pricing, not a hard limit; the real cost is logged after each call. Reply **yes** to spend, or
**no**."

Wait for an explicit yes in reply to this question. A yes to anything earlier does not count.

## 4. Run

1. Call services 1 and 2. Then choose the primary keyword: the keyword with the most monthly
   searches that the profile's audience would type (see step 5), then call service 3 for it.
2. After every call, add a row to `costs.md` straight away (create it with the heading if
   missing): date, `keyword-research`, what was called (lane, service, phrase, country), the
   estimate, the actual cost from the response's top-level `cost` field (or `unknown` if the
   response has none), and the user's name. Never write $0 for an unknown cost.
3. If a call fails or returns an error, stop. Log it with what the response says about cost,
   tell the user what failed, and do not retry without a new yes.

## 5. Read the results

- From services 1 and 2, list each keyword with its monthly searches (`search_volume`),
  difficulty (`keyword_difficulty`), and main intent (`search_intent_info.main_intent`). A
  missing value is `unknown`, never 0.
- Use: `primary` for the chosen keyword, `secondary` for others a buyer in the profile's
  audience would type, `skip: <reason>` for the rest. Skip keywords in the voice of the
  buyer's end users or consumers ("where is my money"), job searches, other countries' brands
  and products, anything on the profile's exclude terms, and keywords off the lane's topic.
- From service 3, copy the "people also ask" questions word for word (items of type
  `people_also_ask`). None found: `(none)`.
- Verdict, from the total monthly searches of the primary and secondary keywords: 1000 or more
  `strong`, 10 or more `some`, less than 10 `none`. If nothing came back measured, `unknown`.

## 6. Show and approve

1. Lead with the verdict and the actual total cost (or "unknown").
2. The keyword table and the "people also ask" questions, in the format.
3. The user may change Use values (for example "make 4 secondary", "skip 7").
4. On yes, add the section to `keywords.md` (create it with the heading if missing) and update
   the lane's `Demand` line in `lanes.md` to the verdict. The `costs.md` rows are already
   written and stay as they are, even if the user does not save the keywords.

## Next

Suggest `/whitefox-content-arm-brief` for this lane.

## Rules

- No call before an explicit yes to the price question. Never more than $1.00 per lane per run.
- Only the three services above.
- Every call is logged in `costs.md` right after it runs, with the user's name.
- Numbers come only from DataForSEO responses. Never estimate, round or invent search volumes.
