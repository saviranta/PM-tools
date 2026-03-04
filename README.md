# PM-tools

Reusable LLM workflows and agent patterns for product management. Each tool is self-contained with its own prompt templates, workflow definitions, and usage guide.

## Tools

| Tool | Description | Author | License |
|------|-------------|--------|---------|
| [`evals/`](evals/) | Evaluation framework: golden set rubric, trace schema, red-team scenarios, calibration tracker, automated checks | Lauri Saviranta | MIT |
| [`evals/skills/`](evals/skills/) | Claude Code eval skills — audit, error analysis, synthetic data generation, LLM-as-Judge, RAG evaluation, annotation UI | [Hamel Husain](https://github.com/hamelsmu) | MIT |
| [`workflows/`](workflows/) | State machine for agentic PRD generation — states, transitions, review gates | Lauri Saviranta | MIT |
| [`prompts/`](prompts/) | Standalone prompt templates (e.g. PRD from idea) | Lauri Saviranta | MIT |
| [`templates/`](templates/) | Document skeletons with section guidance | Lauri Saviranta | MIT |

## Structure

```
pm-tools/
├── evals/               # LLM output evaluation framework
│   └── skills/          # Claude Code eval skills (hamelsmu/evals-skills)
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

## Credits

| Contributor | Contribution | Link |
|-------------|-------------|------|
| Lauri Saviranta | Author — PM-tools workflows, evals framework, prompts and templates | [github.com/saviranta](https://github.com/saviranta) |
| Hamel Husain | Eval skills for Claude Code (`evals/skills/`) | [github.com/hamelsmu](https://github.com/hamelsmu) · [hamelsmu/evals-skills](https://github.com/hamelsmu/evals-skills) |

Third-party content is used under its original license. See [`LICENSE`](LICENSE) for full license texts.

## Related

- [job-tools](https://github.com/saviranta/job-tools) — Tools for job search and applications
- [claude-code-tools](https://github.com/saviranta/claude-code-tools) — Claude Code–specific workflows and configurations
