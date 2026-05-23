# claude-devcontainer

Claude Code を auto mode で安全に使うための devcontainer テンプレート。

## 前提条件

- Docker Desktop または Docker Engine
- Visual Studio Code + Dev Containers 拡張機能
- Claude Code Pro プランのアカウント

## セットアップ

1. このリポジトリをクローンまたはコピー

```bash
git clone https://github.com/mura123yasu/claude-devcontainer.git my-project
cd my-project
```

2. VS Code で開く
3. コマンドパレット（`Ctrl+Shift+P` / `Cmd+Shift+P`） → **Dev Containers: Reopen in Container**
4. コンテナビルド完了後、ターミナルで認証:

```bash
claude
# 初回起動時にブラウザが開き、Pro アカウントでの認証が案内される
```

## 使い方

認証済みの状態で `claude` を起動すると、許可プロンプトなしに全ツールが利用できる。

```bash
# 対話モードで起動
claude

# プロジェクトの変更を依頼する例
claude "このプロジェクトにテストを追加して"

# ワンショットで実行
claude -p "README の英語版を作成して"
```

`.claude/settings.json` で Bash・ファイル操作・Web 検索など全ツールが許可済みのため、Claude が作業中に許可を求めてくることはない。

## 構成内容

| 項目 | 内容 |
|------|------|
| ベースイメージ | Ubuntu 24.04 LTS |
| Node.js | LTS 版（Claude Code 動作に必須） |
| GitHub CLI | `gh` コマンドで PR・issue 操作 |
| 認証 | コンテナ内で `claude` を起動して Pro アカウントでログイン |
| Auto mode | `.claude/settings.json` で全ツール許可済み |

## カスタマイズ

言語ランタイムや追加ツールが必要な場合は `.devcontainer/devcontainer.json` の `features` に追加:

```json
"features": {
  "ghcr.io/devcontainers/features/python:1": {},
  "ghcr.io/devcontainers/features/go:1": {}
}
```

利用可能な features: https://containers.dev/features
