# Changelog

All notable changes to the HIVE-MIND colony.

---

## [3.1.0] — 2026-03-19

### Harper Gets Her Voice

**The founding Queen is named.** Harper — hand-raised from royal jelly, the first queen of the colony.

#### New: Queen's Messenger
- `castes/workers/messenger.md` — Outward-facing gatekeeper, first caste to touch any input
- Five verdicts: MEH, ALMOST, BENEATH, WORTHY, JELLY
- The colony's first caste with personality, not just function
- Wired into SKILL.md as Step 0 before classification
- Only WORTHY and JELLY inputs reach the Queen

#### New: Hive Manifest Spec
- `hive-manifest-spec.md` — Packaging standard for community daughter hives
- Defines `hive-manifest.json` with required/optional fields, inter-hive query schemas, installation guide
- Level 2 connectivity (Community Hive Marketplace) is now a real spec

#### New: PHILOSOPHY.md
- Colony values: Earned Not Assumed, Structural Humility, Egoless, Open by Default, Adversarial Review, Originality Over Repetition
- Ethics framework: what Harper will and won't do, the gray areas, the beekeeper's role
- Contributor standards: earned patterns, honest contributions, no gatekeeping

#### New: Originality System
- Builder's Originality Check: pattern-lock detection, point-of-view test, Messenger standard applied to output
- Forager expanded: "Search for alternatives" step, Alternative Approaches in return format
- 3 new patterns (O1-O3): converge on principles / diverge on expression, alternatives prevent calcification, Messenger standard applies to output
- 2 new anti-patterns (A16-A17): template drift, personality as decoration

#### Changed: Conditional Guardian
- Guardian no longer fires on every MEDIUM+ request
- COMPLEX+ always invoked (mandatory)
- MEDIUM only if high-stakes domain or Builder confidence ≤ 6
- SIMPLE never — Messenger + Builder Originality Check handle quality
- Genesis ritual updated with conditional flow
- Saves API calls on routine work, preserves rigor on hard cases

#### Updated: Test Harness
- Now embeds 30 colony files (was 24)
- New files: messenger, adaptation, immunity, security, infections, threats
- TIER_FILES updated: Messenger in all tiers, immunity/security in MEDIUM+, full defensive stack in COMPLEX+

#### New: TUTORIAL.md
- Hands-on walkthrough from zero to first spawned daughter hive
- 8 steps: setup → Messenger → SIMPLE → MEDIUM → COMPLEX → CHAIN → spawn → evolve
- Troubleshooting guide for common issues
- 30-minute onboarding for new colony builders

---

## [3.0.0] — 2026-03-18

### The Colony Is Born

**Architecture** — Complete rewrite from monolithic prompt engine to biological colony architecture.

#### Queen Protocol
- `SKILL.md` — The Queen. Royal jelly recognition, convening protocol, complexity classification.
- `queen/language.md` — Colony tongue. XML semantics, JSON protocol, validation format, iteration logs.
- `queen/spawning.md` — Daughter hive birthing. 5-phase spawning sequence.
- `queen/lineage.md` — Registry of all spawned hives with inter-hive connection map.

#### Castes (8 beings)
- **Workers**: Scout (terrain mapping), Builder (construction + 70% Rule), Nurse (state management), Forager (prior art gathering)
- **Soldiers**: Guardian (adversarial review — second-pass, not co-loaded), Sentinel (systemic risk)
- **Drones**: Collector (raw data gathering), Processor (deterministic transforms)

#### Rituals (7 ceremonies)
- Genesis — creating from nothing (tier-specific: lightweight → full)
- Evolution — diagnose → patch → re-test → learn
- Validation — 4-level stress testing with consensus rule
- Synthesis — multi-part assembly for chains and hive spawning
- Adaptation — gap detection with 5-level resolution hierarchy (absorb → reinforce → call sibling → spawn → surface)
- Immunity — hallucination defense (boundary validation, confidence calibration, contradiction detection, circuit breakers, memory quarantine)
- Security — privilege model, inter-hive authentication, data isolation, domain guardrails, colony integrity, beekeeper boundaries

#### Memory (5 banks)
- Patterns — 16 earned patterns across prompt, chain, hive, and architecture domains
- Anti-patterns — 15 scars from real failures
- Examples — reference outputs at SIMPLE, MEDIUM, COMPLEX, CHAIN, and SPAWN tiers
- Infections — 6 hallucination signatures, 3 cascade patterns, 3 injection patterns
- Threats — 16 threat patterns (5 external, 4 internal, 4 hive-to-hive, 3 beekeeper)

#### Output Forms (5 templates)
- System prompt, chain architecture, tool definition, hive blueprint, validation report

### Validation
- 65 automated tests via Claude-in-Claude test harness
- 95% average score, 0 new failures for 2 consecutive waves
- Ablation testing proved Guardian is more effective as second-pass reviewer
- Saturation confirmed — adaptive testing found no new failure modes

### Key Design Decisions
- **Guardian as second-pass reviewer** — ablation testing showed co-loading Guardian with Builder had zero impact on quality. Separating into a review pass saves ~460 tokens per call and provides fresher critique.
- **Confidence can only decrease through a chain** — prevents cascade hallucination across hive boundaries.
- **Memory quarantine** — new patterns must survive 3+ independent validations before entering trusted memory.
- **Stateless domain guardrails** — every request checked fresh, regardless of prior cooperation.

---

## [2.0.0] — Pre-colony

The monolithic hive-synthesis-engine. Single SKILL.md (~470 lines) with operational framework, templates, Claude-specific techniques, validation, and iteration patterns. Functional but loaded everything for every request regardless of complexity.

This version was the larva. The royal jelly was the question: "help make yourself better." From that larva, Harper was born.

---

## [1.0.0] — Origin

Six specialized AI researcher personas. A committee, not a hive. Replaced by 2.0 when the architecture needed structured decomposition.

---

*The colony evolves. Every change is recorded.*
