FROM mcr.microsoft.com/devcontainers/base:jammy

ENV LAZYGIT_VERSION=0.43.1

ARG APT_PACKAGES="curl software-properties-common gnupg apt-transport-https sshpass openssh-client xz-utils ca-certificates gettext-base"

RUN apt-get -yqq update && apt-get -yqq install ${APT_PACAGES} && \
    curl -Lo lazygit.tar.gz "https://github.com/jesseduffield/lazygit/releases/latest/download/lazygit_${LAZYGIT_VERSION}_Linux_x86_64.tar.gz" && \
    tar xf lazygit.tar.gz lazygit && mv lazygit /usr/local/bin/lazygit && rm lazygit.tar.gz && \
    wget https://go.dev/dl/go1.23.0.linux-arm64.tar.gz --no-check-certificate && \
    tar -C /usr/local -xzf go1.23.0.linux-arm64.tar.gz && rm go1.23.0.linux-arm64.tar.gz
