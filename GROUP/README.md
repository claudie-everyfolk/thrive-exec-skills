# Group Exercise — Facilitator-Led Demo

**Led by:** Mike Taylor
**Format:** Live demo, same dataset through four levels of AI

## The Concept

One Excel file, one task, one difference per step. The exercise demonstrates the four levels of AI using the exact same data and question, showing what changes at each level:

### The Question
> "Analyze this membership and category performance data. What's driving churn?"

### The Four Levels

| Level | Tool | What's Different |
|-------|------|-----------------|
| **Chatbot** | claude.ai | Upload the Excel, ask the question. Claude reads it, gives a text answer. If you want a retention column or chart, Claude tells you what to do (or gives a formula to paste) — but you're toggling back and forth. The spreadsheet doesn't change. |
| **Copilot** | Claude in Excel | Same file, same question. But now the retention column appears *in your spreadsheet*. The chart materializes. You're watching it happen live alongside you. Claude is working *inside* the tool, not just talking about it. |
| **Agent** | Claude Code | Same file, same question. But now it also pulls context from Slack — finds a thread where the ops team discussed a warehouse shipping delay in March that explains the churn spike. It reaches beyond the file to gather context you didn't hand it. |
| **Assistant** | Open Claw | Same everything, but it flags the churn spike to you *before you ask*. Proactive, not reactive. |

## Files

| File | Purpose | Used In |
|------|---------|---------|
| `membership_category_performance.xlsx` | Core dataset — membership and category performance data with a churn spike baked in | All four levels |
| `slack_cs_escalations.md` | #cs-escalations Slack channel showing the Batesville conveyor outage, real-time impact, and post-mortem | Agent level (Claude Code finds this) |
| `prompt.md` | The question to paste at each level | All levels |
| `ai-levels-demo.pptx` | Slide deck for the demo | Presentation |

## How to Run the Demo

### Level 1 — Chatbot (claude.ai)
1. Open claude.ai
2. Upload `membership_category_performance.xlsx`
3. Paste the prompt from `prompt.md`
4. Claude gives text analysis — accurate but flat. It finds the churn spike but can only describe it. No charts appear in your spreadsheet. You're reading an essay about your data.

### Level 2 — Copilot (Claude in Excel)
1. Open the Excel file with Claude/AI copilot enabled
2. Ask the same question
3. **The difference:** retention columns get added to the spreadsheet. Charts appear. Conditional formatting highlights the problem cells. The analysis happens *in the tool you already work in* — not in a separate chat window.

### Level 3 — Agent (Claude Code)
1. Open Claude Code in the exercise folder (which contains both the Excel and the Slack export)
2. Paste the same prompt
3. **The difference:** Claude doesn't just analyze the spreadsheet — it reads the Slack thread too. It connects the Batesville conveyor outage (Feb 24) to the churn spike in Grocery and Pantry Staples. It explains *why* Supplements and Beauty were unaffected (different shipping zone). It pulls in the post-mortem numbers: ~5,700 delayed orders, 2,800 excess cancellations, 22% win-back reactivation rate.
4. The output is richer because the agent gathered context you didn't explicitly provide.

### Level 4 — Assistant (Open Claw)
1. Describe the concept — don't need to demo live
2. **The difference:** The system flags the churn spike to you *before you open the spreadsheet*. It noticed the pattern, correlated it with the Slack thread, and sent you a summary: "Heads up — March churn in Grocery and Pantry spiked 3x. Looks related to the Batesville outage. Here's what I'd recommend."
3. You went from pulling insights to receiving them.

## Teaching Point

The data doesn't change. The question doesn't change. What changes is the *surface area* of what AI can reach and the *initiative* it takes. Each level is strictly more capable than the last — not a different tool for a different job, but a progression in how deeply AI integrates into your workflow.

## The Hidden Story in the Data

The churn spike is concentrated in **Grocery** and **Pantry Staples** during **late February / March 2025**, caused by a conveyor system failure at the Batesville fulfillment center. Key details from the Slack thread:
- Conveyor went down Feb 24, parts took 48-72 hours, full backlog cleared by Mar 5
- ~5,700 orders shipped 5-8 days late
- Supplements, Beauty, Snacks unaffected (different shipping zone)
- ~2,800 excess member cancellations, mostly longtime members (1yr+)
- Win-back campaign achieved 22% reactivation in 48 hours

The chatbot finds the spike. The copilot visualizes it. The agent explains it. The assistant prevents it.
