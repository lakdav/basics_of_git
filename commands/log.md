# log

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

# filter commits by commit message
git log --grep="commit search message"

git log --pretty=format:"%h %s" --graph

# filter commits based on the content of the commit
git log -S'function_name'

git log --after="yy-mm-dd"
git log --before="yy-mm-dd"

git log -- path/to/file
```

Некоторые специальные опции команды git log могут помочь вам обнару­жить, какие изменения откуда пришли и почему. Попробуйте ввести эту ко­манду

```bash
git log --merge --left-right -p

git log --merge --left-right -p tetx.txt
```
