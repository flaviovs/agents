---
description: Save a plan
agent: build
---

# Saving a Plan

Save this plan so that a fresh AI agent can execute all the tasks to complete it.

---

## Pre-flight Check

You must ensure that:

- All details to execute the plan are locked.
- There's no open questions or decisions.

Stop and ask for guidance if any of these is false.

---

## Workflow

Follow this workflow strictly:

1. Break down your plan into small, iterative chunks that build on each other.
2. Look at these chunks and then go another round to break it into small steps.
3. Review the results and make sure that the steps are small enough to be implemented safely with strong testing, but big enough to move the change forward.
4. Iterate until you feel that the steps are right sized for this project.
5. Create a single file for each one of the steps in `.plans/{plan-slug}/NNN-{step-slug}.md`, where `{plan-slug}` is a slug appropriate for this whole planned changeset, `{step-slug}` is a slug for the specific step, and `NNN` is a serial number. Make sure to provide full details for a fresh AI agents reading these files to understand the changes they need to make for each step. Assume that coding agents are fully aware of the rules in the project instructions, do not duplicate standard processes or rules in those files.
6. Create `.plans/{plan-slug}/PLAN.md` with a summary of the plan's goals, constraints, non-goals, and anything a fresh AI agent may need to understand the task without having access to this conversation. Add the following sections to `PLAN.md`:
   - Summary
   - Problem Statement
   - Goals & Objectives
   - Scope
   - Requirements
   - Dependencies & Constraints
   - Assumptions & Risks
   - Acceptance Criteria
7. Create `.plans/{plan-slug}/TODO.md` following this format:

   ```
   # Execution Checklist

   - [ ] `.plans/{plan-slug}/001-{step-slug}.md` - one-sentence description of step 001
   - [ ] `.plans/{plan-slug}/002-{step-slug}.md` - one-sentence description of step 002
   - ...
   ```
8. Report back the `{plan-slug}` and the number of steps.
