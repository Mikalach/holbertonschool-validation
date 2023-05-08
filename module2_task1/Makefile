# variables
APP_NAME = awesome-api
PORT = 9999

build: ## Compile the source code of the application.
	go build

run: ## Run the application.
	./$(APP_NAME) > ./$(APP_NAME).log 2>&1 &

stop: ## Stop the running application.
	pgrep $(APP_NAME) | xargs kill

clean: ## clean the compiled binary and log file.
	make stop
	rm $(APP_NAME) $(APP_NAME).log

test: ## Test the application.
	curl http://localhost:$(PORT)/
	curl http://localhost:$(PORT)/health

lint: cd## Lint the code
	golangci-lint run

help: ## Print this help message
	-grep "##" Makefile | head -n -1 | tr -d '#' 