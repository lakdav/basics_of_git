# tag

```bash
# listing the esisting tags
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
to see info about tag
git show v1.4
```

## Sharing Tags

By default, the git push command doesn’t transfer tags to remote servers,You will have to explicitly
push tags to a shared server after you have created them

```bash
git push origin v1.5

git push --tag
```
