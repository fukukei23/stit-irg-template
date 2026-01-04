# STIT+IRG Governance Registry

**Spec & Test Driven Iteration + Independent Review Gate (STIT+IRG)**  
A governance-first template repository for AI-driven software development.

---

## What this is

This repository is **not a software product**.

It is a **governance template** that defines:
- How specifications are written
- How implementations are reviewed
- How AI is constrained
- How decisions are logged and audited

The goal is to prevent:
- Silent requirement drift
- Self-justifying AI implementations
- Unsafe or irreversible changes
- Undocumented architectural decisions

---

## Core Principles

1. **Specification before implementation**
2. **Independent review is mandatory (Phase 2.5)**
3. **IDE self-checks do NOT count as reviews**
4. **Git is the Single Source of Truth**
5. **Every major decision is logged**

---

## Repository Structure (Canonical)

```text
ARCHITECTURE.md  # Governance Gate Entrypoint (SSOT)
README.md        # This document
README_JA.md     # Japanese version
GOVERNANCE/      # Protocols & AI rules
ARCHITECTURES/   # Architecture templates
DECISION_LOGS/   # Append-only decision records
PROJECT_PROFILES/ # Project-specific constraints
```

---

## How to use this template

1. Click **Use this template** on GitHub
2. Create your own project repository
3. Define your project in `PROJECT_PROFILES/`
4. Update `ARCHITECTURE.md`
5. Start from Phase 1 (Specification)

---

## Mandatory Rule

You may NOT proceed past Phase 2 unless Phase 2.5  
(**Independent Review in a separate AI context**) is completed and logged.

---

## License

MIT License
