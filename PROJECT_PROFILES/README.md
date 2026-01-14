# PROJECT PROFILES

プロジェクト固有の前提条件（Phase 0 成果物）を管理します。

## 構成

- `PROJECT_PROFILE_TEMPLATE.md`: **唯一の正本テンプレート**（新規プロジェクトはこれをコピーして使用）
- `PROJECT_PROFILE_<PROJECT_KEY>.md`: 各プロジェクト別の制約・目的の定義（実在する正本）
- `PROJECT_PROFILE_BUYMA.md`: BUYMA自動化プロジェクトの**例（サンプル）**。他プロジェクトで直接使用・参照しない。

## 運用ルール

1. **新規プロジェクト開始時**:
   - `PROJECT_PROFILE_TEMPLATE.md` をコピーし、`PROJECT_PROFILE_<PROJECT_KEY>.md`（大文字識別子）を作成してください。
2. **記述基準**:
   - `GOVERNANCE/MASTER_PROTOCOL_TEMPLATE.md` の Phase 0 基準およびテンプレート内の指示に従って記述してください。
3. **SSOTの確立**:
   - 一度作成された `<PROJECT_KEY>.md` はそのプロジェクトにおける Phase 1 以降のすべての判断基準（SSOT）となります。
