# PM-tools

Reusable LLM workflows and agent patterns for product management. Each tool is self-contained with its own prompt templates, workflow definitions, and usage guide.

## Tools

| Tool | Description |
|------|-------------|
| [`evals/`](evals/) | Evaluation framework for LLM outputs: golden set rubric, trace schema, red-team scenarios, calibration tracker, automated checks, and Claude Code eval skills |
| [`workflows/single-agent-prd/`](workflows/) | State machine for agentic PRD generation — states, transitions, review gates |
| [`prompts/prd-from-idea/`](prompts/) | Prompt that turns a raw product idea into a structured PRD |
| [`templates/prd-template/`](templates/) | Skeleton PRD document with section guidance |

## Structure

```
pm-tools/
├── evals/               # LLM output evaluation framework + eval skills
├── prompts/             # Standalone prompt templates
├── templates/           # Document skeletons
├── workflows/           # Multi-step agent workflows and state machines
├── checklists/          # Process checklists
├── playbooks/           # End-to-end playbooks combining multiple tools
└── examples/            # Worked examples
```

## Usage

Each tool folder contains a `README.md` with:
- What the tool does and when to use it
- Inputs required and outputs produced
- How to adapt it to your context

Tools are designed to work with Claude (via Claude Code or the API) but the patterns are model-agnostic where noted.

## Third-Party Attributions

The `evals/skills/` folder contains Claude Code eval skills copied from [hamelsmu/evals-skills](https://github.com/hamelsmu/evals-skills) by Hamel Husain, used under the MIT License. See [`evals/skills/LICENSE`](evals/skills/LICENSE).

## Related

- [job-tools](https://github.com/saviranta/job-tools) — Tools for job search and applications
- [claude-code-tools](https://github.com/saviranta/claude-code-tools) — Claude Code–specific workflows and configurations
