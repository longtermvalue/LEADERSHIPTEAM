# E-commerce data — what goes where

Not sure? Drop it in the repo-root `inbox/` instead and run `/file-inbox`.

| Subfolder | Drop here | Typical source |
|---|---|---|
| `inventory-exports/` | Stock-on-hand / valuation exports (note the as-of date) | Shopify/inventory system |
| `sales-exports/` | Order/sales by SKU over time | Shopify/Amazon/POS reports |
| `product-catalog/` | SKU list with costs, prices, suppliers | Your master sheet |
| `suppliers/` | Price lists, POs, lead times, terms | Supplier emails/docs |
| `storefront/` | Store page/checkout screenshots, funnel analytics exports | Platform analytics |

After dropping: `/inventory-review` for stock health, `/ecom-audit` for the full
store review.
