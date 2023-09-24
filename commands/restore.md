# restore

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
