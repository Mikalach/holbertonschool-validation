# variables
APP_NAME = awesome-api
PORT = 9999

build:
	go build

run:
	./$(APP_NAME) > ./$(APP_NAME).log 2>&1 &

stop:
	pgrep $(APP_NAME) | xargs kill

clean: stop
	rm $(APP_NAME) $(APP_NAME).log

test: run
	curl http://localhost:$(PORT)/
	curl http://localhost:$(PORT)/health

help:
	@echo "help: Print this help message."
	@echo "build: Compile the source code of the application."
	@echo "run: Run the application."
	@echo "stop: Stop the running application."
	@echo "clean: Clean the compiled binary and log file."
	@echo "test: Test the application."
	@echo "format: Format the code."