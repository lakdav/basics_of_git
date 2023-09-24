# Git

s## config

```bash
git config --global user.name lakdav
git config --global user.email email@mail.ru
git config --global nit.defaultBranch main
```

## Repositories

There are two types of repositories

- local
- remote

## Initializing a Local Repository

folder for local repository is .git and contains :

- config
- description
- HEAD
- hooks/
- info/
- objects/
- refs/
  - heads
  - tag

```bash
git init -b main
# -b or --initial-branch
```

## Show the state of the working directory and the staging area

```bash
git status
```

## Adding files to the staging area

```bash
git add

# git add <filename>
# git add <filename> <filename>
# git add -A
```

## Making a commit

```bash
# Create a new commit with a commit message
git commit -m "initial commit"

# git commit -m “<message>”
```

## Viewing a list of commits

```bash
# Show a list of commits in reverse chronological order
git log
```

## Creating a Branch

```bash
#list local branches
git branch

# Create a branch
git branch dev

# List local branches and remote-tracking branches
git branch --all

#List the local branches and their upstream branches, if they have any
git branch -vv
```

## Creating a Branch and Switching onto It in One Go

```bash
# Create a new branch and switch onto it
# git switch -c <new_branch_name>
git switch -c feature

# Create a new branch and switch onto it
# git checkout -b <new_branch_name>
git checkout -b feature
```

## What Is HEAD?

HEAD is simply a pointer that tells you which branch you are on

<!-- .git/HEAD  => ref: refs/heads/main -->

## Switching Branches

```bash
git switch feature
#or
git checkout feature
# cat .git/HEAD => ref: refs/heads/feature
```

## Mergin

_fast-forward_ merges : During a fast-forward merge, Git takes the pointer of the target branch and moves it to the commit of the source branch.

There are two steps involved in doing a merge:

1. Switch onto the branch that you want to merge into (the target branch).
2. Use the git merge command and pass in the name of the branch you’re merging (the source branch).

```bash
git merge feature

# Stop the merge process and go back to the state before the mergeq
git merge --abort
```

## Viewing a list of all commits

```bash
git log --all
```

## Checking Out Commits

<!-- detached HEAD -->

```bash
git checkout f195e0c2922f3ac012cc613729ccd7db81e84caa

#This allows you to look at any commit
# HEAD pointer will point directly to a commit instead of pointing to a branch,This means that you will be in something that Git (scarily) calls detached HEAD state
```

## ADDING A CONNECTION TO THE REMOTE REPOSITORY

```bash
git remote add origin git@github.com:lakdav/rainbow.git

# cat .git/config
```

## To see the list of connections to remote repositories

```bash
# List the remote repository connections stored in the local repository by shortname
git remote

# List the remote repository connections in the local repository with shortnames and URLs
git remote -v

```

## PUSHING TO A REMOTE REPOSITORY

```bash
# git push <shortname> <branch_name>
git push origin main
```

## Clone repository

```bash
git clone git@github.com:lakdav/rainbow.git
```

## Delete branch

```bash
# delete a local branch
git branch -d feature

# Delete a remote branch and the associated remote-tracking branch
# git push <shortname> -d <branch_name>
git push origin -d feature
```

## FETCHING CHANGES FROM THE REMOTE REPOSITORY

```bash
# Download data from the remote repository with shortname origin
git fetch

# git fetch <shortname>
# Download data from the <shortname> remote repository
git fetch origin

# Remove remote-tracking branches that correspond to deleted remote branches and download data from the remote repository
git fetch -p

# nothing in your working directory will change when you fetch data from a remote repository
```

## INTEGRATING CHANGES INTO A LOCAL BRANCH

```bash
# 1
git fetch
# 2
git switch main
# 3
git merge origin/main
```

## Defining Upstream Branches

```bash
# Define an upstream branch for the current local branch
# git branch -u <shortname>/<branch_name>
git branch -u origin/main

# -u or --set-upstream-to
```

## To check whether an upstream branch has been defined

```bash
git branch -vv
```

## Pulling Changes from a Remote Repository

```bash
git pull
git pull origin main
```

If the development histories of the local branch and the remote branch in a _git pull_ have diverged, then you must tell Git whether you want to integrate the changes by merging or rebasing (otherwise, you’ll get an error).To tell Git to integrate the changes by merging, you must pass in the _--no-rebase_ option. To tell Git to integrate the changes by rebasing, you must pass in the _--rebase_ option

It is common for Git users to use the _git pull_ command when the development histories of the local and remote branches have not diverged, and therefore a simple fast-forward merge will happen

If the development histories of the local and remote branches have diverged, Git users often prefer to use the _git fetch_

```bash
#              git merge
# git fetch +     or        = git pull
#              gir rebase

```

```bash
git pull origin main --no-rebase
git pull origin main --rebase
```
