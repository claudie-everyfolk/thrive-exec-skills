# Jonas Klink — Exercise Package (VP Product & Design, Thrive Market)

## Facilitator Guide

### Participant Context
Jonas leads Product & Design at Thrive Market (membership-based organic/natural e-commerce). His design team is deeply AI-integrated (Figma Make credits exhausted monthly, Claude CoWork as "second brain"). PM team has productive but more fragmented AI use. Key pain point: PMs spend 37% of time on sprint management (target: <20%) and only 18% on discovery/strategy (target: 30%+).

### Key Insight to Reinforce
Jonas already knows AI gets to 50-60% fast but closing to production quality requires meaningful human effort. These exercises lean into that — the prompts produce strong first drafts, and the iteration hooks show how Claude Code's agentic workflow helps close the remaining 40-50% faster than manual editing.

### Exercise Sequence

| # | Exercise | Time | Core Skill |
|---|----------|------|------------|
| 1 | Product Artifact Co-Author | 25 min | Structured document generation from multiple context files |
| 2 | Sprint Health Analyzer | 25 min | CSV analysis + operational intelligence |
| 3 | Opportunity Detection | 25 min | Multi-source signal aggregation + strategic synthesis |

### Exercise 1: Product Artifact Co-Author (01-product-artifact-coauthor/)
**Setup:** Participant opens the folder, reads `prompt.md`, and pastes the prompt into Claude Code while in the exercise directory (so `@`-file references resolve).

**What to watch for:**
- Claude should pick up the spec format from `prior_specs.md` and match it
- The Syndigo PIM launch date (April 20) should appear as a dependency in the spec
- Amplitude instrumentation plan should reference realistic e-commerce events
- RICE scoring should be grounded in the data from `product_context.md`

**Coaching moments:**
- If the spec is generic, show how adding `@product_context.md` and `@prior_specs.md` to the prompt dramatically improves output
- Demonstrate iteration: "Make the acceptance criteria more specific for the mobile experience" or "Add edge cases for members with multiple dietary restrictions"
- Connect to their Q2 initiative: this is exactly the Product Artifact Co-Authoring workflow

### Exercise 2: Sprint Health Analyzer (02-sprint-health/)
**Setup:** Same as above. The CSV has realistic sprint data with mid-sprint disruptions.

**What to watch for:**
- Claude should identify the scope creep (3 tickets added mid-sprint by stakeholder)
- The sick engineer and production incident should surface as velocity drags
- Blocked items should have actionable root cause analysis
- Standup summary should be concise and PM-ready

**Coaching moments:**
- Show how Claude can generate different views: "Now format this as a message I'd post in our #dev-standup Slack channel"
- Demonstrate the time savings: "This analysis would normally take 30-45 minutes of Jira clicking"
- Connect to their target: getting PM sprint management time from 37% to <20%

### Exercise 3: Opportunity Detection (03-opportunity-detection/)
**Setup:** Three data files representing different signal sources. The prompt asks Claude to synthesize across all of them.

**What to watch for:**
- The GLP-1 signal should surface as a top opportunity (rising filter usage + Instacart competitive move)
- Mobile performance issues should correlate across NPS feedback and product metrics
- The Syndigo PIM launch should appear as an enabler for personalization opportunities
- Competitive threats should map to specific product roadmap items

**Coaching moments:**
- This is the hardest exercise — show how Claude handles ambiguity and makes judgment calls
- Demonstrate follow-up: "Expand the GLP-1 opportunity into a full discovery sprint plan"
- Connect to their Q3-Q4 initiative: this is the AI-Powered Opportunity Detection workflow

### General Tips
- Jonas is a product leader — he'll appreciate structured output and clear prioritization
- His team already uses Claude CoWork, so the mental model isn't new — focus on Claude Code's ability to work with files and produce structured artifacts
- Emphasize the workflow: context files + clear prompt = production-ready first draft that's 50-60% done
- The "Iteration Hooks" section in each prompt is designed to show that the remaining 40-50% can be closed through conversation, not manual rewriting
