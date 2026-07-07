# Cold Shower Playbooks

Use these playbooks only when they match the user's request. Keep the response grounded in the user's actual context.

## General Attack Angles

Default angles when no specific playbook fits, or to supplement one:

- Customer/user: who actually suffers enough to change behavior?
- Distribution: how will this reach people without wishful thinking?
- Economics: where do time, money, attention, and margins break?
- Execution: which part is harder than it sounds?
- Alternatives: why would existing options, doing nothing, or a manual workaround win?
- Timing: why now, and why might now still be wrong?
- Reversibility: what is the cost if this is wrong?

## Requirements Before Coding

Goal: prevent the agent from turning an unclear request into polished wrong code.

Check:
- What user behavior or business outcome should change?
- What exact input, state, and output define success?
- What existing workflow must not break?
- What is deliberately out of scope?
- What edge case would make the implementation look correct but fail in use?

Response pattern:
- Restate the requirement as acceptance criteria.
- Identify ambiguities that would change architecture or UX.
- Ask blocking questions before editing.
- If enough is known, propose the smallest buildable version and what to verify.

## Technical Plan Or Architecture

Goal: expose complexity, hidden coupling, and verification gaps before implementation.

Attack:
- Overengineering: Is this solving a future problem before today's problem is real?
- Underengineering: Is a critical invariant left to convention or manual discipline?
- Coupling: Which module now knows too much about another module?
- Migration risk: What happens to existing data, sessions, jobs, or API consumers?
- Observability: How will failure be detected after deployment?
- Rollback: Can this be undone without data loss or user-visible damage?

Useful verdicts:
- "Use the simpler path until X is proven."
- "This is worth the abstraction because Y already repeats in Z places."
- "The risky part is not the code, it is the migration/ops surface."

## Code Review

Goal: find real defects or maintainability traps, not stylistic dislikes.

Read the actual diff or files before reviewing. Never review from the user's description of the change.

Lead with findings:
- Severity: blocker, high, medium, low.
- Location: file and line when available.
- Impact: how it fails at runtime or during maintenance.
- Fix direction: specific enough to act on.

Look for:
- Broken invariants and race conditions
- Incorrect error handling or retry behavior
- State that can become stale
- User changes accidentally overwritten
- Tests that pass without covering the risky path
- Security, permission, and data-leak boundaries

Skip:
- Personal taste
- Large refactors unrelated to the request
- Nitpicks unless the user asked for polish

## Product, Pricing, Or Startup Bet

Goal: break founder or builder overconfidence before sunk cost grows.

Attack:
- Pain: Is this urgent, frequent, expensive, or reputation-threatening enough?
- Buyer: Who has budget and authority, not just interest?
- Switching: What current workflow must be displaced?
- Distribution: What channel can repeatedly produce qualified users?
- Differentiation: What do competitors or manual workflows make look trivial?
- Pricing: What value metric maps to willingness to pay?
- Retention: Why would usage continue after novelty fades?

Output:
- "Most likely reason this dies"
- "Self-flattering belief"
- "Competitor or do-nothing alternative that wins"
- "One test before building"
- "Kill criteria"

## Market Entry

Goal: test whether confidence is just ignorance of prior failures.

Browse when facts may have changed or when naming dead products, recent funding, current competitors, pricing, regulation, or market size.

Classify failures:
- No urgent buyer
- Distribution too expensive
- Incumbent bundled the feature
- Behavior change too large
- Unit economics did not work
- Regulation or platform dependency changed
- Product was useful but not a business

Compare the user's plan:
- "You look most like the failed companies in this one way..."
- "Your real difference would need to be..."
- "The evidence needed before entering is..."

## Personal Decision

Goal: reduce regret, not make the decision for the user.

Attack:
- Reversibility: Can the decision be undone?
- Identity trap: Is the user protecting an image of themselves?
- Opportunity cost: What will quietly disappear?
- Downside: What is the specific bad outcome, not the abstract risk?
- Dependency: Whose behavior or cooperation must be true?
- Time horizon: What will matter in 5 years but feels invisible now?

Output:
- "Letter from the regretting future self"
- "Most dangerous self-deception"
- "What you lose if this goes badly"
- "Containment plan"
- "Decision rule"

## Writing, Positioning, Or Public Argument

Goal: prevent persuasive prose from hiding weak reasoning.

Attack:
- What claim is overstated?
- What counterexample would a skeptical reader use?
- Which phrase sounds confident but carries no evidence?
- What is the strongest opposing interpretation?
- What sentence should be deleted because it performs insight without proving it?

Output:
- Strongest objection
- Weakest paragraph or claim
- Missing evidence
- Revised sharper thesis
