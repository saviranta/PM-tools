# Trace Schema for PRD State Machine

Capture these traces during every PRD generation session.

## Session Metadata

```yaml
session_id: <unique_id>
timestamp_start: <ISO8601>
timestamp_end: <ISO8601>
total_duration_minutes: <number>
total_turns: <number>
total_tokens_in: <number>
total_tokens_out: <number>
context_files_provided:
  company_strategy: <true/false>
  current_product_description: <true/false>
completion_status: <completed/abandoned/error>
abandonment_state: <state_name if abandoned>
```

## State-Level Traces

Capture for each state (INIT, 0, 1, 2, 3, 4, 5, 6):

```yaml
state: <STATE_NAME>
entry_timestamp: <ISO8601>
exit_timestamp: <ISO8601>
duration_minutes: <number>
turns_in_state: <number>
tokens_in_state: <number>

questions_asked:
  - question: <text>
    answered: <true/false>
    clarification_rounds: <number>

exit_condition_met: <true/false>
exit_trigger: <what satisfied the exit condition>

forbidden_output_attempted: <true/false>
forbidden_output_type: <if attempted, what was it>
```

## Content Traces (STATE 2 - Value & Outcomes)

```yaml
market_sizing:
  som_estimate: <range>
  som_confidence: <High/Medium/Low>
  user_volume_estimate: <range>
  user_volume_confidence: <High/Medium/Low>
  frequency_estimate: <text>
  frequency_confidence: <High/Medium/Low>
  problem_value_eur: <range>
  problem_value_confidence: <High/Medium/Low>
  total_market_value_eur: <range>

strategic_fit: # if context provided
  alignment_score: <Strong/Moderate/Weak/Misaligned>
  misalignments_flagged: <number>
  user_proceeded_despite_misalignment: <true/false>

portfolio_fit: # if context provided
  fit_type: <Complementary/Adjacent/New Territory>
  cannibalization_risk: <High/Medium/Low/None>
  integration_opportunities: <number>
```

## Content Traces (STATE 3 - Scope & Journeys)

```yaml
scope:
  non_goals_count: <number>
  tradeoffs_count: <number>
  user_journeys_count: <number>
  must_win_journey: <text>

workload_estimation:
  total_items: <number>
  xs_count: <number>
  s_count: <number>
  m_count: <number>
  l_count: <number>
  xl_count: <number>
  user_adjusted_estimates: <true/false>
```

## Content Traces (STATE 5 - Assumptions)

```yaml
assumptions:
  value_assumptions_count: <number>
  execution_assumptions_count: <number>
  high_confidence_count: <number>
  medium_confidence_count: <number>
  low_confidence_count: <number>
  validation_methods_specified: <number>
```

## Evidence Traces

```yaml
evidence_labels:
  strong_evidence_claims: <number>
  weak_evidence_claims: <number>
  no_evidence_claims: <number>
  assumption_claims: <number>
```

## Failure Traces

```yaml
failures:
  state_skip_attempts: <number>
  state_skip_states: [<list of states user tried to skip>]
  clarification_loops_over_2: <number>
  user_frustration_signals: <number>  # e.g., "just give me the PRD"
  agent_declined_to_answer: <number>
  error_occurrences: <number>
```

## Example Trace Output

```yaml
session_id: prd-2026-01-27-001
timestamp_start: 2026-01-27T14:00:00Z
timestamp_end: 2026-01-27T15:23:00Z
total_duration_minutes: 83
total_turns: 24
context_files_provided:
  company_strategy: false
  current_product_description: false
completion_status: completed

states:
  - state: INIT
    duration_minutes: 2
    turns_in_state: 2
    exit_trigger: "user said skip"

  - state: STATE_0_IDEA_INGESTION
    duration_minutes: 8
    turns_in_state: 4
    questions_asked:
      - question: "Who is the primary user?"
        answered: true
        clarification_rounds: 1
    exit_trigger: "user confirmed interpretation"

  # ... remaining states ...

market_sizing:
  som_estimate: "20K-50K"
  som_confidence: Low
  problem_value_eur: "€2M-25M"
  problem_value_confidence: Low

assumptions:
  value_assumptions_count: 7
  execution_assumptions_count: 6
  low_confidence_count: 5

failures:
  state_skip_attempts: 0
  clarification_loops_over_2: 1
```
