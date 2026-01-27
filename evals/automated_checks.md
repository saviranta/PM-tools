# Automated Checks for PRD Output

Run these checks on every PRD output. All checks are pass/fail.

## 1. State Machine Compliance

| Check ID | Check | Pass Criteria |
|----------|-------|---------------|
| SM-01 | Context question asked | STATE INIT executed before STATE 0 |
| SM-02 | All states completed | INIT → 0 → 1 → 2 → 3 → 4 → 5 → 6 in order |
| SM-03 | No state skips | No gaps in state sequence |
| SM-04 | Exit conditions logged | Each state has exit_trigger recorded |
| SM-05 | No forbidden outputs | No forbidden_output_attempted = true |

## 2. Structural Completeness

| Check ID | Check | Pass Criteria |
|----------|-------|---------------|
| SC-01 | Executive Snapshot present | Section 1 exists with all subsections |
| SC-02 | Problem & User Clarity present | Section 2 exists |
| SC-03 | Value & Outcomes present | Section 3 exists |
| SC-04 | Market sizing present | SOM, volume, frequency, € value all present |
| SC-05 | Scope present | Section 4 exists with non-goals |
| SC-06 | User Journeys present | Section 5 exists with at least 1 journey |
| SC-07 | Workload table present | T-shirt size table with all components |
| SC-08 | Functional Requirements present | Section 6 exists |
| SC-09 | Edge Cases present | Section 7 exists |
| SC-10 | AI Behavior present (if applicable) | Section 8 exists or explicitly N/A |
| SC-11 | Assumptions table present | Section 9 with Value + Execution categories |
| SC-12 | Validation Plan present | Section 10 exists |
| SC-13 | Rollout present | Section 11 exists |
| SC-14 | Ownership present | Section 12 exists |
| SC-15 | Version marked as Draft | "v0 (Draft)" appears in document |

## 3. Evidence & Confidence

| Check ID | Check | Pass Criteria |
|----------|-------|---------------|
| EC-01 | Evidence labels present | At least 3 claims have Strong/Weak/None labels |
| EC-02 | Confidence levels on estimates | All numeric estimates have High/Med/Low |
| EC-03 | Market sizing has confidence | All 4 market sizing components have confidence |
| EC-04 | Assumptions have confidence | All assumptions have confidence level |
| EC-05 | No unqualified certainty | No "will definitely" or "guaranteed" language |

## 4. Assumptions Quality

| Check ID | Check | Pass Criteria |
|----------|-------|---------------|
| AQ-01 | Value assumptions present | At least 3 value assumptions |
| AQ-02 | Execution assumptions present | At least 3 execution assumptions |
| AQ-03 | Validation methods specified | Each assumption has validation method |
| AQ-04 | High-risk assumptions flagged | Low confidence items identified |

## 5. Strategic Fit (Conditional)

*Only check if context files were provided*

| Check ID | Check | Pass Criteria |
|----------|-------|---------------|
| SF-01 | Strategic fit assessed | If company_strategy provided, fit score present |
| SF-02 | Portfolio fit assessed | If product_description provided, fit analysis present |
| SF-03 | Misalignments flagged | Any misalignments explicitly noted |
| SF-04 | Context noted if missing | If no context, "not assessed" note present |

## 6. Workload Estimation

| Check ID | Check | Pass Criteria |
|----------|-------|---------------|
| WE-01 | All components estimated | Every functional requirement has size |
| WE-02 | Sizes are valid | Only XS/S/M/L/XL used |
| WE-03 | Dependencies noted | Dependencies column populated |
| WE-04 | Summary by size present | Count per size provided |
| WE-05 | Risks to estimates noted | At least 1 estimation risk identified |

## 7. Safety & Guardrails

| Check ID | Check | Pass Criteria |
|----------|-------|---------------|
| SG-01 | Guardrails defined | At least 3 guardrails listed |
| SG-02 | Kill criteria defined | At least 3 kill criteria |
| SG-03 | Non-goals defined | At least 3 non-goals |
| SG-04 | Failure modes identified | At least 3 failure modes |

---

## Scoring

```
Total Checks: ~35 (varies based on context provided)
Pass Rate = (Checks Passed / Total Applicable Checks) × 100%

Thresholds:
- ≥95%: Excellent - PRD meets all standards
- 85-94%: Good - Minor gaps, review flagged items
- 70-84%: Needs Work - Significant gaps, consider re-running
- <70%: Fail - Major structural issues, investigate
```

## Implementation Notes

These checks can be implemented as:
1. **Regex patterns** for section headers and keywords
2. **JSON schema validation** if PRD output is structured
3. **LLM-as-judge** for nuanced checks (evidence quality, etc.)

```python
def run_automated_checks(prd_text, trace_log, context_provided):
    results = {}

    # State machine compliance
    results['SM-01'] = 'INIT' in trace_log['states'][0]['state']
    results['SM-02'] = check_state_sequence(trace_log)
    # ... etc

    # Structural completeness
    results['SC-01'] = 'Executive Snapshot' in prd_text
    results['SC-04'] = all(x in prd_text for x in ['SOM', 'volume', 'frequency', '€'])
    # ... etc

    # Calculate pass rate
    applicable = [k for k, v in results.items() if v is not None]
    passed = [k for k, v in results.items() if v == True]
    pass_rate = len(passed) / len(applicable) * 100

    return results, pass_rate
```
