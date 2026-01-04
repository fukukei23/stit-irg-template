# AI Development Protocol（設計憲法レジストリ）

## これは何か

このリポジトリは、**「Spec & Test Driven Iteration + Phase 2.5 Independent Review Gate」** をプロジェクトの大小によらず標準化するための **テンプレリポジトリ** である。

- 開発を開始する前に必ず本レジストリの内容を参照する
- 「推測を排除し、仕様とテストで開発を回す」ことを強制する
- 全文書の参照は **リポジトリ相対パス** で行うこと（絶対パス禁止）

---

## フォルダ構成と Canonical Paths

### [GOVERNANCE/](./GOVERNANCE/)
- **[MASTER_PROTOCOL_TEMPLATE.md](./GOVERNANCE/MASTER_PROTOCOL_TEMPLATE.md)** (Canonical)
  - すべての開発に共通する最上位プロトコル（仕様駆動・テスト先行）
- **[REVIEW_PACKET_TEMPLATE.md](./GOVERNANCE/REVIEW_PACKET_TEMPLATE.md)**
  - Phase 2.5 独立レビュー用の指示書雛形
- **[spec/](./GOVERNANCE/spec/)** (Canonical Spec Location)
  - 各プロジェクトの最新仕様書（Phase別）はここに集約する
  - 旧 `docs/spec/` 等にファイルがある場合は「Superseded」注記を入れてここへ誘導すること

### [ARCHITECTURE.md](./ARCHITECTURE.md) (Gate Entrypoint)
- 各プロジェクトの設計図への入口
- 実装開始前に必ず参照すべき **Gate の要石**

### [PROJECT_PROFILES/](./PROJECT_PROFILES/)
- プロジェクト固有の前提条件（Phase 0 成果物）

### [ARCHITECTURES/](./ARCHITECTURES/)
- プロジェクト別の詳細設計図（[ARCHITECTURE_TEMPLATE.md](./ARCHITECTURES/ARCHITECTURE_TEMPLATE.md) を使用）

### [DECISION_LOGS/](./DECISION_LOGS/)
- 判断・失敗・却下理由を記録する **不変のログ**

---

## 運用フロー（STIT + IRG）

以下の手順（Phase 1 → 2 → 2.5 → 4）を最短フローとする。

1. **Phase 1: Spec & Test Definition**
   - 仕様書を [GOVERNANCE/spec/](./GOVERNANCE/spec/) に作成し、テストコードを定義する
2. **Phase 2: Implementation**
   - 仕様とテストを満たす実装を行う
3. **Phase 2.5: Independent Review Gate (IRG)**
   - **必須条件**: 開発環境から切り離された **別コンテキスト（新規チャット等）** で外部 AI (ChatGPT/Claude等) にレビューさせる
   - **IDE 内自己チェックは無効**: カーソル等の自己チェックはこのフェーズに該当しない
   - `REVIEW_PACKET_TEMPLATE.md` を使用して指示を投げる
4. **Phase 4: Merge & Assetization**
   - レビュー結果を `DECISION_LOGS/` に転記し、設計資産として固定する

---

## 重要なルール

- **推測禁止**: 不明点は必ず言語化し、情報を提示させてから進める
- **絶対パス禁止**: ローカルや環境固有の絶対パスはリンク切れの原因となるため、すべてリポジトリ相対パスで記述する
- **独立レビュー必須**: 第三者（AI）の視点による検証なしに Phase 4 に進んではならない

---

## このフォルダの位置づけ

本レジストリは **すべてのソースコード、すべてのツールより上位** に位置する設計憲法である。ここに書かれたルールを遵守できない場合、その開発を開始してはならない。
