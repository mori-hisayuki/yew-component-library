# ベースイメージとして公式のRustイメージを使用
FROM rust:latest

# 必要なパッケージをインストール
RUN apt-get update && apt-get install -y \
    build-essential \
    libssl-dev \
    pkg-config \
    clang \
    && rm -rf /var/lib/apt/lists/*

# 必要なコンポーネントをインストール
RUN rustup update \
    && rustup target add wasm32-unknown-unknown

# cargo-binutilsをインストール
RUN curl -L --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/cargo-bins/cargo-binstall/main/install-from-binstall-release.sh | bash

# trunkをインストール
RUN cargo binstall trunk -y
