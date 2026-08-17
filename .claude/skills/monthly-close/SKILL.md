---
name: monthly-close
description: Run the monthly finance close — ingest any new statements into the ledger, produce the month's P&L summary, update AR/AP, refresh the cash forecast, and surface opportunities. Use when the user says "monthly close", "close the month", or "month end".
---

Run the finance close for the most recently completed month (confirm which month if
ambiguous).

## Sequence
1. **Ingest**: check `inbox/` for unfiled financial documents (file them via the
   `/file-inbox` flow first), then run the `cfo-bookkeeper` method — process any
   statement files not yet in `channels/finance/ledger/processed-files.md`. If the
   month's statements aren't dropped yet, stop and list exactly which files are
   needed — and remind that dropping them anywhere in `inbox/` is enough.
2. **Analyze**: `cfo-financial-analyst` method for the month — P&L, variances,
   trends. If a budget exists in `data/budgets/`, include `cfo-budget-analyst`
   variance mode.
3. **AR/AP snapshot**: `cfo-ar-ap-analyst` method if invoice/bill data exists —
   at minimum, deposits vs. issued invoices from what's on file.
4. **Cash**: refresh the 13-week forecast (`cfo-cashflow-forecaster` method) with
   the new closing balances.
5. **Opportunities**: quick pass of `cfo-cost-optimizer` flags from the new month's
   transactions (full sweep is `/cost-cut`, not here).
6. **Package**: one close report at
   `channels/finance/reports/YYYY-MM-DD-monthly-close-<month>.md` — month P&L,
   cash position & runway, AR/AP highlights, flags, and "for the owner: 3 numbers
   that matter this month." Reply with the executive summary and the report path.

## Rules
- Reconciliation failures stop the pipeline for that account — report them, don't
  build analysis on unreconciled data.
- Uncategorized transactions above the channel threshold: list the questions for
  the owner at the top of the reply, not buried.
