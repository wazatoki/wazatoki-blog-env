# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.155.1/containers/ubuntu/.devcontainer/base.Dockerfile

# [Choice] Ubuntu version: bionic, focal
ARG VARIANT="focal"

ARG user=unknown
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# [Optional] Uncomment this section to install additional OS packages.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    make build-essential wget curl
 
WORKDIR /tmp

ARG GO_VERSION="1.16"
RUN curl -fsSOL https://golang.org/dl/go${GO_VERSION}.linux-amd64.tar.gz \
    && tar -C /usr/local -xzf go${GO_VERSION}.linux-amd64.tar.gz

ARG HUGO_VERSION="0.84.3"
RUN curl -fsSOL https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_${HUGO_VERSION}_Linux-64bit.deb \
    && dpkg -i hugo_${HUGO_VERSION}_Linux-64bit.deb

ENV PATH=$PATH:/usr/local/go/bin:/usr/local/node-${NODE_VERSION}-linux-x64/bin:/root/go/bin

RUN mkdir /root/go
