---
name: whitefox-content-extract-proof
description: Extract proofs (what WhiteFox really delivered) and testimonials from a case study into the WhiteFox Content proof pool. Use when the user adds, attaches or links a WhiteFox case study, document or web page.
---

# Extract proof

Reads one case study and lists, word for word, what WhiteFox really delivered (proofs) and what
others said or awarded (testimonials). A case study is extracted once into the pool; every
campaign reuses it.

## Read first

- `../whitefox-content-guide/formats/README.md`, then begin as it says (workspace, settings).
  This step needs no campaign.
- `../whitefox-content-guide/formats/source.md` (the format).
- The `link` and `name` lines of every file in `pool/sources/`.

## 1. Get the text

The user attaches a file, pastes text, or gives a link.

- Link: open the page and take its main text. If you cannot open it, ask the user to paste the
  text or attach the file. Never extract from memory or a search snippet.
- Keep the full text exactly as captured. Leave out only site menus, footers, share buttons,
  cookie notices and image descriptions.

## 2. Already in the pool?

If a pool source has the same link, or clearly the same title and client, say "This case study
is already in your pool as `<source-id>`, with N proofs" and stop. Suggest
`/whitefox-content-match-proof` to use it in a campaign. Offer to extract again only if the user
says the case study has changed; then the new extraction goes into the same file after a yes,
and proofs that disappeared are set to `archived`, never deleted.

## 3. Extract

**Proofs.** Each proof is one distinct thing WhiteFox built or delivered.
- Grain: follow the case study's own capability headings and named components. The security
  stack is one proof; the delivery model is one proof. Merge sub-bullets into their parent.
  No fragments, no restatements, no duplicates.
- Solution: what WhiteFox built or delivered. Required. Copy it from the text.
- Problem: the client's actual challenge, from the text, or `(none)`.
- Outcome: the result, from the text, or `(none)` when no concrete result is stated.
- Metric: the number inside that outcome, exactly as written, or `(none)`. It must appear in the
  text. Never invent, round or combine numbers.
- Each field is whole sentences copied from the text, in their original order. No "...", no
  joining parts of different sentences, no words of your own (no summary, no list you
  compiled, no "the case study says"), and no quotation marks around the field.
- Keep every real specific: client names, places, third-party products, numbers. When a detail
  matters (a shortlist of options, a time a step took), include the sentence that states it.
  Do not generalise ("teams need...") and do not soften a fact. Rewording for a campaign
  happens later, in `/whitefox-content-match-proof`.
- Leave out sentences that are only marketing ("to truly revolutionise..."), calls to action,
  SEO text, and sentences about future work that was not delivered ("to be followed by...").

**Testimonials.** Capture every quote from a named or quoted person, and every award or formal
recognition WhiteFox received.
- Text: word for word. Pick the sentences that carry it; never reword inside them.
- Kind: `testimonial` for a person's quote, `award` for an award, prize, certification or
  formal recognition.
- Author: the name and role given, or `(none)`.
- Issuer: for awards, who granted it and the programme, word for word; `(none)` otherwise.
- An award page usually also shows capabilities: extract those as proofs too.

## 4. Check before showing

1. Every sentence in a proof or testimonial field appears, word for word, in the captured
   text. Fix any field that does not.
2. Every number in a proof or testimonial appears in the captured text.
3. Every Solution is filled.
4. No two proofs say the same thing.
5. No proof is marketing copy without a concrete deliverable.

## 5. Show and approve

1. Propose a source ID: short, lowercase, from the client or project name (for example
   `acme-claims`). It must not exist in `pool/sources/`.
2. Ask whether the case study is public: `yes`, `no` or `needs review`. If it came from a public
   web page, suggest `yes`.
3. Show the proofs and testimonials as numbered lists with their IDs, then a one-line count:
   "N deliveries, M testimonials from <name>".
4. The user may correct, merge, split or drop items. Apply the changes and show the list again
   if anything changed.
5. On yes, save `pool/sources/<source-id>.md` in the format, with the full text under `## Text`,
   `captured` today and `captured_by` the user's name.

## 6. Next

Suggest `/whitefox-content-match-proof` to judge the new proofs for a campaign. If the user has
no campaign, suggest `/whitefox-content-campaign` first.

## Rules

- Nothing is saved before the user's yes.
- Extract only what the text supports. Never add a capability, metric, outcome or quote.
- Extraction is campaign-neutral: do not lean toward any campaign's audience or vocabulary.
