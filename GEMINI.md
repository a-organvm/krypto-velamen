# GEMINI.md — KRYPTO-VELAMEN Project Context

## Project Overview
**KRYPTO-VELAMEN** is a living cultural operating system and queer archive platform. It is a distributed, collaborative instrument designed to document, encode, and preserve queer interiority through the dialectic of the **Double-Channel Text**.

### Core Architecture
The project is organized as a **Monorepo** using a microservices architecture:

- **Apps**:
  - `apps/web-platform`: The "Surface Story." A Next.js (React) frontend featuring an interactive archive grid, a cyberpunk terminal interface, and collaborative journal tools.
- **Services**:
  - `services/identity-service`: The "Mask." A FastAPI service managing user profiles, JWT authentication, and privacy calibration.
  - `services/community-service`: The "Substrate." A Django REST Framework service for threaded discussions and collaborative co-authoring.
  - `services/knowledge-graph`: The "Atlas." A GraphQL engine (Strawberry) mapping connections between authors, mechanisms, and fragments using Neo4j.
  - `services/archive-engine`: The "Core." A Python-based engine (`orchestrator.py`) for scaffolding and validating creative fragments.
  - `services/agent-swarm`: The "Spirit." Autonomous AI agents embodying specific queer literary personas.
  - `services/titan-governor`: The "Law." A governance service (TAXIS) that audits repository health and enforces archival protocols.

---

## 🛠 Tech Stack
- **Languages**: Python 3.10+, TypeScript, SQL, Cypher (Neo4j).
- **Frameworks**: Next.js 14, FastAPI, Django, Strawberry (GraphQL).
- **Data**: PostgreSQL, Neo4j, Redis, SQLite (dev).
- **Infrastructure**: Docker Compose, GitHub Actions.
- **Styling**: Tailwind CSS, Framer Motion (glitch aesthetics).

---

## 🚀 Building and Running

### Full Stack (Docker)
The entire system can be orchestrated via Docker Compose:
```bash
cd infrastructure
docker-compose up --build
```

### Individual Services
- **Archive Engine**:
  ```bash
  cd services/archive-engine
  python tools/orchestrator.py dashboard
  ```
- **Web Platform**:
  ```bash
  cd apps/web-platform
  npm run dev
  ```
- **Identity Service**:
  ```bash
  cd services/identity-service
  uvicorn main:app --reload
  ```

---

## 📖 Development Conventions

### The Double-Channel Schema
Every creative fragment in `services/archive-engine/drafts/` must follow the 9-variable encoding schema:
1. `$SURFACE_STORY`: Legible layer.
2. `$SUBSTRATE_STORY`: Hidden queer layer.
3. `$MASK_TYPE`: Formal cover structure.
4. `$SIGNAL_TYPE`: How the substrate leaks.
5. `$SURVEILLANCE_PRESSURE`: External/internal threat level.
6. `$PLAUSIBLE_DENIABILITY`: 1-5 scale.
7. `$AFFECT_COST`: Emotional toll of hiding/exposure.
8. `$MULTIMEDIA_LINK`: ETCETER4 soundtrack/visual link.
9. `$AUDIENCE_PROJECTION`: Recorded witness recognition.

### Coding Style
- **Python**: PEP 8 compliance, Pydantic for data validation, asynchronous endpoints where possible.
- **Frontend**: Functional React components, Tailwind for layout, Framer Motion for interactive states.
- **Git**: Conventional Commits (e.g., `feat:`, `fix:`, `infra:`).

### The Field Model
- **Field I (Waking)**: `krypto-velamen` core.
- **Field II (Dreaming)**: `chthon-oneiros` (sibling project).
- **Migration**: Use `orchestrator.py flip` to suggest Field II transformations.

---

## 🤝 Contributing
Refer to `services/archive-engine/.github/CONTRIBUTING.md` for detailed guidelines on adding new author research or creative fragments.

<!-- ORGANVM:AUTO:START -->
## System Context (auto-generated — do not edit)

**Organ:** ORGAN-II (Art) | **Tier:** standard | **Status:** GRADUATED
**Org:** `organvm-ii-poiesis` | **Repo:** `krypto-velamen`

### Edges
- *No inter-repo edges declared in seed.yaml*

### Siblings in Art
`core-engine`, `performance-sdk`, `example-generative-music`, `metasystem-master`, `example-choreographic-interface`, `showcase-portfolio`, `archive-past-works`, `case-studies-methodology`, `learning-resources`, `example-generative-visual`, `example-interactive-installation`, `example-ai-collaboration`, `docs`, `a-mavs-olevm`, `a-i-council--coliseum` ... and 16 more

### Governance
- Consumes Theory (I) concepts, produces artifacts for Commerce (III).

*Last synced: 2026-05-23T00:26:31Z*

## Active Handoff Protocol

