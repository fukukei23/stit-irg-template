# ARCHITECTURE.md

## Metadata（Gate Required）
- Version: 0.2.0
- LastUpdated: 2026-01-04
- CommitHash: (set after first commit)

## Purpose
このファイルは、本レジストリ全体の **Single Source of Truth（SSOT）** および  
**Gate（参照強制）** の入口である。

本レジストリは、個別プロジェクトそのものを管理するものではなく、  
**設計原則・テンプレート・参照規約を提供するための「設計憲法」レポジトリ**である。

すべての下位プロジェクトにおける実装作業は、  
Phase 1 を開始する前に本ファイルを参照し、  
**自リポジトリ側に存在する設計図（ARCHITECTURE.md / PROJECT_PROFILE.md）を正本として確認**しなければならない。

## Canonical Architecture Templates
- [Architecture Template (for new projects)](./ARCHITECTURES/ARCHITECTURE_TEMPLATE.md)

## How to Use (Operational Rule)

1. **新規プロジェクト開始時**  
   - 下位プロジェクトのリポジトリ内にて、  
     `ARCHITECTURES/ARCHITECTURE_<PROJECT_ID>.md` を  
     本レジストリのテンプレートを参考に作成する。

2. **設計の記述**  
   - 下位プロジェクト側の設計図において、以下を明示する。  
     - スコープ  
     - モジュール構成  
     - データフロー  
     - 責務境界  
     - 非目標  
     - リスク

3. **例示としての登録方法の確認（本レジストリ側）**  
   - 下記の "Active Project Architecture" セクションは、  
     **設計図をどのように整理・参照するかの「例」**を示すものである。  
   - **本レジストリは、下位リポジトリにおけるアクティブプロジェクトや正本を定義しない。**  
   - 実際の運用では、  
     **各下位リポジトリ自身が保持する ARCHITECTURE.md を正として管理すること。**

## Active Project Architecture (Example Only)

- このセクションは **登録・参照方法の例示のみ**を目的とする。
- **特定のプロジェクトが現在アクティブであることを示すものではない。**
- 下位リポジトリに対して、プロジェクト名・正本を強制する効果は持たない。

Example:
- ProjectId: BUYMA
- CanonicalArchitectureDoc: ARCHITECTURES/ARCHITECTURE_BUYMA.md

## Notes
- `ARCHITECTURES/ARCHITECTURE_TEMPLATE.md` はあくまで雛形であり、  
  Gate は **本ファイルの存在**と、  
  **下位リポジトリ側で適切に定義された設計図の存在**を要求する。
- 全パスは **相対パス** で記述される。
