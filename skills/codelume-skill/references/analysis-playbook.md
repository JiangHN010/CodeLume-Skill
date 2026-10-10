# Source Analysis Playbook

Use this reference when the repository is unfamiliar, spans multiple modules, or hides runtime wiring behind frameworks or configuration.

## 1. Establish the checkout

Capture enough context to make the textbook reproducible:

- repository root and relevant subproject;
- current revision, branch, or a snapshot date when Git metadata is unavailable;
- dirty-worktree status without altering existing changes;
- repository instructions and documentation conventions;
- language, build system, and executable entry points.

Prefer `rg --files` and targeted searches over broad recursive reads. Treat filenames and directory names as clues until code, configuration, or tests confirm their role.

## 2. Build the system map

Create a compact working map before following individual functions:

| Question | Evidence to inspect |
| --- | --- |
| What can start the system? | routes, main methods, commands, jobs, consumers, exports |
| What are the module boundaries? | manifests, imports, build modules, package layout |
| How are implementations selected? | constructors, DI modules, registries, annotations, config |
| Where does durable state live? | repositories, migrations, schemas, filesystem adapters |
| Which boundaries leave the process? | HTTP clients, SDKs, queues, subprocesses, tool calls |
| What constrains behavior? | tests, validation, feature flags, security rules, timeouts |

Do not assign architectural roles from package names alone. Confirm at least one real caller and one implemented responsibility for each core module in the textbook.

## 3. Trace a vertical slice

Choose a user-visible or externally observable scenario. Record the trace as a table while exploring:

| Step | Actual symbol | Input or state | Work performed | Output or side effect | Evidence status |
| --- | --- | --- | --- | --- | --- |

Search both directions: follow callees from the entry point and search callers of important implementations. Frameworks often break a textual call chain; bridge the gap with registration, annotations, generated metadata, or tests, and label the bridge as inferred if runtime selection cannot be proven from the checkout.

For asynchronous work, distinguish these moments when they exist:

1. the initiating thread accepts or queues work;
2. a local callback or future reports handoff;
3. an external system acknowledges receipt;
4. a consumer or worker performs business work;
5. durable state or a final response records completion.

Do not collapse these into a single "success" event.

## 4. Inspect data and state

For each important object, identify where it is created, validated, transformed, stored, copied, or released. Note ownership and consistency boundaries. Check:

- request and response models;
- domain entities and value objects;
- persistence records and migrations;
- caches and invalidation;
- transaction start and commit locations;
- identifiers used to correlate retries or events;
- mutable shared state, locks, or thread-local context.

## 5. Follow failure behavior

Find the code responsible for invalid input, missing data, external timeouts, duplicate work, retries, rollback, cleanup, and user-visible error mapping. Describe only paths supported by code or tests. A library dependency implies available capability, not configured behavior.

## 6. Validate claims

Choose checks that can falsify the important claims. Examples include a focused unit or integration test, compilation of the affected module, a local example command, or inspection of generated route metadata. Record skipped checks and why.

Before writing, challenge each major statement:

- Which file and symbol establish this?
- Does this describe source structure, configured intent, tested behavior, or observed runtime behavior?
- Could dependency injection, configuration, concurrency, or an external service change the result?
- Is the statement current for this checkout?

Any statement without a satisfactory answer becomes inferred, suggested, unknown, or is removed.

## 7. Turn evidence into design teaching

Write a connected technical chapter rather than an audit report or worksheet:

1. Open with the problem, constraints, and one architectural thesis.
2. Explain the major boundaries in prose, supported by an overall diagram. Describe why each boundary exists and how the parts collaborate; do not substitute a responsibility table for explanation.
3. For each selected principle, load [design-principle-template.md](design-principle-template.md), complete its private causal brief, and finish the principle before moving on. A principle unsupported in any required slot stays out of the textbook.
4. Keep the module inventory subordinate to the design story. Explain simple modules in concise source-linked prose. Load [complex-module-template.md](complex-module-template.md) only for modules with a non-obvious mechanism worth teaching.
5. When useful, close a design principle with a brief source-grounded takeaway: name the broader problem, the conditions that make this design worthwhile, and when the simpler alternative is better. Keep it inside that principle and end after those three points.

Write for programmers across experience levels and language backgrounds unless the user requests otherwise, but do not announce an audience profile. Define a term in the sentence or paragraph where it first matters; do not create a glossary section. Introduce concepts in implementation-neutral terms, then show how the repository expresses them in its actual language and framework. Weave traces, state changes, tests, and failures into the relevant design discussion instead of creating a standalone proof chapter. Add file-reading instructions, learning sequences, or exercises only when requested.

Use Markdown links readers can open from the final document. Check relative paths after saving, and name the file and symbol in prose so the explanation survives line drift.
