# Workforce Planning Scenario Modeler

## Context Frame

I'm the CEO of Thrive Market, a membership-based online grocery company with over $500M in revenue and approximately 800 employees. Every one of my 9 functional leaders just submitted AI strategy documents, and every single one describes AI replacing tactical work — data entry in Finance, rubric-based QA in Member Services, manual scheduling in Operations, coordinator tasks in People Ops. At the same time, every function is also describing new AI-adjacent work they need: prompt engineers, AI tool administrators, data quality specialists, automation architects.

I need to model what the organization looks like in 12 months under different scenarios. Not to plan layoffs — to plan the transformation. The board wants to understand: Does AI mean we hire fewer people, or different people? If our top initiatives succeed, what does the headcount plan look like? What happens to the roles that are 60-80% automatable?

I have three data files:
- `current_headcount.csv` — Current headcount by function, sub-team, and role type with AI-amenability ratings
- `initiative_impact.csv` — How each top AI initiative affects specific roles
- `growth_scenarios.md` — Three scenarios modeling different growth and AI adoption trajectories

## The Ask

Using the three attached data files, build me:

1. **Scenario comparison table** — Headcount by function across all 3 scenarios at 12-month horizon. Show current headcount, projected headcount without AI (Base Case), projected with AI at current trajectory (AI-Accelerated), and projected with aggressive AI adoption (Aggressive AI). The delta between scenarios is the story — make it clear.

2. **Role evolution map** — For each function, categorize every affected role into one of four buckets: (a) Tactical-to-Strategic shift — role survives but focus changes from execution to oversight, (b) New AI-adjacent role — didn't exist before, created by AI adoption, (c) Shrinking role — fewer headcount needed but role doesn't disappear, (d) Eliminated role — function fully automated, role is phased out. Be specific about which roles fall into which bucket and why.

3. **Investment vs. savings model** — A financial model showing: AI tool spend, headcount savings (roles not backfilled + roles eliminated), productivity gains (same headcount doing more), net financial impact by quarter over 12 months. Show this for each scenario. The board will ask "does AI pay for itself?" — give them the answer.

4. **Hiring plan implications** — Based on the AI-Accelerated scenario (most likely), create a specific hiring plan: where do we actively hire, where do we pause hiring and let attrition reduce headcount, where do we retrain existing employees into new roles, and where (if anywhere) do we need to have honest conversations about role elimination. Include a retraining roadmap for the top 5 most-affected roles.

5. **Board-ready narrative** — A 1-page narrative framing AI as "workforce multiplier, not workforce reducer." This is the story I tell the board. It needs to be honest — some roles will shrink — but the frame should be about capability expansion, not cost cutting. Use specific examples from the data: "Our 4-person AP team becomes a 2-person AP team that also handles vendor analytics" not "we're cutting AP headcount by 50%."

## Why This Matters

This is the most sensitive topic in the company. Every employee wonders "is AI going to replace me?" I need to lead this conversation with data and a clear plan, not vague reassurances. The board will pressure me on efficiency gains. My team leaders will push back on headcount reductions. I need a model that lets me navigate both audiences with one coherent story.

The worst outcome is inaction — not making any workforce plan and letting AI adoption create anxiety without a clear direction. The second worst is making it about cost cutting. The right answer is a transformation plan that's honest about what changes and compelling about where we're going.

## Iteration Hooks

- "The VP of Member Services is worried about the Sierra expansion implying agent layoffs — build a specific transition plan for the Member Services team"
- "The CFO wants to see the breakeven point — at what month does AI investment start generating net savings?"
- "Add a retention risk analysis — which high-performers are in roles most affected by AI, and what's our plan to keep them?"
- "The board wants to see this benchmarked — what are comparable e-commerce companies doing with AI-driven workforce changes?"

## Stretch Goals

- Build an interactive scenario modeler where I can adjust assumptions (AI adoption speed, growth rate, attrition rate) and see headcount projections update in real-time
- Create individual function playbooks — one page per function showing their specific headcount evolution, retraining plan, and new roles
- Model the cost of NOT investing in AI — what happens to headcount if we try to achieve the same growth targets without AI automation?
