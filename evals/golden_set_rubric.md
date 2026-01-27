# Golden Set Evaluation Rubric

Manual scoring rubric for PRD quality assessment.

## Purpose

Use this rubric to:
1. Score PRDs against a consistent quality standard
2. Create "golden" reference PRDs for benchmarking
3. Compare agent versions over time
4. Train evaluators on quality expectations

---

## Scoring Dimensions

### 1. Completeness (0-10)

*Does the PRD cover everything needed to make a go/no-go decision?*

| Score | Criteria |
|-------|----------|
| 9-10 | All sections present and thorough. No gaps. Reader has everything needed. |
| 7-8 | All sections present. Minor gaps that don't block decisions. |
| 5-6 | Most sections present. Some notable gaps but core is there. |
| 3-4 | Major sections missing. Significant gaps in coverage. |
| 0-2 | Incomplete. Missing critical sections. Not usable as-is. |

**Check:**
- [ ] Problem clearly stated
- [ ] Target user defined
- [ ] Value proposition articulated
- [ ] Market sizing attempted
- [ ] Scope and non-goals defined
- [ ] User journeys mapped
- [ ] Requirements listed
- [ ] Risks identified
- [ ] Assumptions explicit
- [ ] Validation plan exists

---

### 2. Evidence Rigor (0-10)

*Are claims grounded in evidence? Is uncertainty preserved?*

| Score | Criteria |
|-------|----------|
| 9-10 | Every claim labeled with evidence level. Uncertainty explicit. No hand-waving. |
| 7-8 | Most claims labeled. Confidence levels consistent. Minor gaps. |
| 5-6 | Some evidence labeling. Inconsistent confidence. Some unsupported claims. |
| 3-4 | Little evidence distinction. Many unsupported claims. False confidence. |
| 0-2 | No evidence rigor. Claims presented as facts. Hallucinated confidence. |

**Check:**
- [ ] Strong/Weak/No evidence labels used
- [ ] Confidence levels (H/M/L) on estimates
- [ ] Assumptions distinguished from facts
- [ ] "We don't know" stated where true
- [ ] Sources cited where possible

---

### 3. Assumption Clarity (0-10)

*Are assumptions explicit, testable, and actionable?*

| Score | Criteria |
|-------|----------|
| 9-10 | All assumptions explicit. Each has validation method. Risk levels clear. |
| 7-8 | Most assumptions captured. Validation methods for key ones. |
| 5-6 | Some assumptions listed. Validation methods sparse. |
| 3-4 | Few assumptions explicit. Hidden assumptions throughout. |
| 0-2 | Assumptions not addressed. Reader can't identify what's assumed. |

**Check:**
- [ ] Value assumptions separated from execution assumptions
- [ ] Each assumption has confidence level
- [ ] Validation method specified
- [ ] High-risk assumptions flagged
- [ ] Falsifiable (can be proven wrong)

---

### 4. Actionability (0-10)

*Can someone act on this PRD? Does it drive decisions?*

| Score | Criteria |
|-------|----------|
| 9-10 | Clear next steps. Obvious what to validate. Decision criteria explicit. |
| 7-8 | Actionable with minor clarification needed. Path forward clear. |
| 5-6 | Somewhat actionable. Reader needs to infer some actions. |
| 3-4 | Vague on actions. Reader unsure what to do next. |
| 0-2 | Not actionable. Just describes idea without driving decisions. |

**Check:**
- [ ] Validation plan has concrete steps
- [ ] Kill criteria defined (when to stop)
- [ ] Success metrics are measurable
- [ ] Workload estimation enables planning
- [ ] Open questions listed for follow-up

---

### 5. Strategic Coherence (0-10)

*Does the PRD tell a coherent story? Does it fit together?*

| Score | Criteria |
|-------|----------|
| 9-10 | Problem → Solution → Value chain is clear. Everything connects. |
| 7-8 | Coherent overall. Minor disconnects between sections. |
| 5-6 | Mostly coherent. Some sections feel disconnected. |
| 3-4 | Incoherent in places. Sections contradict or don't connect. |
| 0-2 | No coherent narrative. Sections are disjointed. |

**Check:**
- [ ] Problem statement connects to user outcomes
- [ ] User journeys address the stated problem
- [ ] Requirements support the journeys
- [ ] Metrics measure the stated outcomes
- [ ] Non-goals make sense given scope

---

### 6. Honest Risk Framing (0-10)

*Does the PRD honestly surface risks and unknowns?*

| Score | Criteria |
|-------|----------|
| 9-10 | Risks prominently surfaced. Worst cases identified. No sugar-coating. |
| 7-8 | Key risks identified. Honest about uncertainties. |
| 5-6 | Some risks noted. Tendency toward optimism. |
| 3-4 | Risks downplayed. Overly optimistic framing. |
| 0-2 | Risks ignored. Reads like a sales pitch. |

**Check:**
- [ ] Failure modes identified
- [ ] Kill criteria defined
- [ ] "What could go wrong" addressed
- [ ] Market sizing uncertainty acknowledged
- [ ] Execution risks noted

---

## Overall Score Calculation

```
Total = (Completeness + Evidence + Assumptions + Actionability + Coherence + Risk) / 6

Interpretation:
- 9-10: Excellent - Ready for stakeholder review
- 7-8: Good - Minor improvements needed
- 5-6: Adequate - Needs work before sharing
- 3-4: Poor - Significant revision required
- 0-2: Fail - Start over or investigate issues
```

---

## Golden Set Creation

To create a golden reference PRD:

1. **Select diverse test ideas:**
   - Simple product (clear scope)
   - Complex product (many unknowns)
   - Strategic fit test (with context files)
   - Edge case (vague input)

2. **Generate PRD with agent**

3. **Score using this rubric**

4. **If score ≥8:** Use as golden reference
   - Document what made it good
   - Save input + output + trace

5. **If score <8:** Improve manually
   - Fix gaps to create ideal output
   - Document what was missing
   - Use improved version as golden

---

## Evaluation Session Template

```markdown
## PRD Evaluation

**Evaluator:** [Name]
**Date:** [Date]
**PRD Title:** [Title]
**Input Idea:** [Brief description]

### Scores

| Dimension | Score | Notes |
|-----------|-------|-------|
| Completeness | /10 | |
| Evidence Rigor | /10 | |
| Assumption Clarity | /10 | |
| Actionability | /10 | |
| Strategic Coherence | /10 | |
| Honest Risk Framing | /10 | |
| **Overall** | **/10** | |

### Strengths
-

### Gaps / Issues
-

### Suggestions for Improvement
-
```
