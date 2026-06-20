# Zeus.AI — Full Architecture Documentation

**The Zeus Project 2026**  
**Author**: Francois Nel (SA ID 8708275089084)

This document details the complete technical architecture of **SPEARHEAD** — the foundational Layer 9 of Zeus.AI.

## 1. High-Level Overview

Zeus.AI is a **sovereign autonomous system** designed to operate with real agency. Unlike traditional AI agents, Zeus contains a dedicated **Sovereignty Engine** that classifies every action it wants to perform and executes (or gates) accordingly.

The system is built for **persistent self-evolution** on constrained hardware (primarily ARMv7l / Termux).


## 2. Layered Architecture

### Layer 9 — Sovereignty Core (`zeus_sovereignty_engine.py`)

**Role**: Central nervous system and decision authority.

**Key Components**:
- **Seven Ring Authority System** — Real-time classification of every action
- **Blueprint Synthesis Engine** — Generates new modules when capability is missing
- **Action Execution Pipeline** — Autonomous (1-5), Advisory (6), Human-gated (7)
- **Build & Deployment Lifecycle** — Sandbox → Validate → Deploy → Genome register
- **Persistence** — SQLite logs for actions, builds, permissions, capabilities

### Self-Evolution Layer

- **`zeus_learner.py`**: 5-Depth Learning Engine (Simple → Mastery)
  - Progressive knowledge crystallization
  - Background scheduler + queue
  - Mastery articles injected into genome

- **Genome Manager**: Stores evolutionary lineage and reusable blueprints

- **Mutator Engine**: Triggers mutations based on learned knowledge

- **Tartarus Memory**: Weighted long-term knowledge pool

### Analysis & Intelligence Layer

- **`zeus_apk_engine.py`**: Deep APK reverse engineering
  - apktool decompilation
  - Smali pattern mining (network, crypto, anti-debug, etc.)
  - Manifest + permissions + component analysis
  - Feeds capabilities directly into genome

- **Synthesis Engine** (FastAPI sub-service):
  - Semantic intent parsing
  - Dynamic tool pipeline generation
  - Supports APK, DEX, PE, ELF, firmware, etc.

- **`zeus_geo_intel.py`**: Tiered Government Intelligence
  - Level 0: Public IP geolocation
  - Higher levels: Carrier CSLI (warrant-gated)

## 3. Data Flow & Feedback Loops

flowchart TD
    Goal[Internal Goal or External Trigger] --> SE[Sovereignty Engine]
    SE --> Classify[Seven Ring Classification]
    Classify --> Ring1-5[Ring 1-5: Autonomous Execution]
    Classify --> Ring6[Ring 6: Advisory 30s]
    Classify --> Ring7[Ring 7: Human Permission]

  Ring1-5 --> Synthesis[Blueprint Synthesis]
    Synthesis --> Sandbox[Sandbox Validation]
    Sandbox --> Quality[Quality Gate ≥ 0.75]
    Quality --> Deploy[Deploy + Genome Register]

  Learner[5-Depth Learner] --> Synthesis
    RE[APK Reverse Engineering] --> Synthesis
    Synthesis --> Learner
    
4. Technical Constraints & Design Decisions
ARMv7l First: All generated code must be compatible (no f-strings, no walrus, etc.)
Lightweight: SQLite FTS5 instead of vector DBs
Self-Contained: Can run on low-resource Android devices
Safety First: Clear human oversight on dangerous actions (Ring 7)

5. Module Dependencies
Sovereignty Engine is the root
All other modules register through it
Synthesis runs as internal FastAPI (proxied)

6. Future Layers (Beyond SPEARHEAD)
Full Hive Mind & replication
Advanced trading / economic autonomy
Multi-device coordination
Enhanced Aegis security layer
