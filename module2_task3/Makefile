# variables
APP_NAME = awesome-api
PORT = 9999

build: ## Compile the source code of the application.
	make lint
	-go mod init github.com/Mikalach/$(APP_NAME)
	go build

run: ## Run the application.
	./$(APP_NAME) > ./$(APP_NAME).log 2>&1 &

stop: ## Stop the running application.
	pgrep $(APP_NAME) | xargs kill

clean: ## Clean the compiled binary, log file, and coverage report.
	-make stop
	-rm -f $(APP_NAME) $(APP_NAME).log coverage-*.out

test: ## Test the application (unit tests only).
	-make unit-tests
	-make integration-tests

lint: ## Lint the code.
	golangci-lint run

unit-tests: ## Run the unit tests.
	go test -v -short -coverprofile=coverage-units.out

integration-tests: ## Run the integration tests.
	go test -v -coverprofile=coverage-integrations.out

help: ## Print this help message.
	-grep "##" Makefile | head -n -1 | tr -d '#' 
