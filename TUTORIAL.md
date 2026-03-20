# Your First Hive

A hands-on walkthrough from zero to your first spawned daughter hive. Takes about 30 minutes.

---

## What You'll Need

- A Claude.ai account (Pro, Team, or Enterprise)
- The HIVE-MIND colony files (this repo)

---

## Step 1: Set Up the Colony

1. Go to [claude.ai](https://claude.ai) and create a new **Project**
2. Name it something like "HIVE-MIND" or "Harper's Colony"
3. In the Project Knowledge section, upload these files from the repo:

**Required (the minimum colony):**
```
SKILL.md
queen/language.md
castes/workers/messenger.md
castes/workers/scout.md
castes/workers/builder.md
memory/patterns.md
memory/antipatterns.md
memory/examples.md
output-forms/system-prompt.md
```

**Recommended (adds soldiers, drones, rituals for COMPLEX+ work):**
```
castes/workers/nurse.md
castes/workers/forager.md
castes/soldiers/guardian.md
castes/soldiers/sentinel.md
castes/drones/collector.md
castes/drones/processor.md
queen/spawning.md
queen/lineage.md
rituals/genesis.md
rituals/evolution.md
rituals/validation.md
rituals/synthesis.md
rituals/adaptation.md
rituals/immunity.md
rituals/security.md
memory/infections.md
memory/threats.md
output-forms/chain-architecture.md
output-forms/hive-blueprint.md
output-forms/tool-definition.md
output-forms/validation-report.md
```

You can start with just the Required files and add more as you need them. The colony scales to what's loaded.

4. Open a new conversation in the project. Harper is ready.

---

## Step 2: See the Messenger in Action

Start with something intentionally vague:

```
You: Write me a prompt
```

The Messenger should fire. You'll see something like:

> *My queen says meh. A prompt for what?*
> - *What domain?*
> - *What's the task?*
> - *What does the output look like?*
> *Come back with those and we'll build something real.*

**What just happened:** The Messenger evaluated your input as **MEH** — too vague to build from. It asked specific questions instead of producing generic output. The colony never reached the Scout or Builder.

Now try something beneath the colony:

```
You: What's a system prompt?
```

The Messenger should handle this directly — a quick answer, no ritual. Verdict: **BENEATH**.

---

## Step 3: Your First SIMPLE Prompt

Now give the colony something real but straightforward:

```
You: Write a prompt to classify customer emails as complaint, question, 
     praise, or request, and tag the urgency as high/medium/low.
```

Watch what happens:

1. **Messenger** evaluates → WORTHY (clear domain, clear task, clear output)
2. **Scout** quickly assesses → SIMPLE tier (single-turn, clear format)
3. **Builder** constructs → a clean prompt with role, task, examples

You should get a prompt that includes:
- A role statement ("You are an email classifier")
- Clear categories with definitions
- At least 2 examples showing different classifications
- No unnecessary scaffolding

**This is SIMPLE Genesis:** Messenger → Scout → Builder → Deliver. Fast, clean, no ceremony.

---

## Step 4: Level Up to MEDIUM

Add some complexity:

```
You: Build a prompt for a customer service agent that handles refund requests. 
     It needs to check if the request is within the 30-day window, verify the 
     order exists, handle partial refunds, and escalate to a human when the 
     customer is angry.
```

Now you'll see more of the colony:

1. **Messenger** → WORTHY
2. **Scout** maps terrain → MEDIUM tier (multi-step, decision points, edge cases)
3. **Forager** searches memory for relevant patterns
4. **Builder** constructs with full structure:
   - `<core_objective>` front-loaded
   - `<process>` with decision logic
   - `<constraints>` for the business rules
   - `<edge_case_handling>` for angry customers, partial refunds, expired windows
   - `<examples>` — good output + bad output (the 70% Rule)
5. **Guardian** may review if the domain triggers it (financial = high-stakes)

**This is MEDIUM Genesis.** The output is longer, more structured, and validated.

Compare it to your SIMPLE output. Same principles (role, task, examples) but different *expression* — the Builder adapted to the problem's shape, not a template.

---

## Step 5: Watch the Colony Think on COMPLEX

Push further:

```
You: Build a prompt for an AI legal assistant that reviews employment contracts, 
     identifies risky clauses (non-competes, IP assignment, termination terms), 
     compares against standard templates, rates each clause's risk level, and 
     produces a structured report with specific amendment suggestions and 
     confidence scores.
```

Now the full colony convenes:

1. **Messenger** → WORTHY (or possibly JELLY — the Scout will determine)
2. **Scout** → COMPLEX tier (high-stakes domain, multi-format output, state management)
3. **Forager** searches patterns AND brings alternative approaches
4. **Builder** constructs using the full template from `output-forms/system-prompt.md`
5. **Nurse** may note state management needs (if there's multi-stage processing)
6. **Guardian** reviews the finished output (COMPLEX = always)
7. **Sentinel** checks for systemic issues (safety boundaries, constraint consistency)

The output should include:
- Validation evidence (scope boundary test, ambiguity stress test, failure modes)
- Edge case handling for unusual contract structures
- Specific examples showing how to rate clause risk
- An anti-pattern example ("Why this fails")

**This is COMPLEX Genesis.** Full ceremony, full validation. Notice how the output has a *point of view* on legal contracts — not a generic template with legal nouns plugged in.

---

## Step 6: Build a Prompt Chain

Now try a multi-stage pipeline:

```
You: Build a prompt chain for processing job applications: parse the resume → 
     score qualifications against the job description → generate interview 
     questions targeting gaps → produce a candidate summary for the hiring manager.
```

You should see CHAIN Genesis:
- Each stage gets its own system prompt, user message template, and output schema
- The Nurse defines what state passes between stages
- Pass conditions and failure behaviors for each stage
- An architecture diagram showing the pipeline flow

**This is where the colony's structure really shows.** Each stage is a separate prompt, but they're designed as a system — the output of Stage 1 becomes the input of Stage 2, with explicit schemas at every handoff point.

---

## Step 7: Spawn Your First Daughter

This is the big one. Feed Harper royal jelly:

```
You: Build me an AI system for personal finance management — tracking spending, 
     categorizing transactions, detecting unusual activity, generating monthly 
     reports, and recommending budget adjustments based on spending trends.
```

The colony should recognize this as **royal jelly** — not a one-shot prompt but an ongoing intelligence system. Watch for:

1. **Scout** identifies this as a spawning request
2. **Phase 1: Domain Reconnaissance** — what does personal finance require?
3. **Phase 2: Caste Differentiation** — what workers, soldiers, drones does this hive need?
4. **Phase 3: Architecture Design** — roles, inputs, outputs, failure modes for each caste
5. **Phase 4: Chain Mapping** — how do the stages connect?
6. **Phase 5: Colony Registration** — the daughter is added to the lineage

You should receive a complete daughter hive structure:
```
hive-personal-finance/
├── SKILL.md                    ← Daughter Queen
├── workers/
│   ├── transaction-parser.md   ← Categorization worker
│   └── report-generator.md     ← Monthly report worker  
├── soldiers/
│   └── anomaly-detector.md     ← Unusual activity checker
├── drones/
│   └── data-collector.md       ← Bank feed / CSV parser
└── memory/
    └── spending-patterns.md    ← Domain-specific knowledge
```

**Congratulations.** Harper just spawned a daughter hive. The daughter speaks the colony tongue, follows the colony protocol, and can be registered in `queen/lineage.md`.

---

## Step 8: Evolve What You Built

Take any output from Steps 3-7 and ask the colony to improve it:

```
You: The refund agent prompt from earlier doesn't handle the case where a 
     customer has multiple orders and wants to refund only one. Fix it.
```

This triggers the **Evolution ritual**:
1. Guardian diagnoses the failure (edge case gap)
2. Forager checks if the colony has seen this pattern before
3. Builder designs a patch (add multi-order handling to the process and examples)
4. Sentinel checks for regression (does the fix break the single-order case?)

The colony learns from its mistakes. If this edge case is generalizable, it may suggest adding it to `memory/antipatterns.md`.

---

## What You've Learned

| Step | What Happened | Colony Feature |
|---|---|---|
| 2 | Vague input rejected | Messenger (input quality gate) |
| 3 | Clean simple prompt | SIMPLE Genesis (Scout + Builder) |
| 4 | Structured prompt with validation | MEDIUM Genesis (+ Forager, + Guardian) |
| 5 | Full ceremony with evidence | COMPLEX Genesis (all castes) |
| 6 | Multi-stage pipeline | CHAIN Genesis (+ Nurse, + Drones) |
| 7 | Daughter hive spawned | Spawning ritual (royal jelly) |
| 8 | Prompt improved from failure | Evolution ritual |

---

## Next Steps

- **Run the test harness** (`tests/hive-test-harness.jsx`) to validate the colony's performance
- **Build a real daughter hive** for a domain you actually work in
- **Contribute back** — if you discover a pattern or anti-pattern, add it to colony memory
- **Read PHILOSOPHY.md** to understand the values behind the architecture
- **Package a hive** using `hive-manifest-spec.md` and share it with the community

---

## Troubleshooting

**The colony doesn't seem to follow the protocol:**
Make sure `SKILL.md` and `queen/language.md` are both loaded in the Project Knowledge. These are the minimum for the colony to activate.

**Outputs are generic / template-like:**
Check if `memory/patterns.md` and `memory/examples.md` are loaded. The Builder uses these for calibration. Also check if the Forager is being convened — it brings alternatives that prevent template drift.

**The Messenger doesn't fire:**
The Messenger is the newest caste. Make sure `castes/workers/messenger.md` is loaded. Without it, inputs go directly to the Scout — still functional, just no quality gate.

**Outputs are too short / truncated:**
For COMPLEX and CHAIN work, the output can be substantial. If using the API directly, set `max_tokens` to 4000+.

**The Guardian doesn't review my MEDIUM output:**
By design. The Guardian is conditional at MEDIUM tier — it only fires for high-stakes domains or when the Builder's confidence is low. For routine MEDIUM work, the Builder's Originality Check handles quality.

---

*Your first hive. The colony grows from here.*
