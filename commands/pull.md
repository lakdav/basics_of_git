# pull

From Git version 2.27 onward, git pull will give a warning if the pull.rebase variable is not set. Git will keep warning you until you set the variable.

If you want the default behavior of Git (fast-forward if possible, else create a
merge commit): git config --global pull.rebase "false"
If you want to rebase when pulling: git config --global pull.rebase "true"

```bash
git pull origin dev
```
