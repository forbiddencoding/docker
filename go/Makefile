# If you see pwd_unknown showing up, this is why. Re-calibrate your system.
PWD ?= pwd_unknown

GO=go

IS_CI ?= false

# all our targets are phony (no files to check).
.PHONY: validate-go-version start-docker stop-docker run

# suppress makes own output
.SILENT:

validate-go-version: ## Validates the installed version of go against server's minimum requirement.
	@if [ $(GO_MAJOR_VERSION) -gt $(MINIMUM_SUPPORTED_GO_MAJOR_VERSION) ]; then \
		exit 0 ;\
	elif [ $(GO_MAJOR_VERSION) -lt $(MINIMUM_SUPPORTED_GO_MAJOR_VERSION) ]; then \
		echo '$(GO_VERSION_VALIDATION_ERR_MSG)';\
		exit 1; \
	elif [ $(GO_MINOR_VERSION) -lt $(MINIMUM_SUPPORTED_GO_MINOR_VERSION) ] ; then \
		echo '$(GO_VERSION_VALIDATION_ERR_MSG)';\
		exit 1; \
	fi

start-docker: ## Starts the docker containers for the local environment
	@echo start running targets for local environment
	docker compose -f docker-compose.yml up $(c)

stop-docker: ## Stops the docker containers for the local environment
	@echo stopping targets for local environment
	docker compose -f docker-compose.yml stop $(c)

run: stop-docker validate-go-version start-docker ## Starts the docker containers for local environment
	@echo running services for development
