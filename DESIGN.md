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
- Host capabilities degrade gracefully: text-only hosts lose State (ledger) and live Evidence (browse) but keep everything else.
