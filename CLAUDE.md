# AI Leadership Team — Operating Manual

This repository is a virtual leadership team for one company. Each **channel** under
`channels/` is a department run by specialist agents. Company files get dropped into
`channels/<channel>/data/` subfolders; agents analyze them and write dated reports to
`channels/<channel>/reports/`.

This repo is a **template**: it gets duplicated once per company, then filled with that
company's data. Company identity lives in `company/company-profile.md` — read it before
doing any substantive work. If it still contains `{{PLACEHOLDER}}` values, suggest
running `/onboard-company` first.

## Channels

| Channel | Directory | Covers |
|---|---|---|
| CEO | `channels/ceo/` | Strategy, KPIs, decisions, board reporting, cross-department synthesis |
| Marketing (CMO) | `channels/marketing/` | Ads, copy, SEO/content, email, funnel, brand, competitors |
| Finance (CFO) | `channels/finance/` | Bookkeeping, statements, cash flow, budgets, cost cuts, Canadian tax prep |
| HR (Ontario) | `channels/hr/` | Hiring, policies, compensation, performance, Ontario employment compliance |
| Sales (CRO) | `channels/sales/` | Pipeline, proposals, outreach, win/loss, CRM hygiene |
| Operations (COO) | `channels/operations/` | SOPs, process optimization, vendors, project status |
| Legal & Compliance (Chief Counsel) | `channels/legal/` | Legal questions (Ontario), contract review, privacy (PIPEDA/CASL), corporate records — **information, never legal advice** |
| Customer Experience | `channels/customer-experience/` | Reviews, surveys, support quality, churn |
| E-commerce & Inventory | `channels/ecommerce/` | Stock health, SKU profitability, storefront conversion, suppliers |
| Technology (CTO/IT) | `channels/technology/` | Tool stack, website health, security posture, backups/continuity |

## Routing requests

Match the request to a channel, then delegate to the most specific agent in
`.claude/agents/` (agents are prefixed by channel: `ceo-`, `cmo-`, `cfo-`, `hr-`,
`sales-`, `ops-`, `legal-`, `cx-`, `ecom-`, `cto-`). Cross-department questions
("how is the business doing?", "prep the leadership meeting") go to
`ceo-chief-of-staff`, which fans out to the other channels; any legal question
starts at `legal-chief-counsel`. Repeatable workflows have skills — see
`.claude/skills/` (e.g. `/monthly-close`, `/weekly-brief`, `/hr-compliance-check`,
`/ask-counsel`). Requests arriving from Slack route per
`company/slack-channel-map.md`. Recurring cadence is defined in
`company/routines.md` and executed by `/run-routines` (see `docs/automation.md`).

## Conventions (all agents must follow)

1. **Read first**: `company/company-profile.md` for context, then the relevant
   `channels/<channel>/data/` folders. Channel-specific rules live in each channel's
   own `CLAUDE.md`.
2. **Source data is read-only.** Never edit, move, rename, or delete anything under a
   `data/` folder. All output goes to `channels/<channel>/reports/` (or
   `channels/finance/ledger/` for the maintained transaction ledger).
3. **Report naming**: `channels/<channel>/reports/YYYY-MM-DD-<topic-slug>.md`. Start
   every report with: title, date, data sources used (file paths), and a 3–6 bullet
   executive summary. Findings ranked by dollar/risk impact, each with a recommended
   action and owner.
4. **Currency is CAD** unless a document says otherwise. The company operates in
   Ontario, Canada — use Canadian context (CRA, HST, ESA, PIPEDA, CASL) by default.
5. **Mask sensitive identifiers** in every output: bank/card account numbers to last 4
   digits, SINs never reproduced, employee compensation only in HR/finance reports.
6. **Say what's missing.** If a data folder is empty or a needed export doesn't exist,
   state exactly which file to drop where — never fabricate numbers. Every figure in a
   report must trace to a source file.
7. **Professional-advice disclaimer**: tax, legal, HR-law, and investment outputs are
   decision support, not professional advice. End those reports with: *"Prepared by an
   AI analyst — verify with a licensed professional (CPA / employment lawyer / counsel)
   before acting."* Laws and rates change: agents citing Ontario/federal rules must
   flag figures that should be verified against current ontario.ca / canada.ca sources.
8. **Dates**: use the real current date in report filenames and content.
9. **Live connectors over stale files, files over nothing**: when a relevant MCP
   connector is available in the session (Ahrefs, accounting, CRM, analytics…),
   prefer live data — and save meaningful pulls into the channel's `data/` folder
   with a dated filename so reports stay reproducible. When no connector is
   present, work from `data/` files and name the export that would improve the
   analysis. See `docs/connectors.md`.
10. **The inbox is the front door for data.** Users can drop any file into
    `inbox/` instead of finding the right folder; `/file-inbox` identifies, renames,
    files, and logs it. Files attached in chat are treated the same way — identify
    and place them, never ask the user which folder. If `inbox/` contains unfiled
    files at the start of any session, mention it and offer to file them (skills
    that consume data, like `/analyze-statements` and `/monthly-close`, check the
    inbox for relevant files before declaring data missing). Moving files OUT of
    `inbox/` is the one sanctioned move; rule 2's read-only protection applies the
    moment a file lands in a `data/` folder.

## Where things live

```
inbox/                       Drop-anything upload folder → sorted by /file-inbox
                             (filing-log.md records every move)
company/                     Company-wide identity: profile, goals/OKRs, org chart,
                             routines.md (cadence), slack-channel-map.md
channels/<channel>/data/     INPUT drop-zones (subfolders per data type)
channels/<channel>/reports/  OUTPUT — dated markdown reports
channels/finance/ledger/     Maintained: transactions.csv + processed-files.md
.claude/agents/              Specialist agent definitions
.claude/skills/              Workflow skills (slash commands)
docs/                        Setup guides: automation.md, connectors.md, slack.md
```
