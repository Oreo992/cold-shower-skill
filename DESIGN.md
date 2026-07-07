# Design Invariant

This document is for maintainers of the skill, not for the model executing it. SKILL.md is the compiled artifact; this is the source of truth for what belongs in it.

## The One-Sentence Definition

> Cold Shower is a calibration engine: it makes the user's confidence match the evidence.

Pouring cold water is the surface behavior. The actual job is closing the gap between how sure the user is and how much evidence exists — in either direction. "Proceed, plainly" is calibration too.

## The Five Layers

Every feature in this skill belongs to exactly one of five orthogonal layers:

| Layer | Responsibility | Current implementation |
|---|---|---|
| **Evidence** | Where evidence comes from | Ground Before You Attack; browse rule; Fermi Discipline; Reference Class base rates |
| **Reasoning** | How counter-hypotheses are generated | Steelman; pre-mortem; playbook angles; named methods (ACH, Toulmin, RAT) |
| **Delivery** | How calibration enters the user's head | Elicit-doubts-first; self-distancing; attack-plan-not-person; rationalization callout; language rule |
| **State** | How calibration persists across time | Decision ledger; assumption tracking; verdict upgrades/downgrades; Follow-up Turns |
| **Meta** | How the engine guards its own biases | Prune step; Self-Check Before Sending; conflict-of-interest rule; multi-agent option |

The layers are orthogonal: changing one does not require touching the others.

## The Filter Rule

Any proposed feature must answer: **which layer does it fill, and does it serve confidence-evidence alignment?**

- No layer → it does not belong in this skill.
- Serves something else (persuasion, entertainment, thoroughness for its own sake) → reject.
- Fills a layer already covered → it must replace or sharpen the existing filler, not stack on top.

## The Compilation Rule

The executing model gets a flat, imperative pipeline — never this ontology. Five-layer architecture in SKILL.md would degrade instruction-following, not improve it. When adding a feature: design it here in layer terms, then compile it into SKILL.md as a concrete step, a one-line rule, or a reference file loaded on demand.

Hard constraints on the compiled artifact:

- SKILL.md stays near 100 lines. Anything scenario- or method-specific goes to `references/` and is loaded by an explicit pointer in the workflow.
- Depth scaling suppresses the architecture: light input runs only Reasoning + Delivery. If a one-line "反驳我" ever triggers the ledger or the full template, the compilation has failed.
- Depth follows stakes (reversibility) first, input size second. Input length is a bad proxy for what a decision deserves.
- Host capabilities degrade gracefully: text-only hosts lose State (ledger) and live Evidence (browse) but keep everything else.
- Instruction count is the enemy. Every added step dilutes the execution of every existing step. A feature that cannot justify displacing an existing instruction does not get added — the 2026-07 self-critique found the v3 pipeline (10 steps + 5-item self-check) already past the point of faithful execution, and cut it back.

## Open Assumptions

These are the load-bearing beliefs this design rests on. If one falsifies, revisit the layer it supports.

1. **Invisible internal steps execute.** ~~Unverified.~~ **Tested 2026-07** (same prompt: skill-on vs skill-off vs faithful-execution-with-self-report): steps with visible artifacts (ledger check, browse, Fermi labels, stakes-first depth) executed faithfully; the purely internal prune ran "by feel" per the executor's own report, and the conflict-of-interest check idled. Consequence: prune now emits a visible receipt line ("Pruned: N objections dropped"). Rule extracted: **an instruction only reliably executes if its execution leaves a visible trace in the output.**
2. **Users re-trigger on the same topic.** The ledger's accountability value depends on it. The overdue-`review_by` sweep partially hedges this; if ledger entries still rot unread, the State layer is decoration.
3. **Qualitative base rates stay honest.** Step 4's outside-view assumption slot forbids invented statistics but allows qualitative claims — watch whether these drift into confident-sounding fabrication.

## What the 2026-07 A/B Run Established

- **The skill's marginal value over a bare model is discipline, not sharpness.** The no-skill baseline found the same killer objection (subscription vs episodic demand) and three good points the skilled run missed. What the skill uniquely added: pre-committed kill criteria, verdict vocabulary, evidence-graded assumptions, browsed-and-cited market claims (the baseline asserted competitor facts from memory — exactly the failure the browse rule exists for), and the outside-view fill-in. Budget accordingly: features that enforce discipline earn their lines; features that try to make the critique "smarter" compete with a strong baseline and usually lose.
- **Trigger recall is near-total** — an agent seeing 泼冷水 invoked the skill before producing anything. There is no natural no-skill baseline on a machine where it is installed; low-stakes restraint must come from Depth Scaling, not from the skill failing to fire.
- The elicit-doubts step delivered in the same message cannot aim the current turn's critique (the psychology requires asking first); it was restructured into a stakes-dependent calibrate-the-prior step that also captures stated confidence — closing the gap that a "calibration engine" never measured confidence.
