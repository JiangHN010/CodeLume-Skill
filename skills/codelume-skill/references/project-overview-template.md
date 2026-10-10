# Project Overview Section Contract

Use this contract for the opening architecture narrative and one vertical
runtime slice. Write connected prose in the student's language.

## Opening

Open with the verified problem and the pressure that makes it difficult. State
the project's central architectural response in plain language before naming
frameworks, patterns, packages, or language features.

Explain major boundaries through four questions: why the responsibility exists,
what state or invariant it owns, what it delegates, and how a neighboring part
observes its result. Package names are evidence for the explanation, not the
explanation itself.

## Concrete runtime slice

Choose one representative input, event, or state change and follow it across
the important boundaries. At each transition explain:

1. its concrete representation before the transition;
2. the decision or invariant that triggers the next step;
3. the representation or owned state after the transition;
4. the source symbol responsible; and
5. the observable result or relevant failure semantic.

Use short exact source excerpts only when syntax itself matters. Use explicit
pseudocode when teaching with a simplified representation.

## Completion criterion

The section is complete when a reader can explain the architectural thesis and
replay one real behavior through changing representations and owners. A list of
components or a call graph without causal transitions is incomplete.
