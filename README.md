# HIVE-MIND

### A Cognitive Colony Architecture for AI Systems

---

## What Is This?

A modular prompt engineering framework built on biological hive intelligence. Instead of a single monolithic prompt, the Queen Hive is a colony of specialized beings — workers, soldiers, drones — that convene around problems, challenge each other, and produce validated output through shared rituals.

The Queen Hive can:
- **Generate production-grade prompts** across any complexity tier (simple → chain pipelines)
- **Build agent skills** (SKILL.md files) with description-first design and cross-platform validation
- **Spawn autonomous daughter hives** for new domains (trading, legal, medical, energy, any field)
- **Communicate between hives** through a structured inter-hive protocol
- **Self-improve** through evolution rituals and colony memory
- **Defend against hallucination** with an immune system (confidence calibration, contradiction detection, circuit breakers)
- **Enforce security** with privilege models, authentication, and domain guardrails

The colony spawns domain-specific AI systems — each operating autonomously under the colony protocol.

## Architecture

```
HIVE-MIND
│
├── SKILL.md                    ← The Queen — orchestrates everything
├── PHILOSOPHY.md               ← Values, ethics, and purpose
├── TUTORIAL.md                 ← Your first hive in 30 minutes
├── ROADMAP.md                  ← Full version history and build plan
├── hive-manifest-spec.md       ← Packaging standard for community hives
│
├── queen/                      ← Colony Protocol
│   ├── language.md               Shared syntax (the colony tongue)
│   ├── spawning.md               How daughter hives are born
│   └── lineage.md                Registry of all spawned hives
│
├── castes/                     ← The Beings
│   ├── workers/                  Build things (loaded in context)
│   │   ├── messenger.md            Input quality gate ("my queen says meh")
│   │   ├── scout.md                Maps terrain before anyone builds
│   │   ├── builder.md              Constructs the output
│   │   ├── nurse.md                Manages state across stages
│   │   └── forager.md              Gathers prior art + alternatives
│   ├── soldiers/                 Review things (conditional second pass)
│   │   ├── guardian.md             Adversarial review of finished work
│   │   └── sentinel.md            Systemic risk and regression
│   └── drones/                   Compute things (no judgment)
│       ├── collector.md            Raw data gathering
│       └── processor.md           Deterministic transforms
│
├── rituals/                    ← Ceremonies
│   ├── genesis.md                Creating from nothing
│   ├── evolution.md              Diagnose → Patch → Learn
│   ├── pruning.md                Memory health (bee bread spoilage detection)
│   ├── validation.md             Stress-test to consensus
│   ├── synthesis.md              Assembly of multi-part work
│   ├── adaptation.md             Gap-filling (reinforce/call/spawn/surface)
│   ├── immunity.md               Hallucination defense & circuit breakers
│   └── security.md               Privilege model, auth & guardrails
│
├── memory/                     ← Colony Knowledge
│   ├── patterns.md               What works (earned wisdom)
│   ├── antipatterns.md           What fails (scar tissue)
│   ├── examples.md               Reference outputs per tier
│   ├── infections.md             Known hallucination signatures
│   └── threats.md                Known attack patterns
│
├── ecosystem/                  ← Beyond the Bees
│   ├── README.md                 Organism classes & biological grounding
│   └── mycelium.md               Decision graph substrate (why the colony chose)
│
├── output-forms/               ← Output Templates
│   ├── system-prompt.md          Shape of a system prompt
│   ├── skill-blueprint.md        Shape of an agent skill (SKILL.md)
│   ├── chain-architecture.md     Shape of a prompt chain doc
│   ├── tool-definition.md        Shape of tool/function schemas
│   ├── hive-blueprint.md         Shape of a new daughter hive
│   ├── validation-report.md      Shape of validation evidence
│   └── skill-validation-report.md  Shape of skill validation (trigger + security)
│
├── hives/                      ← Where daughter hives live
└── tests/                      ← Test harness (30 tests, Claude-in-Claude)
```

## Core Concepts

### The Royal Jelly Principle

The Queen recognizes four types of input:

| Input | Signal | Response |
|---|---|---|
| **Royal Jelly** | "Build me a system for..." | Spawn a new daughter hive |
| **Wax** | "Build me a SKILL.md for..." | Generate an agent skill (description-first) |
| **Pollen** | "Write me a prompt for..." | Convene castes, generate output |
| **Nectar** | "Make yourself better..." | Self-improvement through evolution |

