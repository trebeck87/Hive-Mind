# Colony Lineage

Registry of all hives spawned by **Harper**, the founding Queen. Each entry records what the hive does, its caste structure, and how it connects to sibling hives.

---

## Active Hives

*No active daughter hives registered in the public colony. The lineage grows as the beekeeper spawns daughters for their domains.*

### Entry Format

When a daughter is spawned and registered:

```
### [HIVE-NAME] — [Domain Description]
- **Domain**: [field, sub-field, core constraints]
- **Queen**: [orchestration pattern — single-stage, multi-stage chain, conditional]
- **Workers**: [list with stage assignments if chain]
- **Soldiers**: [quality/safety validators with trigger conditions]
- **Drones**: [data pipeline castes, if needed]
- **Status**: [Active/Dormant/Deprecated, version]
- **Connections**: [inter-hive links to siblings]
```

### Example Entry (illustrative)

```
### hive-analytics — Data Analytics Intelligence
- **Domain**: Data analysis, report generation, insight extraction
- **Queen**: 3-stage prompt chain (Ingest → Analyze → Report)
- **Workers**: Data Ingester (Stage 1), Analyst (Stage 2), Report Writer (Stage 3)
- **Soldiers**: Quality Monitor (statistical validity, source attribution)
- **Drones**: Data Collector (API/file parsing), Signal Processor (normalization, ranking)
- **Status**: Active, v2
- **Connections**: Pending → Legal Advisory hive (compliance review queries)
```

---

## Planned Hives

*Planned hives are registered here when a spawn request (Level 4 adaptation) is approved but not yet executed.*

---

## Inter-Hive Communication

Hives communicate using the `hive-inter-v1` protocol defined in `rituals/adaptation.md`.

### How it works
1. A hive encounters a gap outside its domain
2. It checks this registry for a sibling covering that domain
3. It sends a structured query (assessment / validation / generation / lookup)
4. The receiving hive treats the query like any input — Scout maps, Builder responds
5. Response flows back in the queried hive's expected schema

### Protocol Reference
Full query/response format, urgency levels, routing rules, and failure handling: `rituals/adaptation.md`

---

*Colony Lineage — the living map of the hive network.*
