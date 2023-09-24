# Удаление и переименование файлов

## git rm

```bash
##### 1
git rm text.txt
##### 2
git commit -m "Удаляем text"
```

## git mv

```bash
##### 1
mv index.html page.html
##### 2
git rm index.html
##### 3
git add page.html

#####
git commit -m "rename index.html to page.html"

```

```bash
##### 1
git mv index.html page.html

#####
git commit -m "rename index.html to page.html"

```
