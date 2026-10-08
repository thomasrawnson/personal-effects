---
name: case-design-validation
description: Review the correctness and difficulty of authored Personal Effects suitcase puzzles against the authoritative validator and observed player behaviour.
---

# Case Design and Validation
Use one schema and one authoritative legality evaluator. Before promoting a candidate case, verify ID, shapes, rotation, required versus optional belongings, weights, board bounds, constraints, condition text and narrative variants.

Check existence of legal solutions; report exact or bounded solution counts, cutoff and meaning of distinct arrangements. Reject invalid or impossible fixtures. Flag suspicious first-fit/greedy solutions, excess ambiguity and supposedly moral choices that have no viable alternative. Treat solver diagnostics as design evidence, not a quality score.

Capture candidate solution boards and explain what makes the constraint interaction novel. The human designer approves the case, its intended emotional choice and its place in difficulty progression. Measure actual first-solve time and confused/abandoned attempts with testers.

Output per case: validation result, solution-count method, flagged issues, intended competing outcomes, author review decision, playtest observations, and promotion status. Do not automatically publish generated cases.
