# PM-tools

Reusable LLM workflows and agent patterns for product management. Each tool is self-contained with its own prompt templates, workflow definitions, and usage guide.

## Tools

### Discovery & Research

| Tool | Description | Author | License |
|------|-------------|--------|---------|
| [`prompts/user-interview/`](prompts/user-interview/) | Prepare and conduct user interviews that extract truth, not validation (Mom Test) | [assimovt](https://github.com/assimovt) | MIT |
| [`prompts/problem-validation/`](prompts/problem-validation/) | Validate whether a problem is worth solving before building anything | [assimovt](https://github.com/assimovt) | MIT |
| [`prompts/jtbd-analysis/`](prompts/jtbd-analysis/) | Analyze customer motivations using Jobs-to-be-Done and Forces of Progress | [assimovt](https://github.com/assimovt) | MIT |
| [`prompts/research-synthesis/`](prompts/research-synthesis/) | Synthesize user research into actionable insights using atomic research methods | [assimovt](https://github.com/assimovt) | MIT |
| [`prompts/opportunity-mapping/`](prompts/opportunity-mapping/) | Map opportunities using Teresa Torres' Opportunity Solution Trees | [assimovt](https://github.com/assimovt) | MIT |

### Strategy & Positioning

| Tool | Description | Author | License |
|------|-------------|--------|---------|
| [`prompts/competitor-analysis/`](prompts/competitor-analysis/) | Analyze competitive landscape with feature matrices, positioning maps, and strategic gap analysis | [assimovt](https://github.com/assimovt) | MIT |
| [`prompts/product-positioning/`](prompts/product-positioning/) | Position a product using April Dunford's Obviously Awesome framework | [assimovt](https://github.com/assimovt) | MIT |
| [`templates/strategy-doc/`](templates/strategy-doc/) | Write product strategy documents with real tradeoffs and clear choices | [assimovt](https://github.com/assimovt) | MIT |

### Prioritization & Scoping

| Tool | Description | Author | License |
|------|-------------|--------|---------|
| [`prompts/feature-prioritization/`](prompts/feature-prioritization/) | Prioritize features and backlog items using RICE scoring | [assimovt](https://github.com/assimovt) | MIT |
| [`prompts/scope-cutting/`](prompts/scope-cutting/) | Cut scope ruthlessly using Shape Up's appetite-first approach | [assimovt](https://github.com/assimovt) | MIT |
| [`prompts/bet-sizing/`](prompts/bet-sizing/) | Evaluate product bets using Shape Up's appetite model and Bezos's Type 1/Type 2 framework | [assimovt](https://github.com/assimovt) | MIT |

### PRD Writing

| Tool | Description | Author | License |
|------|-------------|--------|---------|
| [`prompts/prd-writing/`](prompts/prd-writing/) | Write structured, opinionated PRDs that engineers actually read | [assimovt](https://github.com/assimovt) | MIT |
| [`prompts/prd-from-idea/`](prompts/prd_from_idea_prompt.md) | Multi-round prompt that turns a raw product idea into a structured PRD | Lauri Saviranta | MIT |
| [`templates/prd-template/`](templates/prd_template.md) | Skeleton PRD document with section guidance | Lauri Saviranta | MIT |
| [`workflows/single-agent-prd/`](workflows/single_agent_prd_state_machine.md) | State machine for agentic PRD generation — states, transitions, review gates | Lauri Saviranta | MIT |

### Launch & Measure

| Tool | Description | Author | License |
|------|-------------|--------|---------|
| [`checklists/launch-plan/`](checklists/launch-plan/) | Plan product launches with the right tier and coordinated checklists | [assimovt](https://github.com/assimovt) | MIT |
| [`templates/metrics-framework/`](templates/metrics-framework/) | Define product metrics with a North Star, input/output tree, and counter-metrics | [assimovt](https://github.com/assimovt) | MIT |
| [`prompts/experiment-design/`](prompts/experiment-design/) | Design hypothesis-driven experiments and A/B tests with proper methodology | [assimovt](https://github.com/assimovt) | MIT |
| [`workflows/roadmap-planning/`](workflows/roadmap-planning/) | Create outcome-based roadmaps using Now/Next/Later | [assimovt](https://github.com/assimovt) | MIT |

### Evaluation

| Tool | Description | Author | License |
|------|-------------|--------|---------|
| [`evals/`](evals/) | Evaluation framework: golden set rubric, trace schema, red-team scenarios, calibration tracker, automated checks | Lauri Saviranta | MIT |
| [`evals/eval-audit/`](evals/eval-audit/) etc. | Claude Code eval skills — audit, error analysis, synthetic data generation, LLM-as-Judge, RAG evaluation, annotation UI | [Hamel Husain](https://github.com/hamelsmu) | MIT |

## Structure

\`\`\`
pm-tools/
├── evals/               # LLM output evaluation framework + eval skills (hamelsmu/evals-skills)
├── prompts/             # Standalone prompt templates
├── templates/           # Document skeletons
├── workflows/           # Multi-step agent workflows and state machines
├── checklists/          # Process checklists
├── playbooks/           # End-to-end playbooks combining multiple tools
└── examples/            # Worked examples
\`\`\`

## Usage

Each tool folder contains a \`README.md\` with:
- What the tool does and when to use it
- Inputs required and outputs produced
- How to adapt it to your context

Tools are designed to work with Claude (via Claude Code or the API) but the patterns are model-agnostic where noted.

## Credits

| Contributor | Contribution | Link |
|-------------|-------------|------|
| Lauri Saviranta | Author — PM-tools evals framework, PRD workflows, prompts and templates | [github.com/saviranta](https://github.com/saviranta) |
| assimovt | Discovery, Strategy, Prioritization, PRD Writing, and Launch & Measure skills | [github.com/assimovt](https://github.com/assimovt) · [assimovt/productskills](https://github.com/assimovt/productskills) |
| Hamel Husain | Eval skills for Claude Code (\`evals/eval-audit/\` etc.) | [github.com/hamelsmu](https://github.com/hamelsmu) · [hamelsmu/evals-skills](https://github.com/hamelsmu/evals-skills) |

Third-party content is used under its original license. See [\`LICENSE\`](LICENSE) and [\`LICENSE-productskills\`](LICENSE-productskills) for full license texts.

## Related

- [job-tools](https://github.com/saviranta/job-tools) — Tools for job search and applications
- [claude-code-tools](https://github.com/saviranta/claude-code-tools) — Claude Code–specific workflows and configurations
