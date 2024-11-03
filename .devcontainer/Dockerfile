# Debianベースイメージ
FROM debian:bullseye

# 必要なツールをインストール（curl, zip, unzip, git, MySQLクライアント）
RUN apt-get update && apt-get install -y \
    curl zip unzip git \
    default-mysql-client \
    && apt-get clean

# SDKMAN! のインストール
RUN curl -s "https://get.sdkman.io" | bash

# SDKMAN! の初期化とJava, Gradleのインストール
ARG JAVA_VERSION="17.0.6-amzn"
ARG GRADLE_VERSION="8.5"
RUN bash -c "source $HOME/.sdkman/bin/sdkman-init.sh && \
    sdk install java ${JAVA_VERSION} && \
    sdk install gradle ${GRADLE_VERSION}"

# Javaの環境変数設定
ENV JAVA_HOME="/root/.sdkman/candidates/java/current"
ENV PATH="$JAVA_HOME/bin:$PATH"

# 作業ディレクトリを設定
WORKDIR /workspace

# 必要ポートの公開
EXPOSE 8080
