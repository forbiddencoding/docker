# Whalecome 🐳

![Docker](https://img.shields.io/badge/-Docker-informational?style=for-the-badge&logo=docker&logoColor=2496ED&color=27272A)
![Golang](https://img.shields.io/badge/-Golang-informational?style=for-the-badge&logo=go&logoColor=00ADD8&color=27272A)
![NestJS](https://img.shields.io/badge/-NestJS-informational?style=for-the-badge&logo=nestjs&logoColorlogoColor=E0234E&color=27272A)
![temporal](https://img.shields.io/badge/-temporal-informational?style=for-the-badge&logo=temporal&logoColorlogoColor=E0234E&color=27272A)
![Documentation](https://img.shields.io/badge/Documentation-complete-green.svg?style=for-the-badge&color=27272A)
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=for-the-badge&color=27272A)](LICENSE)

A collection of Docker and docker-compose files, sometimes with additional files I use.

## Table of Contents

* [Docker Image Versions](#docker-image-versions)
* [Golang with Live-Reloading](go/README.md)
* [NestJS with development and Multi-Stage production using npm](nestjs-npm/README.md)
* [NestJS with development and Multi-Stage production using yarn](nestjs-yarn/README.md)

## Docker Image Versions

Usually the build section of every Docker Service includes an argument for pulling
a specific image version (e.g., Node.js v18.12).
If no argument is given, it defaults to the ``latest`` tag.

This behaviour can be changed in the ``docker-compose.yml`` or the ``Dockerfile``
respectively.



<div align="center">
    <img src=".github/docker_everywhere_meme.png" alt="Docker - Docker Everywhere"/>
</div>