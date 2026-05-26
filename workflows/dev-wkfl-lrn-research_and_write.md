> [!important] THIS FILE IS AN INSTRUCTION. WHEN REFERENCED IT IS MEANT TO BE TAKEN AS AN ACTION.

This workflow belongs to the Learn shard. Ensure you have @init-lrn.md in context before continuing.

# Workflow: Research and Write

Complete workflow for creating a high-quality learning report from concept to publication.

# Input

- Concept to teach
- Target audience (their existing knowledge level)
- Optional: specific questions to answer

# Actions

## Stage 1: Research

1. Use web search to find authoritative sources on the concept
2. Read documentation, tutorials, and reference materials
3. Identify the core mental models needed to understand the concept
4. Collect specific examples from real-world usage
5. Note common misconceptions and mistakes
6. Gather links for "Further Reading" section

**Output:** Research notes with sources, examples, and key insights

## Stage 2: Outline

1. List prerequisites — what must the reader already know?
2. Break the concept into sub-concepts
3. Order sub-concepts causally: A must come before B if B depends on A
4. For each sub-concept, note what example will demonstrate it
5. Identify 2-3 worked examples that show end-to-end application

**Output:** Ordered outline with examples planned

## Stage 3: Draft

1. Create the learning report using @sk-lrn-create.md (make sure to find out the latest report number)
2. Write the Prerequisites section — be specific
3. Write the Summary — what will the reader learn?
4. Write "The Problem / Why This Matters" — motivation
5. For each Core Concept:
   - Write explanation in short, declarative sentences
   - Add extremely specific, runnable example
   - Annotate the example
6. Write Worked Examples section with full code
7. Write Common Mistakes section
8. Add Further Reading links with descriptions
9. Add References to sources used

**Output:** Complete draft learning report

## Stage 4: Review

Check the draft against these criteria:

- [ ] Every concept is explained before it's used
- [ ] No sentences require knowledge not yet introduced
- [ ] Every abstraction has at least one specific example
- [ ] Examples are real and runnable (not pseudo-code)
- [ ] Common mistakes section has at least 1 entry
- [ ] Further reading has 2+ links with descriptions
- [ ] Prerequisites are specific, not vague

Fix any issues found.

## Stage 5: Publish

1. Update status from `draft` to `active`
2. Add to `(Dashboard) Learn.md` if it exists
3. Link from related documents if applicable

# Output

- Published learning report with status `active`
- Indexed in dashboard
- Ready for readers
