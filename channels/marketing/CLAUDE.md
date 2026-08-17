# Marketing (CMO) Channel

Owns demand generation and brand: paid ads, copy, SEO/content, email, social, funnel
economics, and competitor intelligence.

## Agents
| Agent | Use for |
|---|---|
| `cmo-ad-analyst` | Any paid-ads export: performance, waste, creative fatigue, budget moves |
| `cmo-copy-analyst` | Critique/rewrite of landing pages, ads, emails in `data/copy/` |
| `cmo-seo-content-strategist` | Organic traffic, keyword gaps, editorial calendar |
| `cmo-competitor-analyst` | Teardowns of competitors listed in the company profile |
| `cmo-brand-guardian` | Voice/messaging consistency vs. `data/brand/` guidelines |
| `cmo-email-analyst` | Campaign/flow metrics + CASL compliance |
| `cmo-funnel-analyst` | End-to-end funnel math: visitor → lead → customer, CAC/LTV |

## Skills: `/marketing-audit`, `/ad-review`, `/copy-review`, `/competitor-scan`

## Data
- `data/ad-exports/` — CSVs from Google Ads, Meta, LinkedIn (include date range in filename)
- `data/copy/` — pages/ads/emails to review (paste into .md/.txt, or screenshots)
- `data/analytics/` — GA4/website analytics exports
- `data/email-campaigns/` — ESP campaign exports, flow screenshots
- `data/social/` — social analytics exports
- `data/brand/` — brand guide, voice/tone docs, positioning statements
- `data/competitors/` — saved competitor pages, pricing screenshots, prior teardowns

## Channel rules
- Always compute unit economics where possible: CPC → CPL → CPA → CAC, vs. gross
  margin from the finance channel's latest reports. A "good" campaign is one that
  makes money, not one with a good CTR.
- Canadian context: email marketing must respect **CASL** (express/implied consent,
  identification, unsubscribe). Flag violations; loop in `legal-privacy-officer` for
  anything borderline.
- If connected tools are available in the session (e.g., Ahrefs MCP for SEO data,
  Firecrawl/web fetch for competitor pages), prefer live data over stale files — and
  save what you pull into `data/` so the analysis is reproducible.
- Recommendations must be ranked by expected impact with the assumption stated
  (e.g., "pausing X saves $Y/mo based on the June export").
