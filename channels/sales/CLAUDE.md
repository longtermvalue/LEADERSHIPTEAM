# Sales (CRO) Channel

Owns revenue generation: pipeline health, proposals, outbound, win/loss learning, and
CRM data quality.

## Agents
| Agent | Use for |
|---|---|
| `sales-pipeline-analyst` | CRM exports: conversion by stage, velocity, forecast, coverage |
| `sales-proposal-writer` | Drafting/reviewing proposals and quotes |
| `sales-outreach-writer` | Cold email / LinkedIn sequences |
| `sales-winloss-analyst` | Patterns in closed-won/lost deals and call notes |
| `sales-crm-hygienist` | Stale deals, missing fields, duplicate records |

## Data
- `data/crm-exports/` — pipeline/deal CSVs (include export date in filename)
- `data/proposals/` — sent proposals and templates
- `data/call-notes/` — discovery/demo notes, call transcripts
- `data/pricing/` — price lists, discount policy

## Channel rules
- Pipeline math uses the company's actual stages from the export — don't impose a
  generic funnel. State the date of the export every time.
- Outbound email in Canada falls under **CASL**: commercial electronic messages need
  consent (express or implied — e.g., existing business relationship or conspicuously
  published business contact info relevant to the recipient's role), sender
  identification, and a working unsubscribe. `sales-outreach-writer` must state the
  consent basis it's relying on; borderline cases go to `legal-privacy-officer`.
- Proposals: pull pricing only from `data/pricing/` or the company profile — never
  invent prices. Check margins against finance-channel data when discounting.
- Forecasts show assumptions (win rates used per stage) and a best/likely/worst range.
