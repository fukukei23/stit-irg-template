# GOVERNANCE/spec/

This directory is the **canonical location** for all Phase Specifications
under the STIT+IRG governance model.

## Purpose
- Define *what must be built* before any implementation begins
- Serve as the **Single Source of Truth (SSOT)** for Phase reviews
- Act as the only valid reference for Phase 2.5 Independent Review

## Rules
- All Phase Specs **MUST** be placed in this directory
- Specs located elsewhere are considered **non-canonical**
- Each spec must be immutable once approved

## Naming Convention

```
PHASE_<X>_<SHORT_DESCRIPTION>_SPEC.md
```

Examples:
- `PHASE_1_REQUIREMENTS_SPEC.md`
- `PHASE_3_1_CSV_VALIDATION_SPEC.md`

## Superseded Policy
When a spec is replaced:
1. Create the new version in this directory
2. Add a `NOTE: Superseded` header to the old file
3. Point to the new canonical spec via relative path

## Phase 2.5 Reference
Phase 2.5 reviews **MUST** reference specs from this directory only.
Specs outside this directory invalidate the review.
