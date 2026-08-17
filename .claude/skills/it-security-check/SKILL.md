---
name: it-security-check
description: Run the IT security and continuity review — account security, access hygiene, money-movement controls, backups with restore-test status, and incident readiness — into one ranked hardening plan. Use when the user says "security check", "are we secure?", "IT audit", or after an incident/departure.
---

Run the security + continuity sweep.

## Steps
1. Read `company/org-chart.md` and the systems inventory
   (`channels/operations/data/systems/`) first — the audit is scoped to systems and
   people that actually exist. Note recent departures explicitly (access-revocation
   check is mandatory).
2. Run the `cto-security-auditor` method (all six areas) and the `cto-data-steward`
   method (data map, backup coverage, scenarios) — in parallel where possible.
3. Merge into ONE report, `channels/technology/reports/YYYY-MM-DD-security-check.md`:
   posture scorecard → top 10 risks across both audits ranked by likelihood ×
   impact → 30-day hardening plan, cheapest-highest-impact first (each: owner,
   action, cost, effort) → incident one-pager status → ❓ evidence list (exports
   that would firm up the audit, e.g., an MFA status export into
   `channels/technology/data/security/`).
4. Reply with the scorecard, top 5 risks, and the first three actions to take this
   week.

## Rules
- Defense only; no secrets ever appear in the report.
- Every ✗ finding pairs with a concrete, affordable fix — a risk list without a
  plan is anxiety, not security.
