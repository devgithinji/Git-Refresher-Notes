# Git Basics

###### Check Git Version

`git --version`

###### Create an empty Git repository

`git init`

###### Check working directory & staging area status

`git status`

###### Display all commits of the current branch

`git log`

###### Display all files in the statging area

`git ls-files`

# Commit Creation and Access

###### Add a single file or  Working Directory files to staging area

`git add <filename>`

`git add .`

###### Create a new commit

`git commit -m"commit message"`

###### Checkout to a specific commit(can result to detached head)

`git checkout <commitId>`

# Branch creation and Access

###### Create new branch

`git branch <name>`

`git switch <branchname>` //new command

###### Go to a branch

`git checkout <branchname>`

###### Create and Access new branch

`git checkout -b <branchname>`

`git switch -c <branchname>`

###### Bring other branch changes to current branch (Merge)

`git merge <otherbranch>`

# Deleting Data

###### Remove files in the working directory which were part of another commit

`git rm filename`

if you use `rm <filname>` command you will be required to `git add .` for changes to reflect (the above command does all that in one step)

`git rm --cached <filename>`

used to remove a file from git but keep it in your local repository may be used with `-f` to force delete

`git add filename` //run any of these commands after the file was deleted from the working directory

###### Remove unstaged changes in tracked files

`git checkout -- .`

`git restore <filename> or .` //newer command

###### Remove untracked files

`git clean -df`

###### Remove staged changes

`git reset <filename> && git checkout -- <filename>`

`git restore --staged <filename> or .` //newer command

###### Remove latest commits

`git reset --hard <commitId>` //it will move the commit head to the specified commitId

`git reset --hard HEAD~1` //it will move the commit head to the previous commit

in both commits it will reset all the changes in the working directory(untracked changes) and all the staged changes

`git reset --mixed <commitId> or git reset <commitId>` //commit reset to the specified commitId

`git reset HEAD~1` //commit reset to the previous commit

in both commands the staged files are reset to the working directory (become unstaged)

`git reset --soft <commitId> or git reset --soft HEAD~1`

here the commits are reset to the specified commitId but both the staged and  unstaged changes are not reset

###### Branches

`git branch -D branchname` //delete a branch

###### git stash

used to save uncommited worked when you want to switch between branchs instead of committing unincomplete work'

`git stash`

Stash changes with message

`git stash save <Stashing Message>`

To check all the stored stashes

`git stash list`

To reaply changes that were stashed

`git stash apply`

if you have many stashes you can apply a specific stash by using the command

`git stash apply <stash id>`

Show Stash changes

`git stash show`

this command shows all the changes made to the files

`git stash show -p`

Command to display all the changes in the stashed change

Stash pop this will remove the latest stash and apply the changes to the current branch its like git stash apply but it deletes the poped statsh from the queue

`git stash pop`

Git stash drop used to remove the latest stash from the queue

`git stash drop or git stash drop <stashid>`

Git stash clear used to remove all the available stashes at once

`git stash clear`

###### Git Reflog

used to bring back deleted commits or branches

`git reflog`

if a branch is deleted check the actual commit has of the deleted branch using the above command then checkout to the specific commitId which will create a detached head then create a new branch with the name of the deleted branch















