<div align="center">
    <img src="./media/logo_large.webp" alt="Spec Kit Logo" width="200" height="200"/>
    <h1>🌱 Spec Kit</h1>
    <h3><em>高品質なソフトウェアをより速く構築。</em></h3>
</div>

<p align="center">
    <strong>開発者が製品のシナリオと予測可能な成果に集中できるようにし、毎回ゼロから vibe coding する必要がないオープンソースツールキットです。</strong>
</p>

<p align="center">
    <a href="https://github.com/github/spec-kit/releases/latest"><img src="https://img.shields.io/github/v/release/github/spec-kit" alt="Latest Release"/></a>
    <a href="https://github.com/github/spec-kit/stargazers"><img src="https://img.shields.io/github/stars/github/spec-kit?style=social" alt="GitHub stars"/></a>
    <a href="https://github.com/github/spec-kit/blob/main/LICENSE"><img src="https://img.shields.io/github/license/github/spec-kit" alt="License"/></a>
    <a href="https://github.github.io/spec-kit/"><img src="https://img.shields.io/badge/docs-GitHub_Pages-blue" alt="Documentation"/></a>
</p>

---

## 目次

- [🤔 Spec-Driven Development とは？](#-spec-driven-development-とは)
- [⚡ クイックスタート](#-クイックスタート)
- [📽️ ビデオ概要](#️-ビデオ概要)
- [🧩 コミュニティ拡張機能](#-コミュニティ拡張機能)
- [🎨 コミュニティプリセット](#-コミュニティプリセット)
- [🚶 コミュニティチュートリアル](#-コミュニティチュートリアル)
- [🛠️ コミュニティフレンド](#️-コミュニティフレンド)
- [🤖 対応している AI コーディングエージェント統合](#-対応している-ai-コーディングエージェント統合)
- [🔧 Specify CLI リファレンス](#-specify-cli-リファレンス)
- [🧩 Spec Kit を自分好みにカスタマイズ：拡張機能とプリセット](#-spec-kit-を自分好みにカスタマイズ拡張機能とプリセット)
- [📚 コア哲学](#-コア哲学)
- [🌟 開発フェーズ](#-開発フェーズ)
- [🎯 実験的な目標](#-実験的な目標)
- [🔧 前提条件](#-前提条件)
- [📖 詳細情報](#-詳細情報)
- [📋 詳細なプロセス](#-詳細なプロセス)
- [🔍 トラブルシューティング](#-トラブルシューティング)
- [💬 サポート](#-サポート)
- [🙏 謝辞](#-謝辞)
- [📄 ライセンス](#-ライセンス)

## 🤔 Spec-Driven Development とは？

Spec-Driven Development（仕様駆動開発）は、従来のソフトウェア開発の常識を**覆す**アプローチです。何十年も前から、コードが最優先で、仕様はコーディングの「本番作業」が始まったら捨ててしまう足場に過ぎませんでした。Spec-Driven Development はこの状況を変えるものです：**仕様が実行可能**になり、開発を導くだけでなく、直接 working implementation を生成します。

## ⚡ クイックスタート

### 1. Specify CLI のインストール

お好みのインストール方法を選択してください：

> **重要:** Spec Kit の公式でメンテナンスされているパッケージは、この GitHub リポジトリからのみ公開されています。PyPI 上で同名のパッケージは**このプロジェクトとは関係なく**、Spec Kit のメンテナによってメンテナンスされていません。必ず以下のように GitHub から直接インストールしてください。

#### オプション 1: 永続的なインストール（推奨）

一度インストールして、どこでも使用できます。安定性のために特定のリリースタグを固定してください（最新版は [Releases](https://github.com/github/spec-kit/releases) を確認してください）：

```bash
# 特定の安定版をインストール（推奨 — vX.Y.Z を最新のタグに置き換えてください）
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git@vX.Y.Z

# または main から最新版をインストール（未リリースの変更を含む可能性があります）
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git

# 代替: pipx を使用（これも動作します）
pipx install git+https://github.com/github/spec-kit.git@vX.Y.Z
pipx install git+https://github.com/github/spec-kit.git
```

その後、正しいバージョンがインストールされたことを確認してください：

```bash
specify version
```

そしてツールを直接使用します：

```bash
# 新規プロジェクトを作成
specify init <PROJECT_NAME>

# または既存プロジェクトで初期化
specify init . --integration copilot
# または
specify init --here --integration copilot

# インストール済みツールを確認
specify check
```

Specify をアップグレードするには、[アップグレードガイド](./docs/upgrade.md) を参照してください。クイックアップグレード：

```bash
uv tool install specify-cli --force --from git+https://github.com/github/spec-kit.git@vX.Y.Z
# pipx ユーザー: pipx install --force git+https://github.com/github/spec-kit.git@vX.Y.Z
```

#### オプション 2: 一回限りの使用

インストールせずに直接実行：

```bash
# 新規プロジェクトを作成（安定版に固定 — vX.Y.Z を最新のタグに置き換えてください）
uvx --from git+https://github.com/github/spec-kit.git@vX.Y.Z specify init <PROJECT_NAME>

# または既存プロジェクトで初期化
uvx --from git+https://github.com/github/spec-kit.git@vX.Y.Z specify init . --integration copilot
# または
uvx --from git+https://github.com/github/spec-kit.git@vX.Y.Z specify init --here --integration copilot
```

**永続的なインストールの利点:**

- ツールがインストールされたままになり、PATH で利用可能
- シェルエイリアスを作成する必要なし
- `uv tool list`、`uv tool upgrade`、`uv tool uninstall` によるより良いツール管理
- クリーンなシェル設定

#### オプション 3: エンタープライズ / エアギャップインストール

環境が PyPI や GitHub へのアクセスをブロックしている場合は、[エンタープライズ / エアギャップインストール](./docs/installation.md#enterprise--air-gapped-installation)ガイドを参照してください。接続されたマシンで `pip download` を使用して、携帯性のある OS 固有の wheel バンドルを作成する手順が記載されています。

### 2. プロジェクトの原則を確立

プロジェクトディレクトリでコーディングエージェントを起動します。ほとんどのエージェントは spec-kit を `/speckit.*` スラッシュコマンドとして公開します；Codex CLI のスキルモードでは代わりに `$speckit-*` を使用します。

**`/speckit.constitution`** コマンドを使用して、プロジェクトの統治原則と開発ガイドラインを作成し、その後のすべての開発を導きます。

```bash
/speckit.constitution コード品質、テスト基準、ユーザーエクスペリエンスの一貫性、パフォーマンス要件に焦点を当てた原則を作成してください
```

### 3. 仕様を作成

**`/speckit.specify`** コマンドを使用して、構築したいものを記述します。**何を**、**なぜ**に焦点を当て、テクノロジースタックには焦点を当てないでください。

```bash
/speckit.specify 私の写真を別々のフォトアルバムに整理できるアプリケーションを構築します。アルバムは日付でグループ化され、メインページでドラッグアンドドロップで再編成できます。アルバムは他のネストされたアルバムには決して含まれません。各アルバム内では、写真がタイルのようなインターフェースでプレビューされます。
```

### 4. 技術的な実装計画を作成

**`/speckit.plan`** コマンドを使用して、テクノロジースタックとアーキテクチャの選択を提供します。

```bash
/speckit.plan アプリケーションは最小限のライブラリ数で Vite を使用します。可能な限りバニラの HTML、CSS、JavaScript を使用します。画像はどこにもアップロードされず、メタデータはローカルの SQLite データベースに保存されます。
```

### 5. タスクに分解

**`/speckit.tasks`** を使用して、実装計画から実行可能なタスクリストを作成します。

```bash
/speckit.tasks
```

### 6. 実装を実行

**`/speckit.implement`** を使用して、計画に従ってすべてのタスクを実行し、機能を構築します。

```bash
/speckit.implement
```

詳細なステップバイステップの手順については、[包括的なガイド](./spec-driven.md)を参照してください。
## 📽️ ビデオ概要

Spec Kit を実際の動作で見たいですか？[ビデオ概要](https://www.youtube.com/watch?v=a9eR1xsfvHg&pp=0gcJCckJAYcqIYzv)を視聴してください！

[![Spec Kit ビデオヘッダー](/media/spec-kit-video-header.jpg)](https://www.youtube.com/watch?v=a9eR1xsfvHg&pp=0gcJCckJAYcqIYzv)

## 🧩 コミュニティ拡張機能

> [!NOTE]
> コミュニティ拡張機能は、それぞれの作者によって独立して作成・メンテナンスされています。GitHub と Spec Kit のメンテナは、コミュニティカタログにエントリを追加するプルリクエストをフォーマット、カタログ構造、またはポリシー準拠のためにレビューする場合がありますが、**拡張機能コード自体のレビュー、監査、承認、またはサポートは行いません**。コミュニティ拡張機能ウェブサイトもサードパーティのリソースです。インストールと使用前に拡張機能のソースコードを確認し、自己責任で使用してください。

🔍 **[コミュニティ拡張機能ウェブサイト](https://speckit-community.github.io/extensions/)でコミュニティ拡張機能を閲覧および検索してください。**

以下のコミュニティ貢献拡張機能が [`catalog.community.json`](extensions/catalog.community.json) で利用可能です：

**カテゴリ:**

- `docs` — 仕様アーティファクトを読み取り、検証、または生成
- `code` — ソースコードをレビュー、検証、または変更
- `process` — フェーズ全体でワークフローをオーケストレート
- `integration` — 外部プラットフォームと同期
- `visibility` — プロジェクトの健全性や進捗を報告

**効果:**

- `Read-only` — ファイルを変更せずにレポートを生成
- `Read+Write` — ファイルを変更し、アーティファクトを作成、または仕様を更新

| 拡張機能 | 目的 | カテゴリ | 効果 | URL |
|----------|------|----------|------|-----|
| Agent Assign | 特化した Claude Code エージェントを spec-kit タスクに割り当ててターゲット実行 | `process` | Read+Write | [spec-kit-agent-assign](https://github.com/xymelon/spec-kit-agent-assign) |
| AI-Driven Engineering (AIDE) | AI アシスタントを使用してビジョンから実装までの一連の7ステップワークフロー | `process` | Read+Write | [aide](https://github.com/mnriem/spec-kit-extensions/tree/main/aide) |
| Architect Impact Previewer | 実装前に提案された変更のアーキテクチャへの影響、複雑さ、リスクを予測 | `visibility` | Read-only | [spec-kit-architect-preview](https://github.com/UmmeHabiba1312/spec-kit-architect-preview) |
| Archive Extension | 統合された機能をメインプロジェクトメモリにアーカイブ | `docs` | Read+Write | [spec-kit-archive](https://github.com/stn1slv/spec-kit-archive) |
| Azure DevOps Integration | OAuth 認証を使用してユーザーストーリーとタスクを Azure DevOps のワークアイテムと同期 | `integration` | Read+Write | [spec-kit-azure-devops](https://github.com/pragya247/spec-kit-azure-devops) |
| Blueprint | AI 駆動開発でコードリテラシーを維持：/speckit.implement 実行前に仕様アーティファクトから各タスクの完全なコードブループリントをレビュー | `docs` | Read+Write | [spec-kit-blueprint](https://github.com/chordpli/spec-kit-blueprint) |
| Branch Convention | /specify のための設定可能なブランチとフォルダ命名規則、プリセットとカスタムパターン | `process` | Read+Write | [spec-kit-branch-convention](https://github.com/Quratulain-bilal/spec-kit-branch-convention) |
| Brownfield Bootstrap | 既存のコードベースに spec-kit をブートストラップ — アーキテクチャを自動検出し、SDD を段階的に採用 | `process` | Read+Write | [spec-kit-brownfield](https://github.com/Quratulain-bilal/spec-kit-brownfield) |
| Bugfix Workflow | 構造化されたバグ修正ワークフロー — バグをキャプチャし、仕様アーティファクトにトレースし、仕様を外科的にパッチ | `process` | Read+Write | [spec-kit-bugfix](https://github.com/Quratulain-bilal/spec-kit-bugfix) |
| Canon | キャノン駆動（ベースライン駆動）ワークフローを追加：仕様優先、コード優先、仕様ドリフト。Canon Core プリセットのインストールが必要 | `process` | Read+Write | [spec-kit-canon](https://github.com/maximiliamus/spec-kit-canon/tree/master/extension) |
| Catalog CI | spec-kit コミュニティカタログエントリの自動検証 — 構造、URL、差分、リンティング | `process` | Read-only | [spec-kit-catalog-ci](https://github.com/Quratulain-bilal/spec-kit-catalog-ci) |
| CI Guard | CI/CD のための仕様準拠ゲート — 仕様の存在を検証し、ドリフトをチェックし、ギャップがある場合はマージをブロック | `process` | Read-only | [spec-kit-ci-guard](https://github.com/Quratulain-bilal/spec-kit-ci-guard) |
| Checkpoint Extension | 実装の途中で変更をコミットし、最後に非常に大きなコミットが1つだけになるのを防ぐ | `code` | Read+Write | [spec-kit-checkpoint](https://github.com/aaronrsun/spec-kit-checkpoint) |
| Cleanup Extension | 実装後の品質ゲート — 変更をレビューし、小さな問題（スカウトルール）を修正し、中程度の問題のタスクを作成し、大きな問題の分析を生成 | `code` | Read+Write | [spec-kit-cleanup](https://github.com/dsrednicki/spec-kit-cleanup) |
| Conduct Extension | コンテキスト汚染を減らすためにサブエージェント委任で spec-kit フェーズをオーケストレート | `process` | Read+Write | [spec-kit-conduct-ext](https://github.com/twbrandon7/spec-kit-conduct-ext) |
| Confluence Extension | 仕様と計画ファイルを要約する Confluence ドキュメントを作成 | `integration` | Read+Write | [spec-kit-confluence](https://github.com/aaronrsun/spec-kit-confluence) |
| DocGuard — CDD 強制 | キャノニカル駆動開発の強制。自動チェック、AI 駆動ワークフロー、spec-kit フックを使用してプロジェクトドキュメントを検証、スコアリング、トレース。NPM のランタイム依存関係ゼロ | `docs` | Read+Write | [spec-kit-docguard](https://github.com/raccioly/docguard) |
| Extensify | 拡張機能と拡張機能カタログの作成と検証 | `process` | Read+Write | [extensify](https://github.com/mnriem/spec-kit-extensions/tree/main/extensify) |
| Fix Findings | spec の見つかった問題をクリーンになるまで自動的に分析・修正・再分析のループ | `code` | Read+Write | [spec-kit-fix-findings](https://github.com/Quratulain-bilal/spec-kit-fix-findings) |
| FixIt Extension | spec 対応のバグ修正 — バグを仕様アーティファクトにマッピングし、計画を提案し、最小限の変更を適用 | `code` | Read+Write | [spec-kit-fixit](https://github.com/speckit-community/spec-kit-fixit) |
| Fleet Orchestrator | すべての SpecKit フェーズでヒューマン・イン・ザ・ループゲートを伴って完全な機能ライフサイクルをオーケストレート | `process` | Read+Write | [spec-kit-fleet](https://github.com/sharathsatish/spec-kit-fleet) |
| GitHub Issues Integration 1 | GitHub Issues から仕様アーティファクトを生成 — 問題をインポートし、更新を同期し、双方向のトレーサビリティを維持 | `integration` | Read+Write | [spec-kit-github-issues](https://github.com/Fatima367/spec-kit-github-issues) |
| GitHub Issues Integration 2 | 既存の GitHub 問題からローカル仕様を作成および同期 | `integration` | Read+Write | [spec-kit-issue](https://github.com/aaronrsun/spec-kit-issue) |
| Iterate | 2段階の定義と適用ワークフローで仕様ドキュメントを反復 — 実装中に仕様を微調整し、すぐに構築に戻る | `docs` | Read+Write | [spec-kit-iterate](https://github.com/imviancagrace/spec-kit-iterate) |
| Jira Integration | 設定可能な階層とカスタムフィールドサポートで Jira のエピック、ストーリー、および問題を spec-kit の仕様とタスク分解から作成 | `integration` | Read+Write | [spec-kit-jira](https://github.com/mbachorik/spec-kit-jira) |
| Learning Extension | 実装から教育ガイドを生成し、メンタリングコンテキストで明確化を強化 | `docs` | Read+Write | [spec-kit-learn](https://github.com/imviancagrace/spec-kit-learn) |
| MAQA — マルチエージェント & 品質保証 | 協調者 → 機能 → QA エージェントワークフロー、並列 worktree ベースの実装。言語非依存。インストールされたボードプラグインを自動検出。オプションの CI ゲート | `process` | Read+Write | [spec-kit-maqa-ext](https://github.com/GenieRobot/spec-kit-maqa-ext) |
| MAQA Azure DevOps Integration | MAQA のための Azure DevOps Boards 統合 — 機能の進行に伴ってユーザーストーリーとタスクの子を同期 | `integration` | Read+Write | [spec-kit-maqa-azure-devops](https://github.com/GenieRobot/spec-kit-maqa-azure-devops) |
| MAQA CI/CD Gate | GitHub Actions、CircleCI、GitLab CI、Bitbucket Pipelines を自動検出。QA ハンドオフをブロックし、パイプラインがグリーンになるまで待機 | `process` | Read+Write | [spec-kit-maqa-ci](https://github.com/GenieRobot/spec-kit-maqa-ci) |
| MAQA GitHub Projects Integration | MAQA のための GitHub Projects v2 統合 — 機能の進行に伴ってドラフト問題とステータスカラムを同期 | `integration` | Read+Write | [spec-kit-maqa-github-projects](https://github.com/GenieRobot/spec-kit-maqa-github-projects) |
| MAQA Jira Integration | MAQA のための Jira 統合 — ボードを通過する機能の進行に伴ってストーリーとサブタスクを同期 | `integration` | Read+Write | [spec-kit-maqa-jira](https://github.com/GenieRobot/spec-kit-maqa-jira) |
| MAQA Linear Integration | MAQA のための Linear 統合 — 機能の進行に伴ってワークフローステート全体で問題とサブ問題を同期 | `integration` | Read+Write | [spec-kit-maqa-linear](https://github.com/GenieRobot/spec-kit-maqa-linear) |
| MAQA Trello Integration | MAQA のための Trello ボード統合 — 仕様からボードを埋め、カードを移動し、リアルタイムでチェックリストをチェック | `integration` | Read+Write | [spec-kit-maqa-trello](https://github.com/GenieRobot/spec-kit-maqa-trello) |
| MarkItDown Document Converter | ドキュメント（PDF、Word、PowerPoint、Excelなど）を Markdown に変換し、仕様の参考資料として使用 | `docs` | Read+Write | [spec-kit-markitdown](https://github.com/BenBtg/spec-kit-markitdown) |
| Memory Loader | ライフサイクルコマンドの前に .specify/memory/ ファイルをロードし、LLM エージェントがプロジェクト統治コンテキストを持つように | `docs` | Read-only | [spec-kit-memory-loader](https://github.com/KevinBrown5280/spec-kit-memory-loader) |
| Memory MD | Spec Kit プロジェクトのためのリポジトリネイティブの永続的なメモリ | `docs` | Read+Write | [spec-kit-memory-hub](https://github.com/DyanGalih/spec-kit-memory-hub) |
| MemoryLint | エージェントメモリ統治ツール：AGENTS.md と憲法の間の境界の競合を自動的に監査し、修正 | `process` | Read+Write | [memorylint](https://github.com/RbBtSn0w/spec-kit-extensions/tree/main/memorylint) |
| Microsoft 365 Integration | Teams のメッセージ、会議の議事録、SharePoint/OneDrive のファイルをローカルの Markdown として取得し、仕様生成に使用 | `integration` | Read+Write | [spec-kit-m365](https://github.com/BenBtg/spec-kit-m365) |
| Onboard | spec-kit プロジェクトに新しい開発者のための文脈的なオンボーディングと段階的な成長。仕様を説明し、依存関係をマッピングし、理解を検証し、次のステップをガイド | `process` | Read+Write | [spec-kit-onboard](https://github.com/dmux/spec-kit-onboard) |
| Optimize | コンテキスト効率のための AI 統治の監査と最適化 — トークン予算、ルールの健全性、解釈可能性、圧縮、一貫性、エコー検出 | `process` | Read+Write | [spec-kit-optimize](https://github.com/sakitA/spec-kit-optimize) |
| OWASP LLM Threat Model | OWASP Top 10 for LLM Applications 2025 の脅威分析、エージェントアーティファクト | `code` | Read-only | [spec-kit-threatmodel](https://github.com/NaviaSamal/spec-kit-threatmodel) |
| Plan Review Gate | タスク生成を許可する前に、spec.md と plan.md を MR/PR 経由でマージすることを要求 | `process` | Read-only | [spec-kit-plan-review-gate](https://github.com/luno/spec-kit-plan-review-gate) |
| PR Bridge | spec アーティファクトからプルリクエストの説明、チェックリスト、サマリーを自動生成 | `process` | Read-only | [spec-kit-pr-bridge-](https://github.com/Quratulain-bilal/spec-kit-pr-bridge-) |
| Presetify | プリセットとプリセットカタログの作成と検証 | `process` | Read+Write | [presetify](https://github.com/mnriem/spec-kit-extensions/tree/main/presetify) |
| Product Forge | 研究からリリースまでの完全な製品ライフサイクル — ポートフォリオ、ライトモード、モノレポ、オプションの V モデル | `process` | Read+Write | [speckit-product-forge](https://github.com/VaiYav/speckit-product-forge) |
| Project Health Check | Spec Kit プロジェクトを診断し、構造、エージェント、機能、スクリプト、拡張機能、git の健全性の問題を報告 | `visibility` | Read-only | [spec-kit-doctor](https://github.com/KhawarHabibKhan/spec-kit-doctor) |
| Project Status | 現在の SDD ワークフローの進捗を表示 — アクティブな機能、アーティファクトの状態、タスクの完了、ワークフローフェーズ、拡張機能のサマリー | `visibility` | Read-only | [spec-kit-status](https://github.com/KhawarHabibKhan/spec-kit-status) |
| QA Testing Extension | 仕様からの受入基準のブラウザ駆動または CLI ベースの検証による体系的な QA テスト | `code` | Read-only | [spec-kit-qa](https://github.com/arunt14/spec-kit-qa) |
| Ralph Loop | AI エージェント CLI を使用した自律的な実装ループ | `code` | Read+Write | [spec-kit-ralph](https://github.com/Rubiss/spec-kit-ralph) |
| Reconcile Extension | 機能アーティファクトを外科的に更新して実装ドリフトを調整 | `docs` | Read+Write | [spec-kit-reconcile](https://github.com/stn1slv/spec-kit-reconcile) |
| Red Team | /speckit.plan の前に仕様の敵対的レビュー — 並列レンズエージェントが、構造的に clarify/analyze できないリスク（プロンプトインジェクション、完全性ギャップ、クロス仕様ドリフト、サイレント障害）を表面化。構造化された見つかった問題のレポートを生成；仕様への自動編集なし | `docs` | Read+Write | [spec-kit-red-team](https://github.com/ashbrener/spec-kit-red-team) |
| Repository Index | 既存のリポジトリのインデックスを生成し、概要、アーキテクチャ、モジュールレベルを提供 | `docs` | Read-only | [spec-kit-repoindex](https://github.com/liuyiyu/spec-kit-repoindex) |
| Retro Extension | メトリクス、仕様の正確性評価、改善提案を伴うスプリントの振り返り分析 | `process` | Read+Write | [spec-kit-retro](https://github.com/arunt14/spec-kit-retro) |
| Retrospective Extension | 実装後の振り返��� — 仕様準拠スコア、ドリフト分析、ヒューマンゲート付き仕様更新 | `docs` | Read+Write | [spec-kit-retrospective](https://github.com/emi-dm/spec-kit-retrospective) |
| Review Extension | 実装後の包括的なコードレビュー — コード品質、コメント、テスト、エラーハンドリング、タイプデザイン、簡素化のための専門エージェント | `code` | Read-only | [spec-kit-review](https://github.com/ismaelJimenez/spec-kit-review) |
| Ripple | 実装後のテストでキャッチできない副作用を検出 — 9つのドメイン非依存カテゴリでデルタアンカー分析 | `code` | Read+Write | [spec-kit-ripple](https://github.com/chordpli/spec-kit-ripple) |
| Reconcile Extension | 機能アーティファクトを外科的に更新して実装ドリフトを調整 | `docs` | Read+Write | [spec-kit-reconcile](https://github.com/stn1slv/spec-kit-reconcile) |
| Red Team | /speckit.plan の前に仕様の敵対的レビュー — 並列レンズエージェントが、構造的に clarify/analyze できないリスク（プロンプトインジェクション、完全性ギャップ、クロス仕様ドリフト、サイレント障害）を表面化。構造化された見つかった問題のレポートを生成；仕様への自動編集なし | `docs` | Read+Write | [spec-kit-red-team](https://github.com/ashbrener/spec-kit-red-team) |
| Repository Index | 既存のリポジトリのインデックスを生成し、概要、アーキテクチャ、モジュールレベルを提供 | `docs` | Read-only | [spec-kit-repoindex](https://github.com/liuyiyu/spec-kit-repoindex) |
| Retro Extension | メトリクス、仕様の正確性評価、改善提案を伴うスプリントの振り返り分析 | `process` | Read+Write | [spec-kit-retro](https://github.com/arunt14/spec-kit-retro) |
| Retrospective Extension | 実装後の振り返り — 仕様準拠スコア、ドリフト分析、ヒューマンゲート付き仕様更新 | `docs` | Read+Write | [spec-kit-retrospective](https://github.com/emi-dm/spec-kit-retrospective) |
| Review Extension | 実装後の包括的なコードレビュー — コード品質、コメント、テスト、エラーハンドリング、タイプデザイン、簡素化のための専門エージェント | `code` | Read-only | [spec-kit-review](https://github.com/ismaelJimenez/spec-kit-review) |
| Ripple | 実装後のテストでキャッチできない副作用を検出 — 9つのドメイン非依存カテゴリでデルタアンカー分析 | `code` | Read+Write | [spec-kit-ripple](https://github.com/chordpli/spec-kit-ripple) |
| SDD Utilities | 中断されたワークフローを再開し、プロジェクトの健全性を検証し、仕様からタスクへのトレーサビリティを確認 | `process` | Read+Write | [speckit-utils](https://github.com/mvanhorn/speckit-utils) |
| Security Review | フルプロジェクトのセキュア・バイ・デザインセキュリティ監査に加え、段階的、ブランチ/PR、計画、タスク、フォローアップ、適用レビュー | `code` | Read+Write | [spec-kit-security-review](https://github.com/DyanGalih/spec-kit-security-review) |
| SFSpeckit | 18のコマンドを備えたエンタープライズ Salesforce SDLC、完全な SDD ライフサイクルに対応 | `process` | Read+Write | [spec-kit-sf](https://github.com/ysumanth06/spec-kit-sf) |
| Ship Release Extension | リリースパイプラインを自動化：プレフライトチェック、ブランチ同期、チェンジログ生成、CI 検証、PR 作成 | `process` | Read+Write | [spec-kit-ship](https://github.com/arunt14/spec-kit-ship) |
| Spec Reference Loader | 機能仕様の ## References セクションを読み取り、リストされたドキュメントのみをコンテキストにロード | `docs` | Read-only | [spec-kit-spec-reference-loader](https://github.com/KevinBrown5280/spec-kit-spec-reference-loader) |
| Spec Critique Extension | 製品戦略とエンジニアリングリスクの観点から spec と plan の二重レンズ批判的レビュー | `docs` | Read-only | [spec-kit-critique](https://github.com/arunt14/spec-kit-critique) |
| Spec Diagram | SDD ワークフロー状態、機能進捗、タスク依存関係の Mermaid 図を自動生成 | `visibility` | Read-only | [spec-kit-diagram-](https://github.com/Quratulain-bilal/spec-kit-diagram-) |
| Spec Orchestrator | 機能間のオーケストレーション — 状態を追跡し、タスクを選択し、並列仕様間の競合を検出 | `process` | Read-only | [spec-kit-orchestrator](https://github.com/Quratulain-bilal/spec-kit-orchestrator) |
| Spec Refine | 仕様をインプレースで更新し、変更を plan とタスクに伝播し、アーティファクト間の影響を差分表示 | `process` | Read+Write | [spec-kit-refine](https://github.com/Quratulain-bilal/spec-kit-refine) |
| Spec Scope | 努力量の推定とスコープ追跡 — 作業量を推定し、スコープクリープを検出し、フェーズごとに時間を予算化 | `process` | Read-only | [spec-kit-scope-](https://github.com/Quratulain-bilal/spec-kit-scope-) |
| Spec Sync | 仕様と実装間のドリフトを検出し、解決。AI アシストされた解決、ヒューマン承認 | `docs` | Read+Write | [spec-kit-sync](https://github.com/bgervin/spec-kit-sync) |
| Spec Validate | 仕様アーティファクトの理解検証、レビューゲート、承認状態 — 段階的クイズ、ピアレビュー SLA、/speckit.implement の前のハードゲート | `process` | Read+Write | [spec-kit-spec-validate](https://github.com/aeltayeb/spec-kit-spec-validate) |
| Spec2Cloud | Azure への出荷に最適化された spec-driven ワークフロー | `process` | Read+Write | [spec2cloud](https://github.com/Azure-Samples/Spec2Cloud) |
| SpecTest | 仕様基準からテストスキャフォールドを自動生成し、カバレッジをマッピングし、テストされていない要件を検出 | `code` | Read+Write | [spec-kit-spectest](https://github.com/Quratulain-bilal/spec-kit-spectest) |
| Squad Bridge | Speckit 仕様とタスクから Squad エージェントチームをブートストラップし、同期 | `process` | Read+Write | [spec-kit-squad](https://github.com/jwill824/spec-kit-squad) |
| Staff Review Extension | 実装を仕様に対して検証し、セキュリティ、パフォーマンス、テストカバレッジをチェックするスタッフエンジニアレベルのコードレビュー | `code` | Read-only | [spec-kit-staff-review](https://github.com/arunt14/spec-kit-staff-review) |
| Status Report | Spec-driven ワークフローのプロジェクト状態、機能進捗、次のアクションの推奨 | `visibility` | Read-only | [Open-Agent-Tools/spec-kit-status](https://github.com/Open-Agent-Tools/spec-kit-status) |
| Superpowers Bridge | obra/superpowers スキルを spec-kit SDD ワークフロー全体でオーケストレート（clarification、TDD、review、verification、critique、debugging、branch completion） | `process` | Read+Write | [superpowers-bridge](https://github.com/RbBtSn0w/spec-kit-extensions/tree/main/superpowers-bridge) |
| Superpowers Bridge (WangX0111) | spec-kit を obra/superpowers（ブレインストーミング、TDD、サブエージェント、コードレビュー）にブリッジし、統一された再開可能なワークフロー、グレースフルデグレード、セッション進捗追跡 | `process` | Read+Write | [superspec](https://github.com/WangX0111/superspec) |
| TinySpec | 小さなタスクのための軽量シングルファイルワークフロー — 重いマルチステップ SDD プロセスをスキップ | `process` | Read+Write | [spec-kit-tinyspec](https://github.com/Quratulain-bilal/spec-kit-tinyspec) |
| Token Consumption Analyzer | SDD ワークフロー全体でトークン消費をキャプチャ、分析、比較 | `visibility` | Read-only | [spec-kit-token-analyzer](https://github.com/coderandhiker/spec-kit-token-analyzer) |
| V-Model Extension Pack | 開発仕様とテスト仕様のペア生成を V-Model で強制し、完全なトレーサビリティを提供 | `docs` | Read+Write | [spec-kit-v-model](https://github.com/leocamello/spec-kit-v-model) |
| Verify Extension | 実装後の品質ゲート、実装されたコードを仕様アーティファクトに対して検証 | `code` | Read-only | [spec-kit-verify](https://github.com/ismaelJimenez/spec-kit-verify) |
| Verify Tasks Extension | パフォーマンス完了の検出：tasks.md で [X] とマークされたタスクで実際の実装���ないもの | `code` | Read-only | [spec-kit-verify-tasks](https://github.com/datastone-inc/spec-kit-verify-tasks) |
| Version Guard | 計画と実装の前に、ライブ npm レジストリに対してテクノロジースタックのバージョンを検証 | `process` | Read-only | [spec-kit-version-guard](https://github.com/KevinBrown5280/spec-kit-version-guard) |
| What-if Analysis | 要件変更の下流への影響（複雑さ、労力、タスク、リスク）を事前にプレビュー | `visibility` | Read-only | [spec-kit-whatif](https://github.com/DevAbdullah90/spec-kit-whatif) |
| Wireframe Visual Feedback Loop | SVG ワイヤーフレームの生成、レビュー、sign-off を spec-driven 開発に追加。承認されたワイヤーフレームは spec 制約として /speckit.plan、/speckit.tasks、/speckit.implement によって尊重される | `visibility` | Read+Write | [spec-kit-extension-wireframe](https://github.com/TortoiseWolfe/spec-kit-extension-wireframe) |
| Work IQ | Microsoft 365 組織の知識を spec-driven 開発ワークフローに統合 | `integration` | Read-only | [spec-kit-workiq](https://github.com/sakitA/spec-kit-workiq) |
| Worktree Isolation | チェックアウト切り替えなしで並列機能開発のための分離された git worktree を生成 | `process` | Read+Write | [spec-kit-worktree](https://github.com/Quratulain-bilal/spec-kit-worktree) |
| Worktrees | 並列エージェントのためのデフォルトオンの worktree 分離 — サブリングまたはネストされたレイアウト | `process` | Read+Write | [spec-kit-worktree-parallel](https://github.com/dango85/spec-kit-worktree-parallel) |

独自の拡張機能を送信するには、[拡張機能公開ガイド](extensions/EXTENSION-PUBLISHING-GUIDE.md)を参照してください。
## 🎨 コミュニティプリセット

コミュニティ貢献プリセットは、Spec Kit の動作をカスタマイズします — ツールを変更せずにテンプレート、コマンド、用語を上書きします。完全なリストは [コミュニティプリセット](https://github.github.io/spec-kit/community/presets.html) ページを参照してください。

> [!NOTE]
> コミュニティプリセットはサードパーティの貢献であり、Spec Kit チームによってメンテナンスされていません。使用前に注意深く確認し、上記のドキュメントページで完全な免責事項を参照してください。

独自のプリセットを送信するには、[プリセット公開ガイド](presets/PUBLISHING.md)を参照してください。

## 🚶 コミュニティチュートリアル

コミュニティ貢献チュートリアルで、さまざまなシナリオにおける Spec-Driven Development の実際の動作を確認してください。完全なリストは [コミュニティチュートリアル](https://github.github.io/spec-kit/community/walkthroughs.html) ページを参照してください。

## 🛠️ コミュニティフレンド

Spec Kit を拡張、可視化、または構築するコミュニティプロジェクト。完全なリストは [コミュニティフレンド](https://github.github.io/spec-kit/community/friends.html) ページを参照してください。

## 🤖 対応している AI コーディングエージェント統合

Spec Kit は 30 以上の AI コーディングエージェントと連携します — CLI ツールと IDE ベースのアシスタントの両方。完全なリストとノート、使用詳細は [対応している AI コーディングエージェント統合](https://github.github.io/spec-kit/reference/integrations.html) ガイドを参照してください。

インストールされたバージョンで利用可能な統合をすべて確認するには、`specify integration list` を実行してください。

## 利用可能なスラッシュコマンド

`specify init` を実行した後、AI コーディングエージェントは構造化開発用のこれらのスラッシュコマンドにアクセスできます。スキルモードをサポートする統合の場合、`--integration <agent> --integration-options="--skills"` を渡すと、スラッシュコマンドプロンプトファイルの代わりにエージェントスキルがインストールされます。

#### コアコマンド

Spec-Driven Development ワークフローのための必須コマンド：

| コマンド | エージェントスキル | 説明 |
| --- | --- | --- |
| `/speckit.constitution` | `speckit-constitution` | プロジェクトの統治原則と開発ガイドラインを作成または更新 |
| `/speckit.specify` | `speckit-specify` | 構築したいものを定義（要件とユーザーストーリー） |
| `/speckit.plan` | `speckit-plan` | 選択したテクノロジースタックで技術的実装計画を作成 |
| `/speckit.tasks` | `speckit-tasks` | 実装のための実行可能なタスクリストを生成 |
| `/speckit.taskstoissues` | `speckit-taskstoissues` | 生成されたタスクリストを GitHub の問題に変換して追跡と実行 |
| `/speckit.implement` | `speckit-implement` | 計画に従ってすべてのタスクを実行し、機能を構築 |

#### オプションのコマンド

品質と検証を強化するための追加コマンド：

| コマンド | エージェントスキル | 説明 |
| --- | --- | --- |
| `/speckit.clarify` | `speckit-clarify` | 未定義の領域を明確化（`/speckit.plan` の前に推奨；以前は `/quizme`） |
| `/speckit.analyze` | `speckit-analyze` | アーティファクト間の整合性とカバレッジ分析（`/speckit.tasks` の後、`/speckit.implement` の前） |
| `/speckit.checklist` | `speckit-checklist` | 要件の完全性、明確さ、一貫性を検証するカスタム品質チェックリストを生成（"English のユニットテスト" のようなもの） |

## 🔧 Specify CLI リファレンス

完全なコマンド詳細、オプション、および例については、[CLI リファレンス](https://github.github.io/spec-kit/reference/overview.html)を参照してください。

## 🧩 Spec Kit を自分好みにカスタマイズ：拡張機能とプリセット

Spec Kit は2つの補完的なシステム — **拡張機能**と**プリセット** — に加えて、1回限りの調整のためのプロジェクトローカルオーバーライドを通じて、ニーズに合わせて調整できます：

| 優先度 | コンポーネントタイプ | 場所 |
| --- | --- | --- |
| ⬆ 1 | プロジェクトローカルオーバーライド | `.specify/templates/overrides/` |
| 2 | プリセット — コアと拡張機能をカスタマイズ | `.specify/presets/templates/` |
| 3 | 拡張機能 — 新しい機能を追加 | `.specify/extensions/templates/` |
| ⬇ 4 | Spec Kit コア — 組み込みの SDD コマンドとテンプレート | `.specify/templates/` |

- **テンプレート**は**ランタイム**に解決されます — Spec Kit はスタックを上から下に歩き、最初の一致を使用します。
- プロジェクトローカルオーバーライド（`.specify/templates/overrides/`）は、完全なプリセットを作成せずに単一プロジェクトの1回限りの調整を可能にします。
- **拡張機能/プリセットコマンド**は**インストール時**に適用されます — `specify extension add` または `specify preset add` を実行すると、コマンドファイルがエージェントディレクトリ（例：`.claude/commands/`）に書き込まれます。
- 複数のプリセットまたは拡張機能が同じコマンドを提供する場合、最高優先度のバージョンが勝ちます。削除すると、次に高い優先度のバージョンが自動的に復元されます。
- オーバーライドやカスタマイズが存在しない場合、Spec Kit はそのコアデフォルトを使用します。

### 拡張機能 — 新しい機能を追加

Spec Kit のコアを超えた機能が必要な場合は、**拡張機能**を使用します。拡張機能は新しいコマンドとテンプレートを導入します — たとえば、組み込みの SDD コマンドでカバーされていないドメイン固有のワークフローを追加したり、外部ツールと統合したり、まったく新しい開発フェーズを追加したりします。*Spec Kit ができること*を拡張します。

```bash
# 利用可能な拡張機能を検索
specify extension search

# 拡張機能をインストール
specify extension add <extension-name>
```

たとえば、拡張機能は Jira 統合、実装後のコードレビュー、V-Model テストトレーサビリティ、またはプロジェクト健全性診断を追加できます。

完全なコマンドガイドについては、[拡張機能リファレンス](https://github.github.io/spec-kit/reference/extensions.html)を参照してください。利用可能なものは上記の[コミュニティ拡張機能](#-コミュニティ拡張機能)を参照してください。

### プリセット — 既存のワークフローをカスタマイズ

Spec Kit に新しい機能を追加せずに*どのように*動作するかを変更したい場合は、**プリセット**を使用します。プリセットはコアとインストールされた拡張機能に付属するテンプレートとコマンドを上書きします — たとえば、コンプライアンス指向の仕様フォーマットを強制したり、ドメイン固有の用語を使用したり、計画やタスクに組織基準を適用したりします。Spec Kit とその拡張機能が生成するアーティファクトと指示をカスタマイズします。

```bash
# 利用可能なプリセットを検索
specify preset search

# プリセットをインストール
specify preset add <preset-name>
```

たとえば、プリセットは仕様テンプレートを再構成して規制トレーサビリティを要求したり、ワークフローを使用しているメソッド（Agile、Kanban、Waterfall、jobs-to-be-done、またはドメイン駆動設計など）に合わせて適応させたり、計画に必須のセキュリティレビューゲートを追加したり、テストファーストのタスク順序を強制したり、またはワークフロー全体を別の言語にローカライズしたりできます。[ピラートークデモ](https://github.com/mnriem/spec-kit-pirate-speak-preset-demo)はカスタマイズがどのくらい深く進むかを示しています。複数のプリセットを優先順位付きでスタックできます。

完全なコマンドガイド、解決順序、優先順位スタックについては、[プリセットリファレンス](https://github.github.io/spec-kit/reference/presets.html)を参照してください。

### いつどれを使用するか

| 目的 | 使用 |
| --- | --- |
| 新しいコマンドまたはワークフローを追加 | 拡張機能 |
| 仕様、計画、またはタスクのフォーマットをカスタマイズ | プリセット |
| 外部ツールまたはサービスを統合 | 拡張機能 |
| 組織的または規制基準を強制 | プリセット |
| 再利用可能なドメイン固有のテンプレートを提供 | どちらも — テンプレートオーバーライド用のプリセット、新しいコマンドでバンドルされたテンプレート用の拡張機能 |

## 📚 コア哲学

Spec-Driven Development は、以下を強調する構造化されたプロセスです：

- **意図駆動開発** — 仕様が "*how*" の前に "*what*" を定義
- **リッチ仕様作成** — ガードレールと組織原則を使用
- **マルチステップ微調整** — 一発のプロンプトからのコード生成ではなく
- **高度な AI モデル機能への依存** — 仕様解釈のため

## 🌟 開発フェーズ

| フェーズ | フォーカス | 主な活動 |
| --- | --- | --- |
| **0-to-1 開発**（"グリーンフィールド"） | スクラッチから生成 | <ul><li>高レベルの要件から開始</li><li>仕様を生成</li><li>実装ステップを計画</li><li>本番対応アプリケーションを構築</li></ul> |
| **クリエイティブな探求** | 並列実装 | <ul><li>多様なソリューションを探索</li><li>多様なテクノロジースタックとアーキテクチャをサポート</li><li>UX パターンを実験</li></ul> |
| **反復的強化**（"ブラウンフィールド"） | ブラウンフィールド近代化 | <ul><li>機能を反復的に追加</li><li>レガシーシステムを近代化</li><li>プロセスを適応</li></ul> |

## 🎯 実験的な目標

私たちの研究と実験は以下に焦点を当てています：

### テクノロジー非依存

- 多様なテクノロジースタックを使用してアプリケーションを構築
- Spec-Driven Development が特定のテクノロジー、プログラミング言語、またはフレームワークに依存しないプロセスであるという仮説を検証

### エンタープライズ制約

- ミッションクリティカルなアプリケーション開発をデモ
- 組織的制約（クラウドプロバイダー、テクノロジースタック、エンジニアリングプラクティス）を組み込み
- エンタープライズデザインシステムとコンプライアンス要件をサポート

### ユーザー中心開発

- 異なるユーザーコホートと好みのためのアプリケーションを構築
- 多様な開発アプローチ（vibe-coding から AI ネイティブ開発まで）をサポート

### クリエイティブおよび反復プロセス

- 並列実装探求の概念を検証
- 強力な反復的機能開発ワークフローを提供
- アップグレードと近代化タスクを処理するためにプロセスを拡張

## 🔧 前提条件

- **Linux/macOS/Windows**
- [対応している](#-対応している-ai-コーディングエージェント統合) AI コーディングエージェント。
- パッケージ管理のための [uv](https://docs.astral.sh/uv/)（推奨）または永続的インストールのための [pipx](https://pypa.github.io/pipx/)
- [Python 3.11+](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads)

エージェントで問題が発生した場合は、問題を開いていただければ、統合を洗練できます。

## 📖 詳細情報

- **[完全な Spec-Driven Development メソッド](./spec-driven.md)** - 全プロセスの深掘り
- **[詳細なチュートリアル](#-詳細なプロセス)** - ステップバイステップの実装ガイド

---

## 📋 詳細なプロセス

<details>
<summary>クリックして詳細なステップバイステップチュートリアルを展開</summary>

Specify CLI を使用してプロジェクトをブートストラップし、必要なアーティファクトを環境に取り込むことができます。実行：

```bash
specify init <project_name>
```

または現在のディレクトリで初期化：

```bash
specify init .
# または --here フラグを使用
specify init --here
# ディレクトリに既にファイルがある場合は確認をスキップ
specify init . --force
# または
specify init --here --force
```

![Specify CLI がターミナルで新しいプロジェクトをブートストラップ](./media/specify_cli.gif)

使用しているコーディングエージェント統合を選択するよう促されます。また、ターミナルで直接事前に指定することもできます：

```bash
specify init <project_name> --integration copilot
specify init <project_name> --integration gemini
specify init <project_name> --integration codex

# または現在のディレクトリ：
specify init . --integration copilot
specify init . --integration codex --integration-options="--skills"

# または --here フラグを使用
specify init --here --integration copilot
specify init --here --integration codex --integration-options="--skills"

# 非空の現在のディレクトリに強制的にマージ
specify init . --force --integration copilot

# または
specify init --here --force --integration copilot
```

CLI は Claude Code、Gemini CLI、Cursor CLI、Qwen CLI、opencode、Codex CLI、Qoder CLI、Tabnine CLI、Kiro CLI、Pi、Forge、Goose、または Mistral Vibe がインストールされているか確認します。インストールされていない場合、または正しいツールを確認せずにテンプレートのみを取得したい場合は、`--ignore-agent-tools` をコマンドに使用：

```bash
specify init <project_name> --integration copilot --ignore-agent-tools
```

### **ステップ 1:** プロジェクトの原則を確立

プロジェクトフォルダに移動し、コーディングエージェントを実行します。例では `claude` を使用しています。

![Claude Code 環境のブートストラップ](./media/bootstrap-claude-code.gif)

`/speckit.constitution`、`/speckit.specify`、`/speckit.plan`、`/speckit.tasks`、および `/speckit.implement` コマンドが利用可能であれば、正しく設定されていることがわかります。

最初のステップは `/speckit.constitution` コマンドを使用してプロジェクトの統治原則を確立することです。これにより、その後のすべての開発フェーズで一貫した意思決定が保証されます：

```text
/speckit.constitution コード品質、テスト基準、ユーザーエクスペリエンスの一貫性、パフォーマンス要件に焦点を当てた原則を作成してください。これらの原則が技術的決定と実装の選択を導くためにどのように統治されるべきかを含めてください。
```

このステップは `.specify/memory/constitution.md` ファイルを作成または更新し、コーディングエージェントが仕様、計画、実装フェーズ中に参照するプロジェクトの基盤となるガイドラインを提供します。

### **ステップ 2:** プロジェクト仕様を作成

プロジェクト原則が確立したら、機能仕様を作成できます。`/speckit.specify` コマンドを使���し、開発したいプロジェクトの具体的な要件を提供します。

> [!IMPORTANT]
> *何を*構築しようとしているか、*なぜ*をできるだけ明確に記述してください。**この時点ではテクノロジースタックに焦点を当てないでください**。

例のプロンプト：

```text
Taskify、チーム生産性プラットフォームを開発します。ユーザーはプロジェクトを作成し、チームメンバーを追加し、タスクを割り当て、コメントし、Kanban スタイルでボード間でタスクを移動できる必要があります。この機能の初期フェーズで、"Create Taskify" と呼びましょう。複数のユーザーを持ちますが、ユーザーは事前に宣言され、事前定義されます。5人のユーザーを2つの異なるカテゴリで作成します。1人のプロダクトマネージャーと4人のエンジニアです。3つの異なるサンプルプロジェクトを作成します。各タスクの状態の標準 Kanban カラムを持ちます。"To Do"、"In Progress"、"In Review"、"Done" です。このアプリケーションにはログインはなく、これは基本機能がセットアップされていることを確認するための最初のテストです。タスクカードの UI で、Kanban ワークボードの異なるカラム間でタスクの現在の状態を変更できる必要があります。特定のカードに無制限の数のコメントを残すことができます。そのタスクカードから、有効なユーザーの1人を割り当てることができます。Taskify を最初に起動すると、5人のユーザーのリストが表示され、从中から選択できます。パスワードは不要です。ユーザーをクリックすると、プロジェクトのリストが表示されるメインビューに入ります。プロジェクトをクリックすると、そのプロジェクトの Kanban ボードが開きます。カラムが表示されます。カードを異なるカラム間でドラッグアンドドロップできるようになります。現在ログインしているユーザーに割り当てられたカードは、他のカードとは異なる色で表示され、素早く自分のカードを確認できます。自分が作ったコメントは編集できますが、他の人が作ったコメントは編集できません。自分が作ったコメントは削除できますが、他の人が作ったコメントは削除できません。
```

このプロンプトが入力された後、Claude Code が計画と仕様の執筆プロセスを開始するはずです。Claude Code はまた、リポジトリをセットアップするためにいくつかの組み込みスクリプトをトリガーします。

このステップが完了すると、新しいブランチ（例：`001-create-taskify`）と `specs/001-create-taskify` ディレクトリに新しい仕様が作成されます。

生成された仕様は、テンプレートで定義された一連のユーザーストーリーと機能要件を含む必要があります。

この段階で、プロジェクトフォルダの内容は次のようになります：

```text
└── .specify
    ├── memory
    │  └── constitution.md
    ├── scripts
    │  ├── check-prerequisites.sh
    │  ├── common.sh
    │  ├── create-new-feature.sh
    │  ├── setup-plan.sh
    │  └── update-claude-md.sh
    ├── specs
    │  └── 001-create-taskify
    │      └── spec.md
    └── templates
        ├── plan-template.md
        ├── spec-template.md
        └── tasks-template.md
```

### **ステップ 3:** 機能仕様の明確化（計画の前に必須）

ベースライン仕様が作成されたら、最初の試行で適切にキャプチャされなかった要件を明確化できます。

技術計画を作成する前に、**下流の再作業を減らすために**構造化された明確化ワークフローを実行する必要があります。

推奨順序：

1. `/speckit.clarify`（構造化）を使用 — クリアランスセクションに回答を記録するシーケンシャルなカバレッジベースの質問。
2. まだ不明な点がある場合は、任意で追加の自由形式の微調整をフォロー。

意図的に明確化をスキップしたい場合（例：スパイクまたは探求的プロトタイプ）、エージェントが欠落した明確化でブロックされないように明示的に述べてください。

例の自由形式の微調整プロンプト（まだ必要な場合の `/speckit.clarify` の後）：

```text
作成する各サンプルプロジェクトまたはプロジェクトには、5から15の間の可変数のタスクが各プロジェクトにランダムに分散して存在する必要があります。各完了ステージに少なくとも1つのタスクが存在することを確認してください。
```

また、Claude Code に **Review & Acceptance Checklist** を検証するよう依頼し、要件を満たすチェック項目にチェックを入れ、満たさない項目はチェックを入れないでください。次のプロンプトを使用できます：

```text
レビューと受入チェックリストを読み、機能仕様が基準を満たすかどうかを確認し、各チェック項目にチェックを入れてください。満たさない場合は空のままにしてください。
```

Claude Code との対話を仕様に関する質問と明確化の機会として使用することが重要です — **その最初の試行を最終的なものとして扱わないでください**。

### **ステップ 4:** プランを生成

これで、テクノロジースタックとその他の技術要件について具体的に述べることができます。プロジェクトテンプレートに組み込まれている `/speckit.plan` コマンドを使用して、次のようなプロンプトを入力できます：

```text
.NET Aspire を使用してこれを生成します。データベースには Postgres を使用します。フロントエンドは Blazor server を使用し、ドラッグアンドドロップのタスクボード、リアルタイム更新を使用します。REST API を作成し、プロジェクト API、タスク API、通知 API を作成します。
```

このステップの出力には、多くの実装詳細ドキュメントが含まれ、ディレクトリツリーは次のようになります：

```text
.
├── CLAUDE.md
├── memory
│  └── constitution.md
├── scripts
│  ├── check-prerequisites.sh
│  ├── common.sh
│  ├── create-new-feature.sh
│  ├── setup-plan.sh
│  └── update-claude-md.sh
├── specs
│  └── 001-create-taskify
│      ├── contracts
│      │  ├── api-spec.json
│      │  └── signalr-spec.md
│      ├── data-model.md
│      ├── plan.md
│      ├── quickstart.md
│      ├── research.md
│      └── spec.md
└── templates
    ├── CLAUDE-template.md
    ├── plan-template.md
    ├── spec-template.md
    └── tasks-template.md
```

指示に基づいて、正しいテクノロジースタックが使用されていることを `research.md` ドキュメントで確認してください。Claude Code に微調整するよう依頼し、特定のコンポーネントが目立つ場合、または使用したいプラットフォーム/フレームワークのローカルインストールバージョンをチェックさせることもできます（例：.NET）。

さらに、選択したテクノロジー��タックの詳細を Claude Code に調査させたい場合（例：.NET Aspire、JS フレームワークなど急速に変化しているもの）、次のようなプロンプトを使用できます：

```text
実装計画と実装詳細を確認し、追加の調査が有益な領域を特定してください。.NET Aspire は急速に変化するライブラリです。特定のバージョンについて、この Taskify アプリケーションで使用するバージョンの詳細を研究ドキュメントに更新し、ウェブからの研究を使用して詳細を明確化するために並列研究タスクをスピンアップしてください。
```

このプロセス中に、Claude Code が間違ったことを研究している可能性があります - 次のようなプロンプトで正しい方向に導くことができます：

```text
これを一連のステップに分解する必要があります。まず、実装中に不確かな部分や追加の研究が有益なタスクのリストを特定してください。それらのタスクのリストを書き留めてください。そして、各タスクに対して、別々の研究タスクをスピンアップして、結果としてすべての非常に具体的なタスクを並列で研究するようにしてください。私が見たのは、.NET Aspire を一般論で研究しているように見えることです。この場合、それはあまり役に立たないと思います。研究は、特定のターゲットされた質問を解決する必要があります。
```

> [!NOTE]
> Claude Code が過剰に熱心になり、要求していないコンポーネントを追加する可能性があります。その理由と変更の出所を明確化するよう依頼してください。

### **ステップ 5:** Claude Code にプランを検証させる

プランが整ったら、Claude Code に実行して、欠落している部分がないことを確認する必要があります。次のようなプロンプトを使用できます：

```text
実装計画と実装詳細ファイルを監査してください。これを読むことで明らかになるタスクのシーケンスがあるかどうかを判断してください。たとえば、コア実装を見ると、コア実装または微調整の各ステップを歩くときに情報を見つけることができる実装詳細の適切な場所を参照することが役立つように見えるかどうかを確認してください。
```

これにより、実装計画が微調整され、Claude Code が計画サイクルで見落とした可能性のある潜在的な盲点を回避できます。初期微調整パスが完了したら、実装に進む前に Claude Code にチェックリストをもう一度確認するよう依頼してください。

また、[GitHub CLI](https://docs.github.com/en/github-cli/github-cli) がインストールされている場合は、Claude Code に現在のブランチから `main` へのプルリクエストを詳細な説明とともに作成するよう依頼し、努力が適切に追跡されることを確認できます。

> [!NOTE]
> エージェントに実装させる前に、Claude Code に詳細をクロスチェックして、過剰にエンジニアリングされた部分がないか確認することも worth です（remember - 過剰に熱心になる可能性があります）。過剰にエンジニアリングされたコンポーネントや決定が存在する場合は、Claude Code に解決するよう依頼してください。Claude Code が [憲法](base/memory/constitution.md) を計画を確立する際の基盤となる部分として準拠していることを確認してください。

### **ステップ 6:** /speckit.tasks でタスクの分解を生成

実装計画が検証されたら、計画を特定の実行可能なタスクに分解し、正しい順序で実行できるようになります。`/speckit.tasks` コマンドを使用して、実装計画から詳細なタスクの分解を自動生成します：

```text
/speckit.tasks
```

このステップは、機能仕様ディレクトリに `tasks.md` ファイルを作成し、以下を含みます：

- **ユーザーストーリーごとに整理されたタスクの分解** - 各ユーザーストーリーが独自のタスクセットを持つ個別の実装フェーズになります
- **依存関係管理** - タスクはコンポーネント間の依存関係（例：モデル → サービス → エンドポイント）を尊重する順序で並べられます
- **並列実行マーカー** - 並列で実行できるタスクは `[P]` でマークされ、開発ワークフローを最適化します
- **ファイルパス指定** - 各タスクには実装が発生する正確なファイルパスが含まれます
- **テスト駆動開発構造** - テストが要求された場合、テストタスクが含まれ、実装の前に書かれるように順序付けられます
- **チェックポイント検証** - 各ユーザーストーリーフェーズには、独立した機能を検証するチェックポイントが含まれます

生成された tasks.md は `/speckit.implement` コマンドのための明確なロードマップを提供し、コード品質を維持し、ユーザーストーリーを段階的に提供する体系的な実装を保証します。

### **ステップ 7:** 実装

準備ができたら、`/speckit.implement` コマンドを使用して実装計画を実行します：

```text
/speckit.implement
```

`/speckit.implement` コマンドは：

- すべての前提条件が整っていることを検証（憲法、仕様、計画、タスク）
- `tasks.md` からタスクの分解を解析
- 依存関係と並列実行マーカーを尊重して正しい順序でタスクを実行
- タスク計画で定義された TDD アプローチに従う
- 進行状況を更新し、エラーを適切に処理

> [!IMPORTANT]
> コーディングエージェントはローカル CLI コマンド（`dotnet`、`npm` など）を実行します - 必要なツールがマシンにインストールされていることを確認してください。

実装が完了したら、アプリケーションをテストし、CLI ログに表示されないランタイムエラー（例：ブラウザコンソールエラー）を解決してください。そのようなエラーをコピーして、コーディングエージェントに解決を依頼できます。

</details>

---

## 🔍 トラブルシューティング

### Linux の Git 認証マネージャー

Linux で Git 認証に問題がある場合は、Git Credential Manager をインストールできます：

```bash
#!/usr/bin/env bash
set -e
echo "Downloading Git Credential Manager v2.6.1..."
wget https://github.com/git-ecosystem/git-credential-manager/releases/download/v2.6.1/gcm-linux_amd64.2.6.1.deb
echo "Installing Git Credential Manager..."
sudo dpkg -i gcm-linux_amd64.2.6.1.deb
echo "Configuring Git to use GCM..."
git config --global credential.helper manager
echo "Cleaning up..."
rm gcm-linux_amd64.2.6.1.deb
```

## 💬 サポート

サポートについては、[GitHub issue](https://github.com/github/spec-kit/issues/new) を開いてください。Spec-Driven Development の使用に関するバグ報告、機能リクエスト、質問を歓迎します。

## 🙏 謝辞

このプロジェクトは [John Lam](https://github.com/jflam) の仕事と研究に大きく影響されており、基づいています。

## 📄 ライセンス

このプロジェクトは MIT オープンソースライセンスの条件の下でライセンスされています。完全な条件については [LICENSE](./LICENSE) ファイルを参照してください。