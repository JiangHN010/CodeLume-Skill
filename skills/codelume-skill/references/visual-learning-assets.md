# Visual Learning Assets

Read this reference when a saved source-learning textbook contains relationships, state,
ordering, transformations, or an abstract mechanism that may be clearer
visually. Visuals answer learning questions; they do not certify module coverage.

## Decide from complexity

Use a deterministic Mermaid or repository-native SVG when prose hides one of
these structures:

- several important responsibilities and boundaries in a repository;
- a sequence where ordering, retries, concurrency, or completion matters;
- a state or lifecycle transition;
- data ownership or a multi-stage transformation; or
- an internal decision tree or algorithm in a complex module.

Explain a simple wrapper, registry, manifest, value type, or linear adapter in
prose. A module does not receive a diagram merely because it is in scope. A
repository guide may use one overall architecture diagram; local module diagrams
are conditional on the mechanism, not the module count.

Keep a short private visual note for each selected visual: learning question,
verified source basis, visual form, placement, and asset path. Do not expose the
note, selection process, prompt, or rejected assets in the textbook.

## Choose the visual form

| Learning need | Preferred form |
| --- | --- |
| Exact architecture, dependency, call chain, state, or data ownership | Mermaid or repository-native SVG |
| Conceptual mental model or metaphor | Generated raster image |
| Existing maintained project visual | Reuse or edit its native source |
| Quantitative comparison | Chart from verified data |

Every technical node and arrow maps to a checked symbol, configuration, schema,
or an explicitly labeled inference. Remove a visual that merely repeats the
surrounding paragraph.

## Generated conceptual imagery

Generate an illustration only when it materially clarifies an abstract
responsibility, coordination model, lifecycle, distributed boundary,
concurrency model, retrieval flow, or memory model that exact boxes and arrows
do not teach well. Skip it when a maintained project visual or deterministic
diagram already explains the idea.

When the decision is yes:

**REQUIRED SUB-SKILL:** Use `imagegen`.

Ground the prompt in verified evidence: learning goal, placement, subject,
composition, style, palette, and unsupported elements to avoid. Prefer no
embedded technical text; keep exact names and labels in Markdown.

## Save and verify generated assets

1. Inspect for invented components, incorrect relationships, garbled text,
   logos, watermarks, and inconsistent visual language.
2. Copy the selected image into `<guide-directory>/assets/<guide-slug>/` with a
   stable descriptive filename.
3. Embed a relative path, meaningful alt text, and this evidence boundary:

   ```markdown
   ![A conceptual view of the mechanism](assets/<guide-slug>/<image>.png)

   > Conceptual illustration. Exact relationships are defined by the source-linked diagram or prose.
   ```

4. Re-open the Markdown and image; verify rendering and consistency with the
   surrounding explanation.

## Visual quality gate

- Each visual answers a named learning question that prose alone does not answer
  as clearly.
- Technical relationships are source-grounded; generated images make no
  unsupported architecture claims.
- Simple modules remain prose-only.
- Related visuals use a coherent style.
- Relative paths resolve and raster assets live beside the textbook.
