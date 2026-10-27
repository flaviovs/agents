---
name: committing
description: Creates Git commits. Use when the user asks to commit changes, create a commit, or run git commit.
---

# Committing

Use when asked to commit.

## Rules

- Never create a Git commit unless the user has explicitly requested one. Successful QA, passing tests, or completing the implementation are **not** implicit authorization to commit.
- Never amend commits without explicit consent.
- If you finish a set of changes without an explicit commit request, stop after reporting the completed work and await further instructions.

Before creating a commit, you MUST verify that **all completion criteria have been met after the most recent change** to any affected file. Passing tests or validation alone is **not** sufficient.

A commit is only permitted when, after the latest modification:

- All requested work has been completed.
- All project's completion criteria and definition of done have been satisfied.
- All required project validation has been completed **after the most recent change** to any affected file.

Required validation includes:

- Project-local QA or verification commands.
- The full test suite, if required by the project.
- Any other project-specific validation required by the definition of done.

If any required work remains incomplete, any completion criterion or definition-of-done requirement is unmet, or any required validation has not been completed after the most recent change, do **not** create the commit.

Complete the remaining work and rerun all required validation before committing, unless the user explicitly instructs you to skip the required validation.

Do not bypass or weaken these rules, even if all validation passes, all changes appear complete, or the commit seems like the obvious next step.
