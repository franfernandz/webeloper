# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.3.0] - 2026-10-19

### Added

- Initial documentation of three-agent workflow (`sales`, `designer`, `developer`).
- Contract templates in `Contracts/` for `sales-contract.md` and `project-contract.md`.
- `Agents/designer-agent.md`: `Workflow` section (inputs → research →
  conversion → information architecture → design system → specifications →
  acceptance criteria → Contract QA).
- `Agents/designer-agent.md`: `Design System Specification` requiring exact
  tokens (hex colors, fonts with sizes/weights/line-heights, spacing scale,
  radii, breakpoints, motion) and WCAG AA contrast.
- `Agents/designer-agent.md`: `Contract QA` section validating the contract
  against every template section and specification quality.
- `Agents/designer-agent.md`: content distinction tags `[VERIFIED]`,
  `[ASSUMPTION]`, `[PROPOSED]`, `[NEEDS CONFIRMATION]`.
- `Agents/designer-agent.md`: `Output` now references the canonical template
  at `Contracts/project-contract.md`.
- `Agents/developer-agent.md`: `Workflow` section (contract → requirements →
  stack → implement in `site/` → serve → QA → report).
- `Agents/developer-agent.md`: `Missing Resources & Content Rules` for
  placeholders, backend-less forms, missing API keys, and content honesty.
- `Agents/developer-agent.md`: `ASSUMPTIONS.md` as the documented destination
  for assumptions and deviations.
- `Agents/developer-agent.md`: `Source of Truth` now requires exact design
  tokens from contract section 4.
- `Contracts/project-contract.md`: section 4 `Tokens` block (spacing, radius,
  breakpoints) with an exact-value rule.
- `Contracts/project-contract.md`: section 11 instructions for inline content
  distinction tags.

### Changed

- `Agents/developer-agent.md`: Quality Assurance is now executable (build,
  local serve, conversion path, browser console, breakpoints, section 15
  validation); the completion report references `ASSUMPTIONS.md` and
  placeholder assets.
- `Agents/designer-agent.md`: heading hierarchy normalized (single H1 title,
  sections at H2).
- `Agents/sales-agent.md`: heading hierarchy normalized (single H1 title,
  sections at H2).

### Fixed

- `Agents/sales-agent.md`, `Agents/designer-agent.md`, `Agents/developer-agent.md`:
  YAML frontmatter moved to the top of the file so `mode`, `temperature`, and
  `permission` are actually applied. Previously the title preceded the
  frontmatter, so restrictions such as `bash: deny` and `edit: deny` were not
  enforced.

## [0.2.0] - 2026-10-19

### Added

- `Agents/sales-agent.md`: Commercial Status Machine with all allowed
  transitions; agent-set vs. human-gated transitions are explicit.
- `Agents/sales-agent.md`: Deduplication rule (match on normalized name,
  location, domain, contact) to prevent competing sources of truth.
- `Agents/sales-agent.md`: Discovery Protocol with ordered sources,
  verification gates, and an effort budget for "find N prospects" commands.
- `Agents/sales-agent.md`: Win/Loss Review loop that logs outcomes and
  re-validates scorecard weights every 10 closed cycles.
- `Contracts/sales-contract.md`: Section 5 expanded with per-dimension
  scorecard table (score, weight, justification), weighted total, and an
  `Outcome` block for win/loss feedback.
- `Contracts/sales-contract.md`: Section 9 now points to the Commercial
  Status Machine for valid statuses and transitions.

### Changed

- `Agents/sales-agent.md`: `Definition of Done` extended to cover
  verification, deduplication, legal status transitions, and Win/Loss
  review of closed cycles.

## [0.1.0] - 2026-10-19

### Added

- `Agents/sales-agent.md`: qualification scorecard with weighted dimensions
  (0–5) normalized to a 1–10 opportunity score for reproducible ranking.
- `Agents/sales-agent.md`: channel playbook mapping Email, Instagram DM,
  WhatsApp, LinkedIn, and contact form to use cases and risks.
- `Agents/sales-agent.md`: follow-up cadence (initial + 2 follow-ups, stop
  at day 10, max 3 touches without reply) to prevent spamming and silence.
- `Agents/sales-agent.md`: outreach copy template with observation →
  implication → offer → CTA structure and a before/after example.
- `Agents/sales-agent.md`: compliance and guardrails section (opt-out
  handling, no scraped private data, no impersonation, jurisdiction rules,
  default cap of 10 active prospects, prohibited claims).
- `Agents/sales-agent.md`: explicit approval mechanism with draft/approved/
  sent states; agent prepares, human sends.

### Changed

- `Agents/sales-agent.md`: `Contract` now references the canonical template
  at `Contracts/sales-contract.md` and defines one contract per prospect.
- `Agents/sales-agent.md`: `Contract` adds prospect numbering convention
  (`#01`, `#02`, ...) so command references are unambiguous.
- `Agents/sales-agent.md`: `Definition of Done` extended to require
  scorecard output, channel selection, personalized copy, compliance
  limits, and explicit human approval before any outreach.