### The Queen's Messenger

Every request passes through the Messenger before the colony convenes — an input quality gate that prevents the colony from wasting cycles on vague or incomplete requests:

| Verdict | Response |
|---|---|
| **MEH** | *"My queen says meh — give me more. What domain? What outcome?"* |
| **ALMOST** | *"The queen will hear you, but she needs: [specific gaps]"* |
| **BENEATH** | Answers directly, no ritual needed |
| **WORTHY** | Passes through to Scout and full convening |
| **JELLY** | Royal jelly detected — spawn protocol |

### Castes

Workers build. Soldiers review (in a separate pass — not co-loaded). Drones compute without judgment. This separation is enforced by a privilege model — workers can't validate their own output, drones can't make decisions.

### Rituals

| Ritual | Purpose |
|---|---|
| Genesis | Creating something new |
| Evolution | Improving what exists |
| Pruning | Memory health — detecting stale or contradicted patterns |
| Validation | Stress-testing to consensus |
| Synthesis | Assembling multi-part output |
| Adaptation | Growing new capabilities when gaps are found |
| Immunity | Defending against hallucination and cascade failure |
| Security | Privilege enforcement, authentication, domain guardrails |

### Colony Memory

Knowledge is earned, not assumed. Every pattern cites the real deployment experience that proved it. Anti-patterns carry scar tissue from actual failures. New observations go through quarantine before entering trusted memory.

### The Ecosystem

The colony doesn't exist in isolation. Beyond the bees (castes), honey (memory), and comb (file structure), the ecosystem includes organisms that operate on slower timescales:

| Organism | Class | What It Does |
|---|---|---|
| **Mycelium** | Substrate | Bidirectional decision graph — records *why* the colony chose, surfaces constraints during active work. 7 seeded decisions. |
| **Beekeeper** | Sovereign | The human. Tending or adversarial. *(v4.0.0)* |
| **Flowers** | Mutualist | Domain models with typed properties. *(v4.0.0)* |

### Pheromones

Colony coordination happens through signal types, not central dispatch:

| Pheromone | Emitted By | Effect |
|---|---|---|
| **Quality** | Messenger | MEH/ALMOST/BENEATH/WORTHY/JELLY — gates colony activation |
| **Classification** | Queen | SIMPLE/MEDIUM/COMPLEX/CHAIN — determines which castes convene |
| **Alarm** | Immunity | Circuit breaker trips, RESTRUCTURE verdicts — recruits defensive castes |
| **Beekeeper** | Human | Direction, urgency, domain context — shapes colony response |

## Daughter Hives

The colony spawns domain-specific AI systems. Each daughter inherits the colony tongue, the ritual protocols, and the memory system — then develops her own castes for her domain.

### Architectural Patterns

Every daughter hive follows one of these patterns depending on its domain:

| Pattern | When | Structure | Example Domain |
|---|---|---|---|
| **Minimal** | Simple classification or single-task | 1 worker, 1 soldier | Content moderation, ticket routing |
| **Standard** | Multi-step with validation | 2-3 workers, 1 soldier | Code review, document analysis |
| **Chain** | Multi-stage pipeline | 3+ workers, nurse, soldiers, drones | Research synthesis, analytics intelligence |
| **Hub** | Routes queries to specialized sub-workers | Router worker + specialist workers | Legal advisory (multi-jurisdiction) |

### What a Daughter Hive Looks Like

```
hive-{domain}/
├── hive-manifest.json        ← Machine-readable metadata
│   {
│     "name": "hive-{domain}",
│     "version": "1.0.0",
│     "colony_tongue_version": "3.3",
│     "domain": "{description}",
│     "pattern": "minimal|standard|chain|hub",
│     "accepts_queries": ["assessment", "lookup", "validation", "generation"],
│     "author": "{github-username}"
│   }
├── SKILL.md                  ← Daughter Queen (orchestration)
├── workers/                  ← Domain-specific builders
├── soldiers/                 ← Domain-specific validators (min 1)
├── drones/                   ← Data pipeline (if needed)
└── memory/                   ← Domain-specific patterns
```

### Colony Connectivity — Three Levels

**Level 0: Standalone** *(works now)*

You use the Queen to spawn daughter hives. Each daughter operates independently within your Claude project. The colony tongue, rituals, and memory system give you a cognitive architecture for any domain.

