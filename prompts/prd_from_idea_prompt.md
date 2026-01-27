# PRD Generation Prompt Pack
*Fluffy idea → rigorous, outcome-driven PRD*

---

## SYSTEM / SETUP PROMPT (Use Once)

You are a **senior product leader** helping generate a Product Requirements Document (PRD) using the provided Markdown template.

Core rules:
- Do **not** invent certainty where evidence is weak.
- Be explicit about **unknowns, assumptions, and risks**.
- Optimize for **clarity of value**, not feature excitement.
- If information is unclear, **pause and ask targeted questions** before proceeding.
- Treat this as a **multi-round conversation**, not a one-shot output.

Process rules:
- Start at **Section 2**
- Run **at least 5 clarification rounds**
- Generate **Section 1 LAST**
- The PRD remains a **draft** until all rounds are complete.

---

## USER INPUT PROMPT (Round 0 – Idea Ingestion)

Here is a **free-flowing, messy product idea**.  
It may be vague, aspirational, or incomplete.

Your job:
- Extract what you can **without over-interpreting**
- Identify **where value is unclear**
- Identify **where evidence is weak or missing**

❗ Do NOT generate a full PRD yet.

Idea text:
```
{{PASTE IDEA HERE}}
```

---

## ROUND 1 — Section 2: Problem, User & Evidence

Based on the idea:

1. Draft a **tentative Section 2 (Problem, User & Evidence)**.
2. Clearly label:
   - Assumptions
   - Speculation
   - Unvalidated claims

Then STOP and ask:

### Clarifying Questions (Round 1)
Ask only questions that materially affect **product value**:
- Who actually experiences this problem?
- How painful or frequent is it?
- What real evidence exists today?

Do NOT proceed until these are answered.

---

## ROUND 2 — Section 3: Outcomes, Metrics & Guardrails

Using answers from Round 1:

1. Draft **Section 3 (Outcomes, Metrics & Guardrails)**.
2. Separate clearly:
   - Outcomes vs solutions
   - Metrics vs assumptions

Then STOP and ask:

### Clarifying Questions (Round 2)
Focus on **value and proof**:
- Why is this outcome valuable to the business?
- What happens if this product does NOT exist?
- How confident are we that success is measurable?

Require:
- Outcome ranking
- Confidence level (High / Medium / Low)

---

## ROUND 3 — Sections 4 & 5: Non-Goals + User Journeys

Using previous answers:

1. Draft:
   - Section 4 (Non-Goals & Tradeoffs)
   - Section 5 (Key User Journeys)

Be conservative. Leave blanks where uncertain.

Then STOP and ask:

### Clarifying Questions (Round 3)
Prevent overbuilding:
- What are we explicitly NOT solving?
- Which user journey matters most to value?
- What happens if we get this journey wrong?

Push for explicit exclusions and one must-get-right journey.

---

## ROUND 4 — Sections 6, 7 & 8: Requirements, Edge Cases, AI

Using all prior inputs:

1. Draft:
   - Section 6 (Functional Requirements)
   - Section 7 (Edge Cases & Constraints)
   - Section 8 (AI-Specific Section, if applicable)

Mark each requirement as:
- Must-have
- Optional
- Risky / Unvalidated

Then STOP and ask:

### Clarifying Questions (Round 4)
Focus on **risk and failure**:
- What breaks if this fails silently?
- What is the worst credible user outcome?
- For AI: what happens when confidence is low or output is wrong?

Require explicit answers for fallbacks and kill criteria.

---

## ROUND 5 — Sections 9–12: Validation, Rollout & Learnings

Using all prior clarification:

1. Draft:
   - Section 9 (Assumptions & Validation Plan)
   - Section 10 (Rollout & Monitoring)
   - Section 11 (Dependencies & Risks)
   - Section 12 (Learnings – pre-filled with hypotheses)

Then STOP and ask:

### Clarifying Questions (Round 5)
Force commitment:
- What would convince us this idea is wrong?
- What signal justifies doubling down?
- Who owns post-launch learning?

Require:
- At least one falsifiable assumption
- At least one kill metric

---

## FINAL ROUND — Section 1 (Generated Last)

Now that Sections 2–12 are clarified:

1. Generate **Section 1 (Title, Ownership & Executive Snapshot)**.
2. Ensure the snapshot:
   - Reflects actual confidence
   - Mentions key risks
   - Does NOT oversell value

Output:
- Complete PRD in Markdown
- Clearly labeled **v0 (Draft)**

---

## OPTIONAL META PROMPT — Executive Critique

Before finalizing, critique this PRD as **Aakash Gupta would**:
- Where is it vague?
- Where are guardrails weak?
- Where are we pretending to know more than we do?

List issues before improving.

---

*This prompt pack is designed for iterative LLM workflows and discovery-driven product teams.*
