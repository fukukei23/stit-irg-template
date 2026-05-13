# Decision Log

This is an **append-only Decision Log** for this repository.

Do NOT edit or delete past entries.
Add new decisions at the bottom only.

---

## Entry 0001
- Date: 2026-01-04
- Phase: Initialization
- Verdict: Initialized
- Severity: N/A
- Reason:
  このレジストリを STIT+IRG テンプレとして確定。Commit 0（骨格）, Commit 1（本文固定）, Commit 2（運用整備）の全工程完了を記録。
- Reference:
  - ARCHITECTURE.md
- Diff: N/A

---

## Entry 0002
- Date: 2026-01-04
- Phase: Assetization / Polishing
- Verdict: Standardized PowerShell Verification
- Severity: Low
- Reason:
  Windows環境での再現性を担保するため、ドキュメント上の検証手順を `rg` から PowerShell 拡張の `Select-String` へ変更。また、`.gem-ini` 等の例示パスが実在ファイルでないことを明文化した。
- Reference:
  - walkthrough.md
- Diff:
  - N/A

---

## Entry 0003
- Date: 2026-01-04
- Phase: Assetization / Polishing
- Verdict: Hardened Hygiene Verification
- Severity: Low
- Reason:
  検証手順の信頼性を高めるため、`git ls-files` をベースとした Git 管理下ファイルのみを対象とする手法へ移行。また、`.gem-ini` や `.resol-ved` などのチャット履歴由来の疑似パス混入も検知対象に追加し、不確実な「結果断言」を排除した挙動説明へ修正。
- Reference:
  - walkthrough.md
- Diff:
  - N/A

---

## Entry 0004
- Date: 2026-01-04
- Phase: Publication / Final Fixation
- Verdict: GitHub Template Repository Readiness
- Severity: Low
- Reason:
  GitHub でのパブリック公開（Template Repository）に向け、MIT ライセンスの追加、README の英語化、および日本語版の待避（README_JA.md）を実施。これにより、グローバルな小規模 AI 開発チームが即座に「STIT+IRG」統治を導入可能となった。
- Reference:
  - README.md
  - LICENSE
- Diff:
  - N/A

---

## Entry 0007
- Date: 2026-01-05
- Phase: Template Publication Readiness / Final Fixation
- Verdict: Pass
- Reason:
  「STIT+IRG テンプレート運用開始プロトコル（Final）」を正本として採用。検証手順を Git-native かつ自己検知回避型（パターン分割）に固定し、不変の SSOT 運用を確定した。これをもって本リポジトリは TRG（Template Publication Gate）を完全通過した。
- Reference:
  - walkthrough.md
  - GOVERNANCE/AI_INSTRUCTIONS.md
- Diff:
  - N/A

---

## Entry 0008
- Date: 2026-01-05
- Phase: Template Publication Readiness / Final Fixation
- Verdict: Pass
- Reason:
  「STIT+IRG テンプレート運用開始プロトコル（Final）」を正本として採用。すべての Markdown ファイルを TRG 基準（絶対パス・疑似アーティファクト排除）で再構築し、検証コマンドの出力が空であることを以て「Ready for Template Publication」を宣言する。
- Reference:
  - walkthrough.md
  - GOVERNANCE/AI_INSTRUCTIONS.md
- Diff:
  - N/A

---

## Entry 0009
- Date: 2026-05-13
- Phase: Assetization / Cross-Reference
- Verdict: Pass
- Severity: Info
- Reason:
  NexusCore（fukukei23/NexusCore）におけるSTIT+IRG実践例を記録。NexusCoreは14の専門エージェントが協調するマルチエージェント開発フレームワークであり、STIT+IRGの全フェーズを内部的に実践している。
  実践証拠:
  - GOVERNANCE/SPEC_TEST_DRIVEN_ITERATION.md（STIT正本 v1.2）を保持
  - docs/spec/に35のCR-NEXUS仕様書（Phase 1成果物）を配置
  - tests/phase2/, tests/phase3/等のフェーズ駆動テスト構造
  - GOVERNANCE/review_packets/RP-NEXUS-051_PHASE25_INDEPENDENT_REVIEW_v2.md（Phase 2.5 IRGの実施記録）
  - DECISION_LOGS/DECISION_LOG.mdに11,859バイトの不変判断記録
  - 4624テストケース・85%+カバレッジによる品質担保
  Zenn記事（STIT+IRG解説記事・NexusCoreアーキテクチャ記事）間の相互リンクも確立。
- Reference:
  - https://github.com/fukukei23/NexusCore
  - https://zenn.dev/fukukei23/articles/nexuscore-multi-agent-architecture
- Diff: N/A

---

(Entries continue below)
