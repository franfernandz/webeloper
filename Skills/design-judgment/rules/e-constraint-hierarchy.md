# Criterion E — Design With a Constraint Hierarchy

## Rule

When criteria or requirements conflict, resolve them by a fixed priority order. Lower priorities never override higher ones. Trends may inform a decision but may never decide it on their own.

## Priority Order (highest to lowest)

1. **Brief, positioning, and commercial objectives.**
2. **Differentiation from competitors.**
3. **Chosen art direction.**
4. **Coherence of the visual system.**
5. **Usability and accessibility.**
6. **Conventions and visual trends.**

## Failure Mode It Prevents

Trends and personal taste silently overriding commercial intent, and the visual system overriding accessibility. Without an order, decisions get made by whatever argument arrives last.

## How to Apply

For any contested decision, the agent states the conflict and resolves it from the top down.

Worked example:

> Conflict: the art direction calls for very low-contrast caption text, but WCAG AA requires a 4.5:1 ratio.
> Resolution: accessibility is priority 5, art direction is priority 3 — but the brief (priority 1) includes serving a broad audience and the client's compliance requirement. The caption contrast rises to meet AA; the art direction adjusts type size and spacing to preserve the intended mood within that constraint.

Note the important nuance: a *higher* priority does not license ignoring a *lower* one. Priority 3 does not permit violating priority 5 by default. Prioritization decides which side bends when they genuinely cannot both hold.

## Trend Handling

Trends sit at the bottom. They may:

- inform typography, motion, or layout choices;
- suggest a starting point for exploration.

They may not:

- be the deciding factor for a significant decision;
- replace a brief-linked rationale.

## Completion Checklist

- Every conflict encountered during design has a stated resolution traceable to this order.
- No significant decision is justified by trend alone (check against criterion A).
- Accessibility requirements are treated as a floor the system must satisfy, not an optional layer.

## Interaction With Other Criteria

- This criterion decides the outcome when A–D produce competing demands.
- It reorders the Operating Principle in the agent's own instructions only where they conflict; the brief remains supreme.
