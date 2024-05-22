# syntax=docker/dockerfile:1
ARG GO_VERSION=latest
ARG CGO_ENABLED=0

FROM golang:${GO_VERSION}

LABEL org.opencontainers.image.authors="forbiddencoding"
LABEL org.opencontainers.image.title="forbiddencoding/docker-golang-air"
LABEL org.opencontainers.version="0.0.2"
LABEL org.opencontainer.image.description="A Docker image for Golang development with Air."
LABEL org.opencontainer.image.url="http.s://github.com/forbiddencoding/docker"
LABEL org.opencontainer.image.licenses="MIT"

STOPSIGNAL SIGTERM

ENV CGO_ENABLED ${CGO_ENABLED}

RUN --mount=type=cache,target=/var/cache/apt \
    apt-get update && apt-get install -y build-essential

RUN go install github.com/cosmtrek/air@latest

WORKDIR /usr/src/app

CMD air -c .air.toml
