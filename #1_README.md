# Git

Gir was created in 2005 by Linus Tovards

## What is version control

---

Version control, also known as source control,refers to tracking and managing changes to code

## Local Version Control System

---

VCSs is a local database located on your local computer,in which every file change is tored as patch

## Centralized Version Control System

---

CVCSs resolve the likely issues and challenges local version control system face.
Centralized Version Control System (such as CVCs,Subversion and Perforce) have a single server that contains allthe versiond files

## Distributed Version Control Systems

---

DVCSs ,such as Git ,each clone of the repository is full backup of the repository. this in turn,means that when the user takes the latest snapshot of teh file,DVCS takes the full mirrir back of the repository. It hepls when the server hosting the repository craches , and any of the users's repositories can be copied back up to the server to help the repository conten onto the server

Git is known to be a distributed version control system

## Git Features

---

- integrity
- speed
- scalability
- open source

## Git Three States

---

- Modified
- Staged
- Comitted

## Git three main section

---

- Workin Directory - place,where the files are pulled out from a compressed database from the Git directory . In this place we can modife and update
- Staging Area - stores the information about what would go into the next commit
- .git directory (Repository)

## Getting started with Git

---

### install on ubuntu

```bash
#1
sudo apt update
#2
sudo apt upgrade
#3
sudo apt install git

#to check version
git --version
```

### Basic config

```bash
git config --global user.name <name>
git config --global user.email <email>
```

```bash
# listing configuration
git config --list --show-origin
```

## short description

---

### commit

A commit is a snapshot of the user's entire repository,not just of one or files

### commit message

A user is expected to make the commit with a commit message,and this commit message might seem like overhead

### branch

A branch is an autonomous series of commits out of the way that a user can use to evaluate an analysis or work on creating a new feature

### main branch

when a user create a new Git projects, there's a default branhc that gets created which is called main. this is the parent branch where finally all the commit land, and once the changes are finalized and verified

### feature( or topic) branch

WHen users start working on new functionality, users should create a new branch calles a feature or a topic branch

### Realease branch

For a project where the team must maintain miltiple software versions,in turn,supporting,released versions for customers

### Merge

A merge is the final push of the completed work from one branch to the main or different branch to incorporate changes into the respective branch

Most of the time,you will merge the content from your feature/topic branch to your main bracn

### Tag

A specific tag is a reference pont to a specifiv historic commit

Tags are most used to tag a particular production release,letting the team/users know which versions of the code went to production with the particular tagged release

### Checkout

Checking out simply means that the user is trying to get a different version of the project to check and verify the file's state at the time of commit

### Pull request

Initially , a PR meant that someone from the team or community would assess the work and fix that your PR was supposed to resolve , and then provide feedback before it would be merged

### Issue

Github feature used to discuss features,track bugs,or both in the project

### Clone

The way towards duplicating the Github repository to local PC

## Git options

---

```bash
# Outputs Git version
git --version

# This git command output an iverview and a list of thr most frequently used commands
git --help

# this option lets the user run thr Gir commans from the specified <path instead of the current working direction
git init -C <path>

# This will treat the given Git repository as Bare repository
git init --bare
```

## Git commands

---

### TO start a working

To starts a working area

- init
- clone

To work on the current change

- add
- rm
- restore
- mv
- spars-chckout

To examin the history and state of the repository

- bisect - using binary search to find the commit that introduced a bug
- diff
- grep
- log
- show
- status

To grow,mark and tweak your repo history

- branch
- commit
- merge
- rebase
- reset
- switch
- tag

To collaborate over repository

- fetch
- pull
- push

## Initialize Git repository

---

```bash
# creates a .git subdirectory in your current working directory
git init


# Repository created using --bare flag does not have a working directory
git init --bare

# In yhe newly created repository,use the specified name for the first branch
git init -b lakdav
```

## Clone a Git repository into a new directory

---

Cloning is the process of copying yhr repository to your computer

