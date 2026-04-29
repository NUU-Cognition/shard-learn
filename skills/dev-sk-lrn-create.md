This skill belongs to the Learn shard. Ensure you have @init-lrn.md in context before continuing.

# Skill: Create Learning Report

Create a new learning report for a specific concept.

# Input

- Concept to teach
- Target audience (what they already know)

# Actions

1. Determine the concept name and create a descriptive title
2. Identify prerequisites — what must the reader already understand?
3. Get the next number with `flint helper type newnumber "Learning Report"`
4. Create the file using @tmp-lrn-learning_report.md template at `Mesh/Types/Learn/(Learning Report) XXX [Concept Name].md`
5. Set status to `draft`
6. Fill in Summary and Prerequisites sections
7. Outline the Core Concepts in causal order (A → B → C)

# Output

- New learning report file in draft status
- Ready for the research and write workflow
