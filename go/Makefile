# If you see pwd_unknown showing up, this is why. Re-calibrate your system.
PWD ?= pwd_unknown

.ONESHELL:
.PHONY: up down log

ifndef GOPATH
GOPATH := $(shell go env GOPATH)
endif

COLOR := "\e[1;36m%s\e[0m\n"

up: ## Starts the docker containers for local environment
	@printf $(COLOR) "starting services for development"
	docker compose -f docker-compose.yml up $(c)

down: ## Stops the docker containers for local environment
	@printf $(COLOR) "stopping services for development"
	docker compose -f docker-compose.yml down

log: ## Shows the logs for the docker containers for local environment
	@printf $(COLOR) "showing logs for development"
	docker compose logs -f -t