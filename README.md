# Webeloper

> A multi-agent web agency pipeline: **Sales → Design → Build**, driven by two contracts.

Webeloper is a set of three specialized AI agents and two contract documents that encode the complete workflow of a web agency. Each agent has a clear role boundary, and each contract acts as the single source of truth for its stage of the process.

The system is designed for agencies and freelancers who want to turn a sales conversation into a client-facing website demo without losing control, inventing facts, or burning time on rework.

---

## How it works

```
┌─────────────┐    ┌──────────────────┐    ┌───────────────┐    ┌─────────────┐    ┌──────────┐
│  Prospect   │ →  │  Sales Agent     │ →  │ Designer Agent│ →  │ Developer   │ →  │ Website  │
│  discovery  │    │  sales-contract  │    │ project-      │    │ Agent       │    │ (demo)   │
│             │    │  (Design Handoff)│    │ contract.md   │    │              │    │          │
└─────────────┘    └──────────────────┘    └───────────────┘    └─────────────┘    └──────────┘
```

1. **Sales Agent** finds, researches and qualifies prospects, and maintains a `sales-contract.md` for each one.
2. When a prospect wants to see a demo, the Sales Agent writes a **Design Handoff** (business and commercial context — not UI decisions).
3. **Designer Agent** reads the handoff and produces `project-contract.md`, a complete, implementation-ready website specification.
4. **Developer Agent** builds the functional website directly from `project-contract.md`, which is the only source of truth for UX/UI.

---

## Agents

### Sales Agent — `Agents/sales-agent.md`

A senior B2B sales strategist and sales copilot for selling websites to small and medium businesses.

- Prospects, researches and qualifies businesses
- Maintains one `sales-contract.md` per prospect
- Designs outreach and follow-up strategy and drafts the messages
- Tracks conversations, objections and buying signals
- Produces the **Design Handoff** when a demo is requested
- The human always approves external communication

### Designer Agent — `Agents/designer-agent.md`

A conversion-focused web designer. Turns business context into a complete website specification.

- Owns information architecture, UX, UI, visual direction, content strategy and responsive behavior
- Produces `project-contract.md` with enough detail that the Developer Agent never has to make major design decisions
- Never writes production code — `project-contract.md` is its only output
- Never invents business facts, reviews, prices or credentials

### Developer Agent — `Agents/developer-agent.md`

A framework-agnostic senior web developer.

- Builds the website described by `project-contract.md`
- Treats the project contract as the single source of truth (the sales contract cannot override it)
- Owns all technical decisions: stack, structure, styling, tooling
- Chooses the simplest technology that delivers the required experience
- Preserves design fidelity and documents any deviation from the contract

---

## Contracts

### `Contracts/sales-contract.md`

The commercial source of truth for a single prospect. Maintained throughout the sales process. It covers:

- Prospect profile and business research
- Current digital presence assessment
- Opportunity and commercial hypothesis
- Qualification scoring
- Outreach strategy and message history
- Conversation log, objections and buying signals
- Commercial status and next action
- **Design Handoff** — the interface between the Sales Agent and the Designer Agent

### `Contracts/project-contract.md`

The authoritative website specification for a single project. It covers:

- Business and project objective, primary and secondary conversions
- Brand, positioning and visual direction
- Design system (colors, typography, visual characteristics)
- Website architecture and page specifications
- Navigation, components, interactions and responsive behavior
- Content and functional requirements
- Assumptions and acceptance criteria

---

## Design principles

- **No invented facts.** Agents never invent reviews, prices, certifications, awards or performance claims. Hypotheses stay hypotheses.
- **Conversion-first.** Every website must define a clear primary conversion.
- **Clear role boundaries.** Each agent owns its stage and does not step into the next one.
- **No over-engineering.** The developer uses the simplest technology that gets the job done.
- **Human in control.** The human approves all external communication and commercial decisions.

---

## Directory structure

```
Webeloper/
├── Agents/
│   ├── designer-agent.md    # Designs websites → writes project-contract.md
│   ├── developer-agent.md   # Builds websites from project-contract.md
│   └── sales-agent.md       # Prospects & sells → maintains sales-contract.md
└── Contracts/
    ├── project-contract.md  # Implementation spec template (Designer's output)
    └── sales-contract.md    # Commercial spec template (Sales's output)
```

---

## Getting started

Webeloper's agents are defined as [opencode](https://opencode.ai) markdown agents. You can use them with opencode or adapt them to any agent runtime that supports markdown agent definitions.

### 1. Install the agents

Place the agent files in your opencode agents directory:

- **Per project:** `.opencode/agents/`
- **Globally:** `~/.config/opencode/agents/`

```bash
# per-project example
mkdir -p .opencode/agents
cp Agents/*.md .opencode/agents/
```

### 2. Initialize the contracts

Copy the contract templates into the project you are working on:

```bash
cp Contracts/sales-contract.md .
cp Contracts/project-contract.md .
```

### 3. Run the pipeline

Open opencode in the project and drive the workflow with the agents:

- **Prospecting:** "find 10 gyms in Buenos Aires" → the Sales Agent discovers and qualifies prospects.
- **Selecting a prospect:** "let's work on prospect #02" → the Sales Agent prepares its `sales-contract.md` and Design Handoff.
- **Designing:** hand the Design Handoff to the Designer Agent → it produces `project-contract.md`.
- **Building:** hand `project-contract.md` to the Developer Agent → it builds the functional website.

---

## Requirements

- [opencode](https://opencode.ai) (or another runtime that supports markdown agent definitions)
- A configured model provider
- The `Contracts/` templates (start with the copies in this repo)

---

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## License

This project is released under the [MIT License](LICENSE).
