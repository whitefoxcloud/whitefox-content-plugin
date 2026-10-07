# Changelog

## 0.4.0

- The evidence steps are built: extract-proof, match-proof, derive-pains, mine-quotes and
  mint-lanes, carrying the WhiteFox content app's rules.
- `whitefox-content-start` says when a newer version is on GitHub and how to update.
- Formats: a proof keeps the case study's own words; the campaign wording for it moves to the
  shelf. A pain may be backed by `gap`. Quotes gain a tier; lanes gain quote variants and flags.
  Every step begins the same way (see `formats/README.md`).

## 0.3.0

- Every step is renamed with the `whitefox-content-` prefix, so WhiteFox commands are easy to
  find and cannot clash with other plugins: `/whitefox-content-start` in the Claude app,
  `/wf-content:whitefox-content-start` in Claude Code.

## 0.2.0

- `start` sets up the workspace folder on first use (settings, folders, starter profiles),
  lists profiles and campaigns, and suggests each campaign's next step.
- `guide`, `house-style`, `profile` and `campaign` are built.
- Workspace formats: rules and one template per file in `skills/guide/formats/`.
- Starter profiles gained `changed_by` and `changed`.

## 0.1.0

- Skeleton: marketplace, the `wf-content` plugin, a working `start` skill, and placeholders for
  every workflow step.
- Starter profiles FIN, INS, HC and AI, transcribed from the WhiteFox content app.
