# PRD State Machine Evals

Evaluation framework for the `single_agent_prd_state_machine` workflow.

## Overview

| Category | Purpose | Frequency |
|----------|---------|-----------|
| Traces | Debug, improve, understand behavior | Every run |
| Automated Evals | Structural correctness | Every run |
| Golden Set Evals | Quality benchmarking | Weekly/monthly |
| User Feedback | Satisfaction & usefulness | Post-session |
| Calibration Evals | Accuracy over time | Quarterly |
| Red Team Evals | Adversarial robustness | Before release |

## Files in This Folder

| File | Purpose |
|------|---------|
| `trace_schema.md` | What to capture during execution |
| `automated_checks.md` | Pass/fail checks run on every PRD |
| `golden_set_rubric.md` | Manual scoring rubric for quality |
| `user_feedback_template.md` | Post-session survey questions |
| `calibration_tracker.md` | Template for tracking estimate accuracy |
| `red_team_scenarios.md` | Adversarial test cases |

## Quick Start

1. **Every run:** Capture traces per `trace_schema.md`
2. **Every run:** Run checks from `automated_checks.md`
3. **Periodically:** Score against golden set using `golden_set_rubric.md`
4. **Post-session:** Collect feedback via `user_feedback_template.md`
5. **Quarterly:** Update `calibration_tracker.md` with actuals vs. estimates