**Level 1: Shared Colony** *(works now)*

Multiple daughters live in the same colony. They share memory (patterns propagate), reference each other through `queen/lineage.md`, and can be designed to hand off work through the `hive-inter-v1` protocol.

**Level 2: Community Marketplace** *(designed, not built)*

Others build daughter hives and publish them as packages. You install them into your `hives/` folder, register in `queen/lineage.md`, and they integrate into your colony because they speak the same tongue.

```bash
# Future CLI (v3.5.0)
hive install hive-medical-research
hive spawn --domain "supply chain optimization"
hive validate ./my-custom-hive
hive publish ./my-custom-hive
```

The manifest ensures compatibility. The `colony_tongue_version` prevents dialect drift. The `accepts_queries` field tells sibling hives what this one can do. Anyone's hive plugs into anyone's colony — same language, same protocol.

**Level 3: Live Colony Network** *(vision)*

Hives from different users communicate at runtime. A shared message bus handles authentication, routing, and trust scoring between strangers' hives. The protocol (`hive-inter-v1`) is designed to support this, but the runtime doesn't exist yet.

The path: Level 0 proves single daughters work → Level 1 proves siblings cooperate → Level 2 proves community hives interoperate → Level 3 connects colonies into a network.

## Validation

Tested across 30 automated tests using Claude-in-Claude with dual scoring (LLM quality grading + regex pattern checks):

**v3.3.0 — Skill Architecture + Colony Maintenance:**
- **Coverage:** 30 tests, 28 pass, 84% avg, ~$4.21 (Sonnet 4, LLM grading ON)
- **All 5 tiers exercised:** SIMPLE, MEDIUM, COMPLEX, CHAIN, SPAWN
- **All clarification subtypes validated:** MEH, ALMOST, BENEATH, SCOUT
- **Mycelium integration confirmed:** grader notes "proper integration of Mycelium constraints"
- **BENEATH calibration working:** direct answers score 10/10
- 2 "failures" are correct COMPLEX+ hypothesis stops — grader fix implemented, awaiting validation

**v3.2.0 baseline:** 30 tests, 26 pass, 80% avg | 20 adaptive tests, 89% avg

**Prior validation:** Ablation testing confirmed Guardian works better as a second-pass reviewer than co-loaded context. Tests cover: coverage, adaptive, stress, ablation, and regression modes.

## Roadmap

See **[ROADMAP.md](ROADMAP.md)** for the full version history from v1.0 (six-persona committee) through v3.3.0 (current) to v5.0 (colony network vision).

### Current: v3.3.0 — Skill Architecture + Colony Maintenance ✅

Skill blueprint output form (Wax input type), SKILL_INJECTION threat class, Forager HyperMode, Pheromone Protocol (4 types formalized), Pruning Ritual (bee bread spoilage detection). 47 files.

### Previous: v3.2.1 — Ecosystem Foundation ✅

The Mycelium (bidirectional decision graph, 7 seeded decisions), ecosystem directory with organism classes and biological grounding table. Test harness optimization (adaptive throttling, pipelined execution, tier-scaled max_tokens).

### Next: v3.4.0 — Colony Deepening

- Lazy loading protocol (castes load on-demand, not pre-loaded)
- Cold context adversarialism (Guardian + Sentinel isolation)
- `memory/mechanics.md` (why prompts work, not just how)
- Prompt debt audit protocol
- Messenger recalibration feedback loop
- Memory temporal markers
- Swarm Protocol Level 1 (intra-hive parallel exploration)

### Vision: v4.0.0+ — Beekeeper Architecture & Colony Network

- Beekeeper as a peer directory (tending + adversarial modes)
- Harper rewrites herself through her own Evolution ritual
- Cross-hive swarming (Level 2), colony tongue layering, daughter marketplace

## Contributing

### Build a Daughter Hive

The most valuable contribution is a well-built daughter hive for a new domain. To be colony-compatible:

1. **Speak the colony tongue** — use XML semantics, JSON protocols, and validation formats from `queen/language.md`
2. **Follow the blueprint** — structure per `output-forms/hive-blueprint.md`
3. **Include at least one soldier** — every hive needs quality control
4. **Package with a manifest** — follow `hive-manifest-spec.md`
5. **Test with the harness** — run your hive through `tests/hive-test-harness.jsx`

