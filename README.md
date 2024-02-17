# GIT Cheat Sheet

## Создание репозитория
- Инициализировать репозиторий можно с помощью команды **git init**.
- Проверить статус, или состояние, репозитория поможет команда **git status**.
- Если вы ошиблись и случайно инициализировали не ту папку, можно «разгитить» её — удалить скрытую подпапку **.git**.

## Добавление файлов в репозиторий
- Команда **git add** позволяет подготовить файл к сохранению.
- Команда **git add --all** подготовит к сохранению сразу все файлы.
- С помощью **git add .** можно добавить в репозиторий текущую папку со всеми файлами.

## GIT Commit
- Коммит можно сделать с помощью команды *git commit*.
- Ключ **-m** позволяет присвоить коммиту сообщение. Помните, что такие сообщения должны быть информативными: чётко описывать изменения.
- В коммит попадает то, что было предварительно добавлено «в корзину», или «в кадр», перед коммитом.

## История коммитов
Для просмотра истории коммитов используют команду **git log** (от англ. log — «журнал»).

## SSH-ключ и его генерация
- *SSH* — протокол, который обеспечивает безопасный обмен данными в сети и использует для этого ключи.
- *SSH-ключ* — ваш виртуальный идентификатор в GitHub. Как ключ от квартиры, он позволяет получить доступ к GitHub-репозиторию. Также SSH используется для доступа к другим удалённым серверам.
- *SSH-ключ состоит из двух частей* — публичной и приватной. Публичный ключ зашифрует данные, а приватный — расшифрует. Приватным ключом ни в коем случае нельзя делиться, иначе любой сможет расшифровать все ваши секреты!

Для генерации SSH-ключа используют команды:

**$ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"**

или

**$ ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"**


После создания SSH-ключа его необходимо привязать к аккаунту GitHub, [здесь](https://practicum.yandex.ru/trainer/git-basics/lesson/4d662a58-3602-4c5c-9fad-be8cff334f37/) можно посмотреть инструкцию.

## Связка локального и удаленного репозиториев
Чтобы привязать удаленный репозиторий к локальному, используют команду **git remote add**. Пример использования команды:

**$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git** ,

где *origin* - (англ. «источник») — стандартный псевдоним, с помощью которого можно обращаться к главному удалённому репозиторию (обычно такой репозиторий один), а *git@github.com:%ИМЯ_АККАУНТА%/first-project.git* - SSH-ссылка на удаленный репозиторий.

## Синхронизация локального и удаленного репозиториев
За отправку изменений на удалённый репозиторий отвечает команда **git push**. В первый раз эту команду нужно вызвать с флагом *-u* и параметрами *origin* (имя удалённого репозитория) и *main* или *master* (название текущей ветки). Флаг *-u* свяжет локальную ветку с одноимённой удалённой.

**$ git push -u origin main** *# Если команда приведёт к ошибке, попробуйте*
                              *# заменить main на master.*

В дальнейшем при работе с удалённым репозиторием флаг *-u* можно опустить и писать просто **git push**.

## Оформление файла README.md
Как правило, в **README.md** проекта можно найти следующую информацию:
- Название проекта и его краткое описание: кем создан, для чего, какие решает задачи и какие закрывает проблемы.
- Технологии, которые применяются в проекте. В чём его отличие от аналогичных.
- Документация проекта — подробная инструкция о том, что представляет собой проект.
- Планы проекта, если они есть.

Вот *пример файла README.md* для Git [на GitHub](https://github.com/git/git/blob/master/README.md).

**Преимущество README.md** в том, что средства командной работы (такие, как GitHub) могут отображать его содержимое в браузере в виде удобной разметки. Для этого нужно не просто залить текст, но и настроить шрифт, заголовки и отступы с помощью markdown. **Маркда́ун** — это специальный язык разметки. Он позволяет красиво отформатировать текстовый документ. Базовый синтаксис языка можно посмотреть [здесь](https://doka.guide/tools/markdown/).
