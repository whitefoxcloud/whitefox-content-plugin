---
name: whitefox-content-match-proof
description: Judge which proofs in the WhiteFox Content pool fit a campaign's audience, and word each matched proof for that audience, saving the verdicts to the campaign's shelf. Use after extracting a case study, or when the user wants to match proofs to a campaign.
---

# Match proof

For one campaign, judges every pool proof not yet judged: does it give WhiteFox permission to
speak to this campaign's audience? Matched proofs get one line of wording for that audience.

## Read first

- `../whitefox-content-guide/formats/README.md`, then begin as it says (workspace, settings,
  campaign, profile).
- `../whitefox-content-guide/formats/shelf.md` (the format).
- The campaign's `shelf.md`, if it exists.
- Every file in `pool/sources/`: the proofs with status `active`.

The proofs to judge are the active pool proofs not listed in `shelf.md`. If there are none, say
"Everything we delivered in your case study library is already checked for <campaign>" and suggest
`/whitefox-content-start` to see the next step. If the pool is empty, suggest
`/whitefox-content-extract-proof`.

Judge at most 20 proofs per round. With more, do 20, save after approval, then offer the next
round.

## How to judge

Use the profile's industry and audience as the lens. Judge each proof on its own substance.

1. Judge every proof in the round: `matched` or `rejected`, with one or two sentences why. If a
   proof cannot be judged (empty or garbled), say so and leave it unjudged.
2. Judge the capability, not keywords. Cross-industry transfer is normal and valuable: never
   reject a proof only because it comes from another industry. Transfer is `direct` when the
   proof's industry is the campaign's industry, `cross-industry` otherwise.
3. A match serves this audience in one of two ways; name which in the why:
   - it maps to a specific workflow or buyer problem of this audience (name it); or
   - it is domain-neutral by nature: engineering, delivery or product practice whose value
     never depended on the origin industry (prototype to production, delivery governance, IP
     ownership, model validation). Name the buying concern it serves (de-risking an engineering
     partner, readiness to scale, AI governance). Word it as what it is; never dress it up as
     this industry.
4. Reject only when:
   - the capability is welded to its origin domain: strip the origin industry and nothing
     usable remains (for example a clinical data-standards converter); or
   - the proof is too thin to support any claim: it names no practice, capability or
     deliverable at all. If a practice can be named (handover, training, IP ownership, a built
     thing), it is not thin: match it with modest wording.
5. Calibration: a mixed pool usually gives both matches and rejections. If every proof gets the
   same verdict, look again. Never force a quota.
6. Wording, for matched proofs: one buyer-readable line for this audience. Abstract, never
   amplify. Use only outcomes and numbers already in that proof. Remove client names, products
   and niches narrower than the audience; keep generic tools and categories. No jargon from the
   origin industry unless it carries over.
7. Whether the case study is public is context for the user, never a reason to reject.

## Check before showing

- Every number in a wording appears in that proof's fields. If not, fix the wording.
- Every matched proof has a wording; every proof in the round has a verdict or is left
  unjudged with a reason.

## Show and approve

1. Lead with what needs the user's eyes: cross-industry matches (is the transfer sound?), and
   any wording you had to fix.
2. Then a table: Proof, Verdict, Transfer, Wording, Why.
3. The user may flip verdicts or edit wordings. Apply and confirm.
4. On yes, add the rows to `shelf.md` (create it with the heading if missing), `Judged` today.
   Leave existing rows untouched. Proofs left unjudged are not written; they come back next
   round.

## Next

If there is at least one `matched` row and no `pains.md`, suggest
`/whitefox-content-derive-pains`. If nothing matched, suggest a case study that fits this
audience with `/whitefox-content-extract-proof`.

## Rules

- Nothing is saved before the user's yes.
- Never change a pool file from this step.
