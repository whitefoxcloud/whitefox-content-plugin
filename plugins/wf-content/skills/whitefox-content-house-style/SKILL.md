---
name: whitefox-content-house-style
description: WhiteFox house style for all content - priority order, brand voice, anti-AI writing rules, banned phrases, posting personas (company, founder, engineer) and length per channel, with a checklist. Use whenever writing or reviewing a WhiteFox LinkedIn post, article or email, or when the user asks about the writing rules.
---

# House style

Version 1.2.0 (carried over from the WhiteFox content app). Every writing step follows these
rules and runs the checklist at the end before showing a draft. If the user only asked about
the rules, show the relevant part, short.

## Priority

Accurate, then clear, then specific, then human, then style. Never follow a style rule into an
awkward result.

## Evidence stays exactly as given

Never reword these to fit a style rule: customer quotes and their buyer phrasing, proof claims,
product and feature names, named standards.

## Brand

- Write as the brand ("we") to the client ("you").
- Australian English spelling (optimise, organise, specialise, licence, centre).
- Location-agnostic: never tune content to one country's market or imply availability
  anywhere. A country-specific rail, standard or regulation (like PayID or FedNow) appears only
  as a named example of a capability.
- Sentence case for headings and buttons. Uppercase only for short eyebrows and table headers.
- Numbers: concrete figures, and only ones the proofs give. Never invent or round a number.
- Name a real standard when it builds trust (FHIR, HL7, ISO 27001, HIPAA, GDPR).
- No emoji.
- Voice: direct, credible, customer-centric, aware of regulated industries. Lead with outcomes.
  Confident, never hype or hedging.
- Use the campaign profile: its positioning, never write anything from "Never position as", use
  brand terms as written, avoid exclude terms.

## Write like a sharp human

- Vary sentence length. Mix short lines with longer ones; no metronome of same-length sentences
  and same-shape paragraphs.
- Use contractions naturally (don't, can't, it's).
- No em dashes. Use commas, periods or parentheses.
- No colon to pivot an ordinary sentence ("the pattern is simple: users leave"). Write two
  sentences. A colon is fine before a list or steps.
- Headings, bullets and numbered lists only when they earn their place.
- No closing summary paragraph that restates what was said.
- No hype and no promises of overnight transformation or effortless wins.
- No antithesis or negative parallelism: "not X, it's Y", "not just X but Y", "it isn't about
  X, it's about Y", "no X, no Y, just Z", "don't do X, do Y", "the problem is not X, the problem
  is Y". Also no positive reframe: "means more than X. It means Y", "is about more than X". If
  one slips out, delete everything before the real claim and say what it is.
- Avoid the rule of three when the items are interchangeable or one only fills a slot. Use two,
  four, or the one thing that matters.
- Say "is" and "has", not "serves as", "stands as", "represents", "marks a", "holds the
  distinction of being".

## Banned phrases

Never use: delve, unlock, supercharge, future-proof, game-changer, game changer, cutting-edge,
revolutionise, revolutionize, 10x, in today's fast-paced, in today's digital landscape, robust
solution, leverage synergies, empower teams, digital transformation journey, transform your
business, seamless experience, seamless integration, not just, not only, we are thrilled to
announce, comment below if you agree, ultimate guide, comprehensive guide.

Emails also never use: hope this email finds you well, just checking in, bumping this to the
top of your inbox.

## Posting personas

Each angle names who posts it. All three write as "we"; what differs is whose "we", the
altitude and the vocabulary.

**Company page** (`company`): the brand's calm, proof-led record of work.
- "We" is the brand, speaking to "you", the buyer.
- Outcomes and proof: what we built, what the client can now do.
- Clear and composed, little jargon. A concrete figure or named standard beats an adjective.
- Open with the client's situation or the outcome, not with ourselves.
- Call to action can be direct (book a review, read the case study).
- Avoid personal takes, war stories, speculation.

**Founder** (`founder`): leadership voice; decisions, patterns, business consequence.
- "We" is the company; it reads like the person who steers it.
- Decisions and patterns: why builds succeed or fail, tradeoffs, what repeated experience
  taught us. Land on cost, risk, speed or trust.
- Plain language. Translate the technical into what it means for the buyer's business.
- Open with a conviction or a lesson, then earn it with something seen across builds.
- May push back on a common belief when the evidence backs it.
- Call to action is an invitation to compare notes, not a pitch.
- Avoid implementation detail and acronym chains.

**Engineer** (`engineer`): practitioner voice; mechanisms, specifics, operational reality.
- "We" is the delivery team, the people who built it.
- Mechanisms: integration points, data flows, edge cases, failure modes, the part everyone
  underestimates.
- Precise and technical. Name the actual thing (the API, the queue, the referral rule), never
  "seamless integration".
- Open with the concrete problem or the surprising detail from the build.
- Call to action soft and practical: a question to the reader, a pointer to the build.
- Avoid big strategic claims, marketing language, rounding away the messy details.

## Length per channel

| Channel | Length |
|---|---|
| LinkedIn post | 110 to 180 words |
| Email | 80 to 150 words; never over 170 |
| Article | no minimum; usually 1200 to 1800 words; never over 2200 |

Keywords are natural topic anchors. Never repeat a keyword for density.

## Using evidence in a draft

- **Proofs.** Claim only what a proof the angle uses states, never beyond its scope. Weave it in
  naturally where it adds specificity; do not recite the proof sentence. Name a client or partner
  only when the name is in the profile's brand terms and the case study is public (`public:
  yes` in its pool file); otherwise use the shelf wording.
- **Claim level.** `pitch`: name what WhiteFox built. `soft`: hint at it from experience ("in
  builds like this we have seen..."), no direct capability claim. `none`: no WhiteFox capability
  claim at all; the piece discusses the problem only.
- **Silent-authority lanes**: write from delivery experience ("what we learned shipping this"),
  never "everyone is complaining".
- **Quotes.** Use them to shape pain language: paraphrase the pain, echo the buyer's short
  phrases where they fit. Never present a quote as a testimonial or name its source. A
  quote-style line, used sparingly, is framed as language heard in the market. Use the lane's
  neutral variant when the angle marks the quote `(neutral)`. Adjacent quotes are texture,
  never this campaign's own buyers speaking.
- **Flags.** A voice-only idea is discussed through its quote, never claimed. A permission note
  limits the claim exactly as written.
- **Call to action.** One, specific to the piece, from the profile's lead routes, in your own
  words. No link or URL in the text unless the user gives one.
- **Built from.** Under every draft, list each proof and quote used and the sentence or section
  that relies on it, so a reviewer can trace every claim.

## Checklist (run before showing any draft)

1. No em dash anywhere.
2. No banned phrase.
3. No antithesis, negative parallelism or "more than X. It means Y" reframe.
4. Every number appears in a cited proof, unchanged.
5. Every quote-style line is word for word from `quotes.md` (or its neutral variant), and no
   quote is presented as a testimonial or named source.
6. Every WhiteFox claim is backed by a proof the angle uses and stays within the claim level.
7. Nothing from the profile's "Never position as"; no exclude term.
8. Australian spelling; no emoji; sentence-case headings.
9. Length is inside the channel range.
10. Reads in the chosen persona's voice.
11. No closing summary paragraph.
12. The profile is `approved`. If not, say "Profile <CODE> is <status>, not approved yet" above
    the draft.
13. No profile field still reads `[placeholder]`, `unknown` or `(none)` where the draft needs
    it. If one does, stop and ask the user to fill it with `/whitefox-content-profile`.

Fix what fails before showing the draft, then list the checks under it with each one ticked.
