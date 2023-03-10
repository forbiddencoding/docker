# NestJS Docker Setup with yarn

<p>
    <img alt="NestJS" src="https://img.shields.io/badge/-NestJS-informational?style=for-the-badge&logo=nestjs&logoColor=white&color=E0234E" />
    <img alt="yarn" src="https://img.shields.io/badge/-yarn-informational?style=for-the-badge&logo=yarn&logoColor=white&color=2C8EBB" />
</p>

NestJS setup with a production build and live-reloading for local development using yarn.

## Table of Contents

* [Commands](#Commands)

---

## Commands

Every command can be found inside the [Makefile](Makefile).

> Note: The usual Docker and Docker Compose commands can still be used.

| Command                    | Description                            |
|:---------------------------|:---------------------------------------|
| ``run``                    | starts container for local development |
| ``stop-docker``            | stops container in local development   |
| ``run-production``         | starts docker for production           |
| ``stop-docker-production`` | stops docker in production             |
