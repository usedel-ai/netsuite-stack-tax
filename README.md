# NetSuite Stack Tax — True Cost Research & Calculator

> **Your NetSuite license is $40k. Your actual bill is $260k–$830k.**

This repository contains open-source research, data, and tools for mid-market finance teams evaluating the true cost of NetSuite and the economics of migrating to Odoo.

Maintained by [del.ai](https://usedel.ai) — AI-led NetSuite to Odoo migration platform.

---

## What's in this repo

| Folder | What you get |
|--------|-------------|
| [`calculator/`](calculator/) | Standalone browser-based Stack Tax Calculator — no login, no backend |
| [`templates/`](templates/) | CFO renewal math template, migration checklist, board talking points |
| [`data/`](data/) | ERP cost comparison CSV (2026), renewal escalation data |
| [`research/`](research/) | Why AI fails on closed ERP, academic citations, NetSuite renewal math |

---

## The Stack Tax Problem

Most CFOs sign a NetSuite contract at $30k–$50k/yr and call it their ERP cost.

That number is missing four more line items:

| Line item | Annual cost |
|-----------|-------------|
| License + per-user fees | $30,000 – $50,000 |
| Alliance Partner retainer | $30,000 – $100,000 |
| SuiteApps (Avalara, Celigo, FloQast) | $20,000 – $50,000 |
| BI tools + ETL (Looker, Snowflake) | $30,000 – $80,000 |
| Internal NetSuite admin headcount | $100,000 – $400,000 |
| **Total annual stack cost** | **$260,000 – $830,000** |

The license is the smallest line item. The stack is what kills you.

**Source:** Panorama Consulting 2024 ERP Report; del.ai market research across 50+ mid-market NetSuite deployments.

---

## The 5-Year Cost of Staying

For a company with a $120k/yr NetSuite stack at 8% annual escalation:

| Year | Annual cost |
|------|-------------|
| Year 1 | $120,000 |
| Year 2 | $129,600 |
| Year 3 | $139,968 |
| Year 4 | $151,165 |
| Year 5 | $163,258 |
| **5-year total** | **$703,991** |

Migration to Odoo via del.ai: starts at $50,000 (one-time) + $24,000–$60,000/yr post-migration.

**5-year savings: $503,000+** on a $120k starting stack.

---

## Why AI Fails on NetSuite

AI agents need five primitives to work in production:

1. **Schema access** — read the full data model, not just what the API exposes
2. **Write capability** — create/update records without vendor-controlled API limits
3. **A canonical ontology** — consistent field names and relationships across modules
4. **Real-time event access** — react to changes as they happen
5. **Code-level extensibility** — modify business logic without SuiteScript lock-in

NetSuite provides none of these for third-party agents. Its API is read-limited, rate-limited, and field-limited by design.

Odoo (open-source, PostgreSQL-backed) provides all five on day one.

This is not an AI problem. It's a substrate problem.

Full analysis: [`research/why-ai-fails-on-erp.md`](research/why-ai-fails-on-erp.md)

---

## ERP Cost Comparison (2026)

Annual total stack cost for a $50M revenue company, 100 users:

| ERP | Min | Max | Notes |
|-----|-----|-----|-------|
| NetSuite | $260,000 | $830,000 | License + partner + apps + admin |
| SAP Business One | $215,000 | $660,000 | License + implementation + support |
| Acumatica | $148,000 | $445,000 | Consumption-based pricing varies |
| **Odoo (via del.ai)** | **$24,000** | **$60,000** | Post-migration, hosting + license only |

Full dataset: [`data/erp-cost-2026.csv`](data/erp-cost-2026.csv)

---

## Use This Repo

**CFO / Controller:**
- Run the [calculator](calculator/index.html) with your actual numbers
- Download [`templates/renewal-math.md`](templates/renewal-math.md) to build your board deck
- Use [`templates/board-talking-points.md`](templates/board-talking-points.md) to frame the migration decision

**NetSuite Admin / IT:**
- See [`templates/migration-checklist.md`](templates/migration-checklist.md) for the 90-day parallel-run process
- Read [`research/why-ai-fails-on-erp.md`](research/why-ai-fails-on-erp.md) before your next AI pilot

**Anyone evaluating ERP migration:**
- Start with [`data/erp-cost-2026.csv`](data/erp-cost-2026.csv) for a benchmark
- See [`research/academic-citations.md`](research/academic-citations.md) for the economic research behind these numbers

---

## About del.ai

[del.ai](https://usedel.ai) migrates mid-market companies ($30M–$300M revenue) from NetSuite to Odoo in 90 days at a fixed price.

- **Fixed price** — no change orders
- **Parallel run** — NetSuite stays live throughout migration, zero cutover risk
- **AI agents included** — two production agents deployed at go-live
- **You own the code** — Odoo is LGPL, your codebase is yours after migration

Questions: [usedel.ai](https://usedel.ai) · Built by [Patrick Xie](https://linkedin.com/in/patrickxie), CEO del.ai

---

*Data current as of June 2026. Sources in [`data/sources.md`](data/sources.md).*