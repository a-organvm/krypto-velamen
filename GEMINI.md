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

*Last synced: 2026-03-25T22:27:09Z*

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
| system | any | phase-closing-and-forward-plan | METADOC: Phase-Closing Commemoration & Forward Attack Plan |
| system | any | research-standards | METADOC: Architectural Typology & Research Standards |
| system | any | sop-ecosystem | METADOC: SOP Ecosystem — Taxonomy, Inventory & Coverage |
| system | any | autonomous-content-syndication | SOP: Autonomous Content Syndication (The Broadcast Protocol) |
| system | any | autopoietic-systems-diagnostics | SOP: Autopoietic Systems Diagnostics (The Mirror of Eternity) |
| system | any | background-task-resilience | background-task-resilience |
| system | any | cicd-resilience-and-recovery | SOP: CI/CD Pipeline Resilience & Recovery |
| system | any | community-event-facilitation | SOP: Community Event Facilitation (The Dialectic Crucible) |
| system | any | context-window-conservation | context-window-conservation |
| system | any | conversation-to-content-pipeline | SOP — Conversation-to-Content Pipeline |
| system | any | cross-agent-handoff | SOP: Cross-Agent Session Handoff |
| system | any | cross-channel-publishing-metrics | SOP: Cross-Channel Publishing Metrics (The Echo Protocol) |
| system | any | data-migration-and-backup | SOP: Data Migration and Backup Protocol (The Memory Vault) |
| system | any | document-audit-feature-extraction | SOP: Document Audit & Feature Extraction |
| system | any | dynamic-lens-assembly | SOP: Dynamic Lens Assembly |
| system | any | essay-publishing-and-distribution | SOP: Essay Publishing & Distribution |
| system | any | formal-methods-applied-protocols | SOP: Formal Methods Applied Protocols |
| system | any | formal-methods-master-taxonomy | SOP: Formal Methods Master Taxonomy (The Blueprint of Proof) |
| system | any | formal-methods-tla-pluscal | SOP: Formal Methods — TLA+ and PlusCal Verification (The Blueprint Verifier) |
| system | any | generative-art-deployment | SOP: Generative Art Deployment (The Gallery Protocol) |
| system | any | market-gap-analysis | SOP: Full-Breath Market-Gap Analysis & Defensive Parrying |
| system | any | mcp-server-fleet-management | SOP: MCP Server Fleet Management (The Server Protocol) |
| system | any | multi-agent-swarm-orchestration | SOP: Multi-Agent Swarm Orchestration (The Polymorphic Swarm) |
| system | any | network-testament-protocol | SOP: Network Testament Protocol (The Mirror Protocol) |
| system | any | open-source-licensing-and-ip | SOP: Open Source Licensing and IP (The Commons Protocol) |
| system | any | performance-interface-design | SOP: Performance Interface Design (The Stage Protocol) |
| system | any | pitch-deck-rollout | SOP: Pitch Deck Generation & Rollout |
| system | any | polymorphic-agent-testing | SOP: Polymorphic Agent Testing (The Adversarial Protocol) |
| system | any | promotion-and-state-transitions | SOP: Promotion & State Transitions |
| system | any | recursive-study-feedback | SOP: Recursive Study & Feedback Loop (The Ouroboros) |
| system | any | repo-onboarding-and-habitat-creation | SOP: Repo Onboarding & Habitat Creation |
| system | any | research-to-implementation-pipeline | SOP: Research-to-Implementation Pipeline (The Gold Path) |
| system | any | security-and-accessibility-audit | SOP: Security & Accessibility Audit |
| system | any | session-self-critique | session-self-critique |
| system | any | smart-contract-audit-and-legal-wrap | SOP: Smart Contract Audit and Legal Wrap (The Ledger Protocol) |
| system | any | source-evaluation-and-bibliography | SOP: Source Evaluation & Annotated Bibliography (The Refinery) |
| system | any | stranger-test-protocol | SOP: Stranger Test Protocol |
| system | any | strategic-foresight-and-futures | SOP: Strategic Foresight & Futures (The Telescope) |
| system | any | styx-pipeline-traversal | SOP: Styx Pipeline Traversal (The 7-Organ Transmutation) |
| system | any | system-dashboard-telemetry | SOP: System Dashboard Telemetry (The Panopticon Protocol) |
| system | any | the-descent-protocol | the-descent-protocol |
| system | any | the-membrane-protocol | the-membrane-protocol |
| system | any | theoretical-concept-versioning | SOP: Theoretical Concept Versioning (The Epistemic Protocol) |
| system | any | theory-to-concrete-gate | theory-to-concrete-gate |
| system | any | typological-hermeneutic-analysis | SOP: Typological & Hermeneutic Analysis (The Archaeology) |

