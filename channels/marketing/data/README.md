# Marketing data — what goes where

Not sure? Drop it in the repo-root `inbox/` instead and run `/file-inbox`.

| Subfolder | Drop here | Typical source |
|---|---|---|
| `ad-exports/` | Campaign/ad/keyword CSVs with the date range in the filename | Google Ads / Meta / LinkedIn → export |
| `analytics/` | Traffic & conversion exports | GA4, Search Console |
| `copy/` | Pages/ads/emails to review (text or screenshots) | Your site/docs |
| `email-campaigns/` | Campaign & flow stats | Mailchimp/Klaviyo/etc. reports |
| `social/` | Social analytics exports | Platform insights |
| `brand/` | Brand guide, voice/tone, positioning | Wherever it lives (or let `cmo-brand-guardian` draft one) |
| `competitors/` | Competitor pages, pricing screenshots | Saved captures |

After dropping: ads → `/ad-review`; copy → `/copy-review`; everything at once →
`/marketing-audit`. Export tips: `docs/data-exports.md`.
