# Token Efficient

A lightweight skill for ChatGPT and Codex that reduces unnecessary context, file reads, searches, tool output, and response length without sacrificing correctness or safety.

[日本語](#日本語) | [English](#english)

## 日本語

### 概要

`token-efficient`は、ChatGPTとCodexの作業品質を保ちながら、不要なトークン消費を減らすための軽量スキルです。

主に次の無駄を抑えます。

- ファイルやログの丸読み
- あてずっぽうな探索と同じ情報の再読
- 小さな変更でのファイル全体の書き直し
- 長すぎるツール出力、途中報告、最終回答
- 根拠のない正確な節約量の主張

一方で、必要な指示、影響範囲、安全確認、検証、エラー処理は省略しません。効率と品質が衝突する場合は、正確性・安全性・タスク完了を優先します。

### 発動方法

このスキルは暗黙発動を無効にしています。必要なタスクで明示的に選択してください。

- ChatGPTデスクトップ: `@token-efficient`
- Codex CLI / IDE: `$token-efficient`、または`/skills`から選択

### インストール

リポジトリ内の`token-efficient`フォルダを、ユーザー用スキルディレクトリへコピーします。

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
Copy-Item -Recurse -LiteralPath ".\token-efficient-repo\token-efficient" -Destination "$env:USERPROFILE\.agents\skills\token-efficient"
```

### 向いているタスク

- コードや文書の調査・編集
- 大きなリポジトリ、ログ、データの確認
- 冗長になりやすい長時間タスク
- 品質を落とさず、読み込みと出力を絞りたい作業

このスキルはトークン削減量を保証するものではありません。実際の消費量は、タスク、モデル、利用ツール、必要な検証によって変わります。

## English

### Overview

`token-efficient` is a lightweight skill for reducing unnecessary token usage while preserving the quality of work performed by ChatGPT and Codex.

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

Copy the repository's `token-efficient` folder into your user skill directory:

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
Copy-Item -Recurse -LiteralPath ".\token-efficient-repo\token-efficient" -Destination "$env:USERPROFILE\.agents\skills\token-efficient"
```

### Good fits

- Investigating or editing code and documents
- Working with large repositories, logs, or datasets
- Long-running tasks that tend to accumulate context
- Tasks where reads and output should stay narrow without reducing quality

This skill does not guarantee a specific token reduction. Actual usage depends on the task, model, tools, and verification required.

## Compatibility

The skill follows the OpenAI agent skill format used by ChatGPT and Codex. See the [OpenAI skill documentation](https://learn.chatgpt.com/docs/build-skills).

## License

No license has been selected yet. Public repository visibility does not by itself grant permission to reuse or redistribute the contents.
