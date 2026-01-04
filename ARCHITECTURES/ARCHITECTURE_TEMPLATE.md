# ARCHITECTURE TEMPLATE

> Canonical: `ARCHITECTURES/ARCHITECTURE_<PROJECT_ID>.md`  
> This is a template. Copy and rename for each project.

---

## Metadata（必須）

- ProjectID: `<PROJECT_ID>`
- ProjectName: `<PROJECT_NAME>`
- Version: `v0.1.0`
- LastUpdated: `YYYY-MM-DD`
- CommitHash: `<git-commit-hash or N/A>`
- Owner: `<Name/Role>`
- Status: `Draft | Active | Deprecated`
- Related:
  - Governance: `GOVERNANCE/MASTER_PROTOCOL_TEMPLATE.md`
  - Review Packet: `GOVERNANCE/REVIEW_PACKET_TEMPLATE.md`
  - Decision Log: `DECISION_LOGS/DECISION_LOG_<PROJECT_ID>.md`（または `DECISION_LOGS/DECISION_LOG_TEMPLATE.md` を複製）

---

## 0. この設計図の目的（Why this exists）

- **Single Source of Truth（SSOT）**として、実装・仕様・レビューの判断基準を固定する
- 変更時の影響範囲、依存関係、責務境界を明示し、破壊的変更を防ぐ
- Phase 2.5（独立レビュー）でのチェック対象を明確化する

---

## 1. スコープ定義

### 1.1 対象（In Scope）
- `<このプロジェクトで扱う機能/領域を列挙>`

### 1.2 非対象（Out of Scope）
- `<意図的に除外するもの（例: UI変更、最適化、リファクタ等）>`

### 1.3 成功条件（Definition of Done）
- 仕様に定義された受け入れ条件（AC）を満たす
- テストが定義され、再現可能なコマンドで実行できる
- Phase 2.5 が **別コンテキスト**で Approve され、Decision Log に記録される

---

## 2. 前提・制約（Constraints）

### 2.1 技術制約
- Language/Runtime: `<Python/Node/etc>`
- Framework: `<Flask/CLI/etc>`
- Storage: `<CSV/DB/etc>`
- External Services: `<OpenAI API 等>`

### 2.2 運用制約
- 書き込み範囲: `<workspace-write / repo only 等>`
- ネットワーク: `<遮断/許可範囲>`
- 秘密情報: `<ENV/Secrets 管理方針>`

### 2.3 ガバナンス制約（必須）
- Spec & Test Driven Iteration を採用
- Phase 2.5 独立レビューを必須（IDE統合AI의 自己チェックは除外）
- レビュアは修正コードを提示しない（指摘・差戻し・承認のみ）

---

## 3. システム全体像（High-level）

### 3.1 ユースケース（利用者視点）
- UC-01: `<例: CSV をインポートし検証結果を得る>`
- UC-02: `<例: 検証エラーを確認し、修正して再実行する>`

### 3.2 構成要素（コンポーネント）
- Component A: `<例: csv_handler>`
- Component B: `<例: validator>`
- Component C: `<例: error types>`
- Component D: `<例: CLI/UI entrypoint>`

### 3.3 外部依存
- `<外部API、外部ファイル形式、DB、OS依存など>`

---

## 4. 責務境界（Responsibility Boundaries）

> ここが曖昧だと、仕様外拡張・依存増加・レビュー破綻が起きる

| Boundary | 役割 | 入力 | 出力 | 禁止事項 |
|---|---|---|---|---|
| Parser | `<例: CSV読み取り>` | `<path/bytes>` | `<rows>` | `<自動修復>` |
| Validator | `<例: 検証>` | `<rows>` | `<errors or ok>` | `<価格再計算等の副作用>` |
| Reporter | `<例: 結果整形>` | `<errors>` | `<report>` | `<ログにPII出力>` |
| Writer | `<例: 保存>` | `<report>` | `<file>` | `<指定外パスへ書込>` |

---

## 5. データフロー（Data Flow）

### 5.1 入力データ定義
- Input Type: `<CSV/JSON/etc>`
- 必須カラム/必須フィールド: `<列挙>`
- 許容形式: `<型、値域、null可否>`

### 5.2 処理フロー（段階）
1. Read: `<読み込み>`
2. Parse: `<行→構造化>`
3. Validate: `<ルール適用>`
4. Fail-Fast or Aggregate: `<方針>`
5. Report: `<エラー/結果出力>`

### 5.3 出力データ定義
- Output Type: `<例: ValidationReport / exceptions>`
- 出力先: `<標準出力/ファイル/返り値>`
- エラー表現: `<例: CSVValidationError>`

---

## 6. 例外・エラー設計（Error & Exception Design）

### 6.1 エラー分類
- UserError: `<入力不備>`
- SystemError: `<IO失敗/依存不具合>`
- ContractError: `<仕様違反/不整合>`

### 6.2 例外の単一入口
- BaseError: `<例: AppError>`
- DomainError: `<例: CSVValidationError>`
- Error Payload: `<code, message, location(row/col), severity>`

### 6.3 ログ方針
- 機密（APIキー、個人情報、トークン等）はログ禁止
- 例外時の情報露出最小化（スタックトレースの扱いも明記）

---

## 7. セキュリティ・安全性（Safety & Security）

### 7.1 想定する悪用・事故
- ファイル破壊（誤パス書込、上書き）
- 入力値汚染（数値/文字列偽装、巨大入力によるDoS）
- 情報露出（ログ、例外文、出力レポート）

### 7.2 防御策（最低限）
- パス制限（workspace内のみ）
- 入力サイズ制限（行数/ファイルサイズ）
- Fail-Fast/中断条件
- 例外メッセージのサニタイズ

---

## 8. テスト戦略（Test Strategy）

### 8.1 テストレベル
- Unit: `<純粋関数/検証ルール>`
- Integration: `<CSV読み取り＋検証>`
- E2E: `<CLI経由など（必要なら）>`

### 8.2 最低限のテスト要件
- 正常系
- 異常系（必須カラム欠落、型不正、境界値）
- 大きめ入力（上限近辺）

### 8.3 実行コマンド
- `pytest -q`（例）
- `<必要な追加コマンド>`

---

## 9. 開発フロー統合（Spec & Test + Phase 2.5）

### 9.1 Spec の正規配置
- Canonical Spec Location:
  - `docs/00_governance/spec/PHASE_<X>_<Y>_<TITLE>_SPEC.md`

### 9.2 Phase 2.5 レビュー実施
- REVIEW_PACKET を作成し、**別コンテキスト**に投げる
- レビュアは修正コードを提示しない
- 判定は Approve / Reject のみ
- Decision Log に転記（必須）

---

## 10. 変更管理（Change Management）

### 10.1 影響範囲の見積もり観点
- 既存CSVの拒否リスク
- 依存増加（新ライブラリ導入）
- 例外型・戻り値変更（互換性）

### 10.2 互換性方針
- Breaking Change の条件: `<列挙>`
- 移行方針: `<段階導入/フラグ/旧仕様サポート期限>`

---

## 11. 未決事項（Open Questions）
- Q1: `<未確定事項>`
- Q2: `<判断が必要な点>`

---

## 12. Decision Log（リンク）
- Decision Log: `DECISION_LOGS/DECISION_LOG_<PROJECT_ID>.md`
- 設計判断は必ずログに残す（却下案も含む）

---
