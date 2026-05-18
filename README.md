# Cold Shower Skill

`cold-shower` is a Codex skill for pressure-testing ideas, plans, requirements, technical designs, products, pricing, market bets, personal decisions, and written arguments before execution.

It is designed to be adversarial toward the idea, not toward the user. The skill focuses on hidden assumptions, likely failure paths, falsification tests, and kill criteria.

## When To Use

Use this skill when you want Codex to:

- pour cold water on an idea
- act as a devil's advocate
- challenge assumptions before coding
- run a pre-mortem
- stress-test product, market, pricing, or technical plans
- ask Socratic questions before a decision
- review an artifact with findings first

The skill also supports Chinese prompts such as `泼冷水`, `挑刺`, `反驳我`, `别给情绪价值`, `苏格拉底式追问`, and `魔鬼代言人`.

## Install

Install into Codex with:

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo Oreo992/cold-shower-skill \
  --path . \
  --name cold-shower
```

Then restart Codex so the new skill is picked up.

## Files

- `SKILL.md` - main skill instructions
- `agents/openai.yaml` - display metadata for OpenAI/Codex surfaces
- `references/playbooks.md` - scenario-specific critique patterns
- `references/question-bank.md` - Socratic questions for underspecified ideas

## Output Style

The default output shape is:

- Cold Read
- Where It Breaks
- Hidden Assumptions
- Questions Before Moving
- Smallest Test
- Verdict

For code or artifact review, it uses findings-first review style with severity and file or line references where available.
