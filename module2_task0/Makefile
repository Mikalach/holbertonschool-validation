# variables
APP_NAME = awesome-api
PORT = 9999

# targets
build:
	go build -o $(APP_NAME) .

run:
	./$(APP_NAME) > ./$(APP_NAME).log 2>&1 &

stop:
	kill "$(pgrep $(APP_NAME))"

clean: stop
	rm -f $(APP_NAME) $(APP_NAME).log

test: run
	curl -sS http://localhost:$(PORT)/
	curl -sS http://localhost:$(PORT)/health

format:
	go fmt ./...

vet:
	go vet ./...

lint:
	golint ./...

help:
	@echo "help: Print this help message."
	@echo "build: Compile the source code of the application."
	@echo "run: Run the application."
	@echo "stop: Stop the running application."
	@echo "clean: Remove the compiled binary and log file."
	@echo "test: Test the application."
	@echo "format: Format the code."