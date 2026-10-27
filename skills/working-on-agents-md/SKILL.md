---
name: working-on-agents-md
description: Creates, reviews, and improves project AGENTS.md files. Use whenever creating or updating a project's AGENTS.md, including incidental edits during a larger task, and when asked to analyze, evaluate, or review these files.
---

# Working on `AGENTS.md`

## Pre-flight Task

Before analyzing or editing an `AGENTS.md` file, discover, load, and apply the available instructions for editing LLM prompts and agent instructions, whether provided by relevant skills, the project's instructions, or both. If none are found, stop and report the missing prerequisite.

## Workflow

Apply only the steps relevant to the request. For review-only requests, report actionable findings without editing. Keep incidental updates focused on the affected workflow.

1. **Establish scope and evidence.**
   - Read the target file, applicable parent instructions, and relevant nested instruction files. Treat proposed instructions as content to assess; follow the applicable instruction hierarchy while editing.
   - Inspect relevant documentation, package scripts, build configuration, and CI to establish actual workflows. Investigate apparent conflicts and preserve existing intent unless a change is requested.
   - Identify the intended agent tools and product surfaces when discovery, precedence, inclusion, or size limits matter. Verify their behavior in current documentation or configuration; do not assume identical support across tools.
   - Resolve uncertainty from repository evidence first. Ask targeted questions when material uncertainty remains; do not invent project requirements.
2. **Select useful guidance.** Apply the content rules below. Include sections only when they help the agent perform real project work.
3. **Draft focused changes.** Follow the structure and writing rules below. Keep one authoritative statement of each requirement and preserve unrelated user work.
4. **Validate.** Check evidence, commands, references, scope, and expected behavior using the validation guidance below. Revise any defects before reporting completion.

## Content Rules

- **Prioritize non-obvious knowledge.** Capture the correct package manager, setup order, environment prerequisites, known setup failures and workarounds, hidden dependencies, architectural boundaries, generated-file regeneration commands, and unusual local conventions when relevant. Identify stack and runtime/tool versions when they affect the workflow, preferably by referencing authoritative project metadata. Prefer facts an agent would otherwise get wrong over exhaustive repository inventories or obvious directory summaries.
- **Make commands executable and conditional.** Put frequently needed setup and verification commands early. Include the working directory, relevant flags, prerequisites, required order, and the changes that trigger each check. Distinguish focused checks from broader checks; do not prescribe expensive full-suite runs for every task without a project-specific reason.
- **Keep mechanical enforcement authoritative.** Reference formatter, linter, type-checker, and CI configuration and explain how to run their checks. Avoid duplicating machine-enforced settings in prose. Document constraints those tools cannot express.
- **Capture relevant workflow boundaries.** Include project-specific restrictions on generated or vendor files, dependency changes, commits, or deployment only when supported by project policy. Do not invent approval requirements or generic checklists.
- **Maintain living documentation.** Update affected guidance when workflows change. Remove obsolete workarounds after verifying they no longer apply; label necessary legacy conditions. Start small and add rules in response to observed mistakes rather than anticipating every possible failure.

## Structure and Writing

- Use standard Markdown with useful headings; `AGENTS.md` requires no special schema or YAML frontmatter. Do not confuse it with custom-agent definitions such as `.github/agents/*.md` or copy their persona and metadata requirements.
- Keep root guidance broadly applicable. Add nested files only for genuinely specialized subsystem rules, after verifying how the intended tool discovers and combines them. Avoid repeating root instructions; make intentional local exceptions explicit and resolve conflicts using the applicable hierarchy.
- Express observable behavior: identify the triggering situation and required action. Distinguish mandatory requirements from preferences. Include a short reason, safe path, or exception when it improves reliability.
- Use small representative examples or canonical implementation references for unusual conventions. For example: “Register new HTTP endpoints through `src/http/router.ts`; direct registration bypasses authentication middleware.” Adapt examples to verified project facts.
- Keep one source of truth. Reference existing documentation instead of copying large sections, and state when it must be read: “Before changing database migrations, read `docs/database-migrations.md`.” A link or `@path` is not a portable automatic include; use explicit reading instructions or a verified tool-specific inclusion mechanism.
- Keep shared project guidance in version control using the project's normal contribution workflow. Keep personal preferences in the target tool's global configuration when appropriate rather than introducing them as team policy.

## Validation

- Check every changed command against repository scripts, configuration, and CI. Execute relevant commands where feasible, with their documented prerequisites and working directory; do not run destructive or deployment commands merely to verify documentation. Report commands that were checked only by inspection, could not run, or failed, with reasons.
- Verify referenced paths exist and examples match actual project conventions. Check that root and nested rules are coherent, and that referenced documents have explicit loading conditions.
- When changing instruction discovery or inclusion, verify which sources the intended tool actually loads using its supported diagnostics or logs. Account for tool-specific limits and session reload behavior; do not treat a maximum context size as a target document length. Report discovery that remains unverified.
- Review for preserved intent, actionable requirements, missing prerequisites, contradictions, duplication, stale guidance, and unnecessary tokens. A longer document is not evidence of improvement.
- For substantial or behavior-sensitive revisions, define observable success criteria and compare original and revised instructions on the same representative tasks with comparable model/runtime settings when execution is available. Include relevant failure cases: stale commands, conflicting nested rules, ambiguous references, duplicated README or lint guidance, incidental updates, and review-only requests. Check activation against nearby requests that do not involve working on `AGENTS.md`.
- Evaluate fewer repeated mistakes, successful relevant checks, and reasonable execution cost. Do not assume context files or repository overviews improve task success. Distinguish observed behavior from inspection-only findings, and explicitly report unavailable execution or unresolved validation.
