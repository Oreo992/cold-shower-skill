# Cold Shower Skill

`cold-shower` is an agent skill for pressure-testing ideas, plans, requirements, technical designs, products, pricing, market bets, personal decisions, and written arguments before execution. It works in Claude Code, Codex, and other agents that support the SKILL.md format.

It is designed to be adversarial toward the idea, not toward the user. The skill focuses on hidden assumptions, likely failure paths, falsification tests, and kill criteria. When the target exists as a real artifact (code, diff, spec, doc), the skill reads it before criticizing instead of arguing against a summary.

## When To Use

Use this skill when you want the agent to:

- pour cold water on an idea
- act as a devil's advocate
- challenge assumptions before coding
- run a pre-mortem
- stress-test product, market, pricing, or technical plans
- ask Socratic questions before a decision
- review an artifact with findings first

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

- `SKILL.md` - main skill instructions
- `agents/openai.yaml` - display metadata for OpenAI/Codex surfaces
- `references/playbooks.md` - attack angles and scenario-specific critique patterns
- `references/question-bank.md` - Socratic questions for underspecified ideas

## Output Style

Response depth scales with input size: a one-line idea gets the single sharpest objection plus a few Socratic questions; a full plan gets the complete structure:

- Cold Read
- Steelman
- Where It Breaks (tagged fatal / serious / friction)
- Hidden Assumptions
- Smallest Test
- Verdict

For code or artifact review, it uses findings-first review style with severity and file or line references. Across follow-up turns it tracks which assumptions were resolved and reports only the delta instead of re-running the full template.
