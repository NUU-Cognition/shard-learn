# Learn Shard

Create pedagogically optimized educational content that teaches humans specific concepts.

## Philosophy

A learning report is not a summary — it is a teaching artifact. Every sentence must earn its place by advancing the reader's understanding. The goal is transfer: after reading, the learner can independently apply the concept.

### Core Principles

1. **Self-contained** — No assumed knowledge beyond stated prerequisites
2. **Directly causal** — Each sentence logically follows from the previous; no jumps
3. **Research-backed** — Concepts verified through research, linked to authoritative sources
4. **Example-rich** — Every abstraction demonstrated with extremely specific, concrete examples
5. **Resource-linked** — Further reading provided for deeper exploration

### Writing Guidelines

- **Sentences:** Short, declarative. One piece of information per sentence.
- **Examples:** Real code, real file paths, real commands that actually run.
- **Progression:** A → B → C. Never reference B before explaining A.
- **Comparisons:** "X is like Y, except Z" to connect to known concepts.
- **Anti-examples:** Show what NOT to do, and explain why it fails.

## How It Works

```
Prerequisites → Core Concepts (with examples) → Worked Examples → Common Mistakes → Further Reading
```

Each learning report follows a strict structure that builds understanding incrementally. The reader never encounters a term or concept that hasn't been explained.

## Lifecycle

| Status | Meaning |
|--------|---------|
| `draft` | Being written, not ready for review |
| `active` | Published, available for learning |
| `archived` | Outdated or superseded |

## Dashboards

| Dashboard | Purpose |
|-----------|---------|
| `(Dashboard) Learn.md` | Index of all learning reports |

## Templates

| Template | File | Purpose |
|----------|------|---------|
| Learning Report | `dev-tmp-lrn-learning_report.md` | Full educational document |

## Skills

| Skill | File | Purpose |
|-------|------|---------|
| Create | `dev-sk-lrn-create.md` | Create a new learning report |
| Visual Explain | `dev-sk-lrn-visual_explain.md` | Generate a visual explainer using Mermaid diagrams, callouts, and tables |

## Workflows

| Workflow | File | Purpose |
|----------|------|---------|
| Research and Write | `dev-wkfl-lrn-research_and_write.md` | Full creation workflow with research phase |

## Quality Checklist

Before marking a learning report as `active`:

- [ ] Prerequisites are explicitly stated
- [ ] Every concept is explained before it's used
- [ ] Every abstraction has at least one specific example
- [ ] Examples use real, runnable code/commands
- [ ] Further reading links are provided and described
- [ ] Common mistakes section exists
