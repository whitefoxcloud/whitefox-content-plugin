---
name: whitefox-content-name-problems
description: Name a campaign's audience problems (the problems our deliveries solve, in the audience's own words), ready for finding quotes. Use after checking what fits, or when the user wants a campaign's audience problems.
---

# Derive pains

Turns the campaign's matched proofs into buyer pains: the problems that exist without what
WhiteFox delivered, phrased the way a real practitioner complains. These are search targets for
`/whitefox-content-find-quotes`. The goal is fixed: B2B demand generation, turning buyers into
enquiries.

## Read first

- `../whitefox-content-guide/formats/README.md`, then begin as it says (workspace, settings,
  campaign, profile).
- `../whitefox-content-guide/formats/pains.md` (the format).
- The campaign's `shelf.md`: the `matched` rows and their wording. For each, the proof's
  Problem, Solution, Outcome and Metric in its pool file.
- The campaign's `pains.md`, if it exists.

If no proof is matched, say so and suggest `/whitefox-content-check-fit`. Stop.

## Derive

Produce a short list, about 8 to 12 pains, for the profile's audience and industry.

- Each pain is the buyer's problem in the buyer's words, never WhiteFox's solution or a
  marketing claim.
- Invert each proof: the proof says "built X"; the pain is what hurts without X, said the way a
  practitioner would complain ("we can't see the full picture, it's scattered across three
  systems"), never "teams need a platform".
- Neutral: no client, product or place, so it matches broad public voices. Specific enough to
  search: never "teams need efficiency".
- It fits this audience and industry.
- Draw from both: the pain each matched proof addresses (list the proof IDs), and nearby pains
  this audience plausibly voices even without proof (write `gap`).
- A proof backs a pain only when its Solution or Outcome directly removes that pain. A passing
  mention is not backing (a proof built "with a focus on compliance" does not back "compliance
  slows every release"): write `gap` instead.
- When several proofs address the same pain, write one pain and list all their IDs.
- Search angle: a phrase you would expect inside a real practitioner's quote about it.

## Compare with existing pains

If `pains.md` already has pains, check each new one against them and against each other. Treat
two pains as the same only if the same fix would satisfy both: the same failure in the same
workflow. A different symptom of the same failure is the same pain. The same area but a
different failure is a new pain. When unsure, it is new.

For a new pain that matches an existing one, do not add it. Show it as "already covered by
PAIN-nn: <the shared failure in one line>". If it brings a proof the existing pain lacks, offer
to add that proof ID to the existing pain's "Backed by".

## Show and approve

1. Proof-backed pains first, then `gap` pains, then "already covered".
2. For each: the pain, its backing, its search angle.
3. The user may edit, drop or add pains. Apply and confirm.
4. On yes, add the approved pains to `pains.md` (create it with the heading if missing),
   numbered after the highest existing PAIN, `Audience` from the profile (or the narrower role
   the pain belongs to), `Derived` today.

## Next

Suggest `/whitefox-content-find-quotes` to find real buyers voicing these pains.

## Rules

- Nothing is saved before the user's yes.
- Only cite proof IDs that are `matched` in this campaign's shelf.