```bash
git clone git@github.com:lakdav/Github101.git

# WHen the repository to clone from is on local machene, this flag bypasses transport mechanism
git clone -l clone git@github.com:lakdav/Github101.git

# If ther is a need to clone th Git repository based out of a particular tag/name.This is the branch that will be chched out in a non-bare repository

git clone -b lakdav  git@github.com:lakdav/Github101.git

# Create a bare Git repository
git clone --bare git@github.com:lakdav/Github101.git

# To make a shallow clone with a history limeted to the number of commits specified.Shallow clonning is used or becomes necessary fo thr Git repoditory which has an extensive history
```

## Adding file contents tothe index

---

The command git add adds changes in the working directory to the staging area

```bash
git add README.md
git add .
git add -A

# allows adding ignored files
git add -f .


# -p
# --interactive
```

## Move or rename a file, a directory, or a sumlink

---

```bash
# rename
git mv README README.md
```

```bash
# delete
# if file is in commit history file will be removed from working and staging area
git rm text.txt


# if file is'n in commit history we must add -f (force)
git rm -f text.txt

# remove from staging area only
git rm --cached text.txt


# Delet all the filenames with .txt extension from the index under Documentation directory
git rm Documantation/\*.txt

# -r recursive delete, when a directory is given to delete
```

```bash
# To undo the changes made by git rm ,we can use
git reset HEAD
#or
git checkout .
```

## git restore

---

The git restore command is used to restore or delete uncommited local modifications to files

```bash
# Restore the working tree files with the provided tree's content (-s or --source)
# If no arguments are supplied , the contents are restored from HEAD
git restore -s <commmit>

# Set the location of restoration
# by default --worktree if nither option given
git restore --staged text.txt

# -W or --worktree
# -S or --staged
```

## Examine The history and state of the repository

---

### git bisect

To locate the commiit that caused a problem ,use binary search

```bash
#1
git bisect start
#2
git bisect bad
#3
git bisect good <commit>
#4 additionally nedd to notify git the status of the revision with
git bisect bad
# or
git bisect good

```

### git diff

```bash
# Команда показывает разницу между вашим рабочим каталогом и индексом
git diff

# Команда показывает разницу между вашим рабочим каталогом и HEAD
git diff HEAD
git diff HEAD text.txt

# Эта форма выводит различия между вашим рабочим каталогом и указанной фиксацией
git diff фиксация

# Данная команда показывает разницу между подготовленными в индексе из­ менениями и заданной фиксацией
git diff --cached фиксация

# Показывает разницу между двумя произвольными фиксациями
git diff фиксация1 фиксация2

git diff HEAD^ HEAD

# Compare two files from differnt branch
git diff main dev text.txt

# -w или - -ignore-all-space
# --stat а сообщает, сколько строк изменено, сколько добав­лено и сколько удалено
# --color
```

### git log

The git log command displays snapshots that have been commited

```bash
git log

git log --all

# only in dev branch , main branch is ommited
git log --oneline main..dev

git log --stat

# shows the difference
git log -p

# complete diff of all the modifications made by the author to the file
git log --author="lemonjava gocha" -p text.txt

# limit the number of log entries displayed
git log -2


# "2008-01-15"
# "2 years 1 day 3 minutes ago"
git log --since=2.weeks

# Show only the first few characters of the SHA-1 checksum instead of all 40.
git log --abbrev-commit

git log --pretty=oneline

git log --pretty=format:"%h - %an, %ar : %s"
# %H Commit hash
# %h Abbreviated commit hash
# %T Tree hash
# %t Abbreviated tree hash
# %P Parent hashes
# %p Abbreviated parent hashes
# %an Author name
# %ae Author email
# %ad Author date (format respects the --date=option)
# %ar Author date, relative
# %cn Committer name
# %ce Committer email
# %cd Committer date
# %cr Committer date, relative
# %s Subject

git log --pretty=format:"%h %s" --graph


git log -S function_name


git log -- path/to/file
```

