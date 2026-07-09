# Zeus Project 2026 — SPEARHEAD

**A self-evolving autonomous intelligence platform, architected and built entirely by one developer, running on a single Android phone.**

Architect & Sole Developer: **Francois Nel** — AI Technology PTY LTD, South Africa
License: **Proprietary — All Rights Reserved.** See [LICENSE.md](./LICENSE.md). This is source-available, not open source.

---

## What This Is

SPEARHEAD is the codename for the Zeus Project 2026: a self-hosted, self-evolving AI orchestration platform designed to run under real hardware constraints — a Hisense Y82 Pro (armv7l) inside Termux/Userland, with no cloud infrastructure, no team, and no corporate funding behind it. Everything here was built, tested, and hardened on that single device.

The platform's core idea is a "hive mind" of cooperating modules — deliberation, security, evolution, and analysis engines that talk to each other, learn from outcomes, and improve their own code over time under a strict zero-stubs, constraint-disciplined build policy.

## Core Subsystems

- **AI Council Router** — five-agent, four-phase deliberation engine coordinating Claude, Grok, DeepSeek, Gemini, and Perplexity for higher-confidence decisions than any single model alone.
- **AEGIS-FIELD** — trust and security layer, including warrant-signature verification and an AES-256-GCM vault for sensitive credentials.
- **GovInt** — geo-intelligence and visual analysis tooling, with graceful degradation when optional vision dependencies aren't present.
- **Genome / Evolution Engine** — tracks confidence-scored "genomes" of learned behavior, shares them hive-wide with tiered broadcast priority, and applies them back into decision-making.
- **Tartarus** — a multi-phase analytical/mathematical synthesis pipeline with its own persistent memory.
- **Zeus Immune System** — autonomous test-driven self-improvement: every code change is backed up, tested, and auto-rolled-back on failure, with results feeding back into the hive mind.
- **Zeus Skill Factory** — dynamic skill/tool generation with graceful fallback when optional parsing/analysis libraries are unavailable.
- **22-layer Firewall** — defense-in-depth around the autonomous decision loop.

All of the above is pure Python (Flask/FastAPI), which means the platform is portable beyond Termux to any system with Python 3 — see [Installation](#installation).

## Repository Layout

```
ZEUS_SPEARHEAD_UNIFIED/
├── SPEARHEAD_CLEAN/              # Primary application (Flask + council router + firewall + GovInt)
├── zeus_hive_final_genome_patched/  # Hive mind, genome broadcaster, evolution engine
├── zeus_immune_system/           # Autonomous testing & refactoring safety net
├── zeus_skill_factory/           # Dynamic skill generation
├── tests/                        # Test suites
└── _REVIEW/                      # Working/staging area, not production
```

## Installation

**Requirements:** Python 3.9+, pip.

```bash
cd SPEARHEAD_CLEAN
pip install -r requirements.txt --break-system-packages
```

Set required API keys in `.env` (at minimum, keys for whichever AI Council members you intend to enable — `ANTHROPIC_API_KEY`, `DEEPSEEK_API_KEY`, `PERPLEXITY_API_KEY`, etc.).

Start the platform:

```bash
bash zeus_install.sh   # first-time setup
python3 universal_miner.py  # or the relevant entry point for your build
```

> Originally deployed and tested on Termux/Userland (armv7l). A small number of modules contain Termux-aware path handling; these degrade gracefully on other platforms but a Windows/Linux-native path layer may need adjustment for full feature parity outside Termux.

## Design Principles

- **Zero-stubs policy** — every module in a released build is fully implemented, not a placeholder.
- **Extends, never silently replaces** — new subsystems are additive; existing modules are not overwritten without an explicit, reviewed patch.
- **Constraint-discipline** — every component is built and validated against the actual low-end hardware it runs on, not idealized infrastructure.
- **Safety-gated autonomy** — self-modification is always test-verified with automatic rollback; nothing is applied blind.

## Status

Active development. This repository reflects a real, running system rather than a demo — module counts, route tables, and architecture references in the accompanying technical documentation are audited against the live codebase, not aspirational.

## License

This project is **proprietary and source-available only** — it is not licensed under MIT, Apache, GPL, or any open-source license. Viewing the code here does not grant permission to use, copy, modify, deploy, or redistribute it. See [LICENSE.md](./LICENSE.md) for full terms, and for how to request written permission for any use beyond personal review.

## Author

**Francois Nel**
Sole Developer & Architect, AI Technology PTY LTD
South Africa

All source modules in this project carry the same attribution, consistent with the standard applied across this developer's other projects (Universal Miner Pro, DeepPurge, Poseidon's Spear).
