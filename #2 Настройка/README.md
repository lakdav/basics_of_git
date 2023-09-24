# Настройка

---

В состав Git входит утилита git config, которая позволяет вам просматривать и устанавливать параметры, контролирующие все аспекты работы и внешнего вида Git. Эти параметры могут быть сохранены в трёх местах:

- /etc/gitconfig (--system)
- ~/.gitconfig (--global)
- .git/config (--file)

## Проверка настроек

```bash
##### для вывода всех переменных, найденных во всем наборе файлов конфигурации
git config --list

##### /etc/gitconfig
git config --list --system

#####  ~/.gitconfig
git config --list --global

##### .git/config
git config --list --local

##### значение конкретного ключа
git config user.name
```

## Имя пользователя и адрес электронной

```bash
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

> Если вы хотите указать другое имя или электронную почту для конкретных проектов, можно выполнить команду без параметра --global в каталоге с нужным проектом.

## Выбор редактора

По умолчанию Git использует стандартный редактор вашей системы, обычно это Vi или Vim

```bash
git config --global core.editor nano
```

## Утилита сравнения

```bash
git config --global merge.tool vimdiff
```

## --unset для удаления настройки

```bash
git config --unset --global user.email
```

```bash
# If you want the default behavior of Git (fast-forward if possible, else create a merge commit)
git config --global pull.rebase "false"
```
