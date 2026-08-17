---
name: cost-cut
description: Run a full cost-optimization sweep — recurring-spend census from the ledger, zombie subscriptions, duplicates, price creep, and negotiation targets, cross-checked against vendor contracts. Use when the user says "find savings", "cut costs", "audit our spending", or "cost cut".
---

Run the savings sweep.

## Steps
1. Verify ledger depth: `channels/finance/ledger/transactions.csv` should cover 6+
   months for a good sweep. Thinner data → run anyway but state the confidence
   limit; no ledger at all → point to `/analyze-statements` first.
2. Run the `cfo-cost-optimizer` method (full sweep, all six passes).
3. Cross-check against `channels/operations/data/vendor-contracts/` and the vendor
   register — contract end dates and notice windows turn "should cancel" into
   "cancel by <date>".
4. Reply with: total addressable savings $/yr, the top 5 actions this week (each
   with $ and the step to take), the verify-usage question list, and the report path
   (`channels/finance/reports/YYYY-MM-DD-cost-optimization.md`).
5. Offer the follow-ups: negotiation scripts for the top targets (already in the
   report), and a calendar of cancellation-notice deadlines.

## Rules
- Nothing gets cancelled by this skill — it produces the decision list; the owner
  executes.
- Every savings number is conservative and shows its math.
