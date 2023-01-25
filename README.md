# Whalecome 🐳

<p>
    <img alt="Docker" src="https://img.shields.io/badge/-Docker-informational?style=for-the-badge&logo=docker&logoColor=white&color=2496ED" />
    <img alt="Golang" src="https://img.shields.io/badge/-Golang-informational?style=for-the-badge&logo=go&logoColor=white&color=00ADD8" />
    <img alt="NestJS" src="https://img.shields.io/badge/-NestJS-informational?style=for-the-badge&logo=nestjs&logoColor=white&color=E0234E" />
</p>

A collection of Docker and docker-compose files, sometimes with additional files I use.

## Table of Contents

* [Docker Image Versions](#docker-image-versions)
* [Golang with Live-Reloading](go/README.md)
* [NestJS with development and Multi-Stage production using npm](nestjs-npm/README.md)
* [NestJS with development and Multi-Stage production using yarn](nestjs-yarn/README.md)

## Docker Image Versions

Usually the build section of every Docker Service includes an argument for pulling
as specific image version (e.g. NodeJS v18.12). If no argument is given, it defaults
to the ``latest`` tag.

This behaviour can be changed in the ``docker-compose.yml`` or the ``Dockerfile``
respectively.



<div align="center">
    <img src=".github/docker_everywhere_meme.png" alt="Docker - Docker Everywhere"/>
</div>