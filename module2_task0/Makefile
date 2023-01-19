build: ##Building a website from scratch
	hugo
	go build -o awesome-api

clean: ##Deleting all content in the directory
	rm -rf ./dist/
	rm -f awesome-api awesome.log

post: ##Create a blog post
	hugo new posts/$(POST_NAME).md
	sed -i '2s/title: .*/title: "$(POST_TITLE)"/' content/posts/$(POST_NAME).md

.SILENT:
help: ##Provides help about the commands
	cat Makefile | grep '##' | tr -d '##'
	
run: ##Runs the app in the background
	./awesome-api >./awesome.log 2>&1 &

stop: ##Stops the app w/ kill
	pkill awesome-api

test: ##Tests the app to check if it runs correctly
	curl http://localhost:9999
	curl http://localhost:9999/health
