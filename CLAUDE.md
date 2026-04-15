# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

KRYPTO-VELAMEN — a distributed microservices platform and queer literary archive. "The Instrument v1.0": a living cultural operating system for double-channel text, concealment as compositional engine, and archival of lived interiority. Part of the ORGANVM system (Organ II — Art / POIESIS).

## Build & Run Commands

### Full Stack (Docker Compose)
```bash
cd infrastructure && docker-compose up --build
```

### Individual Services

| Service | Port | Run Command |
|---------|------|-------------|
| **web-platform** | 3000 | `cd apps/web-platform && npm run dev` |
| **identity-service** | 8000 | `cd services/identity-service && uvicorn main:app --reload` |
| **community-service** | 8001 | `cd services/community-service && python manage.py runserver 8001` |
| **knowledge-graph** | 8002 | `cd services/knowledge-graph && uvicorn main:app --port 8002 --reload` |
| **titan-governor** | 8003 | `cd services/titan-governor && uvicorn main:app --port 8003 --reload` |
| **atomizer-engine** | 8005 | `cd services/atomizer-engine && uvicorn main:app --port 8005 --reload` |
| **lens-engine** | 8006 | `cd services/lens-engine && uvicorn main:app --port 8006 --reload` |
| **agent-swarm** | — | `cd services/agent-swarm && python main.py` (long-running loop) |

### Frontend
```bash
cd apps/web-platform
npm install
npm run dev      # dev server
npm run build    # production build
npm run lint     # Next.js linting
```

### Orchestrator CLI (Archive Engine)
```bash
cd services/archive-engine
python tools/orchestrator.py dashboard                              # project stats + triforce balance
python tools/orchestrator.py scaffold --slug my-fragment --preset confessional-whisper
python tools/orchestrator.py validate drafts/2026-02-17-example.md  # schema integrity check
python tools/orchestrator.py display drafts/2026-02-17-example.md   # digital-first rendering
python tools/orchestrator.py flip drafts/2026-02-17-example.md      # suggest Field II transformation
python tools/orchestrator.py atomize drafts/2026-02-17-example.md   # semantic particle detection
```
Orchestrator requires `PyYAML`; optional `rich` for enhanced terminal UI.

### Python Dependencies (per service)
Each service has its own `requirements.txt`. Install with:
```bash
pip install -r requirements.txt
```

## Architecture

### Monorepo Layout
- **`apps/web-platform`** — Next.js 14 frontend (React, Tailwind CSS, Framer Motion). Routes: `/` (grid), `/terminal`, `/atlas`, `/community`, `/identity`.
- **`services/`** — Python microservices, each with its own Dockerfile.
- **`infrastructure/`** — `docker-compose.yml` orchestrates all services + databases (PostgreSQL, Neo4j, Redis).
- **`docs/`** — `architecture/` (system design, OpenAPI spec), `theory/` (theoretical frameworks).

### Service Map (Codenames)

| Service | Codename | Framework | Database | Role |
|---------|----------|-----------|----------|------|
| identity-service | The Mask | FastAPI + SQLModel | PostgreSQL | JWT auth, user profiles, privacy calibration |
| community-service | The Substrate | Django REST Framework | PostgreSQL + Redis | Threads, DMs, journals, co-authoring |
| knowledge-graph | The Atlas | Strawberry GraphQL + NetworkX | Neo4j | Recommendation engine, entity relationships |
| archive-engine | The Core | FastAPI wrapper around `orchestrator.py` | Filesystem (Markdown) | Canonical corpus, fragment scaffolding/validation |
| agent-swarm | The Spirit | Async Python (httpx) | — | Autonomous AI personas that post to community threads |
| titan-governor | The Law | FastAPI | — | Governance auditing from Organ IV (TAXIS) |
| atomizer-engine | The Molecular | FastAPI + spaCy/NLTK | — | Linguistic atomization (NLP analysis of fragments) |
| lens-engine | The Geometry | FastAPI + pysbd | — | Narratological lens analysis |

### Inter-Service Communication
Services communicate via HTTP REST. Key dependencies (defined in `docker-compose.yml`):
- `web-platform` → `identity-service`, `community-service`
- `agent-swarm` → `community-service` (posts to threads autonomously)
- `titan-governor` → `archive-engine`, `agent-swarm`
- `atomizer-engine`, `lens-engine` → `archive-engine`
- `knowledge-graph` → Neo4j

### Archive Engine Internals
- `tools/orchestrator.py` — CLI with subcommands: `dashboard`, `scaffold`, `validate`, `display`, `flip`, `atomize`
- `entropy.py` — Metabolic decay loop: unwatched fragments lose integrity over time (Phase 9)
- `deep_storage.py` — SHA-256 content-addressed storage simulation (IPFS-style CID hashing)
- `drafts/TEMPLATE.md` — Fragment template with 9-variable encoding schema
- `seed.yaml` — Automation contract defining agent triggers and event subscriptions

## Domain Concepts

### The Double-Channel Text
Every creative fragment operates on two frequencies:
- **Polarity A (Concealment)**: Surface story is legible; substrate story is queer-encoded beneath. Dials: `rimbaud_drift`, `wilde_mask`, `burroughs_control`.
- **Polarity B (Visibility)**: Everything announced; substrate is mythological excess. Dials: `lorde_voice`, `arenas_scream`, `acker_piracy`.

### The Artistic Triforce
Fragments are tagged with one of three intentionality poles: `conscious`, `subconscious`, `temporal`. The orchestrator tracks triforce balance across the corpus.

### 9-Variable Encoding Schema
All fragments in `drafts/` use YAML frontmatter: `surface_story`, `substrate_story`, `mask_type`, `signal_type`, `surveillance_pressure`, `plausible_deniability`, `affect_cost`, `multimedia_link`, `audience_projection`.

