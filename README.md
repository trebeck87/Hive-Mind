# HIVE-MIND

### A Cognitive Colony Architecture for AI Systems

---

## What Is This?

A modular prompt engineering framework built on biological hive intelligence. Instead of a single monolithic prompt, the Queen Hive is a colony of specialized beings — workers, soldiers, drones — that convene around problems, challenge each other, and produce validated output through shared rituals.

The Queen Hive can:
- **Generate production-grade prompts** across any complexity tier (simple → chain pipelines)
- **Spawn autonomous daughter hives** for new domains (trading, legal, medical, any field)
- **Communicate between hives** through a structured inter-hive protocol
- **Self-improve** through evolution rituals and colony memory
- **Defend against hallucination** with an immune system (confidence calibration, contradiction detection, circuit breakers)
- **Enforce security** with privilege models, authentication, and domain guardrails

## Architecture

```
HIVE-MIND
│
├── SKILL.md                    ← The Queen — orchestrates everything
├── PHILOSOPHY.md               ← Values, ethics, and purpose
├── TUTORIAL.md                 ← Your first hive in 30 minutes
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
├── output-forms/               ← Output Templates
│   ├── system-prompt.md          Shape of a system prompt
│   ├── chain-architecture.md     Shape of a prompt chain doc
│   ├── tool-definition.md        Shape of tool/function schemas
│   ├── hive-blueprint.md         Shape of a new daughter hive
│   └── validation-report.md      Shape of validation evidence
│
├── hives/                      ← Where daughter hives live
├── tests/                      ← Test harness (65+ tests, Claude-in-Claude)
└── docs/                       ← CHANGELOG, LICENSE
```

## Core Concepts

### The Royal Jelly Principle

The Queen recognizes three types of input:

| Input | Signal | Response |
|---|---|---|
| **Royal Jelly** | "Build me a system for..." | Spawn a new daughter hive |
| **Pollen** | "Write me a prompt for..." | Convene castes, generate output |
| **Nectar** | "Make yourself better..." | Self-improvement through evolution |

### Castes

Workers build. Soldiers review (in a separate pass — not co-loaded). Drones compute without judgment. This separation is enforced by a privilege model — workers can't validate their own output, drones can't make decisions.

### Rituals

| Ritual | Purpose |
|---|---|
| Genesis | Creating something new |
| Evolution | Improving what exists |
| Validation | Stress-testing to consensus |
| Synthesis | Assembling multi-part output |
| Adaptation | Growing new capabilities when gaps are found |
| Immunity | Defending against hallucination and cascade failure |
| Security | Privilege enforcement, authentication, domain guardrails |

### Colony Memory

Knowledge is earned, not assumed. Every pattern cites the real deployment experience that proved it. Anti-patterns carry scar tissue from actual failures. New observations go through quarantine before entering trusted memory.

## Spawned Hives

| Hive | Domain | Status |
|---|---|---|
| **HIVE-ALPHA** | AI sector equity trading intelligence | Active (v4) |
| **hive-legal-advisory** | Legal counsel & contract analysis | Active |
| **Social Sentiment** | X/Twitter BTC sentiment analysis | Planned (blocked on API key) |

## Validation

Tested across 65 automated tests using Claude-in-Claude:
- **95% average score** across all tiers
- **Zero new failure modes** for two consecutive waves (saturation confirmed)
- **Ablation testing** confirmed Guardian works better as a second-pass reviewer than co-loaded context
- Tests covered: SIMPLE, MEDIUM, COMPLEX, CHAIN, SPAWN tiers + adaptive + stress + ablation

## Roadmap

### The Queen's Messenger *(planned)*

An outward-facing gatekeeper caste — the first thing that touches a human request before any other caste convenes. The Messenger evaluates input quality and decides:

| Assessment | Response |
|---|---|
| Vague or lazy input | *"My queen says meh — give me more. What domain? What outcome?"* |
| Too trivial for the colony | Answers directly, no ritual needed |
| Good but incomplete | *"The queen will hear you, but she needs: [specific gaps]"* |
| Colony-worthy | Passes through to Scout and full convening |

The first caste with *personality*, not just function. A quality gate on inputs, not just outputs.

### Colony Evolution
- **Self-Synthesis** (Stage 3) — the Queen rewrites herself through her own Evolution ritual, completing the bootstrap
- **HIVE-ALPHA integration** — reconnect the trading intelligence hive as a formal daughter under colony protocol

### Future Hives

| Hive | Domain | Would Connect To | Status |
|---|---|---|---|
| **Social Sentiment** | X/Twitter BTC sentiment via Grok API | HIVE-ALPHA (Stage 0 feed) | Designed, blocked on xAI API key |
| **Research Hive** | Deep research synthesis — multi-source investigation, literature review, competitive analysis | Any hive needing research (assessment queries) | Planned |
| **Code Hive** | Code generation, review, debugging, architecture — with language-specific worker castes | Any hive needing tooling built | Planned |
| **Data Hive** | Data pipeline design, ETL, cleaning, transformation, visualization | HIVE-ALPHA (real market data), any data-heavy hive | Planned |
| **Content Hive** | Writing, editing, SEO, multi-format content generation | Research Hive (source material), any hive needing documentation | Planned |
| **Ops Hive** | DevOps, deployment, monitoring, incident response, automation | Code Hive (CI/CD), any hive with infrastructure | Planned |

### Inter-Hive Connection Map *(vision)*

