# Calibration Tracker

Track estimate accuracy over time to improve agent calibration.

---

## Purpose

Over time, compare:
- **Estimated** values (from PRD at creation time)
- **Actual** values (observed after build/launch)

This reveals systematic biases (always over/underestimating) and helps calibrate future PRDs.

---

## Market Sizing Calibration

### Template

| PRD | Date | Metric | Estimated | Confidence | Actual | Variance | Notes |
|-----|------|--------|-----------|------------|--------|----------|-------|
| | | SOM (users/year) | | | | | |
| | | Problem frequency | | | | | |
| | | Per-user value (€) | | | | | |
| | | Total market value (€) | | | | | |

### Example

| PRD | Date | Metric | Estimated | Confidence | Actual | Variance | Notes |
|-----|------|--------|-----------|------------|--------|----------|-------|
| Finlex MCP | 2026-01 | SOM | 20K-50K | Low | 8K | -60% to -84% | Overestimated reach |
| Finlex MCP | 2026-01 | Per-user value | €100-500 | Low | €150 | Within range | Good estimate |

### Calibration Analysis

```
After 10+ PRDs with actuals:

1. Calculate average variance per metric
2. Identify systematic bias:
   - SOM: Typically over/underestimate by X%?
   - Value: Typically over/underestimate by X%?
3. Adjust future estimates or confidence levels accordingly
```

---

## Workload Estimation Calibration

### Template

| PRD | Component | Estimated Size | Actual Effort | Variance | Notes |
|-----|-----------|----------------|---------------|----------|-------|
| | | XS/S/M/L/XL | Days/weeks | | |

### Size-to-Effort Mapping (Calibrate Over Time)

| Size | Initial Assumption | Observed Average | Calibrated Range |
|------|-------------------|------------------|------------------|
| XS | <1 day | | |
| S | <1 week | | |
| M | 1-2 weeks | | |
| L | 2-4 weeks | | |
| XL | >4 weeks | | |

### Example

| PRD | Component | Estimated | Actual | Variance | Notes |
|-----|-----------|-----------|--------|----------|-------|
| Finlex MCP | XML parsing | M | 3 weeks | +50% | Schema more complex than expected |
| Finlex MCP | Chat UI | S | 4 days | On target | |
| Finlex MCP | RAG implementation | M | 2.5 weeks | +25% | Tuning took longer |

---

## Confidence Calibration

### Are confidence levels accurate?

Track what percentage of estimates at each confidence level fall within the estimated range.

| Confidence Level | Expected Accuracy | Observed Accuracy | Calibrated? |
|------------------|-------------------|-------------------|-------------|
| High | >80% within range | | |
| Medium | 50-80% within range | | |
| Low | <50% within range | | |

### Template

| PRD | Metric | Confidence | Within Range? |
|-----|--------|------------|---------------|
| | | High/Med/Low | Yes/No |

### Analysis

```
After 20+ estimates per confidence level:

High confidence estimates within range: ___%
Medium confidence estimates within range: ___%
Low confidence estimates within range: ___%

If High < 80%: Agent is overconfident
If Low > 50%: Agent is underconfident
```

---

## Assumption Validation Tracking

### Template

| PRD | Assumption | Type | Confidence | Validated? | Outcome | Notes |
|-----|------------|------|------------|------------|---------|-------|
| | | Value/Exec | H/M/L | Yes/No/Partial | True/False/Nuanced | |

### Example

| PRD | Assumption | Type | Confidence | Validated? | Outcome | Notes |
|-----|------------|------|------------|------------|---------|-------|
| Finlex MCP | Users will trust free AI tool | Value | Medium | Yes | True | Trust built via citations |
| Finlex MCP | Finlex content sufficient | Exec | Medium | Partial | Nuanced | Gaps in collective agreements |
| Finlex MCP | €100-500 per-user value | Value | Low | No | Unknown | Hard to measure directly |

### Calibration Questions

1. What % of "High confidence" assumptions proved true?
2. What % of "Low confidence" assumptions were validated?
3. Are Value assumptions harder to validate than Execution?
4. Which assumption types are we systematically wrong about?

---

## Risk Prediction Accuracy

### Did flagged risks materialize?

| PRD | Risk Flagged | Severity | Occurred? | Impact | Notes |
|-----|--------------|----------|-----------|--------|-------|
| | | High/Med/Low | Yes/No | As expected / Worse / Less | |

### Calibration Questions

1. What % of High severity risks actually occurred?
2. Did we miss risks that materialized (false negatives)?
3. Did we flag risks that never happened (false positives)?

---

## Quarterly Calibration Review Template

```markdown
## Calibration Review Q[X] 20XX

### PRDs Analyzed: [N]

### Market Sizing
- Average SOM variance: ___%
- Systematic bias: [Over/Under/None]
- Recommendation: [Adjust by X% / No change]

### Workload Estimation
- T-shirt size accuracy: ___%
- Most underestimated component type: ___
- Recommendation: [Adjust size definitions / No change]

### Confidence Levels
- High confidence accuracy: ___%
- Medium confidence accuracy: ___%
- Low confidence accuracy: ___%
- Recommendation: [Recalibrate levels / No change]

### Assumptions
- Value assumption validation rate: ___%
- Execution assumption validation rate: ___%
- Hardest to validate: ___

### Actions for Next Quarter
1.
2.
3.
```
