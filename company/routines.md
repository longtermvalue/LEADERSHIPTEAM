# Routines — Recurring Cadence

The company's operating rhythm. `/run-routines` reads this table, checks what's due
(by comparing each routine's frequency against the date of its latest matching
report), and runs what's owed. Any scheduler can trigger it — a Claude Code Routine,
a GitHub Action, or a human typing `/run-routines` — see `docs/automation.md`.

Edit freely per company: change frequencies, disable rows (set Active to "no"),
add rows for custom skills.

| Routine | Skill | Frequency | Preferred timing | Priority | Active | Notes |
|---|---|---|---|---|---|---|
| Weekly leadership brief | `/weekly-brief` | weekly | Monday morning | 1 | yes | Skips gracefully if nothing new |
| Monthly finance close | `/monthly-close` | monthly | 3rd of month | 1 | yes | Needs the month's statements dropped first — reports what's missing if not |
| Inventory review | `/inventory-review` | monthly | 1st week | 2 | no | Enable for e-commerce/inventory companies; weekly if fast-moving |
| Competitor scan | `/competitor-scan` | monthly | mid-month | 3 | yes | |
| AR/AP + collections refresh | agent: `cfo-ar-ap-analyst` | monthly | with close | 2 | yes | Runs as part of `/monthly-close`; separate row if invoicing is heavy |
| Cost-cut sweep | `/cost-cut` | quarterly | quarter start | 2 | yes | Needs 6+ months of ledger to be useful |
| HR compliance audit | `/hr-compliance-check` | quarterly | quarter start | 2 | yes | Also run after any headcount change |
| IT security check | `/it-security-check` | quarterly | quarter start | 2 | yes | Also run after any departure or incident |
| Marketing audit | `/marketing-audit` | quarterly | quarter start | 3 | yes | Monthly `/ad-review` instead if ad spend is significant |
| Corporate records check | agent: `legal-records-keeper` | semi-annual | Jan & Jul | 3 | yes | Filings, minute book, insurance renewals |
| Board pack | `/board-pack` | quarterly | before board mtg | 2 | no | Enable if there's a board/advisors/lender |
| Ecom audit | `/ecom-audit` | quarterly | quarter start | 3 | no | Enable for e-commerce companies |

## How "due" is determined

Each routine maps to a report naming pattern (e.g., `/weekly-brief` →
`channels/ceo/reports/*-weekly-brief.md`). A routine is **due** when the newest
matching report is older than its frequency allows (weekly: 6+ days, monthly: 28+
days, quarterly: 85+ days, semi-annual: 175+ days), and **overdue** at 1.5× that.
No matching report ever = due.

## Run log

`/run-routines` appends one line per run here so cadence survives any scheduler:

| Date | Routines run | Skipped (reason) |
|---|---|---|
