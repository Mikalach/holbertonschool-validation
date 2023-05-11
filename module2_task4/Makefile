# Makefile
## executable variable
HUGO_EXECUTABLE := hugo

help: ## command help
	fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'

build: ## build files
	./setup.sh
	make check
	hugo

check:## Check if post is valid
	markdownlint -f ./content/posts/*.md
	markdown-link-check ./content/posts/*.md

validate:## Validate the index
	-./w3c_validator.py ./dist/index.html

clean: ## remove all file force ignore nonexistent files
	rm -Rf dist/*

post: ## create new post
	$(HUGO_EXECUTABLE) new posts/$(POST_NAME).md
	sed -i 's/title:.*/title: "$(POST_TITLE)"/' content/posts/$(POST_NAME).md
