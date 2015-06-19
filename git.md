## Setting up workspace
####In System Settings, choose Advanced-> Environment Variable
	Add Environment Variable GO PATH
#### Also
	Edit Variable PATH to add the path to your bin 
## Create a directory
	mkdir goplay
## Create a repository
	git init
## Create a repo source
	cd goplay
	mkdir -p src/github.com/Shrutiz
## Create a project folder
	cd src/github.com/Shrutiz
	mkdir howto
	cd howto
## Create new file
	vim file_name.type
## Add files
	git add file_name
## Commit files
	git commit -m "commit message"
## Push files
	git push
## Before pushing for the first time, set destination by
	git add remote name url
## Check your status
	git status
## Clone a repository
	git clone url_path
## Identify yourself
	git config --global user.name "ShrutiZ"
	git config --global user.email "shru@example.com"
## Compile a go file (exe file is created int your current directory) 
	go build
## Build & Install a go file (exe file will be created in bin)
	go install
## A basic git guide
	http://rogerdudler.github.io/git-guide/