Linked skills: cicd-resilience-and-recovery, continuous-learning-agent, evaluation-to-growth, genesis-dna, multi-agent-workforce-planner, promotion-and-state-transitions, quality-gate-baseline-calibration, repo-onboarding-and-habitat-creation, structural-integrity-audit


**Prompting (Google)**: context 1M tokens (Gemini 1.5 Pro), format: markdown, thinking: thinking mode (thinkingConfig)


## Ecosystem Status

- **delivery**: 0/1 live, 1 planned
- **content**: 0/2 live, 0 planned

Run: `organvm ecosystem show krypto-velamen` | `organvm ecosystem validate --organ II`


## Entity Identity (Ontologia)

**UID:** `ent_repo_01KKKX3RVM8D5VBRSG1B3MRYM4` | **Matched by:** primary_name

Resolve: `organvm ontologia resolve krypto-velamen` | History: `organvm ontologia history ent_repo_01KKKX3RVM8D5VBRSG1B3MRYM4`


## Live System Variables (Ontologia)

| Variable | Value | Scope | Updated |
|----------|-------|-------|---------|
| `active_repos` | 64 | global | 2026-03-25 |
| `archived_repos` | 54 | global | 2026-03-25 |
| `ci_workflows` | 106 | global | 2026-03-25 |
| `code_files` | 0 | global | 2026-03-25 |
| `dependency_edges` | 60 | global | 2026-03-25 |
| `operational_organs` | 8 | global | 2026-03-25 |
| `published_essays` | 29 | global | 2026-03-25 |
| `repos_with_tests` | 0 | global | 2026-03-25 |
| `sprints_completed` | 33 | global | 2026-03-25 |
| `test_files` | 0 | global | 2026-03-25 |
| `total_organs` | 8 | global | 2026-03-25 |
| `total_repos` | 127 | global | 2026-03-25 |
| `total_words_formatted` | 0 | global | 2026-03-25 |
| `total_words_numeric` | 0 | global | 2026-03-25 |
| `total_words_short` | 0K+ | global | 2026-03-25 |

Metrics: 9 registered | Observations: 15536 recorded
Resolve: `organvm ontologia status` | Refresh: `organvm refresh`


## System Density (auto-generated)

AMMOI: 56% | Edges: 41 | Tensions: 33 | Clusters: 5 | Adv: 7 | Events(24h): 23754
Structure: 8 organs / 127 repos / 1654 components (depth 17) | Inference: 98% | Organs: META-ORGANVM:64%, ORGAN-I:55%, ORGAN-II:47%, ORGAN-III:55% +4 more
Last pulse: 2026-03-25T22:27:04 | Δ24h: +3.5% | Δ7d: n/a


## Dialect Identity (Trivium)

**Dialect:** AESTHETIC_FORM | **Classical Parallel:** Music | **Translation Role:** The Poetry — proves formal structures have sensory form

Strongest translations: III (structural), V (analogical), VI (analogical)

Scan: `organvm trivium scan II <OTHER>` | Matrix: `organvm trivium matrix` | Synthesize: `organvm trivium synthesize`

<!-- ORGANVM:AUTO:END -->


## ⚡ Conductor OS Integration
This repository is a managed component of the ORGANVM meta-workspace.
- **Orchestration:** Use `conductor patch` for system status and work queue.
- **Lifecycle:** Follow the `FRAME -> SHAPE -> BUILD -> PROVE` workflow.
- **Governance:** Promotions are managed via `conductor wip promote`.
- **Intelligence:** Conductor MCP tools are available for routing and mission synthesis.
