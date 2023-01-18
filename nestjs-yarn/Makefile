# If you see pwd_unknown showing up, this is why. Re-calibrate your system.
PWD ?= pwd_unknown

IS_CI ?= false

# all our targets are phony (no files to check).
.PHONY: start-docker start-docker-production stop-docker stop-docker-production remove-builder run run-production

# suppress makes own output
.SILENT:

start-docker: ## Starts the docker containers for the local environment
	@echo start running targets for local environment
	docker compose -f docker-compose.yml up $(c)

start-docker-production: ## Starts the docker containers for the local environment
	@echo start running targets for production environment
	docker compose -f docker-compose.prod.yml up $(c)

stop-docker: ## Stops the docker containers for the local environment
	@echo stopping targets for local environment
	docker compose -f docker-compose.yml stop $(c)

stop-docker-production: ## Stops the docker containers for the local environment
	@echo stopping targets for prouction environment
	docker compose -f docker-compose.prod.yml stop $(c)

remove-builder: ## Removes all build stage images
	docker image prune --filter label=stage=builder

run: stop-docker start-docker ## Starts the docker containers for local environment
	@echo running services for development

run-production: stop-docker-production start-docker-production remove-builder ## Starts the docker containers for local environment
	@echo running services for production
