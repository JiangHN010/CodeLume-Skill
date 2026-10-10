# Complex Module Section Contract

Use a full module section only when its internal design materially teaches the
project. A module qualifies when it contains at least one non-obvious mechanism:
state or lifecycle transitions, ordering or concurrency, a multi-party boundary,
substantial data transformation, algorithm/strategy selection, or deliberate
failure isolation.

Explain a simple wrapper, manifest, registry, value type, or one-way adapter in
the overview or a compact module map unless it contains such a mechanism.

## Reader-facing section

Explain:

1. the architectural pressure the module absorbs and why the responsibility is
   separate;
2. its public boundary, owned state or invariant, and delegated work;
3. one concrete input or state change through its important decisions;
4. the alternatives the project avoided and the consequences of the choice;
5. its cost, failure boundary, and the condition where the module would be
   unnecessary.

Read [visual-learning-assets.md](visual-learning-assets.md) only if prose hides
the mechanism. The module does not earn a diagram merely because it exists.

## Completion criterion

The section teaches why the module has its current shape and how its mechanism
works. If it only inventories exports, dependencies, or responsibilities,
replace it with a brief source-linked paragraph.
