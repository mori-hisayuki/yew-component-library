# ベースイメージとして公式のRustイメージを使用
FROM rust:latest

# 必要なパッケージをインストール
RUN apt-get update && apt-get install -y \
    build-essential \
    libssl-dev \
    pkg-config \
    clang \
    llvm \
    && rm -rf /var/lib/apt/lists/*

# 必要なコンポーネントをインストール
RUN rustup update \
    && rustup component add rustfmt clippy \
    && rustup target add wasm32-unknown-unknown

# wasm-packをインストール
RUN curl https://rustwasm.github.io/wasm-pack/installer/init.sh -sSf | sh

WORKDIR /develop
