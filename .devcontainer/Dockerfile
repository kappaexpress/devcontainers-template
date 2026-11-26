# 素の Ubuntu ベース。言語ランタイムは devcontainer.json の features で追加する。
# apt パッケージなど OS レベルの追加が必要になったらここに RUN を足す。
FROM mcr.microsoft.com/devcontainers/base:ubuntu

# uv / uvx を Astral 公式イメージからコピー(公式ドキュメント推奨の方法)
# バージョンを固定したい場合は :latest を :0.7 のようにタグ指定する
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /usr/local/bin/

# Coder のエージェントと VS Code のターミナルから同じ CLI を使う。
ENV PATH="/home/vscode/.local/bin:${PATH}"
USER vscode
RUN bash -e -o pipefail -c '\
    export HOME=/home/vscode; \
    curl -fsSL --retry 3 https://claude.ai/install.sh | bash -s stable; \
    curl -fsSL --retry 3 https://chatgpt.com/codex/install.sh | \
        CODEX_NON_INTERACTIVE=1 CODEX_HOME="$HOME/.local/share/codex" sh; \
    claude --version; \
    codex --version'

# 例: ビルドツールが必要な場合
# USER root
# RUN apt-get update && apt-get install -y --no-install-recommends \
#     build-essential \
#     && rm -rf /var/lib/apt/lists/*
# USER vscode
