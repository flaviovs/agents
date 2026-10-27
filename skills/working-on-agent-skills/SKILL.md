---
name: working-on-agent-skills
description: Creates, reviews, and improves Agent Skills, including SKILL.md metadata, instructions, and supporting resources. Use when asked to create, analyze, evaluate, edit, or improve an Agent Skill or SKILL.md file.
---

# Working on Agent Skills

## Core Principles

- Prefer direct instructions and concrete examples over abstract discussion.
- Use consistent terms and durable guidance. Remove temporary details or label necessary legacy information.
- Do not copy nearby conventions or other instructions automatically; include them only when they are needed for this skill to work reliably.

## Pre-flight Task

Before analyzing or editing a skill, discover, load, and apply the available instructions for editing LLM prompts and agent instructions, whether provided by relevant skills, the project's instructions, or both. If none are found, stop and report the missing prerequisite.

## Workflow

Apply only the steps relevant to the request. When reviewing or making a focused change to an existing skill, do not perform unrelated authoring or restructure unaffected content.

1. **Analyze the request and skill.** Identify objective, scope, constraints, inputs, outputs, triggers, ambiguities, and known failure cases. For existing skills, establish the current behavior and preserve intent unless asked to change it.
2. **Define the capability.** Focus on one clear, reusable capability. Prefer specific, activity-focused names, often in gerund form.
3. **Draft or revise metadata and instructions.** Make only the changes needed, matching specificity to risk.
4. **Add supporting material when useful.** Include workflows, examples, templates, references, or scripts only when they improve clarity or reliability.
5. **Review and validate.** Apply the evaluation and final review requirements below. If a check fails, revise the relevant content and repeat that check.

## Metadata

Use the [Agent Skills specification](https://agentskills.io/specification) as the format baseline. Every `SKILL.md` must contain YAML frontmatter with `name` and `description`, followed by Markdown instructions. Create or update frontmatter as needed. The validity requirements below are mandatory; naming and writing preferences are guidance.

### Name

- The name must be 1–64 characters, use only lowercase letters, numbers, and hyphens, and match the containing directory name. It must not start or end with a hyphen or contain consecutive hyphens.
- Prefer a specific, descriptive, activity-focused name. Gerund forms such as `processing-pdfs` are a useful convention.
- Avoid vague or overly broad names.

### Description

- State what the skill does and when to use it.
- Include domain terms and trigger phrases that distinguish it from other skills.
- The description must be nonempty and at most 1,024 characters.
- Prefer capability-first, third-person wording.
- Avoid generic descriptions.
- Do not use backticks.

## Instructions And Workflows

- Use sections that serve the skill's purpose; do not add sections solely to match a template.
- Keep the main `SKILL.md` focused and under 500 lines as a guideline.
- For multi-step tasks, order the steps as they should be performed and identify required inputs and expected outputs.
- Use flexible guidance where multiple approaches are valid. State a preferred pattern with parameters when a useful default exists.
- Add validation before irreversible or high-impact actions, and explain recovery when validation fails.
- Define how to check outputs against requirements, a style guide, or a validator.

## References, Examples, Scripts, And Assets

- Use progressive disclosure when substantial reference material would distract from the main instructions. Store supporting documentation in `references/`, executable utilities in `scripts/`, and templates or static resources in `assets/` when useful.
- Reference bundled files using paths relative to the skill root. Use Markdown links for documentation, such as `[Reference guide](references/file-name.md)`, and explicit paths or commands for scripts and assets. Link resources directly from `SKILL.md`; avoid reference chains.
- State when and how each resource should be used: read documentation, execute or inspect scripts, or copy, populate, or transform assets. Paths alone do not load or execute resources. For commands, explain how to resolve skill-relative paths when the working directory differs from the skill root.
- Split references by task or domain when that keeps unrelated details out of the main skill. Give files descriptive names, use forward slashes, add a table of contents to references over 100 lines, and remove unused or duplicate material.
- Include examples when they clarify expected behavior; use exact templates for strict output requirements and label adaptable templates as defaults.
- Avoid listing alternatives unless the task requires a choice; give a recommended default and relevant exception.
- Prefer maintained utility scripts for deterministic, repeatable operations when appropriate. State whether to execute a script or consult it as reference.
- Document dependencies, execution requirements, configuration, and non-obvious constants. Follow project dependency conventions; do not assume installation is available or permitted.
- Make script errors actionable. Fail clearly when recovery could conceal invalid input or produce misleading output; use defaults only when they are correct.
- Validate plans and intermediate data before batch, destructive, or high-impact operations. Use visual inspection when rendered output reveals relevant structure that text extraction cannot.

## Evaluation And Final Review

For new skills and substantial or behavior-sensitive changes, define observable success criteria and evaluate realistic representative tasks and known failure cases. For revisions, compare the original and revised skill on the same tasks using comparable model/runtime settings when execution is available. Include activation cases where relevant: requests that should trigger the skill and closely related requests that should not. For new skills, use a no-skill baseline when useful. Revise based on observed failures and repeat affected evaluations; incorporate team feedback when applicable.

Report which checks were executed and which conclusions are inspection-only. If execution is unavailable, state the limitation and do not claim behavioral verification.

Before completing the work, check the applicable items. Omit checks that do not apply to the request; do not expand a focused change into unrelated work.

- The name and description are specific and valid.
- Instructions are concise, actionable, consistent, and aligned with the skill's intended behavior.
- Workflows, outputs, constraints, exceptions, and validation are clear where needed.
- Examples match the instructions; references are directly linked and useful.
- Time-sensitive details are removed or clearly marked as legacy.
- Scripts, dependencies, and execution requirements follow project conventions; critical outputs and intermediate plans are validated.
- Applicable evaluations above are complete, with failures addressed and affected checks rerun, or execution limitations explicitly reported.
- LLM prompt guidelines were followed.
