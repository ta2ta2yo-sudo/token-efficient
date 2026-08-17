# Token Efficient

<p align="center">
  <img src="assets/logo.png" width="128" alt="Token Efficient logo">
</p>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Plugin: skills-only](https://img.shields.io/badge/plugin-skills--only-14B8A6.svg)](.codex-plugin/plugin.json)

A lightweight ChatGPT and Codex plugin that reduces unnecessary context, file reads, searches, tool output, and response length without sacrificing correctness or safety.

[日本語](#日本語) | [English](#english)

> **Distribution status:** The public plugin package and submission materials are ready. OpenAI review and Universal Plugins Directory publication have not been completed yet.

## 日本語

### 概要

`token-efficient`は、ChatGPTとCodexの作業品質を保ちながら、不要なトークン消費を減らすための軽量なskills-onlyプラグインです。外部サーバー、アカウント、認証、APIキーは必要ありません。

主に次の無駄を抑えます。

- ファイルやログの丸読み
- あてずっぽうな探索と同じ情報の再読
- 小さな変更でのファイル全体の書き直し
- 長すぎるツール出力、途中報告、最終回答
- 根拠のない正確な節約量の主張

必要な指示、影響範囲、安全確認、検証、エラー処理は省略しません。効率と品質が衝突する場合は、正確性・安全性・タスク完了を優先します。

### 発動方法

暗黙発動は無効です。必要なタスクで明示的に選択してください。

- ChatGPTデスクトップ: `@token-efficient`
- Codex CLI / IDE: `$token-efficient`、または`/skills`から選択

### インストール

Universal Plugins Directoryでの公開前は、standalone skillとして手動インストールできます。

```text
~/.agents/skills/token-efficient/
├── SKILL.md
└── agents/
    └── openai.yaml
```

Windows PowerShellの例:

```powershell
git clone https://github.com/ta2ta2yo-sudo/token-efficient.git token-efficient-repo
New-Item -ItemType Directory -Force "$env:USERPROFILE\.agents\skills"
Copy-Item -Recurse -LiteralPath ".\token-efficient-repo\skills\token-efficient" -Destination "$env:USERPROFILE\.agents\skills\token-efficient"
```

公開後はUniversal Plugins Directoryからインストールできる予定です。現在の提出状況は[申請チェックリスト](submission/CHECKLIST.md)で確認できます。

### 向いているタスク

- コードや文書の調査・編集
- 大きなリポジトリ、ログ、データの確認
- 冗長になりやすい長時間タスク
- 品質を落とさず、読み込みと出力を絞りたい作業

## English

### Overview

`token-efficient` is a lightweight skills-only plugin for reducing unnecessary token usage while preserving the quality of work performed by ChatGPT and Codex. It requires no external server, account, authentication, or API key.

It focuses on avoiding:

- Reading entire files or logs when targeted ranges are sufficient
- Guess-driven exploration and repeated reads of unchanged evidence
- Rewriting whole files for small changes
- Excessively long tool output, progress updates, and final responses
- Unmeasured claims about exact token or cost savings

It does not skip required instructions, affected context, safety checks, verification, or error handling. When efficiency conflicts with quality, it prioritizes correctness, safety, and task completion.

### Invocation

Implicit invocation is disabled. Select the skill explicitly for tasks where you want it applied.

- ChatGPT desktop: `@token-efficient`
- Codex CLI / IDE: `$token-efficient`, or select it through `/skills`

### Installation

Until it is published in the Universal Plugins Directory, install it manually as a standalone skill:

```text
~/.agents/skills/token-efficient/
├── SKILL.md
└── agents/
    └── openai.yaml
```

Windows PowerShell example:

```powershell
git clone https://github.com/ta2ta2yo-sudo/token-efficient.git token-efficient-repo
New-Item -ItemType Directory -Force "$env:USERPROFILE\.agents\skills"
Copy-Item -Recurse -LiteralPath ".\token-efficient-repo\skills\token-efficient" -Destination "$env:USERPROFILE\.agents\skills\token-efficient"
```

After approval and publication, it is intended to be installable from the Universal Plugins Directory. Track the current state in the [submission checklist](submission/CHECKLIST.md).

### Good fits

- Investigating or editing code and documents
- Working with large repositories, logs, or datasets
- Long-running tasks that tend to accumulate context
- Tasks where reads and output should stay narrow without reducing quality

## Plugin package

```text
.
├── .codex-plugin/plugin.json
├── assets/
├── skills/token-efficient/
├── docs/
└── submission/
```

- [Privacy / プライバシー](docs/PRIVACY.md)
- [Terms / 利用規約](docs/TERMS.md)
- [Support / サポート](docs/SUPPORT.md)
- [Submission checklist](submission/CHECKLIST.md)

This plugin does not guarantee a specific token reduction. Actual usage depends on the task, model, tools, and required verification.

## Compatibility

The skill follows the OpenAI agent skill format used by ChatGPT and Codex. See the [OpenAI skill documentation](https://learn.chatgpt.com/docs/build-skills) and [plugin packaging documentation](https://developers.openai.com/plugins/build/plugins).

## License / ライセンス

MIT License. See [LICENSE](LICENSE).

MITライセンスで公開しています。詳細は[LICENSE](LICENSE)を参照してください。