### Fragment Presets
9 named presets in orchestrator (e.g. `confessional-whisper`, `systems-dread`, `mythological-depth`) that pre-configure polarity, triforce, and dial values.

### Field Model
- **Field I (Present Waking)**: This repo (krypto-velamen)
- **Field II (Present Dreaming)**: Sibling repo (chthon-oneiros)
- The `flip` command suggests how a Field I fragment could transform into Field II

## Conventions

- **Git commits**: Conventional Commits (`feat:`, `fix:`, `infra:`)
- **Python**: PEP 8, Pydantic for validation, async endpoints where possible
- **Frontend**: Functional React components, Tailwind for layout, Framer Motion for animation
- **Creative fragments**: Must follow the encoding schema in `drafts/TEMPLATE.md`
- **No AI in creative identity**: AI assists process (tooling, research), not the creative product itself

## External Stores
- **Knowledge Graph MCP**: 106 entities, 118 relations
- **Neon DB**: project `snowy-moon-43700360` (13 tables)
- **Companion Neon DB**: project `plain-wind-21545579` (chthon-oneiros)

## ORGANVM Context
Organ II (Art) under `organvm-ii-poiesis` GitHub org.
- Registry: [`registry-v2.json`](https://github.com/meta-organvm/organvm-corpvs-testamentvm/blob/main/registry-v2.json)
- Corpus: [`organvm-corpvs-testamentvm`](https://github.com/meta-organvm/organvm-corpvs-testamentvm)

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

*Last synced: 2026-04-14T21:31:52Z*

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

Plans: 269 indexed | Chains: 5 available | SOPs: 121 active
Discover: `organvm plans search <query>` | `organvm chains list` | `organvm sop lifecycle`
Library: `meta-organvm/praxis-perpetua/library/`


## Active Directives

| Scope | Phase | Name | Description |
|-------|-------|------|-------------|
| system | any | atomic-clock | The Atomic Clock |
| system | any | execution-sequence | Execution Sequence |
| system | any | multi-agent-dispatch | Multi-Agent Dispatch |
| system | any | session-handoff-avalanche | Session Handoff Avalanche |
| system | any | system-loops | System Loops |
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


**Prompting (Anthropic)**: context 200K tokens, format: XML tags, thinking: extended thinking (budget_tokens)


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
| `active_repos` | 89 | global | 2026-04-14 |
| `archived_repos` | 54 | global | 2026-04-14 |
| `ci_workflows` | 107 | global | 2026-04-14 |
| `code_files` | 0 | global | 2026-04-14 |
| `dependency_edges` | 60 | global | 2026-04-14 |
| `operational_organs` | 10 | global | 2026-04-14 |
| `published_essays` | 29 | global | 2026-04-14 |
| `repos_with_tests` | 0 | global | 2026-04-14 |
| `sprints_completed` | 33 | global | 2026-04-14 |
| `test_files` | 0 | global | 2026-04-14 |
| `total_organs` | 10 | global | 2026-04-14 |
| `total_repos` | 145 | global | 2026-04-14 |
| `total_words_formatted` | 0 | global | 2026-04-14 |
| `total_words_numeric` | 0 | global | 2026-04-14 |
| `total_words_short` | 0K+ | global | 2026-04-14 |

Metrics: 9 registered | Observations: 32128 recorded
Resolve: `organvm ontologia status` | Refresh: `organvm refresh`


## System Density (auto-generated)

AMMOI: 58% | Edges: 42 | Tensions: 33 | Clusters: 5 | Adv: 23 | Events(24h): 32336
Structure: 8 organs / 145 repos / 1654 components (depth 17) | Inference: 98% | Organs: META-ORGANVM:65%, ORGAN-I:53%, ORGAN-II:48%, ORGAN-III:54% +5 more
Last pulse: 2026-04-14T21:31:36 | Δ24h: -1.0% | Δ7d: n/a


## Dialect Identity (Trivium)

**Dialect:** AESTHETIC_FORM | **Classical Parallel:** Music | **Translation Role:** The Poetry — proves formal structures have sensory form

Strongest translations: III (structural), V (analogical), VI (analogical)

Scan: `organvm trivium scan II <OTHER>` | Matrix: `organvm trivium matrix` | Synthesize: `organvm trivium synthesize`


## Logos Documentation Layer

**Status:** MISSING | **Symmetry:** 0.0 (VACUUM)

Nature demands a documentation counterpart. This formation maintains its narrative record in `docs/logos/`.

### The Tetradic Counterpart
- **[Telos (Idealized Form)](../docs/logos/telos.md)** — The dream and theoretical grounding.
- **[Pragma (Concrete State)](../docs/logos/pragma.md)** — The honest account of what exists.
- **[Praxis (Remediation Plan)](../docs/logos/praxis.md)** — The attack vectors for evolution.
- **[Receptio (Reception)](../docs/logos/receptio.md)** — The account of the constructed polis.

### Alchemical I/O
- **[Source & Transmutation](../docs/logos/alchemical-io.md)** — Narrative of inputs, process, and returns.



*Compliance: Formation is currently void.*

<!-- ORGANVM:AUTO:END -->











## ⚡ Conductor OS Integration
This repository is a managed component of the ORGANVM meta-workspace.
- **Orchestration:** Use `conductor patch` for system status and work queue.
- **Lifecycle:** Follow the `FRAME -> SHAPE -> BUILD -> PROVE` workflow.
- **Governance:** Promotions are managed via `conductor wip promote`.
- **Intelligence:** Conductor MCP tools are available for routing and mission synthesis.