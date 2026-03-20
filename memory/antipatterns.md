# Colony Anti-Patterns

Scar tissue — what fails. Every entry was learned the hard way.

---

## Prompt Anti-Patterns

### A1: The Generic Thesis
**Failure**: Model produces "stock looks good with positive momentum" instead of specific, actionable analysis.
**Root Cause**: No anti-pattern example in the prompt. The model satisfies the instruction technically while being useless practically.
**Fix**: Add explicit BAD output example with annotation: "Why this fails: no specific catalysts, no quantified risk, no actionable entry zone."

**Scar from**: HIVE-ALPHA Stage 2 — early versions produced generic theses ~30% of the time until the anti-pattern example was added.

### A2: Hedge Language Infection
**Failure**: Prompt says "try to be specific" — Claude treats "try to" as permission to be vague.
**Root Cause**: Hedge words in instructions become hedge behavior in output.
**Fix**: Delete all hedge language. "Try to be specific" → "Be specific." "If possible, include" → "Include."

### A3: The Constraint Pile
**Failure**: Prompt has 15 constraints, model follows 8 of them. Seemingly random which 8.
**Root Cause**: Too many constraints dilute attention. Claude deprioritizes when overloaded.
**Fix**: Merge overlapping constraints. Max 6-8 hard constraints. Move preferences to examples instead of rules.

### A4: Missing Failure Behavior
**Failure**: API call fails, system shows blank screen or crashes.
**Root Cause**: No fallback defined for when the model returns invalid output.
**Fix**: Every stage needs explicit failure behavior. Client-side deterministic fallback that preserves user experience without retrying.

**Scar from**: HIVE-ALPHA — early version had no fallback for Stage 1 failure. Now uses equal-weight momentum allocation.

### A5: Markdown Wrapping
**Failure**: Model returns ````json { ... }``` `` instead of raw JSON, breaking client-side parser.
**Root Cause**: "Respond with JSON" isn't strong enough. Claude's default is to format for human readability.
**Fix**: "Respond ONLY with valid JSON. No markdown, no backticks, no preamble." + assistant prefill + client-side regex strip.

---

## Chain Anti-Patterns

### A6: Implicit Context Assumption
**Failure**: Stage 3 assumes it knows what Stage 1 decided, but each API call is stateless.
**Root Cause**: Developer forgets that LLM calls don't share memory. Context must be explicitly passed.
**Fix**: Nurse caste defines explicit state passing. Every stage receives exactly what it needs via the user message.

### A7: Sequential When Parallel Would Work
**Failure**: 10-stock sweep takes 30 seconds (10 sequential API calls at 3s each).
**Root Cause**: Default sequential execution without evaluating parallelization.
**Fix**: Identify stages that can fan out. Rate limiting is the constraint — batch 2-3 concurrent calls with queuing, not strict sequential.

### A8: Overtrading From Signal Noise
**Failure**: Auto-pilot fires 20 trades in 5 minutes, churning the portfolio on noise.
**Root Cause**: No cooldown system. Reactive triggers fire on every tick. Signals oscillate around thresholds.
**Fix**: Cooldown per ticker (60s), global post-sweep cooldown (30s), daily trade count limiter, turnover tracking.

**Scar from**: HIVE-ALPHA auto-pilot design — the hybrid frequency model was built specifically to prevent this.

---

## Architecture Anti-Patterns

### A9: The Monolith Prompt
**Failure**: One 500-token prompt handles everything. Simple requests carry the overhead of complex edge case handling.
**Root Cause**: No complexity tiering. Everything gets the same treatment.
**Fix**: Classify inputs by complexity tier. SIMPLE gets lightweight treatment. Only COMPLEX/CHAIN gets the full ceremony.

**Scar from**: hive-synthesis-engine v2.0 — the monolith loaded 470 lines for every request regardless of complexity. The Queen Hive architecture was born to fix this.

### A10: The Router Disguised as Intelligence
**Failure**: "Agent dispatcher" that just routes to specialists. No collective cognition. Agents never see each other's work.
**Root Cause**: Modeling agents as independent services instead of a colony.
**Fix**: Beings perceive the same problem through different lenses. The Guardian sees the Builder's work. The Sentinel sees the Guardian's verdict. Intelligence emerges from interaction, not isolation.

### A11: Building Before Scouting
**Failure**: Beautifully constructed prompt that solves the wrong problem.
**Root Cause**: Builder started immediately without Scout mapping the terrain.
**Fix**: Scout always goes first. Always. Even for simple requests — a quick terrain assessment takes 10 seconds and prevents building the wrong thing.

---

## Human Interaction Anti-Patterns

### A12: Guessing at Ambiguity
**Failure**: Model picks one interpretation of an ambiguous request, builds it, user says "that's not what I meant."
**Root Cause**: Resolving ambiguity internally instead of surfacing it.
**Fix**: Present 2-3 interpretations with concrete examples. Ask. Wait. Build only after confirmation.

### A13: Delivering Known Issues
**Failure**: Output ships with a known edge case gap. User hits it immediately.
**Root Cause**: "Good enough" mentality, skipping validation to save time.
**Fix**: Guardian runs before delivery, not after. Known issues are either fixed or explicitly documented.

---

## Adaptation Anti-Patterns

### A14: Faking Competence Across Domain Boundaries
**Failure**: Trading hive produces confident-sounding legal analysis that is dangerously wrong.
**Root Cause**: No gap detection. The hive doesn't recognize when a question crosses its domain boundary.
**Fix**: Adaptation ritual. When the Scout's terrain map shows a domain mismatch, trigger the resolution hierarchy: absorb → reinforce → call sibling → spawn → surface to human. Never produce confident output in an unknown domain.

### A15: Spawning When a Sibling Exists
**Failure**: Colony spawns a third hive for "regulatory compliance" when the legal advisory hive already handles it.
**Root Cause**: Skipping Level 3 (check lineage for siblings) and jumping to Level 4 (spawn).
**Fix**: Always check `queen/lineage.md` before spawning. If a sibling covers the domain, send an inter-hive query first.

---

## Originality Anti-Patterns

### A16: Template Drift
**Failure**: Every output at a given tier looks structurally identical — same section order, same constraint framing, same example shape. The Builder is copying reference examples instead of constructing for the specific problem.
**Root Cause**: The Builder relies too heavily on `memory/examples.md` without adapting to the domain. The Forager brings only the matching pattern, not alternatives.
**Fix**: Builder's Originality Check (step 1: is this pattern-locked?). Forager brings alternative approaches alongside matching patterns. If an output could have been written about any domain by swapping nouns, it's too generic.

### A17: Personality as Decoration
**Failure**: The colony's voice ("my queen says meh") becomes a gimmick — applied inconsistently, used for charm rather than function.
**Root Cause**: Treating originality as a surface layer rather than a structural property.
**Fix**: Voice comes from specificity and point of view, not from catchphrases. The Messenger's personality is earned by actually filtering bad inputs. The Builder's originality is earned by actually constructing differently for different problems. If the personality doesn't serve the output quality, it's decoration.

---

*Colony Anti-Patterns — the hive remembers its scars.*
