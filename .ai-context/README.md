# AI Context Directory - Optimized for Token Efficiency

**Last Updated**: 2025-12-25
**Purpose**: Hierarchical AI context with lazy loading and shared submodule

---

## Token Optimization Strategy

**Solution**: 3-tier architecture with lazy loading + shared submodule.

**Result**: < 100 lines loaded at startup (~2-3% token budget).

---

## Directory Structure

```
.ai-context/
├── ESSENTIAL.md                    # [Tier 1] Always loaded (< 100 lines)
│
├── context/                        # [Tier 2] Project-specific context
│   ├── coding/                     # Coding standards (to be added)
│   ├── architecture/               # Architecture docs (to be added)
│   └── workflows/                  # Workflow docs (to be added)
│
├── shared/                         # [Submodule] Shared across projects
│   ├── developer/
│   │   └── YOSHIHIRO_NAKAHARA_PROFILE.md
│   ├── analytics/
│   │   └── SEO_Keywords_Tracking.md
│   ├── methodology/
│   │   ├── AI_COLLABORATION.md
│   │   ├── DESIGN_PHILOSOPHY.md
│   │   └── SCALE_ARCHITECTURE.md
│   ├── insights/
│   │   └── ... (insight documents)
│   ├── workflows/
│   │   ├── DOCUMENTATION_CREATION.md
│   │   └── GITHUB_PROJECTS.md
│   └── README.md
│
├── knowledge/
│   └── archive/                    # Historical reference
│
└── README.md                       # This file
```

---

## Shared Submodule

The `shared/` directory is a Git submodule pointing to:
**https://github.com/BonoJovi/ai-context-shared**

### Why Submodule?

- **Single source of truth**: Common files managed in one place
- **Cross-project consistency**: All projects share the same context
- **Easy updates**: `git submodule update --remote` syncs all projects

### Submodule Commands

```bash
# Update to latest shared context
git submodule update --remote

# Clone project with submodules
git clone --recurse-submodules <repo-url>

# Initialize submodules after clone
git submodule init && git submodule update
```

---

## Usage Guidelines for AI

### Session Startup (Automatic)
- **ESSENTIAL.md** is loaded automatically via CLAUDE.md
- Contains: Current phase, critical rules, quick references
- Size: < 100 lines (token-efficient)

### When Coding
Load as needed from `context/coding/` (to be added as project develops)

### When Designing
Load as needed from `context/architecture/` (to be added as project develops)

### When Understanding "Why"
Load from shared:
- `@.ai-context/shared/methodology/AI_COLLABORATION.md`
- `@.ai-context/shared/methodology/DESIGN_PHILOSOPHY.md`
- `@.ai-context/shared/insights/`

---

**This structure ensures AI assistants can efficiently access the right information at the right time, with minimal token overhead and cross-project consistency.**
