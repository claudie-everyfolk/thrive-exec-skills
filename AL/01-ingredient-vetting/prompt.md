# Ingredient Vetting Workflow

## Context Frame

I'm April Lane, Chief Merchant at Thrive Market. We're building an in-house ingredient vetting tool to replace our current third-party platform (Novi), which costs us $175-200K per year. Every product that comes onto Thrive Market goes through ingredient review against our quality standards -- we reject anything with artificial preservatives, high fructose corn syrup, hydrogenated oils, and dozens of other ingredients our members trust us to screen out.

Right now this process involves manual cross-referencing between vendor submissions and our standards document. I have a batch of new product submissions that need vetting, and I want to see how Claude Code handles the full workflow.

## The Ask

Using the attached files -- `ingredient_submissions.csv` (product submissions from vendors) and `thrive_ingredient_standards.md` (our quality standards) -- please:

1. **Screen every product** in the submissions file against our ingredient standards. For each product, classify every listed ingredient as Acceptable, Restricted (requires documentation), Unacceptable, or Unknown (not in our standards and needs FSQA review).

2. **Generate a per-product vetting report** that shows: product name, brand, overall status (Approved / Conditional Approval / Rejected / Needs Review), a table of each ingredient with its classification, and specific notes on why any ingredient was flagged.

3. **Flag all documentation requirements** -- for any product with Restricted ingredients, list exactly what documentation the vendor needs to provide (non-GMO verification, sustainable sourcing certificates, third-party testing, etc.).

4. **Produce a batch summary table** with columns: Brand, Product, Status, Flag Count, Top Issue, and a recommended action (Approve / Request Docs / Reject / Escalate to FSQA).

5. **Create an escalation list** for our FSQA (Food Safety & Quality Assurance) team -- products with Unknown ingredients or borderline cases that need human expert review, with the specific question FSQA should answer for each.

6. **Calculate batch statistics** -- approval rate, most common flagged ingredients across submissions, vendors with the cleanest submissions vs. those needing the most work.

## Why This Matters

This workflow currently takes our quality team 2-3 hours per batch of 15-20 products. If Claude Code can handle the cross-referencing accurately, we can scale vetting to handle 100+ products per batch and redeploy the Novi budget ($175-200K/yr) toward expanding our quality standards and sourcing team.

## Iteration Hooks

- Ask Claude to reformat the vetting report as a vendor-facing document (different tone -- collaborative, not internal audit language)
- Add a new ingredient to the Unacceptable list and re-run the batch to see what changes
- Request a "close call" analysis -- products that passed but were one ingredient away from rejection
- Ask for the output as a structured CSV you could import into a product management system

## Stretch Goals

- Have Claude generate a template email to each vendor summarizing their submission results and any required documentation
- Ask Claude to suggest additions to the standards document based on patterns it sees in the Unknown ingredients
- Request a decision tree diagram (in markdown) showing the vetting logic flow
