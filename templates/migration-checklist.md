# NetSuite → Odoo Migration Checklist
*del.ai 90-Day Parallel-Run Process*

NetSuite stays live throughout. No cutover weekend. Zero data loss risk.

---

## Phase 1 — Discovery (Days 1–21)

### Week 1: Map the current state
- [ ] Export full NetSuite chart of accounts
- [ ] List all active SuiteApps with monthly cost and owner
- [ ] Document all SuiteScript customizations (custom records, workflows, scripts)
- [ ] List all third-party integrations (Celigo, Boomi, iPaaS connectors)
- [ ] Identify Alliance Partner scope: what do they own vs what is internal?
- [ ] Pull 12 months of historical transaction volume by module
- [ ] Document month-end close process (who does what, in what order)
- [ ] List all custom reports and saved searches used in operations

### Week 2: Risk assessment
- [ ] Flag any SuiteScript customizations with no equivalent in Odoo standard
- [ ] Flag integrations where del.ai needs to build connectors
- [ ] Identify data quality issues in NetSuite (duplicate vendors, orphan records)
- [ ] Confirm go-live date (must not overlap with audit period or board reporting)
- [ ] Get sign-off from Controller on parallel-run verification criteria

### Week 3: Odoo environment setup
- [ ] del.ai provisions Odoo instance (staging + production)
- [ ] Install required Odoo Enterprise modules
- [ ] Configure chart of accounts in Odoo to match NetSuite
- [ ] Set up user roles and permissions

---

## Phase 2 — Build & Migrate (Days 22–60)

### Data migration
- [ ] Export NetSuite master data: customers, vendors, products, chart of accounts
- [ ] Transform and import to Odoo (del.ai handles transformation scripts)
- [ ] Verify record counts match: customers ✓ vendors ✓ products ✓
- [ ] Import open transactions: open AR, open AP, open POs as of migration date
- [ ] Verify open balance match between NetSuite and Odoo

### Integration rebuild
- [ ] Rebuild each third-party integration on Odoo (or validate existing Odoo connector)
- [ ] Test each integration with real data in staging
- [ ] Document new integration architecture

### Customization rebuild
- [ ] For each SuiteScript customization: build Odoo equivalent or confirm standard coverage
- [ ] User acceptance testing: Controller runs through month-end process in staging Odoo
- [ ] Fix issues found in UAT

### AI agent deployment
- [ ] del.ai deploys Agent 1 (AP automation or AR matching — TBD based on highest value)
- [ ] del.ai deploys Agent 2 (month-end close assistant or inventory reconciliation)
- [ ] Controller approves agent output in staging

---

## Phase 3 — Parallel Run & Go-Live (Days 61–90)

### Parallel run (2–4 weeks)
- [ ] Both NetSuite and Odoo run simultaneously
- [ ] Controller posts same transactions in both systems daily
- [ ] Weekly reconciliation: do balances match?
- [ ] Identify and fix any discrepancies

### Go-live gate (all must pass)
- [ ] 3 consecutive weeks of clean parallel-run reconciliation
- [ ] All integrations verified in production
- [ ] Controller signs off on Odoo month-end close capability
- [ ] Finance team trained on Odoo (del.ai handles training)
- [ ] AI agents tested in production with real transactions

### Go-live
- [ ] Cutover date confirmed (not during close, not during audit)
- [ ] NetSuite set to read-only (historical access retained)
- [ ] Odoo becomes system of record
- [ ] Alliance Partner contract terminated or restructured

### Post go-live (Days 91–120)
- [ ] First Odoo month-end close completed
- [ ] NetSuite historical data archived (read-only access maintained for 12 months)
- [ ] Stack Tax recalculation: new annual cost vs old (document savings)
- [ ] AI agent performance review: output quality + hours saved

---

## Who Owns What

| Task | Owner |
|------|-------|
| Migration scripts and data transformation | del.ai |
| Odoo configuration and customization | del.ai |
| AI agent build and deployment | del.ai |
| Business process documentation | Client (Controller) |
| UAT sign-off | Client (Controller) |
| Parallel-run reconciliation | Client + del.ai |
| Alliance Partner transition | Client |

---

*Template by [del.ai](https://usedel.ai) · Open source · June 2026*
*Questions: [usedel.ai](https://usedel.ai)*