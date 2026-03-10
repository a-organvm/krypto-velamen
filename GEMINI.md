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

**Organ:** ORGAN-II (Art) | **Tier:** standard | **Status:** PUBLIC_PROCESS
**Org:** `organvm-ii-poiesis` | **Repo:** `krypto-velamen`

### Edges
- *No inter-repo edges declared in seed.yaml*

### Siblings in Art
`core-engine`, `performance-sdk`, `example-generative-music`, `metasystem-master`, `example-choreographic-interface`, `showcase-portfolio`, `archive-past-works`, `case-studies-methodology`, `learning-resources`, `example-generative-visual`, `example-interactive-installation`, `example-ai-collaboration`, `docs`, `a-mavs-olevm`, `a-i-council--coliseum` ... and 14 more

### Governance
- Consumes Theory (I) concepts, produces artifacts for Commerce (III).

*Last synced: 2026-03-08T20:11:34Z*

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


## Active Directives

| Scope | Phase | Name | Description |
|-------|-------|------|-------------|
| system | any | prompting-standards | Prompting Standards |
| system | any | research-standards-bibliography | APPENDIX: Research Standards Bibliography |
| system | any | research-standards | METADOC: Architectural Typology & Research Standards |
| system | any | sop-ecosystem | METADOC: SOP Ecosystem — Taxonomy, Inventory & Coverage |
| system | any | autopoietic-systems-diagnostics | SOP: Autopoietic Systems Diagnostics (The Mirror of Eternity) |
| system | any | cicd-resilience-and-recovery | SOP: CI/CD Pipeline Resilience & Recovery |
| system | any | cross-agent-handoff | SOP: Cross-Agent Session Handoff |
| system | any | document-audit-feature-extraction | SOP: Document Audit & Feature Extraction |
| system | any | essay-publishing-and-distribution | SOP: Essay Publishing & Distribution |
| system | any | market-gap-analysis | SOP: Full-Breath Market-Gap Analysis & Defensive Parrying |
| system | any | pitch-deck-rollout | SOP: Pitch Deck Generation & Rollout |
| system | any | promotion-and-state-transitions | SOP: Promotion & State Transitions |
| system | any | repo-onboarding-and-habitat-creation | SOP: Repo Onboarding & Habitat Creation |
| system | any | research-to-implementation-pipeline | SOP: Research-to-Implementation Pipeline (The Gold Path) |
| system | any | security-and-accessibility-audit | SOP: Security & Accessibility Audit |
| system | any | session-self-critique | session-self-critique |
| system | any | source-evaluation-and-bibliography | SOP: Source Evaluation & Annotated Bibliography (The Refinery) |
| system | any | stranger-test-protocol | SOP: Stranger Test Protocol |
| system | any | strategic-foresight-and-futures | SOP: Strategic Foresight & Futures (The Telescope) |
| system | any | typological-hermeneutic-analysis | SOP: Typological & Hermeneutic Analysis (The Archaeology) |

Linked skills: evaluation-to-growth


**Prompting (Google)**: context 1M tokens (Gemini 1.5 Pro), format: markdown, thinking: thinking mode (thinkingConfig)

<!-- ORGANVM:AUTO:END -->


## ⚡ Conductor OS Integration
This repository is a managed component of the ORGANVM meta-workspace.
- **Orchestration:** Use `conductor patch` for system status and work queue.
- **Lifecycle:** Follow the `FRAME -> SHAPE -> BUILD -> PROVE` workflow.
- **Governance:** Promotions are managed via `conductor wip promote`.
- **Intelligence:** Conductor MCP tools are available for routing and mission synthesis.
