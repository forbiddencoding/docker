ARG GO_VERSION=latest

FROM golang:${GO_VERSION}

LABEL org.opencontainers.image.authors="forbiddencoding"

ENV GO111MODULE "on"
ENV GOOS "linux"
ENV CGO_ENABLED 1

RUN ["go", "install", "github.com/cosmtrek/air@latest"]

RUN mkdir /usr/src/app
WORKDIR /usr/src/app

COPY . .

RUN go mod tidy
RUN go mod download
RUN go mod verify

COPY ./.air.toml /

COPY ./entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
RUN sed -i -e 's/\r$//' /entrypoint.sh

STOPSIGNAL SIGTERM

# Healthcheck to make sure container is ready
HEALTHCHECK --interval=30s --timeout=10s CMD curl -f http://localhost:8080/health || exit 1

ENTRYPOINT ["/bin/bash", "-c", "/entrypoint.sh"]