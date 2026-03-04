# Evals

Evaluation resources for PM-tools workflows.

## Folder Structure

| Path | Purpose |
|------|---------|
| `trace_schema.md` | What to capture during execution |
| `automated_checks.md` | Pass/fail checks run on every PRD |
| `golden_set_rubric.md` | Manual scoring rubric for quality |
| `user_feedback_template.md` | Post-session survey questions |
| `calibration_tracker.md` | Template for tracking estimate accuracy |
| `red_team_scenarios.md` | Adversarial test cases |
| `skills/` | Claude Code eval skills (see below) |

## Quick Start

1. **Every run:** Capture traces per `trace_schema.md`
2. **Every run:** Run checks from `automated_checks.md`
3. **Periodically:** Score against golden set using `golden_set_rubric.md`
4. **Post-session:** Collect feedback via `user_feedback_template.md`
5. **Quarterly:** Update `calibration_tracker.md` with actuals vs. estimates

## Eval Skills (Claude Code)

The `skills/` folder contains Claude Code skills adapted from [hamelsmu/evals-skills](https://github.com/hamelsmu/evals-skills) by Hamel Husain (MIT License). These guide an AI coding agent through common eval tasks.

| Skill | What it does |
|-------|-------------|
| `eval-audit` | Audit an eval pipeline and surface problems with prioritized severity — **start here if new to evals** |
| `error-analysis` | Guide through reading traces and categorizing failures |
| `generate-synthetic-data` | Create diverse synthetic test inputs using dimension-based tuple generation |
| `write-judge-prompt` | Design LLM-as-Judge evaluators for subjective quality criteria |
| `validate-evaluator` | Calibrate LLM judges against human labels using data splits, TPR/TNR, and bias correction |
| `evaluate-rag` | Evaluate retrieval and generation quality in RAG pipelines |
| `build-review-interface` | Build custom annotation interfaces for human trace review |

### Attribution

Skills in `skills/` are copied from [hamelsmu/evals-skills](https://github.com/hamelsmu/evals-skills) and are used under the MIT License. See `skills/LICENSE` for the full license text. Original author: Hamel Husain.
