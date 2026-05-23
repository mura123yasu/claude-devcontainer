# Claude Code Devcontainer Template

このリポジトリは Claude Code を auto mode で安全に使うための devcontainer テンプレートです。

## 構成

- `.devcontainer/devcontainer.json` — devcontainer 設定。Ubuntu 24.04 ベース、Node.js LTS、GitHub CLI を含む
- `.claude/settings.json` — Claude Code の `permissionMode: "auto"` 設定
- `.gitignore` — 認証情報・ローカル設定を除外

## 認証

コンテナ初回起動後、ターミナルで `claude` を実行すると認証フローが案内される。Pro プランのアカウントでログインする。

## Auto Mode の仕組み

`.claude/settings.json` で `permissionMode: "auto"` を設定している。これは Claude Code のネイティブな auto mode であり、`claude --permission-mode auto` と同等。個別ツールを列挙する代わりに、Claude Code 本体の動作モードとして許可プロンプトなしで動作する。
