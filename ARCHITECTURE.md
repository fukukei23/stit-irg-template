# ARCHITECTURE.md

## Metadata（Gate Required）
- Version: 0.2.0
- LastUpdated: 2026-01-04
- CommitHash: (set after first commit)

## Purpose
このファイルは、本レジストリ全体の **Single Source of Truth（SSOT）** および **Gate（参照強制）** の入口である。
すべての実装作業は、Phase 1 を開始する前にこのファイルを参照し、プロジェクト固有の設計図を確認しなければならない。

## Canonical Architecture Templates
- [Architecture Template (for new projects)](./ARCHITECTURES/ARCHITECTURE_TEMPLATE.md)

## How to Use (Operational Rule)
1. **新規プロジェクト開始時**:
   - `ARCHITECTURES/ARCHITECTURE_<PROJECT_ID>.md` をテンプレートから作成する。
2. **設計の記述**:
   - スコープ、モジュール構成、データフロー、責務境界、非目標、リスクを定義する。
3. **入口の更新**:
   - 下記の "Active Project Architecture" セクションを更新し、作成した設計図へリンクさせる。

## Active Project Architecture
- CurrentProjectId: **BUYMA**
- CanonicalArchitectureDoc: [ARCHITECTURES/ARCHITECTURE_BUYMA.md](./ARCHITECTURES/ARCHITECTURE_BUYMA_MANAGER.md) (Example)

## Notes
- `ARCHITECTURES/ARCHITECTURE_TEMPLATE.md` はあくまで雛形であり、Gate はこの `ARCHITECTURE.md` 自体の存在と、そこから辿れる詳細設計図を要求する。
- 全パスは **相対パス** で記述される。
