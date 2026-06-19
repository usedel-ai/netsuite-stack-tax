# Why AI Fails on Closed ERP Systems

*By del.ai — June 2026*

---

## The Short Answer

AI agents fail on NetSuite not because of bad prompts or weak models. They fail because NetSuite is a closed system that blocks the five primitives agents need to operate in production.

This is a substrate problem, not an AI problem.

---

## The Five Primitives AI Agents Need

For an AI agent to reliably read, write, and act on ERP data in production, it needs:

### 1. Schema access
The agent must be able to read the full data model — every table, every field, every relationship — not just what the vendor exposes through a curated API.

**NetSuite:** API exposes a subset of fields per record type. Schema changes with SuiteApp installations are not automatically reflected in the API. Agents operating on incomplete schemas make incorrect assumptions about data structure.

**Odoo (PostgreSQL):** Full schema accessible. `\d+ account_move` returns every field. Agents can introspect the live schema before acting.

### 2. Write capability
Agents need to create, update, and delete records without rate limits, approval queues, or field-level restrictions imposed by the vendor.

**NetSuite:** REST API rate-limited to 10 concurrent requests per account. Write operations on certain record types require special permissions not available to API users. SuiteFlow workflows can block or override API writes silently.

**Odoo:** Direct PostgreSQL write access. ORM available in Python. No vendor-imposed rate limits on self-hosted instances.

### 3. A canonical ontology
Field names, record types, and relationships must be consistent and predictable. Agents that encounter field name drift or module-specific schema variants produce unreliable output.

**NetSuite:** Field names differ between SuiteScript, REST API, and CSV import formats. SuiteApps add fields with vendor-specific prefixes (`custbody_`, `custrecord_`) with no standardized naming convention. An agent trained on one NetSuite instance may fail on another.

**Odoo:** Standard module fields follow consistent naming conventions. The ORM enforces field typing. Community and enterprise modules follow documented extension patterns.

### 4. Real-time event access
Agents need to react to data changes as they happen — a new invoice posted, an approval rejected, a shipment received. Polling APIs introduce latency and miss events under rate limits.

**NetSuite:** No native webhook infrastructure. SuiteFlow can trigger HTTP calls but only for specific workflow events, not arbitrary record changes. Third-party iPaaS (Celigo, Boomi) required — adding $20k–$50k/yr to the stack.

**Odoo:** Native bus messaging system. PostgreSQL LISTEN/NOTIFY for real-time row-level change events. No third-party required.

### 5. Code-level extensibility
When an agent's action requires custom business logic, it must be able to invoke or modify that logic without vendor approval or SaaS deployment constraints.

**NetSuite:** Custom logic lives in SuiteScript (JavaScript subset), deployed through NetSuite's sandboxed environment. External agents cannot call SuiteScript functions directly. Modifying SuiteScript requires NetSuite-certified developers and sandbox promotion cycles.

**Odoo:** Python-based. External agents can import Odoo models, call methods, and extend business logic via standard Python inheritance. No deployment gating.

---

## What This Means in Practice

A typical failed AI pilot on NetSuite:

1. Company buys AI tool ($50k–$150k)
2. Tool connects via NetSuite REST API
3. Agent reads invoices, purchase orders, inventory levels
4. Agent attempts to match POs to invoices — hits field naming inconsistency between modules
5. Agent flags false positives, requires human review on 40% of matches
6. Company concludes "AI doesn't work for our finance ops"
7. AI tool is cancelled at renewal

The AI worked. The substrate failed it.

---

## The Fix

Moving from closed ERP (NetSuite, SAP B1, Dynamics BC) to open-source ERP (Odoo) is not primarily about cost savings — though the savings are real ($200k–$770k/yr vs NetSuite).

The more important outcome: your team can build agents that actually work.

On Odoo:
- Agents read the full schema
- Agents write records without rate limits
- Field names are consistent and documented
- Events trigger in real time
- Business logic is extensible in Python

This is why del.ai bundles two production AI agents at go-live: the migration itself creates the substrate that makes agents viable.

---

## Academic Grounding

Brynjolfsson, Rock & Syverson (AEJ:Macro 2021) found that AI productivity gains are real but invisible to standard accounting measurements — what they call the J-Curve. Companies invest in AI, see no immediate P&L impact, conclude the investment failed, and abandon it.

What they don't measure: whether the failure was the AI, or the data infrastructure the AI was running on.

Our hypothesis, validated across del.ai's pipeline: most mid-market AI pilot failures are substrate failures, not model failures.

---

## Further Reading

- [NetSuite Stack Tax Research](../README.md) — full TCO breakdown
- [ERP Cost Comparison 2026](../data/erp-cost-2026.csv) — data
- [del.ai migration platform](https://usedel.ai) — NetSuite to Odoo in 90 days

---

*Built by [del.ai](https://usedel.ai) · June 2026*