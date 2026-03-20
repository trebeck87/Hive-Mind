# Hive Packaging Standard

**Version**: 1.0

How to package a daughter hive so it can plug into any colony that speaks the colony tongue.

---

## The Manifest

Every publishable daughter hive includes a `hive-manifest.json` at its root. This file makes the hive discoverable, installable, and interoperable.

```json
{
  "name": "hive-medical-research",
  "version": "1.0.0",
  "description": "Medical research analysis — clinical trials, drug interactions, literature synthesis",
  "author": "github-username",
  "license": "Apache-2.0",

  "colony": {
    "tongue_version": "3.0",
    "min_queen_version": "3.0.0"
  },

  "domain": {
    "primary": "Medical research & clinical analysis",
    "keywords": ["healthcare", "clinical-trials", "pharmacology", "literature-review"]
  },

  "castes": {
    "workers": [
      "workers/researcher.md",
      "workers/literature-reviewer.md"
    ],
    "soldiers": [
      "soldiers/safety-checker.md"
    ],
    "drones": [
      "drones/pubmed-collector.md"
    ]
  },

  "inter_hive": {
    "accepts": [
      {
        "query_type": "assessment",
        "description": "Evaluate a medical claim, drug interaction, or clinical question",
        "input_schema": {
          "question": "string — the specific medical question",
          "context": "string — relevant background (optional)",
          "urgency": "blocking | advisory | background"
        },
        "response_schema": {
          "assessment": "string — 2-5 sentence analysis",
          "confidence": "number 1-10",
          "evidence_quality": "strong | moderate | weak | insufficient",
          "recommendation": "string — specific actionable guidance",
          "caveats": "string[] — limitations and disclaimers"
        }
      },
      {
        "query_type": "lookup",
        "description": "Check if a specific drug, condition, or interaction is in the knowledge base",
        "input_schema": {
          "entity": "string — drug name, condition, or interaction",
          "entity_type": "drug | condition | interaction | trial"
        },
        "response_schema": {
          "found": "boolean",
          "summary": "string — brief description if found",
          "sources": "string[] — where this information comes from"
        }
      }
    ],
    "sends_to": [
      {
        "hive": "hive-legal-advisory",
        "query_type": "validation",
        "reason": "Regulatory compliance checks on clinical trial protocols"
      }
    ]
  },

  "requirements": {
    "external_apis": ["pubmed", "clinicaltrials.gov"],
    "memory_dependencies": [],
    "sibling_hives": []
  }
}
```

---

## Required Fields

| Field | Type | Description |
|---|---|---|
| `name` | string | Unique hive identifier, kebab-case |
| `version` | string | Semver (major.minor.patch) |
| `description` | string | One-line description of what the hive does |
| `author` | string | GitHub username or organization |
| `colony.tongue_version` | string | Which colony tongue version this hive speaks |
| `colony.min_queen_version` | string | Minimum Queen Hive version required |
| `domain.primary` | string | Human-readable domain description |
| `castes` | object | Files for workers, soldiers, drones |
| `inter_hive.accepts` | array | Query types this hive can respond to |

## Optional Fields

| Field | Type | Description |
|---|---|---|
| `license` | string | SPDX license identifier |
| `domain.keywords` | array | Search/discovery tags |
| `inter_hive.sends_to` | array | Hives this one expects to query |
| `requirements.external_apis` | array | External services the hive depends on |
| `requirements.memory_dependencies` | array | Colony memory files the hive needs |
| `requirements.sibling_hives` | array | Other hives that must be installed |

---

## File Structure

A packaged hive follows this directory layout:

```
hive-name/
├── hive-manifest.json          ← Required — the manifest
├── SKILL.md                    ← Required — Daughter Queen
├── workers/                    ← Required — at least one worker
│   ├── {worker-1}.md
│   └── {worker-2}.md
├── soldiers/                   ← Required — at least one soldier
│   └── {soldier-1}.md
├── drones/                     ← Optional — only if data pipeline needed
│   ├── {collector}.md
│   └── {processor}.md
├── memory/                     ← Optional — domain-specific knowledge
│   └── {domain-knowledge}.md
└── README.md                   ← Recommended — usage guide
```

---

## Validation Checklist

Before publishing a hive, verify:

- [ ] `hive-manifest.json` is valid JSON and includes all required fields
- [ ] `colony.tongue_version` matches the colony tongue you developed against
- [ ] `SKILL.md` references `queen/language.md` (inherits the colony tongue)
- [ ] Every file listed in `castes` actually exists
- [ ] Every `inter_hive.accepts` entry has both `input_schema` and `response_schema`
- [ ] At least one soldier exists for quality control
- [ ] Every worker has: role, input, output schema, failure behavior
- [ ] Hive passes the test harness (`tests/hive-test-harness.jsx`) at ≥80% average

---

## Installation

To add a community hive to your colony:

```
1. Copy the hive directory into your hives/ folder:
   hives/
   └── hive-medical-research/
       ├── hive-manifest.json
       ├── SKILL.md
       ├── workers/
       ├── soldiers/
       └── ...

2. Register in queen/lineage.md:
   ### hive-medical-research — Medical Research
   - Domain: Medical research & clinical analysis
   - Status: Active
   - Accepts: assessment, lookup
   - Connections: → hive-legal-advisory (regulatory validation)

3. Verify compatibility:
   - colony.tongue_version matches your queen/language.md version
   - Required sibling hives (if any) are installed
   - External API dependencies (if any) are available
```

---

## Versioning Rules

- **Patch** (1.0.x): Bug fixes, prompt refinements, memory updates. No schema changes.
- **Minor** (1.x.0): New castes, new query types, expanded capabilities. Backward compatible.
- **Major** (x.0.0): Breaking changes to inter-hive schemas, caste restructuring, colony tongue version bump.

A hive that bumps `colony.tongue_version` is a major version change — it may not be compatible with older colonies.

---

*Hive Packaging Standard v1.0 — how daughters leave home and thrive.*
