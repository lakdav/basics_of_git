# branch

```bash
# выводит список веток
git branch
git branch --list

# create branch
git branch dev

# Rename the branch
# -m or --move
git branch --move bad-branch-name corrected-branch-name

# force renaming branch (if branch name already exist)
git branch -M <existing branch name>

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
