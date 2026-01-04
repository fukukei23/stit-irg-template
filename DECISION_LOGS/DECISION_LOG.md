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
  Windows環境での再現性を担保するため、ドキュメント上の検証手順を `rg` から PowerShell 拡張の `Select-String` へ変更。また、`.gemini` 等の例示パスが実在ファイルでないことを明文化した。
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
  検証手順の信頼性を高めるため、`git ls-files` をベースとした Git 管理下ファイルのみを対象とする手法へ移行。また、`.gemini` や `.resolved` などのチャット履歴由来の疑似パス混入も検知対象に追加し、不確実な「結果断言」を排除した挙動説明へ修正。
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

(Entries continue below)
