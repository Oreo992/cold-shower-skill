# Cold Shower Skill

`cold-shower` is an agent skill for pressure-testing ideas, plans, requirements, technical designs, products, pricing, market bets, personal decisions, and written arguments before execution. It works in Claude Code, Codex, and other agents that support the SKILL.md format.

At its core it is a calibration engine: its job is to make your confidence match the evidence, in either direction. It is adversarial toward the idea, not toward the user. The skill focuses on hidden assumptions, likely failure paths, falsification tests, and kill criteria. When the target exists as a real artifact (code, diff, spec, doc), the skill reads it before criticizing instead of arguing against a summary. For major decisions it keeps a decision ledger in `~/.cold-shower/` — assumptions, verdict, kill criteria, review date — and holds you accountable to it in later sessions.

## When To Use

Use this skill when you want the agent to:

- pour cold water on an idea
- act as a devil's advocate
- challenge assumptions before coding
- run a pre-mortem
- stress-test product, market, pricing, or technical plans
- ask Socratic questions before a decision

It critiques decisions, not diffs — for code review, use a dedicated review tool.

The skill also supports Chinese prompts such as `泼冷水`, `挑刺`, `反驳我`, `别给情绪价值`, `苏格拉底式追问`, and `魔鬼代言人`.

## Install

### Claude Code

Clone into your personal skills directory and restart Claude Code:

```bash
git clone https://github.com/Oreo992/cold-shower-skill ~/.claude/skills/cold-shower
```

Then invoke it with `/cold-shower`, or just ask for cold water in natural language.

### Codex

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo Oreo992/cold-shower-skill \
  --path . \
  --name cold-shower
```

Then restart Codex so the new skill is picked up.

## Files

- `SKILL.md` - main skill instructions (the compiled pipeline)
- `DESIGN.md` - design invariant for maintainers: the five-layer model and the filter rule for new features
- `agents/openai.yaml` - display metadata for OpenAI/Codex surfaces
- `references/playbooks.md` - attack angles and scenario-specific critique patterns
- `references/methods.md` - named methods (reference class forecasting, ACH, Toulmin, Fermi, RAT, 10/10/10, self-distancing, two-way doors), selected by target type
- `references/question-bank.md` - Socratic questions for underspecified ideas
- `references/examples.md` - worked examples: low-stakes restraint and a condensed full-depth run

## Output Style

Response depth scales with stakes (reversibility and blast radius), not input length: a casual take gets the single sharpest objection plus a few Socratic questions; an irreversible decision — even stated in one line — gets the complete structure:

- Cold Read (thesis + steelman)
- Where It Breaks (tagged fatal / serious / friction)
- The Load-Bearing Assumption (with the outside-view fill-in)
- Smallest Test (with pre-committed kill criteria)
- Verdict (including your stated confidence vs what the evidence supports)
- a receipt line counting the objections pruned for not surviving an obvious rebuttal

For high-stakes decisions it asks your confidence up front ("几成把握？") and records it in the ledger, so when the outcome is known, both the verdict and your calibration get scored. Across follow-up turns it tracks which assumptions were resolved and reports only the delta instead of re-running the full template.
