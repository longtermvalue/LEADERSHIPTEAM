# Finance data — what goes where

Not sure? Drop it in the repo-root `inbox/` instead and run `/file-inbox`.

| Subfolder | Drop here | Typical source |
|---|---|---|
| `bank-statements/` | Monthly chequing/savings statements (PDF or CSV) | Online banking → statements/documents |
| `credit-card-statements/` | Monthly card statements | Card portal → statements |
| `accounting-exports/` | P&L, balance sheet, trial balance, GL, AR/AP aging | QuickBooks/Xero → Reports → export |
| `invoices/` | Invoices you issued; AR aging | Accounting/invoicing tool |
| `bills/` | Supplier bills you owe | Email/AP folder |
| `budgets/` | Budget spreadsheets | Wherever the budget lives |
| `tax/` | Prior returns, notices of assessment, CRA letters, installment notices | CPA / CRA My Business Account |

After dropping statements: `/analyze-statements` (or `/monthly-close` at month
end). Export tips per system: `docs/data-exports.md`.
