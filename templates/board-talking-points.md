# Board Talking Points: ERP Migration Decision
*For CFOs presenting a NetSuite → Odoo migration to the board*

---

## Frame the Decision Correctly

Do not present this as "we are switching ERP systems."

Present it as: **"We are making a capital allocation decision that changes our cost structure and unlocks AI infrastructure."**

The board cares about three things:
1. Risk (can this go wrong?)
2. Cost (what does it cost vs what do we save?)
3. Strategic position (does this help us compete?)

Address all three. In that order.

---

## Talking Point 1 — The Cost Structure

> "Our current NetSuite stack costs us $[X] per year. That's the license, the Alliance Partner, the SuiteApps, the BI tools, and two admin headcount. The license is $[Y] — the rest is $[X-Y] we don't talk about. Over five years at current escalation rates, we spend $[5-year total]. The migration alternative costs $50k one-time and $30k per year after. Payback is [N] months."

**What to have ready:** the renewal-math template filled with your actual numbers. If the board asks "how do you know the escalation rate?" — the honest answer is "Oracle decides and doesn't publish it. Our conservative estimate is 8% annually based on recent renewal data across similar companies."

---

## Talking Point 2 — The Risk Profile

> "The risk of migrating is bounded. del.ai runs a parallel operation: NetSuite stays live throughout. We reconcile both systems weekly. We don't cut over until three consecutive weeks of clean reconciliation. The risk of not migrating is unbounded: Oracle controls our renewal price, our Alliance Partner earns margin on that renewal, and we have no financial ceiling."

**What to have ready:** the migration checklist, specifically the go-live gate criteria. Showing the board a checklist of what must pass before go-live signals process discipline.

**On vendor viability (they will ask):**
> "If del.ai were to close tomorrow, our Odoo codebase runs without them. It's LGPL open source — 50,000 implementation partners globally can support it. Our data is in PostgreSQL, which we own. Compare that to what happens if Oracle makes a decision about NetSuite's future."

---

## Talking Point 3 — The AI Infrastructure Play

> "Our board has asked about our AI strategy. The honest answer is that AI agents cannot work reliably on NetSuite. It's a closed system — agents can read limited data through a rate-limited API, but cannot write reliably, cannot access our full schema, and cannot react to real-time events. On Odoo, agents have full database access. del.ai ships two production agents at go-live. This migration is how we answer the board's AI question."

**Source to cite if asked:** Brynjolfsson, Rock & Syverson (AEJ:Macro 2021) — AI productivity is real but invisible to standard accounting during the infrastructure build phase (the J-Curve). We are positioning for the payoff phase.

---

## Questions the Board Will Ask

**"What happens to our data?"**
Data migrates to Odoo. NetSuite is kept on read-only access for 12 months post go-live for historical lookups. After 12 months, export to archive. No data is lost.

**"How does this affect month-end close?"**
Controller runs month-end close in Odoo staging during parallel run. We don't go live until Controller confirms it works. The first Odoo month-end close happens before cutover.

**"What's the total cost including migration?"**
One-time migration: ~$50k. Year 1 total (migration + Odoo): ~$80k. Year 2+: ~$30k/yr. Compare to current $[X]/yr.

**"Why del.ai and not a traditional Odoo partner?"**
Traditional Odoo partners charge time-and-materials, typically $150k–$400k. del.ai is fixed price ($50k starting), includes AI agents, and specializes in NetSuite migrations specifically. The methodology is documented (parallel run, go-live gates, agent deployment).

---

*Template by [del.ai](https://usedel.ai) · Open source · June 2026*