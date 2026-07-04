# 素の Ubuntu ベース。言語ランタイムは devcontainer.json の features で追加する。
# apt パッケージなど OS レベルの追加が必要になったらここに RUN を足す。
FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

# uv / uvx を Astral 公式イメージからコピー(公式ドキュメント推奨の方法)
# バージョンを固定したい場合は :latest を :0.7 のようにタグ指定する
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /usr/local/bin/

# 例: ビルドツールが必要な場合
# RUN apt-get update && apt-get install -y --no-install-recommends \
#     build-essential \
#     && rm -rf /var/lib/apt/lists/*