If `.conductor/active-handoff.md` exists, **READ IT FIRST** before doing any work.
It contains constraints, locked files, conventions, and completed work from the
originating agent. You MUST honor all constraints listed there.

If the handoff says "CROSS-VERIFICATION REQUIRED", your self-assessment will
NOT be trusted. A different agent will verify your output against these constraints.

## Session Review Protocol

At the end of each session that produces or modifies files:
1. Run `organvm session review --latest` to get a session summary
2. Check for unimplemented plans: `organvm session plans --project .`
3. Export significant sessions: `organvm session export <id> --slug <slug>`
4. Run `organvm prompts distill --dry-run` to detect uncovered operational patterns

Transcripts are on-demand (never committed):
- `organvm session transcript <id>` — conversation summary
- `organvm session transcript <id> --unabridged` — full audit trail
- `organvm session prompts <id>` — human prompts only


## System Library

Plans: 269 indexed | Chains: 5 available | SOPs: 8 active
Discover: `organvm plans search <query>` | `organvm chains list` | `organvm sop lifecycle`
Library: `/Users/4jp/Code/organvm/praxis-perpetua/library`


## Active Directives

| Scope | Phase | Name | Description |
|-------|-------|------|-------------|
| system | any | atomic-clock | The Atomic Clock |
| system | any | execution-sequence | Execution Sequence |
| system | any | multi-agent-dispatch | Multi-Agent Dispatch |
| system | any | session-handoff-avalanche | Session Handoff Avalanche |
| system | any | system-loops | System Loops |
| system | any | prompting-standards | Prompting Standards |
| system | any | background-task-resilience | background-task-resilience |
| system | any | context-window-conservation | context-window-conservation |
| system | any | session-self-critique | session-self-critique |
| system | any | the-descent-protocol | the-descent-protocol |
| system | any | the-membrane-protocol | the-membrane-protocol |
| system | any | theory-to-concrete-gate | theory-to-concrete-gate |
| system | any | triangulation-protocol | triangulation-protocol |

Linked skills: SOP-TRIADIC-REVIEW-PROTOCOL, cicd-resilience-and-recovery, continuous-learning-agent, evaluation-to-growth, genesis-dna, multi-agent-workforce-planner, promotion-and-state-transitions, quality-gate-baseline-calibration, repo-onboarding-and-habitat-creation, session-self-critique, structural-integrity-audit, the-membrane-protocol, triple-reference


**Prompting (Google)**: context 1M tokens (Gemini 1.5 Pro), format: markdown, thinking: thinking mode (thinkingConfig)


## Atomization Pipeline

Run `organvm atoms pipeline --write && organvm atoms fanout --write` to generate task queue.


## System Density (auto-generated)

AMMOI: 25% | Edges: 0 | Tensions: 0 | Clusters: 0 | Adv: 27 | Events(24h): 37975
Structure: 8 organs / 148 repos / 1654 components (depth 17) | Inference: 0% | Organs: META-ORGANVM:63%, ORGAN-I:53%, ORGAN-II:48%, ORGAN-III:54% +5 more
Last pulse: 2026-05-23T00:26:28 | Δ24h: n/a | Δ7d: n/a


## Dialect Identity (Trivium)

**Dialect:** AESTHETIC_FORM | **Classical Parallel:** Music | **Translation Role:** The Poetry — proves formal structures have sensory form

Strongest translations: III (structural), V (analogical), VI (analogical)

Scan: `organvm trivium scan II <OTHER>` | Matrix: `organvm trivium matrix` | Synthesize: `organvm trivium synthesize`


## Logos Documentation Layer

**Status:** ACTIVE | **Symmetry:** 0.5 (DREAM)

Nature demands a documentation counterpart. This formation maintains its narrative record in `docs/logos/`.

### The Tetradic Counterpart
- **[Telos (Idealized Form)](../docs/logos/telos.md)** — The dream and theoretical grounding.
- **[Pragma (Concrete State)](../docs/logos/pragma.md)** — The honest account of what exists.
- **[Praxis (Remediation Plan)](../docs/logos/praxis.md)** — The attack vectors for evolution.
- **[Receptio (Reception)](../docs/logos/receptio.md)** — The account of the constructed polis.

### Alchemical I/O
- **[Source & Transmutation](../docs/logos/alchemical-io.md)** — Narrative of inputs, process, and returns.



*Compliance: Record exists without implementation.*

<!-- ORGANVM:AUTO:END -->












## ⚡ Conductor OS Integration
This repository is a managed component of the ORGANVM meta-workspace.
- **Orchestration:** Use `conductor patch` for system status and work queue.
- **Lifecycle:** Follow the `FRAME -> SHAPE -> BUILD -> PROVE` workflow.
- **Governance:** Promotions are managed via `conductor wip promote`.
- **Intelligence:** Conductor MCP tools are available for routing and mission synthesis.