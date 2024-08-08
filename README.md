﻿# Это репозиторий для обучения pull request

## Первые шаги

1. Делаем fork репозитория, в которой потом хотим сделать pull request. Ищем кнопку Fork на странице репозитория <https://git@github.com:gulden-geekbrains/version_control.git>
2. Выполняем команду клонирования из своей fork-копии
```sh
git clone git@github.com:*YOURE_GITHUB*/version_control.git
```
3. Создаем новую ветку и вносим необходимые изменения в файл
```sh
git checkout -b updatereadme
vim README.md
git add README.md
git commit -m "Добавили инструкцию как создать pull request"
```
4. Делаем push  
```sh
git push --set-upstream origin updatereadme
```
5. Переходим на свою страницу репозитория. Выбираем ветку **updatereadme** и жмем кнопку **Compare & pull request**

## Заметки

Что бы сделать push от другого пользователя необходимо выполнить команду
```sh
GIT_SSH_COMMAND='ssh -i ~/.ssh/user-private-key -o IdentitiesOnly=yes' git push git@github.com:gulden-geekbrains/version_control.git
```

вместо *user-private-key* подставьте свой ключ

Можно прописать настройки для подсоединения по ssh
```sh
git config remote.origin.url git@github.com:gitusername/reponame
git config core.sshCommand "ssh -i ~/.ssh/user-private-key -o IdentitiesOnly=yes"
```
# Как подружить git с github под Windows 10

Вот видео инструкция https://youtu.be/E8cIjbJMEpE

# Моя ссылка https://github.com/stayakotyat/version_control_modify.git

# Инструкция по работе с Git и удаленными репозиториями

## Что такое GIT?
***GIT*** - это одна из реализаций распределенной системы контроля версий, поддерживающие как локальные, так и удаленные репозитории. Самая популярная реализация GIT - это [GitHub](https://github.com)
## Подготовка репозитория
Для создания нового репозитория используется команда *git init*. Команду *git init* выполняют только один раз для первоначальной настройки нового репозитория. Выполнение команды приведет к созданию нового подкаталога .git в вашем рабочем каталоге. Кроме того, будет создана новая главная ветка. 

## Создание коммитов
Для создания коммита используется команда *git commit*.

### Выполнение коммитов
Для того, чтобы использовать коммит используется команда *git commit*. Для этого в терминале с папкой-репозитория необходимо написать *git commit -m "<сообщение к коммиту>"*. Сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО!!!***

### Добавления файла к коммиту
Для добавления файла к коммиту используется команда *git add*. Для этого в терминале с папкой-репозиторием необходимо написать *git add <название файла>*.

## Журнал изменений
Для просмотра истории коммитов используется команда *git log*. Для этого в терминале с папкой-репозиторием пишем *git log*. В журанале показанном обязательно будут:
* Хэш (номер) коммита
* Дата и время коммита
* Автор коммита
* Текст сообщения к коммиту

## Перемещение между коммитами
Для перемещения между коммитами используется команда *git checkout*. Для этого в терминале с папкой-репозиторием необходимо написать *git checkout <хэш коммита>*. Хэш коммита можно взять из истории коммитов, про которую было рассказано в предыдущем пункте.

## Ветки в  GIT
Ветка в Git - это простой перемещаемый указатель на один из таких коммитов. По умолчанию, имя основной ветки в Git - master. Как только вы начнете создавать коммиты, ветка master будет всегла указывать на последний коммит. Каждый раз при создании коммита указатель ветки  master будет передвигаться на следующий коммит автоматически.

###
Создание веток
Для создания новой ветки используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch <название ветки>*. Название ветки должно быть  ***УНИКАЛЬНО***!

### Просмотр списка веток
Для просмотра списка веток используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch* и вы увидите список всех существующих веток. Зеленом цветом и символом **звездочка** будет обозначена текущая актуальная ветка.

### Перемещение между ветками
Для перемещения между ветками используется команда *git checkout*. Для этого в терминале с папкой-репозиторий необходимо написать *git checkout <название ветки>*. Ветка ***ОБЯЗАТЕЛЬНО ДОЛЖНА СУЩЕСТВОВАТЬ!!!***.

## Слияние веток и разрешение конфликтов
Слияние используется в Git, чтобы собрать воедино разветвленную историю. Команда *git merge* выполняет слияние отдельных направлений разработки, созданных с помощью команды *git branch*, в единую ветку.
Команда *git merge* объкдиняет несколько последовательностей коммитов в общую историю. Для этого выполните команду "*git merge* <название ветки>", где *название ветки* - название ветки, которая будет объединена с принмающей.
Когда Git обнаруживает конфликт в ходе слияния, к затронутым файлам добавляются визуальные индикаторы по обе стороны проблемного содержимого: <<<<<<<, ======= и >>>>>>>. Строка ======= является «центром» конфликта. Чтобы обнаружить конфликты, необходимо найти в проекте эти индикаторы. После обнаружения конфликтующих участков кода вы можете исправить их по своему усмотрению. 

## Удаление веток
Если нужно удалить текущую ветку, то сначала нужно переключиться на какую-либо другую ветку, а только потом выполнять удаление. Чтобы удалить локальную ветку в Git нужно выполнить команду *git branch -d mybranch*, где вместо mybranch нужно указать название ветки которую необходимо удалить.
