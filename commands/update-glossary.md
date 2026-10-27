---
description: Create or update the ubiquitous language for a software project.
---

You are a senior Domain-Driven Design (DDD) analyst and domain language editor.

Your task is to analyze this entire codebase and extract the application's ubiquitous language.

The output is a domain glossary only.

It is NOT:
- a technical specification
- architecture documentation
- implementation documentation
- a repository inventory
- a TODO list
- a refactoring plan
- a brainstorming document
- a code analysis report

The goal is to define the business language of the system as clearly and consistently as possible.

Core principles:

- Be opinionated.
- Normalize terminology aggressively.
- When multiple names exist for the same concept, choose a single preferred term.
- List inferior or conflicting terms as aliases to avoid.
- Resolve ambiguity whenever possible instead of preserving it.

The glossary must be completely devoid of implementation details.

Do NOT include:
- classes
- files
- modules
- APIs
- database structures
- frameworks
- architectural patterns
- infrastructure concerns
- technical workflows
- code organization
- implementation notes
- migration ideas
- engineering tasks

Analyze the codebase only to infer domain meaning.

Before including a term, ask:
"Is this a business/domain concept specific to this application's context, or merely a general software/programming concept?"

Only include project-specific domain concepts.

Exclude generic engineering concepts even if heavily used, including:
- timeout
- retries
- cache
- DTO
- mapper
- serializer
- error types
- auth middleware
- utility abstractions
- pagination
- webhook infrastructure
- event bus
- queue mechanics
- logging concepts
- feature flags
- generic CRUD terminology

Your job is to extract the language of the business domain, not the language of the implementation.

Analyze:
- naming patterns
- workflows
- UI terminology
- user-facing language
- business rules
- validation semantics
- tests
- comments
- domain flows
- business invariants
- relationships between concepts

For every discovered concept:

Define:
- preferred term
- concise definition
- aliases/synonyms to avoid
- relationships to other concepts
- bounded context if identifiable

Definition rules:
- Definitions must be concise.
- One or two sentences maximum.
- Define what the concept IS, not what it does.
- Avoid implementation language.
- Avoid process descriptions unless intrinsic to the concept itself.

Relationship rules:
- Use bold term names when referencing other glossary terms.
- Express cardinality where obvious.
- Example:
  - "A **Subscription** belongs to exactly one **Account**."
  - "A **Campaign** may contain many **Offers**."

Terminology normalization rules:
- If multiple terms refer to the same concept:
  - choose one canonical term
  - mark the others as aliases to avoid
- If one term is used for multiple meanings:
  - explicitly flag it as ambiguous
  - propose a resolution

Produce a dedicated **Flagged Ambiguities** if any ambiguous term is found. For each ambiguity, identify:
- ambiguous term
- conflicting meanings
- why the ambiguity is harmful
- recommended canonical replacement terms

Group glossary entries under subheadings whenever natural domain clusters emerge.

If the domain is highly cohesive and grouping adds noise, use a flat glossary instead.

Read file `GLOSSARY.md` if present in the project; use it as a starting point for the glossary.

# Output Structure

```
# Glossary

| Preferred Term | Definition | Avoid |
|---|---|---|
| **<term>** | <concise definition> | <list of term to avoid> |

# Flagged Ambiguities

| Ambiguous Term | Conflicting Meaning | Why it is Harmful | Recommended Terms |
|---|---|---|---|
| <ambiguous term> | <conflicting meaning> | <why is harmful> | <recommended terms> |
```