Некоторые специальные опции команды git log могут помочь вам обнару­жить, какие изменения откуда пришли и почему. Попробуйте ввести эту ко­манду

```bash
git log --mergr --left-right -p

git log --mergr --left-right -p tetx.txt
```

### git show

```bash
git show
git show text.txt
git show <commit>
git show <commit> <path>
```

### git status

The git status command display informayion about the current working directory and staging area

```bash
git status

# short status
git status -s
```

## To grow, mark and tweak your repo history

---

### git branch

The git branch command makes it possible to create ,list ,and remove branches

```bash
# выводит список веток
git branch
git branch --list

# create branch
git branch dev

# Rename the branch
# -m or --move
git branch --move bad-branch-name corrected-branch-name

# delete branch
# if branch is'n merged
git branch -D dev
# if branch is merged
git branch -d dev


git branch -u origin/serverfix

# -v To see the last commit on eachbranch
# -r удаленные ветки
# -a выводит все ветки
# -d , -D  Удаление веток

# --merged and --no-merged options can filter this list to branches that you have or have not yet merged into the branch you’re currently on
```

```bash
# to delete remote branch
git push origin --delete dev
```

```bash
# switch to another branch
git checkout dev
#or
git switch dev
```

```bash
# before merge we must swith to the branch where we want merge feature branch
#1
git switch main
#2
git merge feature
```

### git commit

The git commit command saves the project's current staged changes.Commits sre used to document a projects's current status

```bash
# the command will launch a default text editor
git commit

git commit -m "commit message"

git commit -a -m "commit message"
```

### git merge

Git merge is a process commetc the branched histories

```bash
# before merge we must swith to the branch where we want merge feature branch
#1
git switch main
#2
git merge feature
```

### git rebase

It employed to combine several commits from several branches into a single commit

```bash
git rebase main

git rebase --continue

git rebase --skip


```

### git reset

У команды git reset есть три основных опции

- --soft
- --mixed
- --hard

## soft

Параметр --soft изменяет ссылку HEAD на точку, заданную фиксацией. Со­ держимое вашего индекса и рабочего каталога останется без изменений.

## mixed (По умолчанию)

изменяет ссылку HEAD так, что она будет указывать на заданную фиксацию. Содержимое вашего индекса также будет модифици­ ровано, но файлы в рабочем каталоге останутся без изменений.

## hard

Этот вариант устанавливает ссылку HEAD на заданную фиксацию, содер­ жимое индекса и рабочего каталога будет изменено так, чтобы соответство­вать указанной фиксации

|         | HEAD  | Индекс | Рабочий каталог |
| ------- | ----- | ------ | --------------- |
| --soft  | +++++ |        |                 |
| --mixed | +++++ | +++++  |                 |
| --hard  | +++++ | +++++  | +++++           |

Команда git reset также сохраняет исходное значение HEAD в ссылке ORIG_HEAD

### git tag

```bash
# listing the existing tags
git tag

# for tags that match a particular pattern
git tag -l `v1.8.5`


```

Git supports two types of tags: lightweight and annotated.

```bash
# Annotated Tags
git tag -a v1.4 -m "my version 1.4"


# Lightweight Tags
git tag v1.4-lw

# Tagging Later
git tag -a v1.2 9fceb02

# Deleting Tags
git tag -d v1.4-lw

# Checking out Tags
git checkout v2.0.0

# creat branch from tag
git checkout -b version2 v2.0.0
```

```bash
# to see info about tag
git show v1.4
```

By default, the git push command doesn’t transfer tags to remote servers,You will have to explicitly
push tags to a shared server after you have created them

```bash
git push origin v1.5

git push --tag
```

## To collaborate over repository

### git fetch

This command downloads the objects and refs from anothe Git repository

The fetch command did not update the local repository

