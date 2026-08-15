<p align="center">
  <img src="logo.png" alt="Webeloper logo" width="320">
</p>

<h1 align="center">Webeloper</h1>

> A multi-agent web agency pipeline: **Sales → Design → Build**, driven by two contracts.
> Un pipeline multiagente de agencia web: **Ventas → Diseño → Desarrollo**, guiado por dos contratos.

<p align="center">
  <a href="https://ko-fi.com/mrnandz"><img alt="Support me on Ko-fi" src="https://img.shields.io/badge/ko--fi-Support%20me-FF5E5B?logo=kofi&logoColor=white"></a>
  <a href="https://cafecito.app/mrnandz"><img alt="Invítame un cafecito" src="https://img.shields.io/badge/cafecito-Inv%C3%ADtame%20un%20cafecito-1E5FA8?logo=buy-me-a-coffee&logoColor=white"></a>
</p>

---

# English

## What is Webeloper?

Webeloper is a set of three specialized AI agents and two contract documents that encode the complete workflow of a web agency. Each agent has a clear role boundary, and each contract acts as the single source of truth for its stage of the process.

The system is designed for agencies and freelancers who want to turn a sales conversation into a client-facing website demo without losing control, inventing facts, or burning time on rework.

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

## Design principles

- **No invented facts.** Agents never invent reviews, prices, certifications, awards or performance claims. Hypotheses stay hypotheses.
- **Conversion-first.** Every website must define a clear primary conversion.
- **Clear role boundaries.** Each agent owns its stage and does not step into the next one.
- **No over-engineering.** The developer uses the simplest technology that gets the job done.
- **Human in control.** The human approves all external communication and commercial decisions.

## Directory structure

```
Webeloper/
├── Agents/
│   ├── designer-agent.md    # Designs websites → writes project-contract.md
│   ├── developer-agent.md   # Builds websites from project-contract.md
│   └── sales-agent.md       # Prospects & sells → maintains sales-contract.md
├── Contracts/
│   ├── project-contract.md  # Implementation spec template (Designer's output)
│   └── sales-contract.md    # Commercial spec template (Sales's output)
└── logo.png                 # Project logo
```

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

## Requirements

