# Claude Code Devcontainer Template

このリポジトリは Claude Code を auto mode で安全に使うための devcontainer テンプレートです。

## 構成

- `.devcontainer/devcontainer.json` — devcontainer 設定。Ubuntu 24.04 ベース、Node.js LTS、GitHub CLI を含む。`postCreateCommand` で Claude Code をインストールし、`~/.claude/settings.json` に `permissionMode: "auto"` を書き込む
- `.gitignore` — 認証情報・ローカル設定を除外

## 認証

コンテナ初回起動後、ターミナルで `claude` を実行すると認証フローが案内される。Pro プランのアカウントでログインする。

## Auto Mode の仕組み

devcontainer 作成時の `postCreateCommand` で `~/.claude/settings.json`（グローバル設定）に `permissionMode: "auto"` を書き込む。これにより、コンテナ内で起動した Claude Code は許可プロンプトなしで動作する。
