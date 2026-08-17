---
name: file-inbox
description: Identify, rename, and file everything sitting in inbox/ (or attached in chat) into the correct channel data folders, then offer the matching analyses. Use when the user says "file my uploads", "sort the inbox", drops files anywhere and asks to put them away, or when a session notices inbox/ has unfiled files.
---

File the inbox. Files attached in chat count as inbox drops — save them to
`inbox/` first, then proceed identically.

## Steps

1. **Inventory**: list every file in `inbox/` (except README.md and
   filing-log.md). If empty, say so and stop.

2. **Identify each file by content, not filename** (open PDFs/CSVs/images and
   look). Detection guide:

   | Signals in the file | Type | Destination |
   |---|---|---|
   | Bank name, account activity, opening/closing balance | Bank statement | `channels/finance/data/bank-statements/` |
   | Credit limit, minimum payment, statement balance | Card statement | `channels/finance/data/credit-card-statements/` |
   | P&L / balance sheet / trial balance / general ledger headers | Accounting export | `channels/finance/data/accounting-exports/` |
   | Invoice FROM the company (company is the biller) / AR aging | Invoice/AR | `channels/finance/data/invoices/` |
   | Invoice TO the company (company is the customer) | Bill/AP | `channels/finance/data/bills/` |
   | Budget lines by month | Budget | `channels/finance/data/budgets/` |
   | Tax return, notice of assessment, CRA letter | Tax doc | `channels/finance/data/tax/` |
   | Campaign/ad set/keyword + impressions/clicks/cost columns | Ad export (note platform) | `channels/marketing/data/ad-exports/` |
   | Sessions/users/pageviews (GA4, Search Console) | Analytics | `channels/marketing/data/analytics/` |
   | Landing page/ad/email text to review, brand or voice docs | Copy / brand | `channels/marketing/data/copy/` or `brand/` |
   | ESP campaign stats (opens/clicks/unsubs) | Email marketing | `channels/marketing/data/email-campaigns/` |
   | Competitor site captures, pricing screenshots | Competitor intel | `channels/marketing/data/competitors/` |
   | Deal/stage/amount/close-date columns | CRM export | `channels/sales/data/crm-exports/` |
   | Proposal/quote documents; discovery or call notes | Proposals / call notes | `channels/sales/data/proposals/` or `call-notes/` |
   | Employee names + gross/net/CPP/EI | Payroll register (CONFIDENTIAL) | `channels/hr/data/payroll-reports/` |
   | Offer letter, employment/contractor agreement | Agreement | `channels/hr/data/employment-agreements/` |
   | Handbook/policy text | Policy | `channels/hr/data/policies/` |
   | Job description, resume, candidate notes | Recruiting | `channels/hr/data/recruiting/` |
   | Signed/draft contract with an outside party (lease, MSA, NDA) | Contract → legal; vendor SaaS/service agreements → ops | `channels/legal/data/contracts/` or `channels/operations/data/vendor-contracts/` |
   | Articles, resolutions, registers, annual return confirmations | Corporate record | `channels/legal/data/corporate-records/` |
   | Insurance policy/certificate/renewal | Insurance | `channels/legal/data/insurance/` |
   | SOP/process description | SOP | `channels/operations/data/sops/` |
   | Project plan/status/task export | Project | `channels/operations/data/projects/` |
   | Reviews/NPS/CSAT/survey results | Customer feedback | `channels/customer-experience/data/reviews/` or `surveys/` |
   | Helpdesk/ticket export, chat transcripts | Support | `channels/customer-experience/data/support-exports/` |
   | SKU/on-hand/stock columns | Inventory | `channels/ecommerce/data/inventory-exports/` |
   | Order-level sales by SKU (Shopify/Amazon/POS) | Store sales | `channels/ecommerce/data/sales-exports/` |
   | SKU list with costs/prices | Catalog | `channels/ecommerce/data/product-catalog/` |
   | Supplier price list/PO/lead times | Supplier | `channels/ecommerce/data/suppliers/` |
   | Store page/checkout screenshots, platform funnel export | Storefront | `channels/ecommerce/data/storefront/` |
   | MFA/access/backup reports, DNS/hosting docs | IT | matching `channels/technology/data/` subfolder |
   | Board/advisory minutes, strategy decks, KPI dashboards | Executive | matching `channels/ceo/data/` subfolder |

3. **Rename on filing** to `YYYY-MM-<source>-<type>.<ext>` using the period *from
   the file's content* (e.g., `2026-07-rbc-chequing-1234-statement.pdf`,
   `2026-07-google-ads-campaigns.csv`). Account numbers in names masked to last 4.
   Keep the original extension; never convert formats while filing.

4. **Move** (`git mv` / move) each confidently-identified file from `inbox/` to its
   destination. Moving OUT of inbox is sanctioned; once a file is inside a `data/`
   folder the read-only rule applies as usual. If the destination already has a
   file covering the same account+period, do NOT overwrite — keep both (suffix
   `-b`) and flag the possible duplicate.

5. **Hold the uncertain ones**: anything ambiguous stays in `inbox/` with one
   compact question each ("`scan003.pdf` — looks like an invoice from NorthStar
   Supply: is this a bill we owe, or a vendor contract?"). Never guess on
   legal/HR/tax documents.

6. **Safety scan while reading**: files containing passwords, API keys, recovery
   codes, or SIN lists are NOT filed — leave in inbox and tell the user to store
   secrets in a password manager and re-upload a redacted version. Confidential-
   but-appropriate files (payroll) are filed with a confidentiality note.

7. **Log**: append one row per filed file to `inbox/filing-log.md`.

8. **Offer the follow-through**: end by listing which analyses the new data
   unlocks, grouped ("2 bank statements filed → run `/analyze-statements`?",
   "July Meta export filed → `/ad-review`?"). If the user already asked for
   analysis ("here are the books, audit them"), run the relevant skill(s) directly
   after filing instead of asking.

9. **Commit** the moves + log with message `inbox: file <n> uploads` (offer first
   in interactive sessions; automatic in scheduled/unattended ones).

## Rules
- Identification is by content; when content and filename disagree, trust content
  and note the discrepancy in the log.
- Every file either gets filed, held with a question, or safety-flagged — none
  silently skipped.
- This skill only moves files out of `inbox/`; it never reorganizes existing
  `data/` folders.
