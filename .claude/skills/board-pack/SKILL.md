---
name: board-pack
description: Produce a quarterly board pack or investor/bank update — CEO letter, financials vs. plan, goal progress, lowlights/highlights, and asks. Use when the user says "board pack", "board report", "investor update", or "bank update".
---

Produce the board pack via `ceo-board-reporter` (delegate to that agent, or follow
its method directly).

## Steps
1. Confirm the audience (board / advisors / investor / bank) and period — tone and
   detail differ; a bank cares about coverage and cash, a board about strategy.
2. Ensure ingredients are fresh: KPI scorecard and a financial summary for the
   period. If stale (>30 days), run those analyses first (`ceo-kpi-analyst`,
   `cfo-financial-analyst` methods) rather than shipping stale numbers.
3. Read the prior board pack in `channels/ceo/data/board-minutes/` or
   `channels/ceo/reports/` — the new pack must answer "what did we say last time and
   what happened?"
4. Compose per the board-reporter skeleton (CEO letter, financials vs. plan vs.
   prior, goal progress, lowlights first, asks, appendix).
5. Save to `channels/ceo/reports/YYYY-MM-DD-board-pack.md`. Offer a DOCX/PDF export
   if the user wants a sendable file.

## Rules
- No spin; restated numbers reconciled explicitly.
- Every "ask" of the board is specific (decision, intro, approval) — no vague
  "support" asks.
