# Skill maintenance

The English files are the canonical source:

- `codelume-skill/SKILL.md`
- `codelume-skill/references/*.md`
- `codelume-skill/agents/openai.yaml`

For every content change, edit the English canonical file first, then update its matching Chinese translation under `codelume-skill/translations/zh-CN/` in the same change. Preserve meaning, structure, relative links, trigger conditions, and completion criteria across both versions. Validate the English skill and verify that both versions remain UTF-8 and contain no stale cross-version links.

Use the Superpowers `writing-skills` RED-GREEN-REFACTOR workflow for every behavior-changing edit. Run a realistic baseline without the skill in a temporary workspace, record the actual failure, make the minimum English change that addresses it, synchronize the Chinese translation, and rerun the same scenario with the skill. If the no-guidance control does not exhibit the target failure, do not add speculative guidance.
