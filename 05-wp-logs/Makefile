# We like colors
# From: https://coderwall.com/p/izxssa/colored-makefile-for-golang-projects
RED=`tput setaf 1`
GREEN=`tput setaf 2`
RESET=`tput sgr0`
YELLOW=`tput setaf 3`

# And add help text after each target name starting with '\#\#'
.PHONY: help
help: ## This help message
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'

.PHONY: run
run: ## Install setup/
	@echo "$(YELLOW)==> Running Compose$(RESET)"
	@docker-compose up -d

.PHONY: stop
stop:
	@echo "$(YELLOW)==> Stopping Compose$(RESET)"
	@docker-compose stop

.PHONY: clean
clean:
	@echo "$(YELLOW)==> Cleaning Compose$(RESET)"
	@docker-compose rm

.PHONY: logs
logs:
	docker-compose logs

.PHONY: logs-db
logs-db:
	docker-compose logs db