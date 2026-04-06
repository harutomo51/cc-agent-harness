# cc-agent-harness

Claude Code Agent Team のスキル定義・運用基盤リポジトリ。

19の専門エージェントが連携してWebアプリ開発を行うマルチエージェントシステムの設定・定義を管理します。

## 概要

- **性質**: Claude Code Agent Team のスキル定義・運用基盤（コード開発プロジェクトではない）
- **主要ファイル形式**: Markdown（エージェント定義）、JSON（スキーマ、タスク）
- **エージェント定義**: `.claude/agents/`（19エージェント）

## エージェント構成

| エージェント | 略称 | 役割 |
|------------|------|------|
| **ceo** | CEO | 統括者・人間との唯一の窓口 |
| **agent-router** | AR | 専門エージェントへのルーティング・実行計画策定 |
| **knowledge-manager** | KM | 知識・コンテキスト管理 |
| **context-graph** | CG | 依存関係グラフ・変更影響分析 |
| **architect-evaluator** | ARCH-EVAL | Gate 1: アーキテクチャ評価 |
| **design-evaluator** | DESIGN-EVAL | Gate 2: デザイン評価 |
| architect | ARCH | システム構造設計 |
| tech-lead | TL | 技術スタック選定・規約策定 |
| ui-ux-designer | UIUX | UI/UX設計 |
| database-specialist | DBA | DB設計・スキーマ |
| project-manager | PM | タスク管理・WBS |
| frontend-expert | FE | UI実装 |
| backend-expert | BE | API実装 |
| infra-expert | INFRA | インフラ構築 |
| cicd-engineer | CICD | CI/CDパイプライン |
| security-expert | SEC | セキュリティ |
| reviewer | REV | コードレビュー |
| tester | TEST | テスト |
| document-writer | DOC | ドキュメント整備 |

## 使い方

開発タスクは **CEO エージェント** に委任してください。

```
CEO -> AR -> 専門エージェント群
```

詳細なオペレーションシーケンスは [OPERATION-SEQUENCE.md](OPERATION-SEQUENCE.md) を参照。

## ワークスペース初期化

初回利用前にワークスペースを初期化してください。

- Windows: `scripts/init-workspace.ps1`
- Linux / macOS: `bash scripts/init-workspace.sh`

## 環境

- OS: Windows 11 / シェル: bash (Git Bash)
- Python: 3.11+（検証スクリプト用）/ 依存管理: `uv`
- Hook 依存: `jsonschema`, `markdownlint-cli`

## ライセンス

[MIT](LICENSE)
