# Stack Tax Calculator

Standalone browser calculator. No dependencies, no login, no backend.

## Use it

Open `index.html` in any browser.

Or embed in any webpage:

```html
<iframe
  src="https://usedel-ai.github.io/netsuite-stack-tax/calculator/"
  width="100%"
  height="700"
  frameborder="0"
></iframe>
```

## What it calculates

Five inputs:
1. NetSuite license + per-user fees
2. Alliance Partner retainer
3. SuiteApps (Avalara, Celigo, FloQast, other)
4. BI tools + ETL (Looker, Snowflake, Fivetran)
5. Internal NetSuite admin FTEs (× $120k/yr)

Outputs:
- Total annual stack cost
- Stack multiplier vs license line
- 5-year staying cost (8% annual escalation)
- 5-year Odoo alternative cost ($50k migration + $30k/yr)
- Payback period (months)
- 5-year net savings

## Embed on your site

Pure HTML/CSS/JS. Copy `index.html` and serve it anywhere.

---

*Built by [del.ai](https://usedel.ai)*