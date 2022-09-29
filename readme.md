# Git Basics

Check Git Version
`git --version`
Create an empty Git repository
`git init`
Check working directory & staging area status
`git status`
Display all commits of the current branch
`git log`
Display all files in the statging area
`git ls-files`

# Commit Creation and Access

Add a single file or  Working Directory files to staging area
`git add <filename>`
`git add .`
Create a new commit
`git commit -m"commit message"`
Checkout to a specific commit(can result to detached head)
`git checkout <commitId>`

# Branch creation and Access

Create new branch
`git branch <name>`
`git switch <branchname>` //new command
Go to a branch
`git checkout <branchname>`
Create and Access new branch
`git checkout -b <branchname>`
`git switch -c <branchname>`
Bring other branch changes to current branch (Merge)
`git merge <otherbranch>`

# Deleting Data

Remove files in the working directory which were part of another commit
`git rm filename`
`git add filename` //run any of these commands after the file was deleted from the working directory
Remove unstaged changes in tracked files
`git checkout -- .`
`git restore <filename> or .` //newer command
Remove untracked files
`git clean -df`
Remove staged changes
`git reset <filename> && git checkout -- <filename>`
`git restore --staged <filename> or .` //newer command
Remove latest commits
`git reset --hard <commitId>` //it will move the commit head to the specified commitId
`git reset --hard HEAD~1` //it will move the commit head to the previous commit
in both commits it will reset all the changes in the working directory(untracked changes) and all the staged changes

`git reset --mixed <commitId> or git reset <commitId>` //commit reset to the specified commitId
`git reset HEAD~1` //commit reset to the previous commit
in both commands the staged files are reset to the working directory (become unstaged)

`git reset --soft <commitId> or git reset --soft HEAD~1`
here the commits are reset to the specified commitId but both the staged and  unstaged changes are not reset
Branches
`git branch -D branchname` //delete a branch



