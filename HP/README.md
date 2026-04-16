# Facilitator Guide: Hetu Patel, CFO — Thrive Market

## Participant Profile

| Field | Detail |
|-------|--------|
| Name | Hetu Patel |
| Title | Chief Financial Officer |
| Company | Thrive Market |
| Industry | E-commerce grocery (organic/natural products) |
| Team context | 100 non-eng staff already using Claude; Hetu is new to Claude Code specifically |
| Key pain points | Month-end variance commentary is manual and slow; no dedicated IR function; FBP team bottlenecked on Data team for analysis |

## Exercises

| # | Exercise | Complexity | Time | Key Skill |
|---|----------|-----------|------|-----------|
| 01 | Variance Commentary Agent | Medium | 30-40 min | Structured financial analysis from tabular data |
| 02 | Investor Q&A Prep | Medium-High | 35-45 min | Narrative generation, anticipating external questions |
| 03 | FBP Analysis Accelerator | High | 40-45 min | Python data analysis on large datasets, visualization |

## Exercise Details

### 01 — Variance Commentary Agent
Hetu pastes a sample P&L (GL trial balance with actuals vs AOP budget) and business context. Claude generates materiality-ranked variance commentary with executive narratives.

**What to watch for:**
- Does Claude correctly identify the largest variances by dollar amount?
- Are the narratives grounded in the business context provided?
- Does the waterfall chart render correctly?

**Common sticking points:**
- Participant may not realize they can iterate on tone/detail level
- If Claude picks the wrong materiality threshold, nudge them to adjust in the prompt

### 02 — Investor Q&A Prep
Builds IR capability where none exists. Claude drafts an earnings narrative, generates anticipated analyst questions with suggested responses, and checks for narrative consistency.

**What to watch for:**
- Quality of anticipated questions (should reflect real analyst concerns)
- Consistency between the narrative and the Q&A answers
- Whether the one-pager captures the right level of detail

**Common sticking points:**
- Participant may want to customize the tone for their specific investor audience
- The "narrative consistency check" is the most novel output — highlight it

### 03 — FBP Analysis Accelerator
The most technical exercise. Claude writes and runs Python to analyze 5,000+ rows of member cohort data that would crash Excel. Produces retention curves, LTV analysis, and category penetration.

**What to watch for:**
- Does Claude generate working Python on first try?
- Are visualizations clear and well-labeled?
- Does the reusable prompt template actually work when tested?

**Common sticking points:**
- If Python errors occur, coach participant to paste the error back and let Claude fix it
- The dataset is intentionally large — this is the point (Excel can't do this easily)
- Encourage them to try the stretch goal of adding their own data questions

## Support Notes

- **Pacing:** Exercise 01 is the warm-up. If Hetu moves fast, exercises 02 and 03 can absorb extra time via stretch goals.
- **Data files:** All synthetic data cross-references where possible (same time periods, consistent company metrics, matching account names).
- **Iteration is the lesson:** The real value isn't the first output — it's showing that Claude can refine based on feedback. Push participants to use the iteration hooks.
- **Excel comparison:** For Exercise 03, if time allows, have Hetu try opening the 5K-row CSV in Excel first to feel the pain point viscerally.
