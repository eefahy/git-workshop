Git Cheatsheet
===============

 - [Setup & Config](#setup--config)
 - [Init & Clone](#init--clone)
 - [Staging & Snapshots](#staging--snapshots)
 - [Moving, Removing, & Restoring](#moving-removing--restoring)
 - [Branches & Merging](#branches--merging)
 - [Inspect & Compare](#inspect--compare)
 - [Temporary Storage](#temporary-storage)
 - [Releases & Version Tags](#releases--version-tags)
 - [Share and Get Updates](#share-and-get-updates)
 - [Rewrite History](#rewrite-history)

## Setup & Config

See where Git is located:  
`which git`

Get the version of Git:  
`git --version`

Basic config for the git client:  
`git config --global user.name "Jane Doe"`  
`git config --global user.email janedoe@example.com`  
`git config --global core.editor "atom --wait"`  
`git config --global color.ui auto`  

See existing git config:  
`git config --list`


## Init & Clone

Initialize Git:  
`git init`

Clone to localhost:  
`git clone https://github.com/user/project.git /path/to/folder`

Clone specific branch to localhost:  
`git clone -b branchname https://github.com/user/project.git`


## Staging & Snapshots

See the status of the working directory:  
`git status`

Stage a file for commit:  
`git add [file]`

Unstage a file but retain changes in the working directory:  
`git reset [file]`

View changes:  
`git diff [--staged]`

Commit staged changes as a new snapshot:  
`git commit [-m] ["Message"]`


## Moving, Removing, & Restoring

Remove files from Git:  
`git rm [--cached] [file]`

Move or rename files:  
`git mv [file] [new/path/filename]`

Restore file from last snapshot:  
`git checkout -- [file]`

Restore file from specific snapshot (in current branch):  
`git checkout cdbfda8 -- [file]`

Add a new commit that undoes a previous commit:  
`git revert cdbfda8`


## Branches & Merging

Show local branches:  
`git branch [-vv]`

Create new branch at current commit:  
`git branch branchname`

Switch working directory to another branch:  
`git checkout branchname`

Merge specified branch history into current branch:  
`git merge branchname`

Stop merge in case of conflicts:  
`git merge --abort`

Bring a commit from another branch into current branch:  
`git cherry-pick [SHA]`


## Inspect & Compare

Show commits with metadata:  
`git log`

Show commits with metadata and patches:  
`git log -p`

Show commits as decorated graph summary:  
`git log --oneline --graph --all --decorate`

Show commits for a specified file:  
`git log --follow [file]`

Compare two branches:  
`git log branchA..branchB`  
`git diff branchA..branchB`  
`git diff origin/master..master`

Compare range of commits:  
`git diff cdbfda8..HEAD`  
`git diff cdbfda8..537a09f`

Show metadata and patch for a given commit:  
`git show [SHA]`


## Temporary Storage

Stash modified and staged changes:  
`git stash`

Show stashed changes:  
`git stash list`

Pop stashed commit from the top:  
`git stash pop`

Mount stashed commit but not drop it:  
`git stash apply`


## Releases & Version Tags

Show all released versions:  
`git tag`

Create a version for release:  
`git tag v1.0.0`

Checkout a specific released version:  
`git checkout v1.0.0`


## Share and Get Updates

Add remote:  
`git remote add [alias] [url]`

Fetch changes from a remote:  
`git fetch [alias]`

Merge fetched commits into current branch:  
`git merge [alias]/[branch]`

Share a branch with a remote:  
`git push [alias] [branch]`

Show remotes [with details]:  
`git remote [-v]`

Show remote branches:  
`git branch -r`

Add an upstream branch to current branch:  
`git branch --set-upstream-to=[alias]/[branch]`

Fetch and merge from upstream:  
`git pull`

Fetch, merge, and rebase from upstream:  
`git pull --rebase`


## Rewrite History

Interactive rebasing of commits:
`git rebase --interactive`

Removes commits newer than specified commit and stages modified files:  
`git reset --soft cdbfda8`

Removes commits newer than specified commit completely:  
`git reset --hard cdbfda8`

Amend the most recent commit:  
`git commit --amend -m "Message"`
