---
name: whitefox-content-find-quotes
description: Search the public web for word-for-word quotes from real people in the audience voicing a campaign's problems (forums, Reddit, interviews, reviews), each with its link. Use after naming audience problems, or when the user wants audience quotes for a campaign.
---

# Mine quotes

For each pain, searches the public web for real people describing it in their own words, and
keeps up to three verbatim quotes with their links. Quotes show how buyers talk; they are never
proof of what WhiteFox did.

## Read first

- `../whitefox-content-guide/formats/README.md`, then begin as it says (workspace, settings,
  campaign, profile).
- `../whitefox-content-guide/formats/quotes.md` (the format).
- The campaign's `pains.md` and `quotes.md` (if it exists).

This step needs web search and the ability to open pages. If you have neither, say so and stop.

## Which pains

By default, the pains with no quote yet and not listed under "Pains with no quotes found". The
user may name other pains. With more than 6 pains to search, do 6, save after approval, then
offer the next round.

## Search

For each pain, one focused search built from its search angle and, where it helps, the
profile's quote-mining vocabulary. Look where practitioners talk: Reddit, industry forums,
practitioner interviews, reviews.

Keep a quote only when all of these hold:

- You opened the page and copied the quote from it, word for word. Never from a search snippet,
  never from memory, never shortened, corrected or stitched together.
- It is a real first-person voice: a practitioner or an authority speaking from experience.
- It is about this pain, not a generic complaint about software.
- You have the page's link. If the site blocks you and you read the quote through a copy (an
  archive snapshot, the site's own search index), store the original page's link and add
  "(read via a copy)" to Context, so the user can check the wording on the original.

Reject: third-party paraphrase ("many companies struggle", "studies show"), vendor marketing
(our platform, we help, seamless, end-to-end), noise and abuse. Never use WhiteFox's own case
studies or site as a quote.

Per pain, keep at most 3, and fewer is fine. When a pain has no genuine voice, record it under
"Pains with no quotes found" with the reason and what you searched. Never pad.

For each kept quote:

- Speaker: the role as far as the page shows it.
- Context: one sentence on what the speaker was talking about.
- Domain: `in-domain` if the speaker works in the profile's industry; `adjacent` if the voice
  is generic or from a nearby field.
- Tier: `tier1` for an anonymous practitioner (forum, Reddit, review complaint); `tier2` for a
  named executive interview or structured review.
- Confidence: `high` for a complete, specific quote from a clear practitioner role; `medium`
  when the role or specificity is partial; `low`, used sparingly, for short or vague quotes
  that need a human check.
- Prefer speakers close to the profile's audience, and quotes that reveal the pain's context
  and business consequence. No two quotes with the same text or the same page and context.

## Show and approve

1. Per pain: its kept quotes (quote, speaker, link, domain, tier, confidence), or its "no quotes
   found" reason.
2. A count: "N quotes for M problems; K problems with no quotes found".
3. The user may drop quotes or ask for another search on a pain. Apply and confirm.
4. On yes, add the quotes to `quotes.md` (create it with the heading if missing), numbered
   after the highest existing QUOTE, `Found` today; add the no-quote pains to "Pains with no
   quotes found" with today's date.

## Next

Suggest `/whitefox-content-choose-topics`.

## Rules

- Nothing is saved before the user's yes.
- No link, no quote. Never invent a quote, a speaker, a source or a link.
- Web search is part of the user's Claude plan: this step has no separate cost.
