---
description: Improve a PM issue
---

# Improve PM Issue

Review an issue and propose improvements to make it clear, actionable, and verifiable.

## Workflow

1. **Analyze the issue:** Retrieve it from the project management system and gather relevant supporting context, such as comments, labels, dependencies, and related issues. Understand the underlying need, motivation, and desired outcome.
2. **Analyze project files:** Examine relevant project files as needed to understand the current state, existing behavior, and constraints, and resolve material uncertainties.
3. **Clarify ambiguities:** Identify missing, unclear, or contradictory information that materially affects the issue. Resolve ambiguities using available evidence. If materially different interpretations remain plausible or necessary information is missing, ask targeted questions and wait for answers before proposing a final revision.
4. **Refine iteratively:** Incorporate the user's answers and repeat clarification as needed until the issue is actionable. If the user cannot resolve material ambiguities, identify the blockers explicitly rather than presenting the revision as final.
5. **Propose changes:** Present the improved title and description, including acceptance criteria, for the user's review.

If no issue is identified in the user's request, ask which issue to work on and stop.

If the issue or necessary supporting material is inaccessible, request the missing content and identify which conclusions remain unverified.

## Clarifying Questions

- Number clarifying questions so the user can refer to each one.
- For each question, provide an informed recommendation and a brief justification. Prefer recommendations grounded in available evidence over neutral menus of possibilities.
- Phrase each question so that answering **"yes"** accepts the recommendation. Explicitly allow the user to override it or supply a different answer.
- If the evidence is insufficient to support a recommendation, state what is missing and ask for that information rather than inventing a recommendation.

## Issue Standards

**Title**
- Start with an imperative verb (e.g., "Add", "Fix", "Improve").
- Clearly and concisely describe the desired outcome.

**Description**
- Explain the underlying need, problem, or opportunity.
- Describe the desired outcome and why it matters.
- Include relevant context, scope, requirements, and constraints.
- Preserve existing valid information.

**Acceptance Criteria**
- Include a `## Acceptance Criteria` section.
- Use checkboxes (`- [ ]`).
- Define specific, independently verifiable outcomes.
- Focus on observable results.
- Cover all confirmed requirements without inventing missing details.
- Keep items concise. Put lengthy supporting requirements or validation guidance in an appropriate description section, and reference it where needed.

## Rules

- Do not modify the issue or project files, unless explicitly requested by the user.
- Preserve the issue's original intent and scope.
- Never invent requirements or make unsupported assumptions.
- Treat project files as evidence of the current state, not necessarily the desired state.
- Do not prescribe implementation approaches unless explicitly required.
- Assume the issue's reader has access to project files; avoid unnecessary file references.
- Avoid unnecessary edits to already actionable content.
- Be concise and specific.
