build: ##Building a website from scratch
	hugo

clean: ##Deleting all content in the directory
	rm -rf ./dist/

post: ##Create a blog post
	hugo new posts/$(POST_NAME).md
	sed -i '2s/title: .*/title: "$(POST_TITLE)"/' content/posts/$(POST_NAME).md

.SILENT:
help: ##Provides help about the commands
	cat Makefile | grep '##' | tr -d '##'

lint: ##lint
	shellcheck setup.sh
	