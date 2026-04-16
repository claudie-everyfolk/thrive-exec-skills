# April Lane -- Chief Merchant | Facilitator Guide

## Participant Profile

**Name:** April Lane
**Title:** Chief Merchant
**Company:** Thrive Market
**Function:** Merchandising, vendor management, product assortment, quality standards

**What she owns:** End-to-end product assortment strategy -- which brands and products make it onto Thrive Market, how they're merchandised to members, and the vendor relationships that power the catalog. Her team manages ingredient vetting, category planning, promotional merchandising (50-300 brands per sale), and vendor negotiations including Joint Business Plans.

**Why these exercises matter for her:** April sits at the intersection of quality, commerce, and vendor relationships. Each exercise targets a real workflow her team runs today -- but with enough volume and complexity that Claude Code's ability to cross-reference data and generate structured output will feel immediately valuable.

---

## Exercises

### Exercise 1: Ingredient Vetting Workflow
**Complexity:** Low-Medium
**Directory:** `01-ingredient-vetting/`
**Time:** 30 min
**What it builds:** An automated ingredient screening system that cross-references product submissions against Thrive's quality standards. Classifies every ingredient, flags documentation requirements, and generates batch approval recommendations.
**Key learning:** Claude Code can replace expensive SaaS tools (Novi, $175-200K/yr) by doing structured data cross-referencing against complex rule sets.

### Exercise 2: Merchandising Brief Generator
**Complexity:** Medium
**Directory:** `02-merchandising-brief/`
**Time:** 35-40 min
**What it builds:** A 5-day themed sale calendar with brand placements, creative brief outlines, and performance predictions -- all generated from brand data, sale parameters, and historical performance.
**Key learning:** Claude Code excels at synthesizing multiple data sources into creative + analytical output simultaneously. The merchandising brief combines quantitative analysis (past performance, margin tiers) with qualitative judgment (theme narrative, brand storytelling).

### Exercise 3: Vendor Scorecard & JBP Prep
**Complexity:** Medium-High
**Directory:** `03-vendor-scorecard/`
**Time:** 40-45 min
**What it builds:** One-page vendor scorecards with benchmarking, JBP talking points, negotiation prep briefs, and a priority-ranked meeting schedule.
**Key learning:** Claude Code can take messy, multi-format data (CSV performance metrics, markdown market context, JSON negotiation history) and produce polished executive-ready output. This is the "Category Manager in a box" exercise.

---

## Support Notes

- **Ingredient vetting** is the most self-contained exercise. If April gets stuck or time is tight, this one stands alone well. The standards doc is detailed enough that Claude Code should produce strong output on the first pass.
- **Merchandising brief** has the most creative latitude. Encourage April to iterate on tone and theme framing -- the Iteration Hooks are designed for this. If output feels generic, prompt her to add brand-specific storytelling constraints.
- **Vendor scorecard** is the most data-intensive. If Claude Code produces a wall of text, coach her toward the Iteration Hook that requests a single-page visual format. The negotiation_history.json file is intentionally rich -- the best output comes from prompts that explicitly reference prior year terms.
- All three exercises use cross-referenced synthetic data. Brand names in sale_brands.csv appear in past_sale_performance.csv. Vendors in vendor_performance.csv appear in negotiation_history.json. This lets Claude Code make connections across files naturally.
- If April finishes early, the Stretch Goals in each exercise push toward automation (scheduling, Slack integration, dashboard output) -- good preview of what a production deployment looks like.
