# Josh Kreinberg — Exercise Package

**Role:** General Counsel & Chief Administrative Officer, Thrive Market
**Workshop:** Hands-on Claude Code for Executives
**Exercises:** 3 (30-45 min each)

---

## Facilitator Guide

### Participant Context

Josh oversees Legal and People Ops at Thrive Market (e-commerce, organic/natural grocery, membership model). Key context for coaching:

- **AI experience:** Legal team uses CoCounsel for research (cut 2-3hr tasks to 30-45min). DocuSign IAM for contract workflows. Not a beginner — but prompting skills are uneven across his teams.
- **#1 concern:** Hallucination in legal AI output. Lean into this — Exercise 2 explicitly builds the "trust but verify" muscle.
- **Dual hat:** GC + CAO means he cares about both legal precision AND employee experience. Exercises 1 and 2 target legal; Exercise 3 targets People Ops. This range is intentional.
- **Team scale:** Legal processes 75-150 contracts/month. People Ops serves ~1,850 employees across HQ, 2 fulfillment centers, and remote.

### Exercise Sequence

| # | Exercise | Time | Core Skill |
|---|----------|------|------------|
| 1 | Contract Triage & Playbook Review | 30-40 min | Structured analysis with cross-referenced rules |
| 2 | Regulatory Research Accelerator | 35-45 min | Research synthesis + hallucination detection |
| 3 | Employee Communications in Thrive's Voice | 30-40 min | Voice matching + audience-aware writing |

**Recommended order:** Run as listed. Exercise 1 builds confidence in Claude's analytical capability. Exercise 2 introduces healthy skepticism (hallucination flagging). Exercise 3 shifts to creative/communication work — a good change of pace to close.

### Setup Instructions

Each exercise folder contains:
- `prompt.md` — the paste-ready prompt (Josh copies this into Claude Code along with the data files)
- Supporting data files that cross-reference each other

**For each exercise:**
1. Have Josh open the exercise folder in Claude Code
2. He pastes the prompt from `prompt.md` and attaches/references the data files
3. Claude produces the deliverables
4. Use the **Iteration Hooks** in the prompt to demonstrate follow-up prompting
5. Discuss the **Stretch Goals** if time permits

### Coaching Notes by Exercise

#### Exercise 1: Contract Triage

**What to watch for:**
- Does Claude correctly identify ALL deviations from the playbook? Key ones: the 3-year initial term, 90-day non-renewal notice, unlimited customer liability carve-outs, perpetual data license, vendor ownership of custom deliverables, one-sided termination for convenience, 8% price escalation, asymmetric liability caps, broad customer indemnification.
- Does it apply the correct escalation threshold? ($175K = Senior Counsel for Yellow, GC for Red)
- Quality of the replacement language — is it actually usable contract markup?

**Key teaching moment:** The Agreement Desk automation notes (Ask #6). This bridges from "Claude as reviewer" to "Claude as system designer" — helping Josh think about which checks can be rules in DocuSign IAM vs. which need human judgment.

**Common pitfall:** Claude may miss the subtle interaction between Section 4.2 (perpetual data license) and Section 8.4 (survival clause referencing Section 4.2). Coach Josh to ask Claude to trace survival clauses.

#### Exercise 2: Regulatory Research

**What to watch for:**
- Does Claude flag its own uncertainty? The hallucination flagging (Ask #4) is the centerpiece. If Claude produces confident citations without caveats, coach Josh to push back: "How confident are you in that citation? What should I verify?"
- Does it catch the outdated guidance in prior_guidance.md? Memo 1 says "we are not aware of any recent enforcement actions" — this should be flagged as potentially stale (6 months old). Memo 2 notes the caveat about state-specific analysis that was never done.
- Does it distinguish between what it knows from the provided regulatory_reference.md vs. what it's drawing from training data?

**Key teaching moment:** The confidence-level flagging creates a reusable pattern. After the exercise, ask Josh: "If your associates produced memos with this kind of confidence tagging, would that change how you review their work?" This connects to building team-wide AI research standards.

**Common pitfall:** Claude may overstate the applicability of the Baudry et al. study (it's a French study with ~700 participants — limited generalizability for US advertising claims). If Claude doesn't flag this, coach Josh to probe.

#### Exercise 3: Employee Comms

**What to watch for:**
- Does the output actually match Thrive's voice guide? Check for: "Thrivers" not "employees," leading with "why," acknowledging impact on individuals, no corporate jargon. The voice guide has specific do/don't examples — compare Claude's output against them.
- Does the channel strategy account for the FC workforce? The 60% hourly worker population should drive decisions about sequencing, language level, and Spanish translation needs.
- Does the RTO communication navigate the equity issue? (FC workers have always been on-site; HQ is getting a commute stipend they don't get.)

**Key teaching moment:** The tone comparison (Ask #5) is the most powerful coaching artifact. Seeing the same message in "generic corporate" vs. "Thrive voice" side-by-side teaches the team exactly what prompting for voice looks like. Save this output — it becomes a reference for People Ops.

**Common pitfall:** Claude may default to generic HR language despite the voice guide. If this happens, coach Josh to paste a specific example from the voice guide and say "match this tone exactly." This demonstrates the difference between describing voice vs. showing examples.

### Cross-Exercise Themes

Thread these themes across all three exercises:

1. **Cross-referencing data files:** All three exercises require Claude to synthesize across multiple documents. This mirrors real legal/HR work where context lives in multiple places.

2. **Iteration is the skill:** The initial prompt produces a first draft. The iteration hooks are where the real work happens. Budget at least 10 minutes per exercise for follow-up prompting.

3. **From analysis to system:** Each exercise includes a stretch goal about building reusable templates/frameworks. This pushes Josh from "Claude as assistant" to "Claude as system builder" — designing prompts his team can use repeatedly.

4. **Trust calibration:** Exercise 1 builds trust (Claude is good at structured rule-matching). Exercise 2 introduces skepticism (Claude can hallucinate on legal citations). Exercise 3 requires judgment (voice matching is subjective). This arc is intentional.

### File Inventory

```
JK/
├── README.md                          # This file
├── 01-contract-triage/
│   ├── prompt.md                      # Paste-ready prompt
│   ├── sample_saas_agreement.md       # 10-section SaaS agreement with embedded issues
│   ├── contract_playbook.md           # Thrive's standard negotiating positions
│   └── risk_tolerance.md              # Risk classification + escalation matrix
├── 02-regulatory-research/
│   ├── prompt.md                      # Paste-ready prompt
│   ├── research_request.md            # Internal request from VP Marketing
│   ├── prior_guidance.md              # Two prior legal memos (one partially outdated)
│   └── regulatory_reference.md        # Key regulatory provisions (incomplete by design)
└── 03-employee-comms/
    ├── prompt.md                      # Paste-ready prompt
    ├── comms_scenario.md              # 3 scenarios at different sensitivity levels
    ├── thrive_voice_guide.md          # "Voice of Thrive" style guide
    └── audience_context.md            # Workforce composition + channel matrix
```
