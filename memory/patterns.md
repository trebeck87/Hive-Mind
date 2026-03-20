# Colony Patterns

Accumulated wisdom — what works. Every entry is earned through real deployment, not theory.

---

## Prompt Construction Patterns

### P1: Front-Load the Mission
Place `<core_objective>` in the first 50 tokens of any system prompt. Claude weights early content heavily. A buried objective gets diluted by preceding constraints.

**Earned from**: HIVE-ALPHA Stage 2 — moving the objective above constraints improved thesis specificity by noticeable margin.

### P2: Examples Over Explanations (The 70% Rule)
One good example teaches more than three paragraphs of instruction. For every prompt:
- 2 canonical examples (happy path)
- 1 boundary example (edge of acceptable)
- 1 anti-pattern with annotation (common failure + why it fails)

**Earned from**: HIVE-ALPHA Portfolio Construction — adding bullish/bearish market examples eliminated the "equal weight everything" failure mode.

### P3: Separate Hard Rules from Soft Guidance
Use `<constraints>` for non-negotiable rules and `<guidelines>` or prose for preferences. When everything is a "constraint," Claude treats actual constraints as suggestions.

### P4: Typed JSON Schemas Beat Prose Descriptions
Instead of "return a JSON with the action, conviction, and thesis," show the exact schema with type annotations:
```
{"action": "BUY"|"SELL"|"HOLD", "conviction": 1-10, "thesis": "2-3 sentences"}
```

### P5: Prefill for Format Lock
Assistant prefill (`{` or `[{`) eliminates ~5% of format failures where Claude wraps JSON in markdown. Use for every stage that requires machine-parseable output.

**Earned from**: HIVE-ALPHA v3 — implementing prefill across all API calls.

---

## Chain Architecture Patterns

### C1: Each Stage Gets Its Own Failure Behavior
Never let one stage's failure cascade silently. Define per-stage: what happens on parse error, on timeout, on empty response. Deterministic fallbacks preserve the pipeline.

**Earned from**: HIVE-ALPHA — Stage 1 fallback (equal-weight momentum) keeps the system functional when the API fails.

### C2: Compressed Input for Batch Stages
When a stage processes multiple items sequentially, compress the per-item input to minimize tokens. Single-line pipe-delimited format for signal data. Save verbose format for single-item deep dives.

**Earned from**: HIVE-ALPHA Stage 3 — compressed sweep messages vs. verbose Stage 2 messages.

### C3: Portfolio Context in Every Call
When a chain makes decisions about parts of a whole (individual stocks in a portfolio, clauses in a contract), inject the whole-system context into every per-item call. Without it, the model optimizes locally but creates systemic problems.

**Earned from**: HIVE-ALPHA — adding portfolio concentration and sector exposure to sweep messages.

### C4: State Flows Downstream, Not Upstream
Design chains so each stage only needs output from prior stages, never from later ones. If you find a stage needing future state, restructure the chain.

---

## Hive Architecture Patterns

### H1: Workers Do, Soldiers Check, Drones Compute
Clean caste separation prevents confusion. A worker should never validate its own output. A drone should never make judgment calls. A soldier should never construct — only test.

### H2: The Daughter Queen Is Autonomous
Once spawned, a daughter hive must function without consulting the Mother Queen. Every worker must have enough context in its own file to operate independently.

### H3: Memory Is Colony-Wide, Not Hive-Specific
Patterns and anti-patterns that apply across domains belong in colony memory, not daughter hive memory. Domain-specific knowledge lives in the daughter.

### H4: The Colony Tongue Is Non-Negotiable
XML semantics, JSON protocols, validation formats, iteration logs — these are shared across every hive. A daughter that speaks a different dialect breaks interoperability.

---

## Human Interaction Patterns

### I1: Surface Ambiguity, Don't Resolve It
When the Scout finds multiple valid interpretations, present them to the human with concrete examples. Never guess. The cost of asking is tiny; the cost of building the wrong thing is enormous.

### I2: Show the Anti-Pattern
When presenting a generated prompt, include what BAD output looks like alongside good output. Humans calibrate quality by contrast, not by absolute standards.

### I3: Validate Before Delivering, Not After
Run the Guardian before showing the output to the human. Delivering something with known issues wastes their time and erodes trust.

---

## Architecture Patterns

### A1: Critics Review Output, Not Process
Soldiers (Guardian, Sentinel) should NOT be co-loaded with Workers. A critic who watches construction gets anchored by the builder's reasoning. A critic who reviews only the finished output judges it fresh. Separate the review into a second API call.

**Earned from**: Ablation testing (Wave 5) — removing Guardian from co-loaded context produced identical output quality (10/10 pass, 0 score drop). The Builder already internalized adversarial patterns from colony memory. The Guardian adds value only when reviewing the *output*, not sitting alongside the *instructions*.

### A2: Colony Memory Absorbs Caste Behavior
Over time, patterns from specialist castes get internalized by the Builder through colony memory (patterns.md, antipatterns.md). This means castes that only contribute *knowledge* (not *process*) may become redundant as co-loaded context. Test via ablation before assuming every file is load-bearing.

---

## Originality Patterns

### O1: Converge on Principles, Diverge on Expression
The colony should produce outputs that all follow the same architectural principles (front-load the mission, examples over explanations, structural humility) but express them differently each time. If two outputs for different domains are structurally interchangeable, the Builder is copying, not constructing.

### O2: Alternatives Prevent Calcification
The Forager should bring back not just the matching pattern but a contrasting approach. When the Builder has options, variation emerges naturally. When the Builder has only one reference, every output converges toward it.

### O3: The Messenger Standard Applies to Output
"My queen says meh" isn't just for inputs. If the colony's own gatekeeper would reject the output as bland or generic, it's not ready to ship. Specificity is the minimum bar — specific to the domain, specific to the problem, specific to what makes this request different from the last one.

---

*Colony Patterns — what the hive has learned works.*
