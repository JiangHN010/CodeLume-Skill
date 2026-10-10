# CodeLume-Skill

CodeLume-Skill is a Codex skill for turning an unfamiliar source repository
into an evidence-grounded source-learning textbook. It teaches the project's
problem, architecture, runtime mechanisms, design reasoning, and tradeoffs by
tracing real code.

CodeLume-Skill 是一个面向 Codex 的源码学习 Skill。它会分析真实代码，并生成有
源码证据支撑的源码学习教科书，重点讲解项目解决的问题、整体架构、运行机制、设计
推导和权衡。

## What it emphasizes

- Explain why a design exists, not only what files and modules exist.
- Trace at least one real input, event, or state through the implementation.
- Teach a few design principles through pressure, alternatives, concrete
  failure, source mechanism, benefit, cost, and applicability boundary.
- Add diagrams only when a complex relationship, lifecycle, or transformation
  is clearer visually.
- Link direct facts to source, label only inference, unknowns, and suggestions,
  and distinguish pseudocode from verbatim source excerpts.

## Repository layout

```text
codelume-skill/
├── SKILL.md                  # English canonical skill
├── agents/openai.yaml        # Codex UI metadata
├── references/               # Analysis and textbook section contracts
└── translations/zh-CN/       # Synchronized Chinese translation
```

The English files are canonical. Every content change must update the matching
Chinese translation in the same change.

## Install in Codex

Install only the English runtime files.

### PowerShell

```powershell
$codexHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $HOME ".codex" }
$target = Join-Path $codexHome "skills\codelume-skill"
New-Item -ItemType Directory -Force $target, "$target\agents", "$target\references" | Out-Null
Copy-Item "codelume-skill\SKILL.md" "$target\SKILL.md" -Force
Copy-Item "codelume-skill\agents\openai.yaml" "$target\agents\openai.yaml" -Force
Copy-Item "codelume-skill\references\*.md" "$target\references" -Force
```

### Bash

```bash
target="${CODEX_HOME:-$HOME/.codex}/skills/codelume-skill"
mkdir -p "$target/agents" "$target/references"
cp codelume-skill/SKILL.md "$target/SKILL.md"
cp codelume-skill/agents/openai.yaml "$target/agents/openai.yaml"
cp codelume-skill/references/*.md "$target/references/"
```

Restart Codex or start a new conversation after installation so the skill list
is refreshed.

## Use

Ask Codex to study a repository, module, runtime flow, component, function, or
implementation detail. The skill is designed to trigger whenever there is even
a small chance that the task involves learning source code.

Example:

```text
Use CodeLume-Skill to study this repository and write a source-learning
textbook that explains its architecture, one end-to-end runtime flow, and the
reasoning behind its most important design decisions.
```

## License

[MIT](LICENSE)
