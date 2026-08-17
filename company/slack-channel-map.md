# Slack Channel Map

> Filled per company (see `docs/slack.md` for setup). Maps Slack channels to repo
> channels so requests and report summaries route correctly. Delete rows that
> don't exist in the workspace; one Slack channel may cover several repo channels
> (small teams often run everything from #leadership).

| Slack channel | Repo channel(s) | Typical requests | Claude invited? |
|---|---|---|---|
| #leadership | `channels/ceo/` (+ cross-channel) | /weekly-brief, decisions, "how's the business?" | ☐ |
| #finance | `channels/finance/` | statement drops, /monthly-close, cash questions | ☐ |
| #marketing | `channels/marketing/` | ad exports, /copy-review, campaign questions | ☐ |
| #sales | `channels/sales/` | pipeline questions, proposal drafts | ☐ |
| #hr | `channels/hr/` | hiring packages, policy questions | ☐ |
| #ops | `channels/operations/` + `channels/technology/` | SOPs, vendor renewals, IT issues | ☐ |
| #store / #ecom | `channels/ecommerce/` | inventory drops, /inventory-review | ☐ |
| #cx / #support | `channels/customer-experience/` | review responses, support audits | ☐ |

**Posting etiquette for agents**: summaries posted to Slack are 3–5 bullets + the
repo report path; sensitive detail (compensation, legal risk, full financials)
stays in the repo reports and is referenced, not pasted, unless the mapped channel
is the private channel for that function.
