# rm

```bash
# if file is in commit history file will be removed from working and staging area
git rm text.txt


# if file is'n in commit history we must add -f (force)
git rm -f text.txt

# remove from staging area only
git rm --cached text.txt

git rm log/\*.log
git rm \*~
```
