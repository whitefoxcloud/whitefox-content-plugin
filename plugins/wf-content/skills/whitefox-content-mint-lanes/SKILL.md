---
name: whitefox-content-mint-lanes
description: Mint content lanes for a WhiteFox campaign (one buyer pain plus the proofs and quotes behind it, framed as a position WhiteFox can own), check them against the evidence, and save them to lanes.md; also makes lanes active, paused or archived. Use after mining quotes, or when the user wants lanes or wants to change a lane's status.
---

# Mint lanes

A lane is one reusable content idea: exactly one buyer pain, the evidence behind it, and a
stance. Each lane later yields many pieces of content. This step frames lanes from evidence
that already exists; it never invents evidence.

## Read first

- `../whitefox-content-guide/formats/README.md`, then begin as it says (workspace, settings,
  campaign, profile).
- `../whitefox-content-guide/formats/lanes.md` (the format).
- The campaign's `shelf.md` (matched rows and wording), `pains.md`, `quotes.md` and `lanes.md`
  (if it exists).

If there are no pains, suggest `/whitefox-content-derive-pains` and stop.

## Change a lane's status

If the user wants to make a lane active, pause it or archive it: show the lane, change its
`Status` after a yes, and stop. Only `active` lanes go on to keyword research and briefs.

## Mint

Propose at most 12 lane candidates: the strongest, most distinct ideas the evidence supports.
Fewer is fine; never pad. Existing lanes are memory: extend the map, never re-propose a lane
that already exists in substance.

1. **One pain per lane.** Each candidate has exactly one pain and cites only IDs that exist in
   this campaign: matched proofs, quotes, pains. A lane may stack several proofs. Its quotes
   should belong to its own pain.
2. **Type follows the evidence, never your choice:**
   - `full-stack`: cites a matched proof and at least one `in-domain` quote.
   - `silent-authority`: cites a matched proof but no `in-domain` quote. Content leads with
     WhiteFox's own delivery experience, never "everyone is complaining". Adjacent quotes may
     add colour, never as the campaign's own voice.
   - `commentary-only`: cites quotes but no proof. Content may discuss the problem and quote
     public voices; it must never claim WhiteFox solves it.
   - No proof and no quote: not a lane.
3. **Label:** a plain 4 to 8 word working label naming the mechanism (for example "KYC sequencing
   vs onboarding drop-off"). Not a headline; headlines come at brief time. No two lanes share a
   label.
4. **Stance names the cause.** Pains and quotes are symptoms. The stance is a one or two sentence
   position that names the design, process or architecture decision causing the symptom ("X
   fails when/because..."). The cause must be readable from the cited quotes or the cited
   delivery experience, never invented. Never restate the pain, dramatise its consequence, or
   give buying advice.
   - Weak: "Every delayed deposit becomes a support ticket." "Do not pick a provider by brand
     name."
   - Strong: "Compliance slows payment integrations when it is discovered instead of
     coordinated." "Payment investigations fail when every system owns a different fragment of
     the truth."
5. **Ownership.** WhiteFox is a software delivery partner, not an industry commentator. The
   reader's takeaway connects to building, fixing, integrating or choosing software, or choosing
   an engineering partner. Generic commentary a media outlet could run is not a lane. "Why
   WhiteFox" says who it speaks to and which proof earns the right to say it (for
   commentary-only: why listening publicly serves this audience).
6. **Search phrases.** Up to three, one per kind (problem, category, question), 2 to 5 words, no
   brands, no punctuation. Each must be something the profile's audience would literally type
   into a search box, in buyer vocabulary, never the voice of the buyer's own end users ("where
   is my money" is an app user's complaint, not a buyer search). Prefer the profile's keyword
   vocabulary. When no natural buyer phrasing exists for a kind, skip it with a reason.
7. **Quote variants.** Quotes are used word for word by default. When a quote names third-party
   products, niches narrower than the audience, or places that do not carry over, add a neutral
   version that abstracts only those specifics. The neutral version is the whole quote, word
   for word, with only those names replaced (for example "[the provider]"): never a fragment,
   never "...". Keep generic tools (Excel, spreadsheets, email) as written. Never strengthen,
   never add numbers.
8. **Numbers.** Every number in a label, stance or quote variant appears in the cited evidence.

## Grounding check (before showing)

Check each candidate's label, stance and "Why WhiteFox" against only its own cited evidence:

- **Invented:** names a capability, category, tool, metric or fact that no cited proof or quote
  supports, word for word or as an honest paraphrase. Fix it or drop the candidate.
- **Permission:** claims WhiteFox has, does or delivers something not backed by a cited proof.
  Quotes never license a WhiteFox claim. Fix it or drop the candidate.
- **Voice only:** a capability-shaped idea (an evaluation dimension, solution category or tool a
  reader could take as "WhiteFox does this") supported only by quotes, in a lane that also cites
  a proof. Keep it, and write a note in `Flags` so later writing discusses it through the quote
  and never claims it. Symptoms and pain vocabulary never need this note.

## Show and approve

1. One block per candidate: label, type, stance, why WhiteFox, pain, proofs, quotes, quote
   variants, search phrases, flags.
2. List any candidate you dropped in the grounding check, and why.
3. The user keeps, drops or edits candidates, and may mark lanes active straight away (on the
   review page, use `choice` `["keep", "active", "drop"]`; typed, for example "make 1 and 2
   active"). Apply and confirm.
4. On yes, add the kept lanes to `lanes.md` (create it with the heading if missing), numbered
   after the highest existing LANE, `Status` active for those marked active and candidate for
   the rest, `Demand` unknown, `Minted` today.
5. If no lane was marked active, ask which lanes to make `active` now. Update their status on
   yes.

## Next

For an `active` lane: `/whitefox-content-arm-brief` to plan its pieces, optionally after
`/whitefox-content-keyword-research` (free with web search, or paid with DataForSEO after a
price is shown).

## Rules

- Nothing is saved before the user's yes.
- Cite only IDs that exist in this campaign. Never invent evidence.
