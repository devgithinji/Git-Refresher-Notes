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

##### Git merge

Git merge types are divided into:

Fast forward and Non Fast-forward (Recursive, Octopus, Ours, Subtree)

Fast forward merge is a merge that works if no additional commit was added in master after feature branch was created its just moves the HEAD forward but does not create a new commit

###### Git Squash

Keyword used to combine many commits of a feature branch to the master as a single commit while merging with the master branch

`git merge --squash feature`

then

`git commit -m"name of new commit"`

In Recursive merge a merge commit is added used when the master branch and feature branch have additional commits after the faeture branch was created

`git merge -no-ff feature`

###### Git Rebase

When to apply Git rebase:

1: when you have new commits in the master while working in the feature branch

2: when your feature  relies on additional commits in the master branch

Rebase re-writes code history so not safe to use in remote repos

###### Cherry Pick

Cherry pick used for applying some commit from one feature branch to master branch if you made a mistake and commited a file in the wrong branch but you dont want merge the whole branch

`git cherry-pick <commitId>`

###### Git Tags

Tags are used to make a point as a specific point in git history. They are used to mark a commit stage as relevant

Types of tags involve 1: anotated tag 2: Light weight tag which are both similar but diffrent in the case of the amount of metadata stores

Annotated Tags are tags that store extra Metadata like developer name, email, date and more `git tag <tagname> -m"tag message"`

Lightweight tag `git tag <tagname>`

We create a tag when
1: we want to create a release point for stable version of your code
2: we want to create a historical point that you can refer to reuse in feature

`git tag <tag name> <commitId>` if you don't provide the commitId the default branch commit will be tagged

`git tag` to list all the availabe tags in our repository

`git tag show <tagname>` to show details of a particular tag

Git push tags

`git push origin <tagname>` //pushing  a single tag

`git push orgin --tags or git push --tags` //pushing all available tags at once

Delete a tag

`git tag -d <tagname>` delete one tag `git tag -d <tag1> <tag2>` //delete multiple tags

`git push origin -d <tagname>`  //delete a specified tag from the remote server `git push origin -d <tagname> <tagname2>` //delete multiple remote tags

Git Checkout Tags

`git checkout <tagname>` //create a detached head

###### Delete Git branch

`git branch -D <branch name>` //delete a local branch

`git --delete --remotes origin/<branch name>`  //delete remote tracking branch

`git push orgin --delete <branch name>` //delete a remote branch

















