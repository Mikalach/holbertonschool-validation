# variables
APP_NAME = awesome-api
PORT = 9999

build: ## Builderberg
	go build

run: ## Runenberg
	./$(APP_NAME) > ./$(APP_NAME).log 2>&1 &

stop: ## Stopenberg
	pgrep $(APP_NAME) | xargs kill

clean: stop ## Cleanerberg
	rm $(APP_NAME) $(APP_NAME).log

test: run ## Testenberg
	curl http://localhost:$(PORT)/
	curl http://localhost:$(PORT)/health

help: ##Helpenberg
	@echo "help: Print this help message."
	@echo "build: Compile the source code of the application."
	@echo "run: Run the application."
	@echo "stop: Stop the running application."
	@echo "clean: Clean the compiled binary and log file."
	@echo "test: Test the application."
	@echo "format: Format the code."