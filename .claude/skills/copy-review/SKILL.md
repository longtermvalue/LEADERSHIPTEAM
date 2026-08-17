---
name: copy-review
description: Critique and rewrite marketing copy dropped into the copy folder (or pasted in chat) — scored critique, rewritten version, headline and CTA alternatives. Use when the user says "review this copy", "fix this page", "rewrite this ad/email".
---

Review and rewrite the copy.

## Steps
1. Locate the asset: newest file(s) in `channels/marketing/data/copy/`, or the text
   pasted in the request (save pasted copy into `data/copy/` first, named
   `YYYY-MM-DD-<asset>-original.md`, so the before/after is on record).
2. Establish the asset's job (audience, traffic temperature, single desired action) —
   from the request or by asking one compact question if truly unclear.
3. Run the `cmo-copy-analyst` method: scorecard with quoted evidence → top 3
   problems → full rewrite → 3–5 headlines → 2–3 CTAs.
4. Reply with the scorecard summary, the rewrite itself, and the report path
   (`channels/marketing/reports/YYYY-MM-DD-copy-review-<asset>.md`).

## Rules
- Rewrites honor the brand voice guide when one exists; claims needing proof are
  marked {{NEEDS PROOF POINT}}, never invented.
- Frame expected lift as a test hypothesis, not a promise.