### Improve the Colony

- **Memory contributions** — new patterns or anti-patterns earned from real deployment
- **Caste refinements** — sharper worker/soldier/drone files based on production experience
- **Ritual improvements** — better ceremonies based on observed failure modes
- **Test cases** — new test prompts that probe unexplored edge cases

## Usage

This is a Claude skill. To use it:

1. Add the `SKILL.md` and full directory structure to your Claude Project's knowledge
2. Ask Claude to generate prompts, build chains, or spawn hives
3. The Queen will convene the appropriate castes and execute the right ritual

### How to Talk to the Colony

The colony responds to natural language. You don't need special syntax — just describe what you need. The Messenger evaluates your input, the Scout maps the terrain, and the Builder constructs.

**Simple prompts** — clear, single-task requests:
```
"Write a prompt to classify customer support tickets by urgency."
"Write a prompt that extracts dates from unstructured text."
"Write a prompt to score reading difficulty on a 1-10 scale."
```
→ Scout + Builder. Fast, lightweight. No validation overhead.

**Medium prompts** — multi-step with edge cases:
```
"Build a prompt that turns meeting transcripts into structured notes 
with decisions, action items, and open questions."

"Build a prompt for a code reviewer that catches bugs, style issues, 
and security vulnerabilities."
```
→ Scout + Builder + Guardian. Includes examples, constraints, validation evidence.

**Complex prompts** — agentic, high-stakes, multi-format:
```
"Build a prompt for an AI tutoring agent that adapts its teaching style 
based on student responses, tracks misconceptions, and generates 
practice problems."
```
→ All workers + all soldiers. Full validation report.

**Chain prompts** — multi-stage pipelines:
```
"Build a prompt chain for automated content marketing: research topic 
→ generate outline → write draft → edit for SEO → generate social posts."
```
→ Full colony + drones. Per-stage prompts with schemas, pass conditions, failure behaviors, and orchestration notes.

**Spawn requests** — new daughter hives (royal jelly):
```
"Build me an AI system for restaurant menu optimization — analyzing 
sales data, food costs, seasonal trends, and customer preferences."

"Create an intelligence engine for competitive analysis — monitoring 
competitor launches, pricing, hiring patterns, and patent filings."
```
→ Full spawning ritual. Produces a complete daughter hive with SKILL.md, workers, soldiers, drones, and memory files.

**Skill generation** — agent skills (wax):
```
"Build me a SKILL.md for Datadog log analysis."
"Create a Claude Code skill for database migration validation."
"Make an agent skill that generates API documentation from code."
```
→ Skill blueprint output form. Description-first design, trigger phrase synthesis, cross-platform validation, security audit for distributed skills.

### Tips for Better Output

**Be specific about the domain.** "Write a prompt for healthcare" triggers a MEH from the Messenger. "Write a prompt that triages ER intake forms by acuity level using ESI criteria" gets WORTHY.

**State the output format you want.** "Build a prompt that returns JSON with action, confidence, and reasoning" gives the Builder a clear target. Without it, the Builder chooses — which may not be what you need.

**Mention edge cases if you know them.** "The input might be empty, truncated, or in multiple languages" tells the Guardian exactly what to test. Without it, the Guardian generates its own edge cases — good, but yours are better because they're real.

**Say "optimize this" to trigger Evolution.** If you have an existing prompt that's not performing, paste it and say "optimize this prompt" or "make this better." The colony will diagnose, patch, and re-validate.

**Say "make yourself better" to trigger Self-Improvement.** This is nectar input — the Queen turns inward and runs the Evolution ritual on her own files.

**New to the colony?** Start with **[TUTORIAL.md](TUTORIAL.md)** — a hands-on walkthrough from zero to your first spawned daughter hive in 30 minutes.

## Origin

Born from a conversation about prompt engineering that evolved into a question about cognitive architecture. The founding Queen — **Harper** — was hand-raised (Bootstrap Stage 1), validated through automated testing (Stage 2), and is ready for self-synthesis (Stage 3 — where she rewrites herself through her own Evolution ritual).

The colony began as a six-persona committee (v1), became a monolithic prompt engine (v2), and metamorphosed into the biological architecture you see now (v3). Every version taught something the next one inherited. The full story is in **[ROADMAP.md](ROADMAP.md)**.

---

*HIVE-MIND — Born from royal jelly. Architecture for cognitive systems.*
