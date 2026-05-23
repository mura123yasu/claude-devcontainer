# Claude Code Devcontainer Template

このリポジトリは Claude Code を auto mode で安全に使うための devcontainer テンプレートです。

## 構成

- `.devcontainer/devcontainer.json` — devcontainer 設定。Ubuntu 24.04 ベース、Node.js LTS、GitHub CLI を含む
- `.claude/settings.json` — Claude Code の auto mode 用 permissions 設定（全ツール許可）
- `.gitignore` — 認証情報・ローカル設定を除外

## 認証

コンテナ初回起動後、ターミナルで `claude` を実行すると認証フローが案内される。Pro プランのアカウントでログインする。

## Auto Mode の仕組み

`.claude/settings.json` で Bash・ファイル操作・Web 取得など全ツールを許可済みのため、`claude` コマンド起動後に許可プロンプトは表示されない。
