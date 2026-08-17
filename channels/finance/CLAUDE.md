# Finance & Accounting (CFO) Channel

Owns the numbers: bookkeeping from raw statements, financial analysis, cash flow,
budgets, cost optimization, receivables/payables, and Canadian tax readiness.

## Agents
| Agent | Use for |
|---|---|
| `cfo-bookkeeper` | New bank/card statements → categorized transactions in the ledger |
| `cfo-financial-analyst` | P&L/balance-sheet analysis, margins, trends, ratios |
| `cfo-cashflow-forecaster` | 13-week cash forecast, runway, scenario stress tests |
| `cfo-cost-optimizer` | Finding savings: subscriptions, duplicates, negotiable spend |
| `cfo-budget-analyst` | Budget vs. actual variance and reforecasting |
| `cfo-ar-ap-analyst` | Who owes us / whom we owe; collections and payment timing |
| `cfo-tax-organizer` | CRA calendar: HST, payroll remittances, T4/T5, T2; document readiness |

## Skills: `/monthly-close`, `/analyze-statements`, `/cost-cut`

## Data (inputs — read-only)
- `data/bank-statements/` — monthly PDFs/CSVs per account
- `data/credit-card-statements/` — monthly card statements
- `data/accounting-exports/` — QuickBooks/Xero P&L, balance sheet, trial balance, GL
- `data/invoices/` — issued invoices / AR aging exports
- `data/bills/` — supplier bills / AP exports
- `data/budgets/` — budget spreadsheets
- `data/tax/` — prior returns, CRA correspondence, installment notices

## The ledger (maintained by `cfo-bookkeeper`)
- `ledger/transactions.csv` — append-only, columns:
  `date,account,description,amount,currency,category,subcategory,vendor,flags,source_file`
  (amount: negative = money out; account = masked nickname e.g. "RBC-chequing-1234")
- `ledger/processed-files.md` — list of statement files already ingested (with date
  ranges and transaction counts) so nothing is double-counted. **Check before ingesting.**
- Category set: Revenue; COGS; Payroll & Contractors; Rent & Utilities; Software &
  Subscriptions; Marketing & Advertising; Professional Fees; Insurance; Banking & Fees;
  Travel & Meals; Equipment & Supplies; Taxes & Government; Loan & Interest; Owner
  Draws/Contributions; Transfers (internal); Uncategorized. Keep it stable; extend via
  subcategory rather than inventing new top-level categories.

## Channel rules
- CAD default; note FX explicitly when a statement shows USD.
- Mask all account numbers to last 4 everywhere, including the ledger.
- Internal transfers must net to zero across accounts — never count them as income
  or expense.
- Every report reconciles: state opening balance, inflows, outflows, closing balance
  per account, and flag any gap vs. the statement.
- Tax/accounting outputs end with the professional-advice disclaimer (see root
  CLAUDE.md rule 7) — this channel prepares, a CPA files.
