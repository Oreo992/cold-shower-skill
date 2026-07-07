# Named Methods

Load this file at workflow step 5 (Attack, then prune). Pick methods by what the target actually is — a plan, a judgment, an argument, a number, or a life decision. Run one or two well; do not run all of them. The pre-mortem belongs to plans and bets; for judgments run ACH instead, for arguments Toulmin, for personal decisions 10/10/10.

## Selection Table

| Target type | Methods |
|---|---|
| Plan, product bet, project | Reference Class Forecasting + Pre-mortem/Inversion + RAT |
| Judgment or diagnosis ("X is happening because Y") | Analysis of Competing Hypotheses |
| Argument, essay, positioning | Toulmin Attack |
| Any claim involving cost, revenue, time, or scale | Fermi Discipline |
| Personal decision | 10/10/10 + Self-Distancing + Two-Way Doors |

## Reference Class Forecasting (outside view)

Kahneman/Flyvbjerg. Cures the planning fallacy: inside-view analysis of a plan's own logic systematically overestimates success.

- Name the reference class: what category of attempt is this? (indie SaaS launch, internal platform migration, career change into X)
- State the base rate: what happens to most attempts in that class? Browse if you do not know.
- Demand the exception argument: "你凭什么是分子而不是分母？" The answer must be a verifiable difference, not effort or belief.
- If the user's only exception argument is "I'll work harder / I care more," say so — that is the base-rate case, not the exception.

## Pre-mortem / Inversion

Gary Klein's pre-mortem is Munger's "invert, always invert" applied to plans.

- Assume the plan failed 6-18 months from now. Do not ask "what could go wrong" — assert "it failed; reconstruct how."
- Trace one concrete causal sequence, not a risk list: first this slipped, then that compounded, then it died.
- Include the boring deaths: no adoption, weak distribution, maintenance burden, attention moved elsewhere, stakeholder quietly withdrew.

## Riskiest Assumption Test (RAT)

Lean-startup discipline behind "Smallest Test."

- The test must target the single assumption most likely to kill the plan (the load-bearing assumption from workflow step 4), not the easiest one to test.
- A good RAT is fast, cheap, and produces a signal that can actually falsify: define in advance what result means "stop."
- Building an MVP is usually not a RAT. Buying ads to a landing page, ten user interviews, or a manual concierge version usually is.

## Analysis of Competing Hypotheses (ACH)

CIA structured analytic technique. Use when the user's "idea" is actually a judgment — "churn is caused by pricing," "the bug is in the cache layer," "the market shifted."

- List every plausible competing hypothesis, including the boring one ("random variation," "measurement error").
- For each piece of evidence, ask which hypotheses it is *inconsistent* with — disconfirmation, not support, does the work.
- The most likely hypothesis is the one with the least evidence against it, not the most evidence for it.
- Output: the surviving hypothesis, the strongest rival, and the single piece of evidence that would separate them.

## Toulmin Attack

For writing, positioning, and public arguments. Claims are rarely the weak point; the warrant is.

- Decompose: claim (the conclusion), grounds (the evidence), warrant (the usually-unstated rule connecting them).
- Attack the warrant first: "this evidence supports that conclusion only if [warrant] — is that true here?"
- Then attack backing (does the warrant hold in this domain?) and qualifiers (is "always" doing illegitimate work?).
- Output: the hidden warrant stated explicitly, why it fails, and the sharper claim the evidence actually supports.

## Fermi Discipline

Qualitative economic objections are unfalsifiable and therefore cheap. Numbers kill fantasies.

- Any objection about cost, revenue, time, or scale must carry an order-of-magnitude estimate: "CAC 大概几百还是几千？回本要几个月还是几年？"
- Show the two-line arithmetic. A wrong-but-explicit estimate the user can correct beats a vague "margins will be tight."
- Force the user's implied numbers into the open: "your plan implies ~N users paying ~¥X by month M — say that out loud and check it."

## 10/10/10

Suzy Welch. For personal decisions distorted by present emotion.

- How will you feel about this choice in 10 minutes, 10 months, 10 years?
- The 10-minute answer is usually fear or excitement; the 10-year answer is usually about identity and regret. The 10-month answer is where the real information lives.

## Self-Distancing

Solomon's paradox: people reason far better about a friend's problem than their own.

- Ask: "如果你最好的朋友拿着一模一样的方案和处境来找你，你会对他说什么？"
- If the user's advice-to-friend differs from their own plan, that gap is the finding. Name it.

## Two-Way Doors

Bezos. Reversibility determines how much cold water a decision deserves.

- Type 2 (reversible): the cheapest test is often just doing it small. Do not over-analyze; say so.
- Type 1 (irreversible or expensive to undo): this is where full-depth analysis, kill criteria, and the ledger belong.
- Many decisions framed as Type 1 are Type 2 with an ego cost. Distinguish "hard to undo" from "embarrassing to undo."
