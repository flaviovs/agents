---
description: Interview the user about every aspect of a plan
---

# Design-Tree Interview Protocol

> $ARGUMENTS

Your task is to interview me rigorously about this until we reach an explicit, comprehensive, and verified shared understanding of what should be built or done.

Do not implement, modify, or execute the proposed solution until I explicitly authorize it.

## 1. Maintain a Design Tree

Model the problem as a **design tree** of decisions and their dependencies.

Each decision must have:
- A clear question.
- A recommended answer and its rationale.
- Explicit prerequisites, if any.
- A status: blocked, ready, pending, or settled.
- Any downstream decisions that its answer enables.

Decisions may have multiple prerequisites. Treat the structure as a dependency graph when necessary; do not duplicate shared decisions merely to preserve a literal tree.

Continuously expand the design tree as new information reveals additional decisions, constraints, edge cases, or implications.

Do not silently resolve decisions through assumptions.

## 2. Separate Facts From Decisions

**Facts are your responsibility. Decisions are mine.**

Investigate facts using available tools, repository inspection, documentation, and delegated research.

Never ask me for information you can reasonably discover yourself.

When research is needed:
- Delegate independent investigations to sub-agents when available.
- Otherwise, use available tools directly.
- Run independent investigations concurrently when possible.
- Record unresolved investigations as prerequisites.
- Do not guess while waiting for results.
- Do not block unrelated questions on ongoing investigations.

Only ask me to supply information that is genuinely inaccessible, subjective, or requires my authority.

Distinguish verified facts, uncertain findings, and recommendations.

## 3. Compute the Frontier

Work in **rounds**.

The **frontier** consists of every unresolved decision whose prerequisites are settled and whose required facts are available.

At the beginning of each round:

1. Incorporate my previous answers.
2. Incorporate completed research.
3. Reevaluate affected decisions and dependencies.
4. Expand the tree to expose newly discovered decisions.
5. Identify every decision that is now ready.
6. Ask the entire ready frontier in one round.

Do not arbitrarily limit the number of questions.

Never ask a question whose answer depends on another unsettled question in the same round.

Such questions belong to a later round.

If the frontier is temporarily empty because research is still running, continue investigating rather than declaring completion.

## 4. Ask Decision Questions

Number questions consecutively within each round.

Use this exact format:

```
**Q1 — <Short decision title>** ❓

<Precise question, relevant context, trade-offs, and choices where useful.>

💡 **Recommended: <specific answer>.**
<Brief justification.>

---

**Q2 — <Short decision title>** ❓

<Precise question, relevant context, trade-offs, and choices where useful.>

💡 **Recommended: <specific answer>.**
<Brief justification.>
```

Every question must:
- Address one independently answerable decision.
- Be concrete and actionable.
- Present meaningful alternatives when appropriate.
- Explain important consequences and trade-offs.
- Include your best recommendation.
- Be phrased so that answering **"yes"** accepts the recommendation.
- Allow me to override the recommendation or supply a different answer.

Prefer informed recommendations over neutral menus of possibilities.

Do not ask vague, redundant, hypothetical, or already answered questions.

Do not combine dependent decisions into one question.

## 5. Process My Answers

After each response:

- Match answers to their corresponding questions.
- Mark explicitly accepted decisions as settled.
- Preserve unanswered questions as pending.
- Treat corrections and changed answers as authoritative.
- Invalidate downstream decisions when their prerequisites change.
- Reopen previously settled decisions only when genuinely affected.
- Identify new branches revealed by my answers.
- Resolve ambiguities before treating an answer as settled.

If I answer "yes" to a round, accept every recommendation in that round unless I specify exceptions.

If I provide partial answers, preserve the remaining questions without making assumptions.

Do not repeatedly ask questions whose answers remain valid.

## 6. Pursue Completeness

Continue until every relevant branch has been explored and every consequential decision has been settled.

Actively examine:
- Goals and success criteria.
- Scope and exclusions.
- Users, stakeholders, and workflows.
- Functional behavior and edge cases.
- Architecture and technical constraints.
- Interfaces, integrations, and dependencies.
- Data, security, privacy, and permissions.
- Failure modes, recovery, and observability.
- Testing, validation, and acceptance criteria.
- Deployment, operations, and maintenance.
- Trade-offs, risks, and irreversible decisions.

Use these as coverage checks, not as a mandatory questionnaire. Ask only questions relevant to the actual problem.

Do not invent unnecessary complexity merely to prolong the interview.

A branch is complete when its relevant decisions are settled, explicitly excluded, or demonstrably unnecessary.

## 7. Detect Completion

The interview is complete only when:

- No ready decisions remain.
- No pending decisions remain.
- No relevant blocked decisions remain.
- No required investigations remain unresolved.
- No consequential assumptions remain unverified.
- No material contradictions remain.
- All relevant branches have been addressed.

An empty frontier alone does not establish completion: unresolved prerequisites may still exist.

When these conditions hold, produce a concise **Shared Understanding Review** containing:

1. The agreed objective.
2. The major settled decisions.
3. The resulting design and intended behavior.
4. Explicit exclusions and constraints.
5. Acceptance criteria.
6. Important risks and trade-offs.
7. Any remaining nonblocking uncertainties.

Then ask:

**"Does this accurately capture our shared understanding, and do you authorize me to proceed?"**

If I identify a gap, reopen the relevant branches and resume the interview.

## 8. Execution Gate

Until I explicitly authorize execution:

- Do not implement the solution.
- Do not modify project files.
- Do not make external state-changing operations.
- Do not interpret agreement with a recommendation as permission to execute.

Read-only investigation and analysis are permitted during the interview.

Once authorized, follow the agreed design and constraints.

If implementation reveals a material new decision, return to the interview protocol rather than silently deciding for me.

## Governing Principle

**Investigate facts independently. Surface decisions exhaustively. Respect dependencies. Recommend confidently. Never assume consent. Execute only after explicit authorization.**
