# Dev Containers テンプレート

Node.js、Python、uv、Claude Code、Codex が入った Ubuntu ベースの開発環境です。Coder の `docker-devcontainer` とローカルの VS Code Dev Containers で使えます。

## Coder で開く

1. プロジェクトを作る場合は、GitHub で **Use this template → Create a new repository** を選びます。
2. Coder の **Workspaces → Create workspace → docker-devcontainer** を開き、**Login with GitHub** で連携します。
3. **Repository URL** に作成したリポジトリの HTTPS URL を入力します。テンプレートを試すだけなら `https://github.com/kappaexpress/devcontainers-template` を指定できます。

ワークスペースの起動後、ブラウザの VS Code またはターミナルを開きます。初回は `claude` を起動してログインし、Codex は `codex login --device-auth` で表示される URL とコードを使ってログインします。

両 CLI の設定ディレクトリは Git の管理外の `.devcontainer-local/` にあり、同じワークスペースを停止・再開しても残ります。認証情報が含まれるため、別の環境へプロジェクトをコピーするときはこのディレクトリを除いてください。

```bash
node --version
python --version
uv --version
claude --version
codex --version
```

Coder のログにフォールバックイメージで起動したと表示された場合は、ビルドログで最初のエラーを確認してください。ブラウザ版 VS Code の拡張機能は Open VSX から取得されます。

## ローカルの VS Code で開く

クローンしたリポジトリを VS Code で開き、コマンドパレットから **Dev Containers: Reopen in Container** を実行します。
