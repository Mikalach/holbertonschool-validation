# variables
APP_NAME = awesome-api
PORT = 9999

build: ## Compile the source code of the application.
	go build

run: ## Run the application.
	./$(APP_NAME) > ./$(APP_NAME).log 2>&1 &

stop: ## Stop the running application.
	pgrep $(APP_NAME) | xargs kill

clean: ## Clean the compiled binary and log file.
	make stop
	rm $(APP_NAME) $(APP_NAME).log

test: ## Test the application.
	curl http://localhost:$(PORT)/
	curl http://localhost:$(PORT)/health

help: ## Print this help message
	@echo "help: Print this help message."
	@echo "build: Compile the source code of the application."
	@echo "run: Run the application."
	@echo "stop: Stop the running application."
	@echo "clean: Clean the compiled binary and log file."
	@echo "test: Test the application."