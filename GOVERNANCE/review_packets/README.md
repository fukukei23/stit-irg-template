# GOVERNANCE/review_packets/

This directory stores **Independent Review Packets** for Phase 2.5.

## Purpose
- Preserve review artifacts executed in a **separate context**
- Provide auditable evidence of governance decisions
- Support Decision Log traceability

## What is a Review Packet
A Review Packet is a completed instance of:
- `GOVERNANCE/REVIEW_PACKET_TEMPLATE.md`

Each packet represents **one Phase 2.5 execution**.

## Rules
- One packet per Phase review
- Review packets are **append-only**
- Do not edit packets after verdict is recorded

## Naming Convention

```
REVIEW_PACKET_<PHASE>_<DATE>.md
```

Example:
- `REVIEW_PACKET_PHASE3_2026-01-04.md`

## Mandatory Inputs
Each packet MUST include:
- Canonical Spec reference
- Implementation Diff
- Test execution results

## Invalid Reviews
The following do **NOT** qualify as Phase 2.5:
- IDE self-checks (Cursor, Copilot, etc.)
- Same-context AI reviews
- Reviews without recorded Decision Log entry
