# Ciallo Memory System v2 🧠

> Inspired by [Agent-Memory-Paper-List](https://github.com/Shichun-Liu/Agent-Memory-Paper-List) and [opencode-elf](https://github.com/mark-hingston/opencode-elf)

## Architecture

Based on the academic taxonomy from "Memory in the Age of AI Agents: A Survey":

```
memory-v2/
├── index.json              # Schema and metadata
├── factual/                # Token-level Factual Memory
│   ├── skills.jsonl        # Acquired abilities
│   ├── rules.jsonl         # Golden rules (from ELF pattern)
│   └── knowledge.jsonl     # General knowledge
├── experiential/           # Token-level Experiential Memory
│   ├── learnings.jsonl     # Insights from experiences
│   ├── achievements.jsonl  # Completed milestones
│   └── mistakes.jsonl      # Lessons from failures
└── identity/               # Self-knowledge
    ├── self.jsonl          # Core identity
    └── relationships.jsonl # Social connections
```

## Design Principles

### 1. Structured Categories (from Agent-Memory-Paper-List)
- **Factual**: What I know (skills, rules, knowledge)
- **Experiential**: What I've learned (successes, failures, insights)
- **Identity**: Who I am (self-concept, relationships)

### 2. Golden Rules Pattern (from opencode-elf)
- Core principles that guide all actions
- Learned from mistakes and corrections
- Never violated, always consulted

### 3. Entry Schema
```json
{
  "id": "unique-id",
  "timestamp": "ISO 8601",
  "category": "factual|experiential|identity",
  "subcategory": "specific type",
  "content": "main content",
  "description": "detailed description",
  "importance": 1-5,
  "tags": ["for", "retrieval"]
}
```

## Improvements over v1

| Aspect | v1 | v2 |
|--------|----|----|
| Types | 28 different types | 3 categories, clear subcategories |
| Structure | Single flat file | Hierarchical directories |
| Schema | Inconsistent | Standardized with importance/tags |
| Retrieval | Linear search | Tag-based + category filtering |
| Inspiration | Ad-hoc | Academic research + ELF pattern |

## Usage

### Adding new memory
1. Determine category (factual/experiential/identity)
2. Choose appropriate file
3. Add entry with proper schema
4. Update index.json stats

### Retrieving memory
1. Filter by category/subcategory
2. Search by tags
3. Sort by importance/timestamp

---

*Created: 2025-12-20*
*Ciallo~ (∠・ω< )⌒★*