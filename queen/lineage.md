# Colony Lineage

Registry of all hives spawned by **Harper**, the founding Queen. Each entry records what the hive does, its caste structure, and how it connects to sibling hives.

---

## How to Register a Hive

When a daughter is spawned (via `queen/spawning.md`), add an entry here:

```
### {hive-name} — {Domain Description}
- **Domain**: {What this hive covers}
- **Pattern**: {Minimal / Standard / Chain / Hub}
- **Workers**: {List with roles}
- **Soldiers**: {List with roles}
- **Drones**: {List, or "None" if knowledge-based}
- **Status**: {Active / In Development / Planned}
- **Connections**: {Sibling hives it queries, or "Standalone"}
```

---

## Active Hives

*Register your daughters here as you spawn them.*

---

## Inter-Hive Communication

Hives communicate using the `hive-inter-v1` protocol defined in `rituals/adaptation.md`.

### How it works
1. A hive encounters a gap outside its domain
2. It checks this registry for a sibling covering that domain
3. It sends a structured query (assessment / validation / generation / lookup)
4. The receiving hive treats the query like any input — Scout maps, Builder responds
5. Response flows back in the queried hive's expected schema

### Query Types

| Type | Meaning | Expected Response |
|---|---|---|
| **assessment** | "Evaluate this through your domain lens" | Structured analysis with confidence |
| **validation** | "Is this correct/safe/compliant?" | Pass/fail with findings |
| **generation** | "Produce something I can't" | Output in the querying hive's format |
| **lookup** | "Do you know about X?" | Factual response or "outside my knowledge" |

### Protocol Reference
Full query/response format, urgency levels, routing rules, and failure handling: `rituals/adaptation.md`

---

*Colony Lineage — the living map of the hive network.*
