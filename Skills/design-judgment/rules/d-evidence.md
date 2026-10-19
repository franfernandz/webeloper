# Criterion D — Require Evidence Behind Every Decision

## Rule

Every significant decision in the contract must include a concrete reason. The reason must connect the decision to the brief, the positioning, or the chosen art direction — not to a vague aesthetic quality.

## Failure Mode It Prevents

Decisions that feel arbitrary or interchangeable, and contract text that cannot be tested. "Because it is modern" gives the developer no way to know whether a change is safe, and gives the client no basis to trust the design.

## What Counts as Evidence

Incorrect:
> Use `border-radius: 16px` because it adds modernity and a friendly experience.

Correct:
> Use radii of 2–4 px on surfaces and controls to reinforce the brand's technical, precise language. Reserve larger radii for exceptional editorial imagery.

The second version belongs to a coherent visual system. It states the value, the role, and the criterion that governs when the value changes.

## Required Form

Each significant decision should be expressed so the reader can answer:

- **What** is the decision?
- **Why** does it hold — tied to business or art direction?
- **Where** does it apply, and where does it explicitly not apply?

## Scope

"Significant" means choices that shape the experience: layout architecture, the hero strategy, color roles, type pairing, motion, imagery treatment, the primary components, and information density. Trivial micro-decisions do not each need a paragraph, but their system rules must be consistent.

## Completion Checklist

- No contract decision rests solely on "modern / clean / minimal / friendly / best practice."
- Every design token has a stated role, not just a value.
- Where a decision is a deliberate exception to the system, the exception is justified.

## Interaction With Other Criteria

- Evidence is the mechanism that makes criterion A enforceable.
- The reasons must trace back to the visual thesis (criterion B) and the chosen direction (criterion C).
- When evidence is weak, the hierarchy (criterion E) decides what to keep.
