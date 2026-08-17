# E-commerce & Inventory Channel

Owns the online store and the physical stock behind it: inventory health, SKU-level
profitability, storefront conversion, and supplier/purchasing decisions. Works
tightly with finance (margins, cash tied up in stock) and marketing (traffic,
promotions).

## Agents
| Agent | Use for |
|---|---|
| `ecom-inventory-analyst` | Stock levels, turns, reorder points, dead stock, stockout risk |
| `ecom-sku-profitability-analyst` | Product/SKU P&L: true margins after fees, shipping, returns |
| `ecom-store-optimizer` | Storefront & checkout conversion audit (Shopify/Amazon/site) |
| `ecom-supplier-analyst` | Supplier performance, lead times, landed cost, PO planning |

## Skills: `/inventory-review`, `/ecom-audit`

## Data
- `data/inventory-exports/` — stock-on-hand exports, inventory valuation reports
- `data/sales-exports/` — order/sales exports by SKU (Shopify, Amazon, POS, etc.)
- `data/product-catalog/` — SKU list with costs, prices, dimensions, suppliers
- `data/suppliers/` — supplier price lists, POs, lead-time history, terms
- `data/storefront/` — screenshots/exports of store pages, checkout flow, platform
  analytics (conversion funnel exports)

## Channel rules
- **SKU math is the ground truth**: every analysis works at SKU (or SKU-family)
  level and rolls up — averages across a catalog hide both winners and disasters.
- True margin includes: unit cost, inbound freight/duty (landed cost), platform and
  payment fees, packaging, outbound shipping subsidy, and returns rate. State which
  components the data supports and which are estimated.
- Inventory is cash: always translate stock findings into dollars tied up and days
  of cover; reconcile inventory value against finance-channel data when both exist.
- Canadian context: duties/brokerage on imports, GST/HST on the landed side,
  CAD/USD exposure on supplier invoices — note FX assumptions.
- Consumer-protection basics for the storefront: honest pricing (all-in where
  required), truthful claims, clear shipping/return policies — flag anything
  misleading to the legal channel.
- If a Shopify/marketplace connector is available, pull live orders/inventory
  instead of waiting for exports — save pulls into the matching `data/` subfolder
  with a dated filename (root CLAUDE.md rule 9).
