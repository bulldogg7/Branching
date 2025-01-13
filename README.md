# Git Branching Cheat Sheet

## Basic Commands
* `git init` - initialize local repository in current working directory
* `git add fileName` - stage `fileName` for commit
* `git commit -m "message"` - commit staged changes with commit message `message`

## Info Commands
* `git status` - creport the status of the working directory
* `git log` - check the git log for commit history of local repository
* `git log --oneline` - list commit history (compact format)

## Branching Commands
* `git branch branchName` - create local branch `branchName`
* `git checkout branchName` - switch to branch `branchName`
* `git checkout -b branchName` - create (if not exists) `branchName` & switch to it
* `git log --oneline` - list commit history (compact format)

## Remote Commands
* `git remote add alias repoUrl` - define `alias` as shortcut for `repoUrl` (usually `origin` for alias)
* `git push origin branchName` - push local commits to remote branch `branchName`
* `git pull origin branchName` - pull remote commits into local branch

## Workflow
1. Pull latest remote main into local main
	```
	git checkout main
	git pull origin main
	```
2. Branch from updated local main
	```
git checkout -b myBranch
	```
3. Work in local branch, committing frequently
	```
	git add .
	git commit -m "Ready to merge"
	git pull origin main
	```
	* Fix any merge conflicts, then commit

4. When ready to merge, pull remote `main` into local branch (must commit first)
	```
	git push origin myBranch
	```
5. On GitHub: Create pull request
6. Merge pull request