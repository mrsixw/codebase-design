---
name: codebase-design
description: Design or improve module interfaces, seams, and testability using deep-module principles and a small public surface.
---

# Codebase design

Design the smallest boundary that lets callers know less. Treat deep modules as
a useful test of a design, not a universal architecture prescription. Use this
skill for one named responsibility, interface, or seam; use
`improve-codebase-architecture` for a repository-wide survey.

## Start from the as-built system

Map the current callers, ownership, data flow, side effects, failure paths, and
test seams. Use the code and configuration as evidence; distinguish the current
design from documentation and from the proposed change.

Identify the responsibility that needs a home, then compare the current shape
with at least one simpler option. Assess each option against:

- the amount of knowledge exposed to callers;
- dependency direction and lifecycle ownership;
- locality of change and failure handling;
- observability and the highest useful test seam;
- migration cost and operational effect; and
- whether the variation exists now or is only hypothetical.

Prefer a small stable interface that hides substantial policy or mechanism.
Accept dependencies when the caller owns their lifecycle. Prefer explicit
results over invisible side effects. Remove pass-through layers when they add no
policy, isolation, or useful seam.

Record the recommendation, evidence, rejected alternatives, trade-offs, and a
proportionate validation approach. Do not impose a framework, create speculative
abstractions, or include unrelated refactoring. This skill produces the design;
it does not modify production code. Treat a later implementation request as
separate work with its own validation.
