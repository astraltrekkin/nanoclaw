# Cursor Cloud Agent base image for nanoclaw.
# Do NOT COPY the project — Cursor checks out the commit itself.
FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive \
    PATH="/root/.local/bin:${PATH}"

# git + sudo required for Cursor Cloud Agent checkout / tooling
# build-essential + python3: better-sqlite3 native compile
RUN apt-get update && apt-get install -y --no-install-recommends \
      ca-certificates \
      curl \
      git \
      sudo \
      build-essential \
      python3 \
    && rm -rf /var/lib/apt/lists/*

# Node 22 (package.json engines.node >= 22)
RUN curl -fsSL https://deb.nodesource.com/setup_22.x | bash - \
    && apt-get install -y --no-install-recommends nodejs \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /workspace
