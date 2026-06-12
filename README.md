# STIT+IRG Governance Registry

<!-- English: A governance-first template repository that enforces specification-driven development with mandatory independent review gates for AI-driven software projects. Prevents silent requirement drift, self-justifying AI implementations, and undocumented architectural decisions. -->

**Spec & Test Driven Iteration + Independent Review Gate (STIT+IRG)**
AI駆動開発における、ガバナンスファーストのテンプレートリポジトリ。

---

## これは何か

本リポジトリはソフトウェアプロダクトではなく、**開発ガバナンスの設計憲法**である。

以下を定義する:
- 仕様書の書き方
- 実装のレビュー方法
- AIへの制約
- 意思決定の記録・監査方法

以下を防止する:
- 暗黙の要件ドリフト
- AIによる自己正当化実装
- 安全性のない・不可逆な変更
- 未記録のアーキテクチャ決定

---

## 中核原則

1. **仕様が実装に先行する**
2. **独立レビューは必須（Phase 3）**
3. **IDE内自己チェックはレビューとして認めない**
4. **GitをSingle Source of Truthとする**
5. **すべての重要な決定を記録する**

---

## テクニカルスタック

| レイヤー | 技術 |
|---------|------|
| ドキュメント | Markdown（すべてプレーンテキスト） |
| 構成管理 | Git（バージョン管理・変更追跡） |
| テンプレートエンジン | なし（生のMarkdownテンプレート） |
| レビュー媒体 | 任意の外部AIコンテキスト（ChatGPT / Claude等） |
| CI/CD | なし（プロセス規約による強制） |

> 本リポジトリはフレームワークやライブラリに依存しない。プロジェクトの言語・ツールを問わず適用可能。

---

## リポジトリ構成

```text
ARCHITECTURE.md       # Gate入口（SSOT）
README.md             # 本ドキュメント
README_JA.md          # 日本語版
LICENSE               # MIT License

GOVERNANCE/           # プロトコルとAIルール
  MASTER_PROTOCOL_TEMPLATE.md   # 最上位プロトコル（仕様駆動・テスト先行）
  AI_INSTRUCTIONS.md            # AIへの指示書テンプレート
  REVIEW_PACKET_TEMPLATE.md     # Phase 3 独立レビュー用指示書
  spec/                         # 仕様書の正規配置場所
  cli/                          # CLI運用サポート
  review_packets/               # レビューパケット

ARCHITECTURES/        # アーキテクチャテンプレート
  ARCHITECTURE_TEMPLATE.md      # 新規プロジェクト用雛形

DECISION_LOGS/        # 追記型の決定記録（不変ログ）

PROJECT_PROFILES/     # プロジェクト固有の制約条件
  PROJECT_PROFILE_TEMPLATE.md   # プロファイル雛形
  PROJECT_PROFILE_BUYMA.md      # BUYMA向けプロファイル（例）
```

---

## 利用方法

### 1. テンプレートから新規リポジトリを作成

GitHubで **Use this template** をクリックし、プロジェクトリポジトリを作成する。

### 2. プロジェクトプロファイルを定義

`PROJECT_PROFILES/` にプロジェクト固有の前提条件を記述する:

```bash
cp PROJECT_PROFILES/PROJECT_PROFILE_TEMPLATE.md \
   PROJECT_PROFILES/PROJECT_PROFILE_<PROJECT_KEY>.md
# スコープ、制約、非目標を記入
```

### 3. アーキテクチャ文書を作成

```bash
cp ARCHITECTURES/ARCHITECTURE_TEMPLATE.md \
   ARCHITECTURES/ARCHITECTURE_<PROJECT_KEY>.md
# モジュール構成、データフロー、責務境界を記入
```

### 4. 開発フェーズを開始

STIT+IRGのPhase 1から順に進める:

```
Phase 0: プロジェクト定義（PROJECT_PROFILE）
Phase 1: 仕様とテストの定義（GOVERNANCE/spec/）
Phase 2: 実装
Phase 3: 独立レビュー（別コンテキストのAIで必須実施）
Phase 4: セキュリティレビュー（任意・OWASP/Red Team）
Phase 5: マージと資産化（DECISION_LOGS/ に記録）
```

---

## 運用フロー詳細

```
               ┌──────────────────────┐
               │  Phase 0: 定義       │
               │  PROJECT_PROFILE作成  │
               └──────────┬───────────┘
                          │
               ┌──────────▼───────────┐
               │  Phase 1: 仕様+テスト │
               │  GOVERNANCE/spec/     │
               └──────────┬───────────┘
                          │
               ┌──────────▼───────────┐
               │  Phase 2: 実装       │
               │  仕様・テストを満たす  │
               └──────────┬───────────┘
                          │
               ┌──────────▼───────────┐
               │  Phase 3: IRG        │ ← 別コンテキストのAI
               │  REVIEW_PACKET使用    │    IDE自己チェックは不可
               └──────────┬───────────┘
                          │
               ┌──────────▼───────────┐
               │  Phase 4: 任意Sec    │ ← OWASP/Red Team視点
               │  セキュリティレビュー  │    明示指示時のみ実施
               └──────────┬───────────┘
                          │
               ┌──────────▼───────────┐
               │  Phase 5: 資産化     │
               │  DECISION_LOGS/      │
               └──────────────────────┘
```

---

## 必須ルール

Phase 3（別コンテキストでの独立レビュー）が完了・記録されるまで、Phase 4以降に進んではならない。これが唯一のハードゲートである。

---

## 既存プロジェクトへの適用例

BUYMAパーソナルショッパー管理ツール向けの適用例を同梱している:
- `PROJECT_PROFILES/PROJECT_PROFILE_BUYMA.md` -- BUYMA向けの制約・非目標

---

## 関連リソース

| 文書 | 説明 |
|------|------|
| [ARCHITECTURE.md](ARCHITECTURE.md) | Gate入口・SSOT |
| [README_JA.md](README_JA.md) | 日本語版README |
| [GOVERNANCE/MASTER_PROTOCOL_TEMPLATE.md](GOVERNANCE/MASTER_PROTOCOL_TEMPLATE.md) | 最上位プロトコル |
| [GOVERNANCE/AI_INSTRUCTIONS.md](GOVERNANCE/AI_INSTRUCTIONS.md) | AIへの指示書 |
| [GOVERNANCE/REVIEW_PACKET_TEMPLATE.md](GOVERNANCE/REVIEW_PACKET_TEMPLATE.md) | レビュー指示書 |

---

## License

MIT License
