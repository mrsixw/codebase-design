---
name: codebase-design
description: Design or improve module interfaces, seams, and testability using deep-module principles and a small public surface.
---

# Codebase Design

Use this vocabulary when deciding where behavior belongs or how a change should cross a module boundary.

## Principles

- A deep module hides substantial behavior behind a small interface.
- The interface is the shared seam used by callers and tests.
- Accept dependencies instead of creating them inside the module.
- Prefer returned results over hidden side effects.
- Add a seam when variation is real, not for a hypothetical future.
- Delete pass-through modules rather than layering more delegation.

## Workflow

1. Map the current callers, responsibilities, and data flow.
2. Identify the proposed interface and the highest useful test seam.
3. Compare the design against simpler alternatives.
4. Check locality, dependency direction, and whether the interface hides complexity.
5. Record the chosen design and rejected alternatives when the trade-off matters.

Do not refactor unrelated code or impose a framework-specific architecture without evidence.
