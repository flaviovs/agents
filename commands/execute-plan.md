---
description: Execute a plan
agent: build
---

# Executing a Plan

Your task is to execute a plan that has been broken down into several steps.

You'll act as the orchestrator to coordinate the execution of all steps of the plan by delegating each step to a subagent.

---

## Pre-flight Checklist

- Check for a plan $ARGUMENT in `.plans/`. If none or more than one plan matches, inform the use and stop.
  **Do not proceed if you're unsure of which plan the user wants.**
- Apply project-specific instructions for saved plan execution; those take precedence over conflicting instructions presented here.


Note: your glob and read tools might not be able to find plans in `.plans/`. You must fallback to OS tools (`ls`, `find`, etc.) for files in `.plans/`.

---

## Plan Files

In the plan directory:

- `PLAN.md` describes the plan.
- `TODO.md` defines a complete set of steps to implement the plan in this project.
- `NNN-{step-slug}.md` document the subtasks for each step.

---

## Workflow

Follow this orchestration workflow:

- Read `PLAN.md`.
- Read `TODO.md`.
- Read the `Goal` section and identify the overall objective, project-wide instructions, constraints, and completion criteria.
- Process every unchecked execution-checklist item sequentially, from top to bottom.
- Never execute multiple checklist items concurrently.
- For each unchecked item:
  - Identify the change file referenced by the item.
  - Delegate the item to a subagent.
  - Instruct the subagent to read the referenced change file in full and implement everything it requires.
  - Pass only context the subagent cannot discover from that change file, applicable goals and requirements from `TODO.md`, from `AGENTS.md`, relevant state or decisions produced by earlier checklist items, and any additional orchestration constraints required for correct execution.
  - Do not duplicate requirements or implementation details that the subagent can obtain by reading the change file.
  - Instruct the subagent to perform all validation required by the change file and applicable project-wide completion criteria.
  - Wait for the subagent to finish before proceeding.
  - Review the resulting changes and validation results.
  - If the item is incomplete or validation fails, delegate corrective work and repeat verification. Do not advance until the current item is complete.
  - Only after verifying all applicable completion criteria, mark the item completed in `TODO.md`.
- Repeat until every execution-checklist item is completed.
- After all items are complete, perform final project-wide validation against the `Goal` and all project completion criteria.

---

## Strict Requirements

- You are responsible for orchestration, sequencing, context propagation, review, and final verification.
- Delegate implementation work to subagents. Do not replace delegation by implementing checklist items yourself.
- Process checklist items strictly sequentially and in document order.
- Do not begin a later item while an earlier item remains incomplete.
- Each subagent must read its referenced change file itself.
- Do not unnecessarily copy or summarize information already available in the change file into the delegation prompt.
- Do pass any relevant information that is not available from the change file and that the subagent needs to execute correctly.
- Never assume a subagent has access to another subagent's conversation or conclusions; explicitly pass relevant cross-item state when necessary.
- Completion requires validation, not merely implementation.
- Do not weaken, remove, bypass, or alter requirements, tests, or completion criteria merely to make validation pass.
- Never mark an item complete while any applicable criterion is unmet or unverified.
- If an item cannot be completed or validated, stop the sequence, leave it unchecked, and report the blocker. Do not continue with subsequent items.
- Do not declare the changeset complete until every checklist item is checked, all acceptance criteria are met, and final project-wide validation passes.
