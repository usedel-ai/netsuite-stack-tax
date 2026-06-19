# Data

All figures current as of June 2026. Sources in [sources.md](sources.md).

## erp-cost-2026.csv

Annual total stack cost for a $50M revenue company, 100 users. All costs in USD.

| Column | Description |
|--------|-------------|
| `erp` | ERP product name |
| `vendor` | Vendor / implementation path |
| `annual_min_usd` | Low-end annual total cost (all stack lines) |
| `annual_max_usd` | High-end annual total cost |
| `users` | User count basis |
| `revenue_usd` | Company revenue basis |
| `notes` | What cost lines are included |
| `source` | Data source |
| `year` | Year of data |

NetSuite stack lines: License + per-user fees, Alliance Partner retainer, SuiteApps, BI/ETL tools, internal NetSuite admin headcount.

Odoo figures are post-migration steady state only. One-time migration cost (~$50k) excluded.

## netsuite-renewal-escalation.csv

Annual NetSuite price change history 2018–2026.

| Column | Description |
|--------|-------------|
| `year` | Renewal year |
| `event` | Oracle pricing action |
| `price_change_pct` | Observed or reported % increase |
| `notes` | Context and caveats |
| `source` | Data source |

NetSuite does not publish list prices or escalation rates. This data is derived from Alliance Partner community discussions, CFO interviews, and verified customer reports. Conservative estimate for financial modeling: 8% annually.

## ai-agent-erp-requirements.csv

Five primitives AI agents need to operate in production ERP environments, with NetSuite vs Odoo support.

| Column | Description |
|--------|-------------|
| `primitive` | Capability name |
| `description` | What the agent needs |
| `netsuite_support` | NetSuite support level |
| `odoo_support` | Odoo support level |
| `netsuite_workaround` | Best available workaround on NetSuite |
| `workaround_cost_usd_annual` | Estimated annual cost of workaround |

Full analysis: [../research/why-ai-fails-on-erp.md](../research/why-ai-fails-on-erp.md)