# Design Principle Section Contract

Use this contract separately for each principle that materially shapes the
project. Select fewer principles when the evidence or available depth is weak.

## Private causal brief

Before writing reader-facing prose, privately fill every slot:

- **Pressure:** verified constraint or recurring problem.
- **Simple approach:** a plausible implementation a competent developer might
  choose first.
- **Concrete failure:** one input, event, scale, change, or recovery scenario
  where that approach becomes incorrect, costly, rigid, or opaque.
- **Reasoning path:** why the failure points toward the project's boundary or
  mechanism rather than merely away from the simple approach.
- **Source mechanism:** starting state, decisions, calls, state/data changes,
  and observable result, linked to exact symbols.
- **Benefit:** behavior made possible or risk reduced.
- **Cost:** complexity, latency, state, coupling, or operational burden added.
- **Boundary:** conditions where the simpler alternative is better.

Do not include the principle when these slots cannot be supported. Mark a
historical motivation reconstructed from current code as `[INFERRED]`.

## Reader-facing lesson

Turn the brief into connected teaching prose:

1. Establish the pressure and plausible simple approach.
2. Walk through the concrete failure so the consequence is visible.
3. Derive the project's response, explaining why each design step follows.
4. Trace the response through actual source and one concrete state or input.
5. Compare behavior before and after, then teach the cost and boundary.

When it helps consolidate the principle, close with one short paragraph that
names the broader problem it addresses, the conditions required for the design
to remain useful, and when the simpler alternative is better. Keep this inside
the principle and end after those three points.

## Completion criterion

A reader can answer “why was this shape needed?”, “what happens in the source
when it operates?”, and “under which conditions is it worthwhile?” without
trusting a pattern name or benefit summary. If any answer is missing, deepen
the lesson or remove it.
