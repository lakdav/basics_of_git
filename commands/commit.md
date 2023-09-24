# commit

```bash
git commit -m '....'

# commit all modified and deleted files, whether they are in the staging area or not
# It’ll just omit untracked files, which won’t be committed
git commit -a -m `....`

# Stage changes will be applied to the previous commit rather than a new one
git commit --amend

# You can avoid adding a message, by using
git commit --allow-empty-message --no-edit
```
