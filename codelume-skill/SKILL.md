---
name: codelume-skill
description: Use when there is even a 1% chance that a student's task involves learning, understanding, or studying source code at any scope, including a repository's architecture, end-to-end runtime flows, modules, components, functions, or implementation details.
---

# CodeLume-Skill

## Overview

Treat source code as a record of design decisions. The saved artifact is a source-learning textbook about the project's problem, architecture, mechanisms, and tradeoffs.

**Core principle:** Every architectural role and runtime transition must trace to source, configuration, a test, or a command result. Keep uncertainty visible.

## When to Use

Choose the smallest useful mode: explain one symbol, trace one flow, study one module, map a repository, or refresh an existing guide. Answer narrow questions directly; save Markdown when requested or when the scope spans multiple files.

## Workflow

1. **Ground the task.** Identify the root, design question, scope, and artifact; read repository instructions and preserve existing changes. Write for programmers across experience levels and language backgrounds unless a narrower audience is requested.
2. **Map before tracing.** Inspect manifests, documentation, configuration, entry points, tests, and module boundaries. Names remain clues until callers and responsibilities confirm them. For unfamiliar or cross-module repositories, read [references/analysis-playbook.md](references/analysis-playbook.md).
3. **Recover the design.** Find the responsibilities, invariants, boundaries, implementation selection, state ownership, failure isolation, and constraints. Trace one vertical slice to prove their runtime effect.
4. **Teach causally.** Before drafting a major principle, privately fill eight slots: pressure, plausible simple approach, concrete failure, reasoning path, source mechanism, benefit, cost, and boundary. Omit or defer a principle when the evidence cannot fill every slot. Prefer a few complete lessons over broad summaries.
5. **Draft by section.** For saved textbooks, use [references/learning-document-template.md](references/learning-document-template.md) as a router and load only the section contract currently being written. Use [references/visual-learning-assets.md](references/visual-learning-assets.md) when relationships, state, or transformations may need a visual. Verify source links and code classifications before delivery.

## Textbook Completion Standard

The textbook is complete only when all of these conditions hold:

- The reader-facing content stays focused on the current project's design and implementation, without production notes or unrelated tasks.
- A reader unfamiliar with the project or its programming language can understand the problem it solves, the overall architecture, the main responsibility boundaries, and one complete runtime flow.
- Every selected design explains the pressure, limitation of a plausible simple approach, reasoning path, actual source mechanism, benefit, cost, and applicability boundary.
- A key runtime flow can be followed through a real input, calls, state changes, and observable result in the source.
- Specialized terms are explained on first use; examples or visuals clarify complex relationships only when they materially improve understanding.
- Direct source facts link to evidence without labels; only inference, unknowns, and suggestions receive explicit labels.
- Teaching rewrites are marked as pseudocode, and source excerpts match the current checkout.
- Every source link, relative path, and image asset resolves correctly.
