# Product Dev Pipeline

A Claude Code plugin providing an end-to-end product development pipeline with specialized agents.

## Agents

| Agent | Role |
|-------|------|
| **product-planner** | Transforms feature ideas into ambitious product specs with user stories, phased rollouts, and sprint-ready epics |
| **sprint-generator** | Implements specs in disciplined sprints with git workflow, self-evaluation, and QA handoff |
| **design-evaluator** | Evaluates UI/UX quality of generated changes (scores Design Quality, Originality, Craft, Functionality) |
| **code-design-evaluator** | Evaluates code quality against SOLID principles (6 dimensions, 120-point scale) |

## Pipeline Flow

```
product-planner → sprint-generator → design-evaluator + code-design-evaluator
     (spec)         (implement)            (QA gate)
```

1. **Product Planner** produces the spec with user stories and sprint groupings
2. **Sprint Generator** implements in organized sprints, writes output to `.generator/`
3. **Design Evaluator** scores UI changes (pass threshold: 7.0/10)
4. **Code Design Evaluator** scores code quality (pass threshold: 70/120)

## Installation

**Option 1: Load for one session**
```bash
claude --plugin-dir /path/to/my-claude-setup
```

**Option 2: Install permanently**
1. Run `/plugin` in Claude Code
2. Go to **Marketplaces** tab → add the local path or GitHub repo
3. Go to **Discover** tab → install `product-dev-pipeline`
4. Choose **User scope** for availability across all projects

## Usage

Once installed, the agents are automatically available in any Claude Code session:

- Describe a feature idea → **product-planner** activates
- Provide a spec to implement → **sprint-generator** activates
- After UI changes → **design-evaluator** runs QA
- After code changes → **code-design-evaluator** runs QA

## License

MIT
