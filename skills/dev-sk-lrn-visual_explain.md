This skill belongs to the Learn shard. Ensure you have @init-lrn.md in context before continuing.

# Skill: Visual Explain

Generate a visual explainer for a concept as a markdown document that renders richly in Obsidian. The output uses Mermaid diagrams, callouts, tables, and structured layout to teach visually rather than through prose.

This is a complement to Learning Reports — use it when a concept is better shown than told (architectures, data flows, state machines, pipelines, relationships, comparisons).

# Input

- Concept to explain visually
- (Optional) Target audience
- (Optional) Existing Learning Report to create a visual companion for

# Actions

## 1. Choose Rendering Approaches

Pick rendering methods based on what you're explaining. Most concepts need **multiple** diagram types to cover different facets — a single diagram is rarely enough.

| Content Type | Method | When to Use |
|-------------|--------|-------------|
| Topology / connections | Mermaid `flowchart` | Systems with components that connect to each other |
| Sequence / protocols | Mermaid `sequenceDiagram` | Request flows, handshakes, multi-step interactions |
| State machines | Mermaid `stateDiagram-v2` | Lifecycle, status transitions |
| Data flow / pipelines | Mermaid `flowchart LR` | Input → transform → output chains |
| Entity relationships | Mermaid `erDiagram` | Data models, schema relationships |
| Class / type hierarchy | Mermaid `classDiagram` | Inheritance, interfaces, composition |
| Timelines / history | Mermaid `timeline` | Chronological events |
| Mind map / taxonomy | Mermaid `mindmap` | Hierarchical categorization |
| Comparisons | Markdown tables | Feature matrices, option evaluation |
| Layered architecture | Stacked callouts | Layers that sit on top of each other |
| Decision logic | Mermaid `flowchart TD` | If/else trees, routing logic |

Plan **4-8 diagrams** across the document. Each major section should have its own visual. Combine methods freely — a sequence diagram for the happy path, a state diagram for the lifecycle, a flowchart for decision logic, and tables for comparisons all belong in the same guide.

## 2. Structure the Document

Every visual explainer follows this structure. The document should be **substantial** — treat it as a complete visual reference, not a quick sketch.

```
Title (# Concept Name — Visual Guide)
├── Overview callout (> [!abstract]) — 2-3 sentence summary
├── The Happy Path / Overview
│   ├── Primary diagram showing the normal/expected flow
│   ├── Walkthrough prose narrating the diagram (1-2 paragraphs)
│   └── Supporting callout or table with key details
├── Core Mechanism sections (2-4 sections, each with its own diagram)
│   ├── Diagram showing this facet of the concept
│   ├── Walkthrough — explain what the diagram shows and why it matters
│   ├── Numbered step-by-step breakdown where applicable
│   ├── Code examples in [!example] callouts where relevant
│   └── Gotchas in [!warning] callouts
├── Practical Concerns (1-2 sections)
│   ├── Decision flowcharts for "when to use what"
│   ├── Comparison tables against alternatives
│   └── Real-world scenarios with annotated diagrams
├── Key Takeaways callout (> [!tip]) — 5-7 bullet points
└── See Also — links to related artifacts and external resources
```

### Depth Guidelines

A visual explainer is a **complete visual reference** for the concept. It should be the document someone bookmarks and returns to.

- **Minimum 4 diagrams**, ideally 6-8. Each should show a different aspect of the concept — not the same thing from slightly different angles.
- **Every diagram gets a walkthrough.** 1-2 paragraphs of prose that narrate what the diagram shows. Don't just repeat the node labels — explain the *why* behind the structure. Call out the non-obvious parts.
- **Include code examples** in `[!example]` callouts wherever the concept has a programmatic interface. Show complete, working code — not snippets. If there are multiple approaches, show both with a comparison table.
- **Include real-world scenarios.** At least one sequence diagram or flowchart should show the concept playing out in a realistic setting (e.g., what happens when things go wrong, edge cases, failure modes).
- **Include a comparison section** if alternatives exist. Use a table with 5+ comparison dimensions, plus a decision flowchart for "when to use what."
- **Warnings and gotchas are first-class content.** Use `[!warning]` callouts for common mistakes, subtle failure modes, and operational concerns. These are often the most valuable part of the guide.

## 3. Write the Diagrams

### Mermaid Rules

- Keep node labels short (2-4 words). Use the walkthrough prose to elaborate.
- Use subgraphs to group related nodes. Label the subgraph clearly.
- For complex diagrams (10+ nodes), split into an overview diagram and detail diagrams rather than one massive graph.
- Use consistent node shapes: `[rectangles]` for processes, `([rounded])` for start/end, `{diamonds}` for decisions, `[(databases)]` for storage, `((circles))` for events.
- Add link labels for non-obvious relationships: `A -->|transforms| B`
- Prefer `TD` (top-down) for hierarchies and state machines. Prefer `LR` (left-right) for pipelines and sequences.
- Use `rect` blocks in sequence diagrams to highlight important phases.
- Use `note over` in sequence diagrams to annotate what's happening at each step.

### Table Rules

- Use tables for structured comparisons, not for layout.
- Bold the distinguishing column values.
- Keep tables under 6 columns — split into multiple tables if wider.
- Aim for 5+ rows in comparison tables — shallow comparisons don't teach anything.

### Callout Rules

Obsidian callouts for semantic framing:

- `> [!abstract]` — Overview / summary at the top
- `> [!tip]` — Key takeaways, best practices
- `> [!warning]` — Gotchas, common mistakes, operational concerns
- `> [!info]` — Context, background, definitions
- `> [!example]` — Concrete examples with complete, working code

Use callouts generously — they break up the document visually and draw attention to important details. Aim for at least 5-6 callouts across the document.

### Code Example Rules

- Code examples go inside `[!example]` callouts with a descriptive title.
- Show **complete, working implementations** — not fragments. The reader should be able to copy-paste and run.
- If there are two approaches to the same thing, show both with distinct examples and explain the tradeoff.
- Annotate code with inline comments for non-obvious lines.

## 4. Create the File

1. Get the next number: `flint helper type newnumber "Learning Report"`
2. Create at `Mesh/Types/Learn/(Learning Report) XXX [Concept Name] — Visual Guide.md`
3. Use this frontmatter:

```yaml
---
id: [generate-uuid]
tags:
  - "#lrn/learning_report"
  - "#lrn/visual"
status: active
date-created: [YYYY-MM-DD]
template: "[[dev-tmp-lrn-learning_report-v0.1]]"
authors:
  - "[[@Person Name]]"
---
```

4. If this is a companion to an existing Learning Report, add a wikilink cross-reference in both documents under their "References" sections.

## 5. Quality Check

Before finishing, verify:

- [ ] At least 4 Mermaid diagrams, each showing a different facet of the concept
- [ ] Every diagram has a walkthrough — 1-2 paragraphs of narration, not just labels repeated
- [ ] At least one complete, working code example (if the concept has a programmatic interface)
- [ ] At least one comparison table with 5+ dimensions (if alternatives exist)
- [ ] At least one `[!warning]` callout covering a non-obvious gotcha or failure mode
- [ ] Key Takeaways section has 5-7 concrete, actionable points
- [ ] The document is a complete visual reference — someone could learn the concept from this alone
- [ ] Every diagram renders in Obsidian (valid Mermaid syntax)
- [ ] No diagram exceeds ~15 nodes without being split

# Output

- A substantial visual explainer Learning Report in the Mesh
- Renders richly in Obsidian with diagrams, callouts, tables, and code examples
- Complete enough to serve as a standalone reference for the concept
