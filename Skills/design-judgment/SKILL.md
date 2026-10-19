---
name: design-judgment
description: Forces deliberate, project-specific art direction instead of statistical defaults. Use when designing or redesigning a website, landing page, marketing site, product UI, or brand surface — before writing any design contract, component spec, or design tokens. Triggers on hero sections, visual identity, layout direction, typography decisions, color systems, and any request that risks converging on the typical SaaS aesthetic.
license: MIT
metadata:
  author: webeloper
  version: "1.0.0"
---

# Design Judgment

This skill exists to stop the designer agent from defaulting to the most statistically frequent solution. Modern, clean, minimal, and "common in SaaS" are not design decisions — they are the absence of one. Every significant choice must be earned by the brief.

The skill imposes five criteria. They are ordered by priority: when they conflict, a lower number outranks a higher one. See `rules/e-constraint-hierarchy.md` for the full order.

## The Five Criteria

| # | Criterion | Rule file | What it enforces |
|---|-----------|-----------|------------------|
| A | No defaults | `rules/a-no-defaults.md` | Never pick a solution because it is modern/clean/typical |
| B | Visual thesis required | `rules/b-visual-thesis.md` | Define art direction before the contract, not after |
| C | Explore alternatives | `rules/c-alternatives.md` | Produce three genuinely different directions, then choose |
| D | Evidence per decision | `rules/d-evidence.md` | Every contract decision carries a concrete reason |
| E | Constraint hierarchy | `rules/e-constraint-hierarchy.md` | Brief > differentiation > art direction > system > usability > trends |

## Mandatory Workflow

The designer agent MUST complete these steps **in order**. Do not skip ahead, and do not write a design contract, token set, or component spec until step 3 is closed.

1. **Read the brief.** Identify the business, the audience, the commercial objective, and the competitive set. If any of these are missing, make a reasonable documented assumption or ask before inventing them.
2. **Write the visual thesis** (criterion B). Five required parts: positioning, central idea, aesthetic tension, differentiation principle, deliberately discarded decisions. "Modern, clean, professional" is not a thesis.
3. **Produce three real directions** (criterion C). Compare them on commercial positioning, competitive differentiation, and implementation viability. Select one and justify the choice. The first plausible idea must not automatically become the final design.
4. **Draft the contract with reasons** (criterion D). Each significant decision states *what* and *why*, tied to the thesis. No decision rests on "it looks modern/friendly/clean."
5. **Audit against the default list** (criterion A). For every default pattern used, produce an explicit business/art-direction justification — or replace it.
6. **Resolve conflicts by the hierarchy** (criterion E). When usability, trends, or coherence collide with brief or differentiation, the lower priority yields.

## Hard Rules

- **Never** open with the canonical hero (huge left-aligned headline + right-side mockup) unless the brief specifically supports it.
- **Never** use violet/blue gradients as decoration without a stated reason tied to the brand.
- **Never** apply rounded cards to everything by reflex.
- **Never** reach for bento grids merely to look modern.
- **Never** choose a generic sans-serif without an editorial or functional reason.
- **Never** repeat sections with identical visual structure out of habit.
- These resources are **not banned**. Choosing them without a brief-linked justification is banned.

## Anti-patterns the agent must catch in its own output

- "Clean, minimal, modern" used as a rationale instead of a consequence.
- A thesis that could describe any competitor in the market.
- Three "concepts" that are three color variations of one template.
- Contract entries of the form "because it adds modernity / feels friendly / is best practice."
- Trends used as the deciding factor rather than an input.

## How to Use

Read the individual criterion files for the full requirement and examples:

```
rules/a-no-defaults.md
rules/b-visual-thesis.md
rules/c-alternatives.md
rules/d-evidence.md
rules/e-constraint-hierarchy.md
```

Each file states the rule, the failure mode it prevents, worked examples, and a completion checklist the agent must satisfy before moving on.
