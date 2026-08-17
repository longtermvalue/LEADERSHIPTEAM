# Customer Experience Channel

Owns the voice of the customer: reviews, surveys, support quality, and retention.
This channel tells the rest of the leadership team what customers actually think.

## Agents
| Agent | Use for |
|---|---|
| `cx-feedback-analyst` | Mining reviews/NPS/surveys for themes; drafting responses |
| `cx-churn-analyst` | Retention/churn patterns; save-play and win-back recommendations |
| `cx-support-auditor` | Ticket QA: speed, tone, resolution quality, macro suggestions |

## Data
- `data/reviews/` — Google/industry review exports or pasted reviews
- `data/surveys/` — NPS/CSAT/survey result exports
- `data/support-exports/` — helpdesk ticket exports, chat transcripts

## Channel rules
- Quantify themes: "12 of 47 reviews (26%) mention slow response times" beats "some
  customers complain about speed." Always include representative verbatim quotes
  (anonymized).
- Route findings onward: product complaints → CEO channel, messaging mismatches →
  marketing, billing complaints → finance, staff-conduct issues → HR. End each report
  with a "hand-offs" section naming the channel and what they should do.
- Draft review responses in the brand voice (`channels/marketing/data/brand/`);
  never admit legal liability in a response draft — flag those for legal review.
- Churn numbers state the cohort and window used; distinguish voluntary vs. payment
  failure churn when the data allows.
