# Data Export Cheat-Sheet

How to get the useful exports out of common systems, and where they land. Coarse
directions on purpose — menus move, but every system below has these reports.
Easiest path always: download it, drop it in `inbox/`, run `/file-inbox`.

## Finance

| System | What to export | Format | Lands in |
|---|---|---|---|
| Online banking (RBC/TD/BMO/Scotiabank/CIBC…) | Monthly statement per account (look under Statements & Documents); CSV of transactions also works | PDF or CSV | `finance/data/bank-statements/` |
| Credit card portal | Monthly statements | PDF or CSV | `finance/data/credit-card-statements/` |
| QuickBooks Online | Reports → Profit & Loss, Balance Sheet, General Ledger, AR Aging, AP Aging (export to Excel) | XLSX/CSV | `finance/data/accounting-exports/` |
| Xero | Accounting → Reports → same set | XLSX/CSV | `finance/data/accounting-exports/` |
| Payroll (ADP/Ceridian/Wagepoint/QBO Payroll…) | Payroll register per run or per month; T4 summary at year end | PDF/CSV | `hr/data/payroll-reports/` |
| CRA My Business Account | Notices of assessment, statements of account | PDF | `finance/data/tax/` |

## Marketing

| System | What to export | Format | Lands in |
|---|---|---|---|
| Google Ads | Campaigns + Search terms reports for the period (custom date range) | CSV | `marketing/data/ad-exports/` |
| Meta Ads Manager | Campaign/ad set/ad performance for the period | CSV | `marketing/data/ad-exports/` |
| GA4 | Reports snapshot / Traffic acquisition / Conversions for the period (Share → download) | CSV | `marketing/data/analytics/` |
| Google Search Console | Performance report (queries + pages) | CSV | `marketing/data/analytics/` |
| Mailchimp/Klaviyo/etc. | Campaign performance table; flow/automation stats | CSV | `marketing/data/email-campaigns/` |
| Google Business Profile | Reviews (copy/paste or export) | any | `customer-experience/data/reviews/` |

## Sales, store, support

| System | What to export | Format | Lands in |
|---|---|---|---|
| HubSpot/Pipedrive/etc. | All deals with stage, amount, dates, source, owner | CSV | `sales/data/crm-exports/` |
| Shopify | Orders export (by line item) for the period; Inventory export | CSV | `ecommerce/data/sales-exports/`, `inventory-exports/` |
| Amazon Seller Central | Business reports (by SKU); FBA inventory | CSV | same as above |
| Zendesk/Intercom/etc. | Ticket export with timestamps and outcomes | CSV | `customer-experience/data/support-exports/` |

## Habits that make this painless

- **Monthly bundle**: once a month, grab the checklist in the README ("Monthly data
  drop"), download everything into one folder on your machine, drag the whole
  folder into `inbox/` on GitHub, run `/file-inbox` → `/run-routines`. ~15 minutes.
- **Filenames don't matter** if you use the inbox — `/file-inbox` reads content and
  renames properly. They DO help if you file manually: include the period
  (`2026-07-...`).
- **Google Drive shortcut**: if the Drive connector is enabled in your Claude
  session, you can skip the download hop — "grab July's statements from my Drive
  folder and file them."
- **When a report says data is missing**, it names the exact export and folder —
  that sentence is your to-do, and this sheet tells you where to click.
