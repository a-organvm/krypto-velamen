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


**Prompting (Anthropic)**: context 200K tokens, format: XML tags, thinking: extended thinking (budget_tokens)


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