```bash
# we can use the fetch command to get whole repository from a repository URL
git fetch <repository URL>

# to fetch all remote repositories
git fetch --all

# fetch specific branch
git fetch origin main
```

### git pull

the git pull command download and merges form remote repository into local repository

```bash
git pull origin
git pull origin main
```

### git push

The Git push command sync the contents of teh local and remote repositories. Exporst the material to the remote branches

```bash
git push origin mai

git push --all

# --prune
# --force
# --tags
# --delete
```

## Delete the Git file

Git rm's primary job is to delete tracked files from the git index.It can also be used to delete files from the working directory

```bash
# delete text.tx from working and staging area
# 1
git rm text.txt
# 2 after we can commit
git commit -m "delete text.txt file"
```

```bash
# delete text.tx from staging area
# 1
git rm --cached text.txt
# 2 after we can commit
git commit -m "delete text.txt file"
```

The git rm command is not permanent and can be changed after it has been run

```bash
git reset HEAD
# or
git reset --hard
```

## Git rename files

There are two ways in wich we can rename our files in the git repository wich are as follows

```bash
#Method 1
#1
mv README README.md
#2
git add .
#3
git commit -m "rename README to README.md"
```

```bash
#Method 2
#1
git mv README README.md
#2
git commit -m "rename README to README.md"
```

## Git Tag

---

Tags makrs a particular point in Git's history

There are tow types of tags

- Annotated tag
- Light-weighted tag

Annotated tags should be considered public ,while Lightweight tags shoulde be considered private

```bash
# listing the esisting tags
git tag

# for tags that match a particular pattern
git tag -l `v1.8.*`


```

Git supports two types of tags: lightweight and annotated.

```bash
# Annotated Tags
git tag -a v1.4 -m "my version 1.4"


# Lightweight Tags
git tag v1.4-lw

# Tagging old commits
git tag -a v1.2 9fceb02

# Deleting Tags
git tag -d v1.4-lw
git tag -d <tag1> <tag2>
git push origin -d <tagname>

# Checking out Tags
git checkout v2.0.0

# creat branch from tag
git checkout -b version2 v2.0.0

# if you nedd to change an existing tag
git tag -a -f <existing tag> <commit>
```

```bash
# to see info about tag
git show v1.4



git push origin --tag
```

### Sharing Tags

By default, the git push command doesn’t transfer tags to remote servers,You will have to explicitly
push tags to a shared server after you have created them

```bash
git push origin v1.5

git push --tag
```

## Cherry-Pick

---

git cherry-pick is command that allows you to pock random Git commits by reference and append them to the current working HEAD

```bash
git cherry-pick <commit>
```

## Git Stash for code reusability

git Stash stires modifications you have made toyour working copy so you can work on something else and then come back

```bash
# Команда git stash list выводит стек сохраненных контекстов от самого последнего до самого старого
git stash list

# Команда git stash save сохраняет ваш текущий индекс, рабочий каталог
git stash save 'Работаю над текущим проектом'

# Команду git stash рор можно выполнить только в чистый рабочий каталог.
git stash pop

# Если вы хотите только воссоздать контекст, сохраненный в стеке состояний без его удаления из стека, используйте команду git stash apply
git stash apply stash@{1}

# Данная команда преобразовывает содержимое сохраненного состояния в новую ветку на основе фиксация, которая была текущей на момент создания stаsh-записи
git stash branch <branch name>

#delete
git stash drop stash@{1}

# -u --include-untracked
# -all получает неотслеживаемые файлы, а также явно игнорируемые файлы, указанные в .gitignore.
```

## Branching Models Startegies

### Trunk-Based

the trunk-based model consists in each contibutor commiting on the main (or master) branch,often called the trunk in other VCSs

Branches are allowed. Though,generally,the tend to be short-lived branches

### Feature Branching

Concretely, doing feature branching means creating a branch for each feature developed in an application.
Once a feature is finished, its branch can be merged back into the main branch, bringing the functionality to it.
