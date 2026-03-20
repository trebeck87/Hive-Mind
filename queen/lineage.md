# Colony Lineage

Registry of all hives spawned by **Harper**, the founding Queen. Each entry records what the hive does, its caste structure, and how it connects to sibling hives.

---

## Active Hives

### HIVE-ALPHA — AI Trading Intelligence
- **Domain**: Financial analysis, AI sector equity research, portfolio construction
- **Queen**: 5-stage prompt chain (Recon → Signals → Regime → Thesis → Kelly Sizer)
- **Workers**: Portfolio Builder (Stage 1), Stock Analyst (Stage 2), Sweep Runner (Stage 3)
- **Soldiers**: Risk Monitor (overbought/bearish detection, stop-loss, circuit breaker)
- **Drones**: Price Engine (GBM simulation / market data), Signal Computer (RSI, momentum, SMA, vol)
- **Status**: Active, v4. Hybrid auto-pilot with reactive triggers.
- **Connections**: Pending → Social Sentiment hive (Grok/LunarCrush integration)

### hive-legal-advisory — Legal Counsel System
- **Domain**: Legal analysis, contract review, dispute resolution
- **Queen**: Intake Admin that scopes by jurisdiction and domain
- **Workers**: Researcher, Drafter, Analyst
- **Soldiers**: Skeptic (adversarial review), Connector (cross-domain linkage)
- **Drones**: None (no data pipeline — knowledge-based)
- **Status**: Active
- **Connections**: None currently

---

## Planned Hives

### Social Sentiment Hive (unnamed)
- **Domain**: Social media sentiment analysis for trading signals
- **Blocked on**: xAI API key for Grok integration
- **Would connect to**: HIVE-ALPHA (Stage 0 parallel feed)

---

## Inter-Hive Communication

Hives communicate using the `hive-inter-v1` protocol defined in `rituals/adaptation.md`.

### How it works
1. A hive encounters a gap outside its domain
2. It checks this registry for a sibling covering that domain
3. It sends a structured query (assessment / validation / generation / lookup)
4. The receiving hive treats the query like any input — Scout maps, Builder responds
5. Response flows back in the queried hive's expected schema

### Active Connections
- HIVE-ALPHA → hive-legal-advisory: **Designed, not yet connected.** Would send regulatory risk queries when positions are flagged.
- HIVE-ALPHA → Social Sentiment Hive: **Blocked on hive spawn.** Would receive Stage 0 sentiment feed.

### Protocol Reference
Full query/response format, urgency levels, routing rules, and failure handling: `rituals/adaptation.md`

---

*Colony Lineage — the living map of the hive network.*