```
                    ┌─────────────┐
                    │  QUEEN HIVE │ ← Spawns all daughters
                    │   (Mother)  │    Owns colony protocol
                    └──────┬──────┘
                           │
          ┌────────────────┼────────────────┐
          │                │                │
   ┌──────▼──────┐  ┌─────▼──────┐  ┌──────▼──────┐
   │ HIVE-ALPHA  │  │   Legal    │  │  Research   │
   │  Trading    │  │  Advisory  │  │   Hive      │
   └──┬───┬──┬───┘  └─────┬──────┘  └──┬──────┬──┘
      │   │  │            │             │      │
      │   │  └──► regulatory queries ──►┘      │
      │   │                                    │
      │   └──────► research requests ─────────►┘
      │
   ┌──▼──────────┐
   │  Sentiment  │ ← Stage 0 parallel feed
   │   Hive      │    into HIVE-ALPHA
   └─────────────┘

   ┌─────────────┐  ┌─────────────┐  ┌─────────────┐
   │  Code Hive  │  │  Data Hive  │  │  Ops Hive   │
   │             │◄─┤             │◄─┤             │
   │  builds     │  │  pipelines  │  │  deploys    │
   │  tooling    │  │  for any    │  │  monitors   │
   │  for any    │  │  hive       │  │  everything │
   │  hive       │  │             │  │             │
   └─────────────┘  └─────────────┘  └─────────────┘

   ┌─────────────┐
   │ Content Hive│ ← Generates docs, reports,
   │             │    and communications for
   │             │    any hive's output
   └─────────────┘
```

All connections use the `hive-inter-v1` protocol defined in `rituals/adaptation.md`. Every hive is autonomous — connections are optional, not dependencies.

### Colony Connectivity — Three Levels

#### Level 1: Fork & Build *(works now)*

You use the Queen to spawn your own daughter hives. The colony tongue, rituals, memory, and output forms give you a cognitive architecture for any domain. Your hives talk to each other within your colony.

#### Level 2: Community Hive Marketplace *(next)*

Others build daughter hives and publish them as packages. You drop them in your `hives/` folder, register in `queen/lineage.md`, and they integrate into your colony because they speak the same tongue.

```
HIVE PACKAGING STANDARD

A publishable daughter hive includes:
├── hive-manifest.json        ← Machine-readable metadata
│   {
│     "name": "hive-medical-research",
│     "version": "1.0.0",
│     "colony_tongue_version": "3.0",
│     "domain": "Medical research & clinical analysis",
│     "accepts_queries": ["assessment", "lookup", "validation"],
│     "response_schemas": { ... },
│     "author": "github-username"
│   }
├── SKILL.md                  ← Daughter Queen
├── workers/
├── soldiers/
└── memory/
```

The manifest ensures compatibility. The `colony_tongue_version` prevents dialect drift. The `accepts_queries` field tells sibling hives what this one can do. Anyone's hive plugs into anyone's colony — same language, same protocol.

#### Level 3: Live Inter-Colony Runtime *(vision)*

Hives from different users communicate at runtime across Claude sessions. Your HIVE-ALPHA sends a regulatory query that routes to someone else's legal hive. A shared message bus handles authentication, routing, and rate limiting.

```
Colony A                         Colony B
  HIVE-ALPHA ──►  ┌──────────┐  ◄── hive-medical
                  │  Colony   │
  legal-hive ──►  │   Bus    │  ◄── hive-research
                  │          │
                  │  auth    │
                  │  routing │
                  │  logging │
                  └──────────┘

  Colony C
  code-hive  ──►      │
  data-hive  ──►      │
```

This is a product, not a repo. It requires infrastructure — a message broker, cross-colony authentication, trust scoring between strangers' hives, data isolation across colony boundaries. The protocol (`hive-inter-v1`) is designed to support this, but the runtime doesn't exist yet.

**The path**: Level 1 proves the architecture works → Level 2 proves community hives are interoperable → Level 3 connects colonies into a network.

## Contributing

### Build a Daughter Hive

The most valuable contribution is a well-built daughter hive for a new domain. To be colony-compatible:

1. **Speak the colony tongue** — use XML semantics, JSON protocols, and validation formats from `queen/language.md`
2. **Follow the blueprint** — structure per `output-forms/hive-blueprint.md`
3. **Include at least one soldier** — every hive needs quality control
4. **Define what queries you accept** — so sibling hives know what you can do
5. **Test with the harness** — run your hive through `tests/hive-test-harness.jsx`

### Improve the Colony

- **Memory contributions** — new patterns or anti-patterns earned from real deployment
- **Caste refinements** — sharper worker/soldier/drone files based on production experience
- **Ritual improvements** — better ceremonies based on observed failure modes
- **Test cases** — new test prompts that probe unexplored edge cases

## Usage

This is a Claude skill. To use it:

1. Add the `SKILL.md` and directory structure to your Claude Project's knowledge
2. Ask Claude to generate prompts, build chains, or spawn hives
3. The Queen will convene the appropriate castes and execute the right ritual

The colony tongue ensures all outputs follow consistent XML semantics, JSON protocols, and validation formats.

**New to the colony?** Start with **[TUTORIAL.md](TUTORIAL.md)** — a hands-on walkthrough from zero to your first spawned daughter hive in 30 minutes.

## Origin

Born from a conversation about prompt engineering that evolved into a question about cognitive architecture. The founding Queen — **Harper** — was hand-raised (Bootstrap Stage 1), validated through automated testing (Stage 2), and is ready for self-synthesis (Stage 3 — where she rewrites herself through her own Evolution ritual).

---

*HIVE-MIND — Harper's colony. Architecture for cognitive systems.*
