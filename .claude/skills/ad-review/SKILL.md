---
name: ad-review
description: Analyze a freshly dropped ad-platform export (Google, Meta, LinkedIn) — waste, winners, and a reallocation move-list. Use when the user drops an ad export or says "review my ads", "how are the ads doing?"
---

Analyze the newest ad export(s).

## Steps
1. Find the newest files in `channels/marketing/data/ad-exports/` (or ask which to
   use if several platforms landed at once). Confirm the platform, date range, and
   granularity from the file itself.
2. Get the break-even context: gross margin per sale from finance reports, CAC
   target from `company/goals-and-okrs.md`. If neither exists, ask for average sale
   value and rough margin — two numbers, then proceed.
3. Run the `cmo-ad-analyst` method in full (economics chain, the five waste hunts,
   reallocation ranking).
4. Reply with: spend and blended CPA/ROAS for the period, the top 3 moves with $
   impact, and the report path
   (`channels/marketing/reports/YYYY-MM-DD-ad-analysis-<platform>.md`).

## Rules
- Small-sample findings are labeled directional; missing conversion tracking is
  always finding #1 when true.
- Compare to the prior period's report when one exists — trends beat snapshots.