- [opencode](https://opencode.ai) (or another runtime that supports markdown agent definitions)
- A configured model provider
- The `Contracts/` templates (start with the copies in this repo)

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Support the project

If Webeloper is useful to you, you can buy me a coffee or leave a tip:

- [Buy me a coffee on Cafecito](https://cafecito.app/mrnandz) ☕
- [Support me on Ko-fi](https://ko-fi.com/mrnandz) ☕

Any support helps keep improving the project. Thank you!

## License

This project is released under the [MIT License](LICENSE).

---

# Español (Latinoamérica)

## ¿Qué es Webeloper?

Webeloper es un conjunto de tres agentes de IA especializados y dos documentos de contrato que codifican el flujo de trabajo completo de una agencia web. Cada agente tiene un límite de rol claro, y cada contrato actúa como la única fuente de verdad para su etapa del proceso.

El sistema está pensado para agencias y freelancers que quieren convertir una conversación de ventas en una demo de sitio web para el cliente sin perder el control, sin inventar hechos ni perder tiempo en retrabajo.

## Cómo funciona

```
┌───────────────┐    ┌──────────────────┐    ┌────────────────┐    ┌──────────────┐    ┌──────────┐
│  Descubrir    │ →  │  Agente de       │ →  │ Agente de      │ →  │ Agente de    │ →  │ Sitio    │
│  prospecto    │    │  Ventas          │    │ Diseño         │    │ Desarrollo   │    │ web (demo)│
│               │    │  sales-contract  │    │ project-       │    │               │    │          │
│               │    │  (Design Handoff)│    │ contract.md    │    │               │    │          │
└───────────────┘    └──────────────────┘    └────────────────┘    └──────────────┘    └──────────┘
```

1. El **Agente de Ventas** encuentra, investiga y califica prospectos, y mantiene un `sales-contract.md` para cada uno.
2. Cuando un prospecto quiere ver una demo, el Agente de Ventas escribe un **Design Handoff** (contexto comercial y de negocio, no decisiones de UI).
3. El **Agente de Diseño** lee el handoff y produce el `project-contract.md`, una especificación de sitio web completa y lista para implementar.
4. El **Agente de Desarrollo** construye el sitio web funcional directamente desde `project-contract.md`, que es la única fuente de verdad para UX/UI.

## Agentes

### Agente de Ventas — `Agents/sales-agent.md`

Un estratega senior de ventas B2B y copiloto de ventas para vender sitios web a pequeñas y medianas empresas.

- Prospecta, investiga y califica negocios
- Mantiene un `sales-contract.md` por prospecto
- Diseña la estrategia de outreach y follow-up y redacta los mensajes
- Lleva el registro de conversaciones, objeciones y señales de compra
- Produce el **Design Handoff** cuando se solicita una demo
- El humano siempre aprueba la comunicación externa

### Agente de Diseño — `Agents/designer-agent.md`

Un diseñador web enfocado en conversión. Convierte el contexto de negocio en una especificación completa del sitio.

- Es dueño de la arquitectura de información, UX, UI, dirección visual, estrategia de contenido y comportamiento responsive
- Produce el `project-contract.md` con suficiente detalle para que el Agente de Desarrollo nunca tenga que tomar decisiones de diseño importantes
- Nunca escribe código de producción — `project-contract.md` es su única salida
- Nunca inventa hechos de negocio, reseñas, precios ni credenciales

### Agente de Desarrollo — `Agents/developer-agent.md`

Un desarrollador web senior agnóstico de frameworks.

- Construye el sitio web descrito por `project-contract.md`
- Trata el contrato de proyecto como la única fuente de verdad (el contrato de ventas no puede anularlo)
- Es dueño de todas las decisiones técnicas: stack, estructura, estilos y herramientas
- Elige la tecnología más simple que entregue la experiencia requerida
- Preserva la fidelidad del diseño y documenta cualquier desviación del contrato

## Contratos

### `Contracts/sales-contract.md`

La fuente de verdad comercial para un solo prospecto. Se mantiene a lo largo de todo el proceso de ventas. Cubre:

- Perfil del prospecto e investigación del negocio
- Evaluación de la presencia digital actual
- Oportunidad e hipótesis comercial
- Puntaje de calificación
- Estrategia de outreach e historial de mensajes
- Registro de conversaciones, objeciones y señales de compra
- Estado comercial y próxima acción
- **Design Handoff** — la interfaz entre el Agente de Ventas y el Agente de Diseño

### `Contracts/project-contract.md`

La especificación autoritativa del sitio web para un solo proyecto. Cubre:

- Objetivo del negocio y del proyecto, conversión primaria y secundaria
- Marca, posicionamiento y dirección visual
- Sistema de diseño (colores, tipografía, características visuales)
- Arquitectura del sitio y especificaciones de cada página
- Navegación, componentes, interacciones y comportamiento responsive
- Requisitos de contenido y funcionalidad
- Supuestos y criterios de aceptación

## Principios de diseño

- **Sin hechos inventados.** Los agentes nunca inventan reseñas, precios, certificaciones, premios ni afirmaciones de resultados. Las hipótesis siguen siendo hipótesis.
- **Primero la conversión.** Cada sitio web debe definir una conversión primaria clara.
- **Límites de rol claros.** Cada agente es dueño de su etapa y no interviene en la siguiente.
- **Sin sobre-ingeniería.** El desarrollador usa la tecnología más simple que resuelve el trabajo.
- **El humano al control.** El humano aprueba toda la comunicación externa y las decisiones comerciales.

## Estructura del proyecto

```
Webeloper/
├── Agents/
│   ├── designer-agent.md    # Diseña sitios web → escribe project-contract.md
│   ├── developer-agent.md   # Construye sitios web desde project-contract.md
│   └── sales-agent.md       # Prospecta y vende → mantiene sales-contract.md
├── Contracts/
│   ├── project-contract.md  # Plantilla de especificación de implementación (salida del Diseñador)
│   └── sales-contract.md    # Plantilla de especificación comercial (salida de Ventas)
└── logo.png                 # Logo del proyecto
```

## Primeros pasos

Los agentes de Webeloper están definidos como agentes markdown de [opencode](https://opencode.ai). Puedes usarlos con opencode o adaptarlos a cualquier runtime de agentes que soporte definiciones de agentes en markdown.

### 1. Instalar los agentes

Coloca los archivos de los agentes en tu directorio de agentes de opencode:

- **Por proyecto:** `.opencode/agents/`
- **Globalmente:** `~/.config/opencode/agents/`

```bash
# ejemplo por proyecto
mkdir -p .opencode/agents
cp Agents/*.md .opencode/agents/
```

### 2. Inicializar los contratos

Copia las plantillas de contrato al proyecto en el que estás trabajando:

```bash
cp Contracts/sales-contract.md .
cp Contracts/project-contract.md .
```

### 3. Ejecutar el pipeline

Abre opencode en el proyecto y maneja el flujo con los agentes:

- **Prospección:** "encontrá 10 gimnasios en Buenos Aires" → el Agente de Ventas descubre y califica prospectos.
- **Seleccionar un prospecto:** "hacemos el 02" → el Agente de Ventas prepara su `sales-contract.md` y el Design Handoff.
- **Diseñar:** pasale el Design Handoff al Agente de Diseño → produce el `project-contract.md`.
- **Desarrollar:** pasale el `project-contract.md` al Agente de Desarrollo → construye el sitio web funcional.

## Requisitos

- [opencode](https://opencode.ai) (u otro runtime que soporte definiciones de agentes en markdown)
- Un proveedor de modelos configurado
- Las plantillas de `Contracts/` (empieza con las copias de este repo)

## Contribuciones

Las contribuciones son bienvenidas. Consulta [CONTRIBUTING.md](CONTRIBUTING.md) para las pautas.

## Apoya el proyecto

Si Webeloper te resulta útil, puedes invitarme un cafecito o una propina:

- [Invítame un cafecito en Cafecito](https://cafecito.app/mrnandz) ☕
- [Apóyame en Ko-fi](https://ko-fi.com/mrnandz) ☕

Cualquier aporte ayuda a seguir mejorando el proyecto. ¡Gracias!

## Licencia

Este proyecto se publica bajo la [Licencia MIT](LICENSE).
