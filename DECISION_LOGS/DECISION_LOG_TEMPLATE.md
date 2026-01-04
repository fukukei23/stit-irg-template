# DECISION_LOG_TEMPLATE.md

This document is an append-only decision log.
All records represent explicit architectural, specification, or governance decisions.
Do not edit past entries. Add new entries only.

## 概要（Purpose）

この Decision Log は、以下を目的とする。

1. **設計・仕様・運用に関する 判断の履歴を不可逆に記録する**
2. **「なぜそうなっているのか」を後から追跡可能にする**
3. **人間・AI を問わず、再判断・自己正当化・暗黙変更を防止する**
4. **Phase 2.5（Independent Review）の 正式な成果物とする**

本ログに記録されていない判断は、制度上は存在しないものとして扱う。

## 記録ルール（Rules）

- **追記のみ（Append-only）**
  - 既存エントリの修正・削除は禁止
- **すべての Phase 2.5 の結果は必ず記録する**
- **Reject / 差戻しも必ず記録する（重要）**
- **判断の「是非」ではなく、「何を・なぜ判断したか」を記録する**

## エントリ記載フォーマット（厳守）

以下のフォーマットを 1 Decision = 1 ブロック として使用する。

---

### Decision ID
- **ID**: `DL-YYYYMMDD-XXX`
- **Date**: `YYYY-MM-DD`
- **Phase**: `Phase X / Phase 2.5 / Governance / Architecture / Spec`
- **Decision Type**:
  - `Approve`
  - `Reject`
  - `Defer`
  - `Amend` (仕様・設計変更を伴う場合)

### Context（判断対象）
- **Target Artifact**:
  - Spec: `<path>`
  - Architecture: `<path>`
  - Implementation Diff: `<git commit hash or diff ref>`
- **Related Phase**:
  - Phase 1 / Phase 2 / Phase 2.5 / Phase 3
- **Reviewer**:
  - AI (Model / Tool name)
  - or Human (Role only, personal name optional)

### Decision（判断内容）
- **Verdict**: `Approve / Reject / Defer`
- **Scope of Decision**:
  - What is approved / rejected exactly
  - 明示的に対象範囲を限定すること

### Rationale（判断理由）
- 判断に至った根拠を箇条書きで記載
- 仕様・設計・安全性・依存関係の観点を含める
- 感想・印象は禁止（事実と論理のみ）
- 例:
  - 仕様定義に存在しない暗黙要件が混入していた
  - CSV 入力の境界値に対する Fail-Fast が保証されていない
  - 既存データを破壊し得る処理順が存在する

### Findings（指摘事項）
Severity ごとに分類する。
- **High**
  - （例）仕様逸脱、データ破壊、セキュリティリスク
- **Medium**
  - （例）将来的な不整合、暗黙仕様の芽
- **Low**
  - （例）可読性、明示不足（※Approve を妨げないもの）

※ Approve の場合も記載可
※ 修正コード例の提示は禁止

### Consequences（結果と影響）
- **Immediate Outcome**:
  - Phase 3 に進行可能 / 差戻し
- **Required Follow-up**:
  - 修正が必要な場合は「戻るべき Phase」を明記
- **Impacted Documents**:
  - 更新が必要な Spec / Architecture / Protocol があれば列挙

### Explicit Non-Decisions（やらなかったこと）
- この判断で 意図的に行わなかったこと を明示する。
- 例:
  - 認証機構の導入は今回判断対象外
  - 自動修復ロジックは Phase 4 以降に委ねる

### Reference
- **Canonical Spec**: `<relative path>`
- **Architecture**: `<relative path>`
- **Review Packet**: `<relative path>`
- **Related Decisions**: `DL-YYYYMMDD-XXX`

---

## 禁止事項（Global）

- 修正コード・擬似コードの記載
- 「こうした方が良い」という抽象的助言のみの記載
- 判断主体が不明確な記録
- 仕様・設計への無断な上書き判断

## 運用メモ（Optional）

- Phase 2.5 の Reject は「失敗」ではない
- Reject が記録されているほど、制度は健全
- このログは 品質と判断の資産である
