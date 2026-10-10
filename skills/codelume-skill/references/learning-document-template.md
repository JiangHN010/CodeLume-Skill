# Source-Learning Textbook Writing Contract

Use this file as a router. Draft one section at a time and load only the
section contract needed for that section. Splitting files helps only when the
contracts are loaded progressively rather than all at once.

## Single purpose

The artifact teaches the student how the project is designed and implemented.
Its reader-facing content may include the problem, architectural thesis,
runtime mechanisms, design reasoning, complex modules, relevant failure
semantics, limits, and source pointers.

Keep troubleshooting runbooks, interview preparation, exercises, contribution
instructions, source-reading orders, production notes, evidence snapshots, and
validation reports outside this textbook. Failure behavior belongs only where it
explains a design choice or invariant.

## Load the section contracts progressively

1. Start with [project-overview-template.md](project-overview-template.md) for
   the problem, architectural thesis, responsibility boundaries, and one
   concrete runtime slice.
2. For each selected major principle, load
   [design-principle-template.md](design-principle-template.md). Finish that
   principle before loading the next section contract.
3. Use [complex-module-template.md](complex-module-template.md) only for a
   module whose internal complexity materially teaches the architecture.
   Explain simple modules briefly in the overview or a compact module map.
4. Read [visual-learning-assets.md](visual-learning-assets.md) only when a
   relationship, lifecycle, transformation, or abstract mechanism may be
   clearer visually.

## Evidence and code contract

- State direct source facts normally and link the file and symbol. Do not add a
  status label to a directly supported fact.
- Prefix only non-facts with exactly `[INFERRED]`, `[UNKNOWN]`, or
  `[SUGGESTED]`. Put the label on the sentence or paragraph it qualifies.
- Introduce every teaching rewrite in the document language. Use **伪代码（教学改写，并非源码原文）：**
  in Chinese and **Pseudocode (teaching rewrite; not source):** in English. A
  different language, renamed identifier, simplified branch, or reconstructed
  object is pseudocode.
- Introduce a verbatim block as **源码节选：** in Chinese or **Source excerpt:** in
  English, and only after comparing it with the linked checkout. If wording,
  identifiers, comments, ordering, or control flow are changed, classify it as
  pseudocode.
- Define specialized terms inline on first use. Keep implementation-neutral
  intuition before language-specific syntax or analogies.
- Use source links as evidence, not a reader-facing audit trail. Put material
  unknowns in the relevant discussion or a concise limits section.

## Minimal article shape

Keep only sections supported by the scope and evidence:

```markdown
# <Project or module>: <architectural thesis>

## The problem behind the code
## The central design and one concrete runtime slice
## Design principles in depth
## Complex module: <name>                 # only when warranted
## Limits and open questions              # only material limits
## Source pointers
```

## Final editorial gate

Read the textbook as a coherent teaching work. It is complete only when:

- the architectural thesis still makes sense if package names are removed;
- every selected principle satisfies its causal contract instead of listing
  components or benefits;
- at least one real input, event, or state is followed through concrete
  representations, decisions, ownership changes, and observable results;
- simple modules do not receive forced deep dives or decorative diagrams;
- status labels and code classifications follow the evidence contract; and
- every relative link resolves from the saved textbook.
