# AI Leadership Team

A duplicatable Claude Code workspace that acts as a full leadership team for one
company. Ten department **channels**, 49 specialist **agents**, and 18 workflow
**skills** (slash commands). Drop company files into each channel's `data/`
folders; the agents analyze them and write dated reports into `reports/`. A
built-in cadence (`company/routines.md` + `/run-routines`) keeps it running on a
schedule — see `docs/automation.md`.

Built for Ontario, Canada businesses: Finance thinks in CAD/CRA/HST, HR is grounded in
Ontario employment law (ESA, OHSA, AODA, Human Rights Code), Legal covers PIPEDA/CASL.

## Quickstart

1. **Duplicate this repo** for a company (see "One repo per company" below).
2. Open it in Claude Code (web, desktop, or CLI).
3. Run **`/onboard-company`** — a short interview that fills in
   `company/company-profile.md`, goals, and org chart.
4. **Drop data** into the `channels/*/data/` folders (map below). PDFs, CSVs,
   spreadsheets, and exports all work.
5. Ask for work in plain language ("analyze last month's bank statements", "review this
   ad export", "are we ESA-compliant?") or run a skill like `/monthly-close`.
6. Put it on autopilot: enable the cadence in `company/routines.md` and schedule
   `/run-routines` (see `docs/automation.md`); optionally wire up Slack channels
   (`docs/slack.md`) and live connectors (`docs/connectors.md`).

## Channels & agents

### CEO — `channels/ceo/`
| Agent | What it does |
|---|---|
| `ceo-chief-of-staff` | Routes cross-department work, fans out to other channels, compiles leadership briefs |
| `ceo-strategy-advisor` | SWOT, positioning, growth options, annual/quarterly strategic plans |
| `ceo-kpi-analyst` | Builds the company scorecard from every channel's data; flags trend breaks |
| `ceo-decision-memo` | Structured decision analysis: options, pre-mortem, recommendation |
| `ceo-board-reporter` | Board packs and investor/stakeholder updates |

### Marketing (CMO) — `channels/marketing/`
| Agent | What it does |
|---|---|
| `cmo-ad-analyst` | Paid ad exports (Google/Meta/LinkedIn): ROAS, CPA, creative fatigue, budget shifts |
| `cmo-copy-analyst` | Critiques and rewrites landing pages, ads, and email copy |
| `cmo-seo-content-strategist` | Organic performance, keyword/content gaps, editorial plan |
| `cmo-competitor-analyst` | Competitor teardowns: positioning, pricing, messaging, channels |
| `cmo-brand-guardian` | Brand voice/messaging consistency audits across all assets |
| `cmo-email-analyst` | Campaign and flow performance; CASL compliance checks |
| `cmo-funnel-analyst` | Full-funnel conversion: where leads leak, what to fix first |

### Finance & Accounting (CFO) — `channels/finance/`
| Agent | What it does |
|---|---|
| `cfo-bookkeeper` | Parses bank/credit-card statements, categorizes every transaction into a maintained ledger |
| `cfo-financial-analyst` | P&L/balance-sheet/trend analysis, margins, ratios, month-over-month movement |
| `cfo-cashflow-forecaster` | 13-week rolling cash flow forecast with scenarios |
| `cfo-cost-optimizer` | Hunts recurring spend: duplicate tools, zombie subscriptions, negotiation targets |
| `cfo-budget-analyst` | Budget vs. actual variance, reforecasts |
| `cfo-ar-ap-analyst` | Receivables aging and collection priorities; payables timing |
| `cfo-tax-organizer` | Canadian small-business tax calendar (HST, payroll remittances, T4/T5, T2) and document readiness |

### Human Resources (Ontario) — `channels/hr/`
| Agent | What it does |
|---|---|
| `hr-policy-advisor` | Drafts/audits handbook and policies against Ontario ESA, OHSA, AODA, Human Rights Code |
| `hr-recruiter` | Ontario-compliant job postings (incl. pay transparency), interview kits, scoring rubrics |
| `hr-onboarding-offboarding` | Onboarding plans; termination checklists with Ontario notice/severance flags |
| `hr-comp-analyst` | Pay bands, payroll review, EHT/WSIB/source-deduction sanity checks |
| `hr-performance-coach` | Review cycles, feedback frameworks, PIPs |
| `hr-compliance-auditor` | Full Ontario compliance sweep: mandatory policies, postings, training, records |

### Sales (CRO) — `channels/sales/`
| Agent | What it does |
|---|---|
| `sales-pipeline-analyst` | CRM exports: stage conversion, velocity, coverage, forecast |
| `sales-proposal-writer` | Drafts and reviews proposals/quotes |
| `sales-outreach-writer` | Cold email / LinkedIn sequences (CASL-aware) |
| `sales-winloss-analyst` | Win/loss patterns from call notes and closed deals |
| `sales-crm-hygienist` | CRM data-quality audit: stale deals, missing fields, duplicates |

### Operations (COO) — `channels/operations/`
| Agent | What it does |
|---|---|
| `ops-sop-writer` | Turns process notes/transcripts into clean SOPs |
| `ops-process-optimizer` | Bottleneck analysis, automation candidates, cost-of-chaos estimates |
| `ops-vendor-analyst` | Vendor contracts, renewal calendar, consolidation opportunities |
| `ops-project-reporter` | Project status rollups with risk flags |

### Legal & Compliance (Chief Counsel) — `channels/legal/`
> ⚠️ This channel produces **legal information, not legal advice** — every output
> carries a disclaimer and points to a licensed Ontario lawyer for decisions.

| Agent | What it does |
|---|---|
| `legal-chief-counsel` | **First stop for any legal question** — Ontario-focused framing, plain-language explanation, risk assessment, and a prepared package for your real lawyer |
| `legal-contract-reviewer` | Plain-English contract review with clause-level risk flags |
| `legal-privacy-officer` | PIPEDA privacy and CASL anti-spam compliance reviews |
| `legal-records-keeper` | Minute book, corporate filing calendar (Ontario/federal), insurance renewals |

### Customer Experience — `channels/customer-experience/`
| Agent | What it does |
|---|---|
| `cx-feedback-analyst` | Mines reviews/NPS/surveys for themes; drafts responses |
| `cx-churn-analyst` | Retention/churn patterns from customer exports; save-play recommendations |
| `cx-support-auditor` | Support ticket QA: response time, tone, resolution quality |

### E-commerce & Inventory — `channels/ecommerce/`
| Agent | What it does |
|---|---|
| `ecom-inventory-analyst` | Stock vs. velocity: reorder points, stockout risk, dead stock, cash tied up |
| `ecom-sku-profitability-analyst` | True margin per SKU after fees/shipping/returns; kill/keep/scale calls |
| `ecom-store-optimizer` | Storefront & checkout conversion audit with $-sized funnel leaks |
| `ecom-supplier-analyst` | Supplier scorecards, landed cost, PO planning, FX exposure |

### Technology (CTO/IT) — `channels/technology/`
| Agent | What it does |
|---|---|
| `cto-stack-auditor` | Tool-stack health: shadow IT, overlaps, seats vs. spend, single-owner risk |
| `cto-website-auditor` | Technical site health: uptime, SSL/DNS/domain expiry, speed, email auth (SPF/DKIM/DMARC) |
| `cto-security-auditor` | Defensive posture: MFA, access hygiene, payment-fraud controls, incident readiness |
| `cto-data-steward` | Backups (with restore-test discipline), data map, retention, continuity scenarios |

## Skills (slash commands)

| Skill | What it runs |
|---|---|
| `/onboard-company` | New-company setup interview → fills `company/` templates |
| `/weekly-brief` | Cross-channel weekly leadership brief |
| `/exec-meeting` | Leadership meeting agenda + talking points from latest reports |
| `/board-pack` | Quarterly board report |
| `/monthly-close` | Finance close: ingest statements → ledger → P&L summary → opportunities |
| `/analyze-statements` | Parse & categorize newly dropped bank/card statements |
| `/cost-cut` | Cost optimization sweep across ledger and vendor contracts |
| `/marketing-audit` | Full marketing review across ads, funnel, email, SEO, brand |
| `/ad-review` | Analyze a fresh ad-platform export |
| `/copy-review` | Critique + rewrite copy files dropped in `data/copy/` |
| `/competitor-scan` | Refresh competitor intel |
| `/hr-compliance-check` | Ontario HR compliance audit |
| `/new-hire` | Job description + interview kit + 30/60/90 onboarding plan |
| `/ask-counsel` | Legal question → Ontario legal information + lawyer-prep package (not legal advice) |
| `/inventory-review` | Stock health: reorder-now list, dead stock, cash in inventory |
| `/ecom-audit` | Full store review: SKU margins, checkout funnel, inventory, suppliers |
| `/it-security-check` | Security + backup/continuity audit with a ranked hardening plan |
| `/run-routines` | Check `company/routines.md` and run whatever's due — the scheduler entry point |

## Data drop-zone map

```
channels/ceo/data/            board-minutes/ strategy-docs/ kpi-snapshots/
channels/marketing/data/      ad-exports/ copy/ analytics/ email-campaigns/ social/ brand/ competitors/
channels/finance/data/        bank-statements/ credit-card-statements/ accounting-exports/
                              invoices/ bills/ budgets/ tax/
channels/hr/data/             policies/ employment-agreements/ payroll-reports/ recruiting/ training-records/
channels/sales/data/          crm-exports/ proposals/ call-notes/ pricing/
channels/operations/data/     sops/ vendor-contracts/ projects/ systems/
channels/legal/data/          contracts/ corporate-records/ insurance/
channels/customer-experience/data/  reviews/ surveys/ support-exports/
channels/ecommerce/data/      inventory-exports/ sales-exports/ product-catalog/
                              suppliers/ storefront/
channels/technology/data/     access/ website/ security/ backups/ it-vendors/
                              (systems inventory is shared at channels/operations/data/systems/)
```

### How to get files in

Any of these works — the agents don't care how the file arrived, only that it's in
the right folder:

1. **GitHub web UI** (easiest, no tools needed): open the repo on github.com,
   navigate to the folder (e.g. `channels/finance/data/bank-statements/`), then
   **Add file → Upload files** and drag the PDFs/CSVs in. Commit. Done.
2. **In a Claude Code session**: attach/drag the file into the chat and say where
   it goes ("file these under finance bank statements") — Claude saves it to the
   folder and can run the analysis in the same breath.
3. **Git locally**: clone, copy files into the folders, commit, push.
4. **Slack** (once connected, see `docs/slack.md`): upload the file in the mapped
   channel and ask @Claude to file + analyze it.

Example — *"I have the books for a financial audit"*: drop bank statements in
`finance/data/bank-statements/`, card statements in `credit-card-statements/`, your
QuickBooks/Xero exports (P&L, balance sheet, general ledger) in
`accounting-exports/`, and any invoices/bills in `invoices/` and `bills/`. Then run
`/analyze-statements` (or `/monthly-close`), and ask for what you want —
"full financial review", "find cost cuts", "are the books consistent?"

**Monthly data drop checklist** (keeps every agent current):
- [ ] Bank + credit-card statements → `finance/data/bank-statements/`, `credit-card-statements/`
- [ ] Accounting export (QuickBooks/Xero P&L + balance sheet) → `finance/data/accounting-exports/`
- [ ] Ad platform exports (Google/Meta/LinkedIn) → `marketing/data/ad-exports/`
- [ ] Website/GA4 analytics export → `marketing/data/analytics/`
- [ ] CRM pipeline export → `sales/data/crm-exports/`
- [ ] Payroll register → `hr/data/payroll-reports/`
- [ ] New reviews / survey results / support export → `customer-experience/data/`
- [ ] Store sales + inventory exports (if e-commerce) → `ecommerce/data/`

## One repo per company

Keep this repo as the **master template** and create a copy per company:

1. On GitHub: repo **Settings → check "Template repository"**, then **"Use this
   template" → Create a new repository** named e.g. `LT-ACMECORP` (**private**).
2. Open the new repo in Claude Code and run `/onboard-company`.
3. Drop that company's data in and start working.

To pull template improvements into a company repo later:
```bash
git remote add template <this-repo-url>
git fetch template
git merge template/main --allow-unrelated-histories
```

## Scheduled routines

The operating rhythm is data, not tribal knowledge: `company/routines.md` defines
what runs and how often (weekly brief, monthly close, quarterly compliance/security/
cost sweeps…), and **`/run-routines`** checks what's due and runs it — skipping
anything blocked on missing data and logging every run.

To put it on a schedule (full guide: `docs/automation.md`):
- **Claude Code Routines** (recommended): claude.ai/code/routines → weekly or
  weekday trigger with the prompt `/run-routines`.
- **GitHub Actions**: copy `docs/automation/routines-github-action.yml` to
  `.github/workflows/routines.yml` and add an API-key secret.
- **Manual**: just type `/run-routines` whenever — it catches up on everything owed.

## Live data connectors

Everything works file-first, but connectors upgrade agents to live data: Ahrefs for
SEO, accounting (QuickBooks/Xero), GA4, CRM, Shopify, helpdesk. The convention:
agents use live data when connected and save pulls into `data/` so reports stay
reproducible. Per-channel table and setup: `docs/connectors.md`.

## Slack channels

Department Slack channels map onto repo channels — invite @Claude (Claude app for
Slack) into #finance/#marketing/#hr/etc., pin the routing note, and fill
`company/slack-channel-map.md`. Drop a file in the channel and ask @Claude to file
and analyze it. Setup and etiquette: `docs/slack.md`.

## Security & disclaimers

- Company repos will contain **sensitive financial, HR, and legal data — always keep
  them private** and limit collaborators. Agents mask account numbers and never
  reproduce SINs.
- Agent output on tax, legal, HR-law, and investment topics is **decision support, not
  professional advice**. Verify with a licensed CPA, employment lawyer, or counsel.
  Ontario/federal rules cited by agents should be checked against current
  ontario.ca / canada.ca guidance — laws and rates change.
