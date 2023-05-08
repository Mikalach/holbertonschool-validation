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

clean: ## clean the compiled binary and log file.
	-make stop
	-rm $(APP_NAME) $(APP_NAME).log

test: ## Test the application.
	curl http://localhost:$(PORT)/
	curl http://localhost:$(PORT)/health

lint: ## Lint the code
	golangci-lint run


unit-test: ## Do the unit tests
	go test -v -short -coverprofile=coverage-units.out

help: ## Print this help message
	-grep "##" Makefile | head -n -1 | tr -d '#' 