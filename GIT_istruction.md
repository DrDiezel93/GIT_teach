![Мальчик за компьютером](Copil-la-calculator_shutterstock.jpg)
# Инcтрукция по работе с GIT
## 1. Проверка наличия установленного GIT
В терминале выполнить команду `git version`

Если `git` установлен, появится информация о версии `git`, иначе будет сообщение об ошибке

## 2. Установка GIT

Устанавливаем последнюю версию GIT с сайта

Устанавливаем с настройками по умолчанию.


## 3. Настройка GIT

Представиться GITу, а именно ввести в терминале 2 команды:
```
git config --global user.name «Ваше имя английскими буквами»
git config --global user.email ваша почта@example.com
```

## 4. Инициализация репозитория

Создаем папку с именем без пробелов на английском языке

Открываем созданную папку в GIT

Инициализация: указываем папку, в которой `git` начнет отслеживать изменения; вводим команду `git init`

Используя "проводник" создаем в папке файл с поддерживаемым расширением (.md, .txt и т.д.) на английском языке без пробелов

Добавляем содержимое рабочего каталога в индекс для последующего отслеживания: вводим команду `git add [название файла.расширение]`

Инициализация репозитория завершена. Осуществляем ввод текста (данных) и начинаем отслеживание

Клонировать существующий репозиторий: используй команду `git clone [адрес репозитория]`

## 5. Запись изменений в репозиторий

После внесения изменений в репозиторий (ввода текста/данных) необходимо сохранить файл: сочетание клавиш **ctrl+s** или через файл **сохранить/сохранить как**

Далее посмотреть текущее состояние GITa, есть ли изменения, которые нужно закоммитить: вводим команду `git status`

В случае наличия изменений, осуществляем их фиксацию (коммитим) введением команд: 
```
git add [название файла.расширение]
git commit -m "[сообщение о внесенных изменений]"

или объединенная команда

git commit -am "[сообщение о внесенных изменений]"
```
Повторяем указанные операции после внесения изменений в репозиторий

Команда `git diff` показывает разницу между текущим файлом, изменения которые необходимо сохранить, и сохранённым

## 6. Просмотр истории коммитов и перемещение между сохранениями

Перед переключением версии файла в GIT используйте команду `git log`, чтобы просмотреть журнал изменений и увидеть количество сохранений

Для просмотра журнала изменений в сокращенном виде используем команду `git log --oneline`

При необходимости переключения в другую версию, отображенную в терминале после команд `git log` или `git log --oneline`, вводим команду `git checkout [первые 7 символов нужного коммита/сохранения]

Для возврата к текущему/актуальному коммиту (сохранению) используем команду `git checkout master` или `git switch -`

## 7. Добавление изображения

Необходимое изображение сохраняем в созданной папке с репозиторием

В требуемом месте, где нужно поместить изображение, пишем строчку:
```
![текст, который увидят, если с изображением что-то случится](название изображения с расширением) т.е. ![]()
```

## 8. Игнорирование файлов

В Git не принято добавлять файлы изображений, их хранят на сторонних носителях. Чтобы исключить ненужные файлы из загрузки, есть команда git ignore

Для этого в проводнике создаем файл `.gitignore`

Перейдя в файл `.gitignore`, записываем (перечисляем) все файлы и (или) расширения файлов, которые git будет игнорировать

Сохраняем (коммитим) изменения, используя команды `git add` и `git commit` (см. раздел 5)

## 9. Работа с ветками 

Создать ветку можно командой `git branch <название новой ветки>`. Делать это надо в папке с репозиторием

Если потребуется переключиться с одной ветки на другую, вызовем команду `git checkout <имя ветки>`

Для создания новой ветки с одновременным переходом в нее используем команды `git cheсkout -b <имя новой ветки>` или `git switch -c <имя новой ветки>`

Когда мы правим текст/код в текущей ветке, автоматического слияния не происходит: можно создавать один документ в разных версиях в разных ветках

Не забываем сохранять (коммитить) изменения, используя команды `git add` и `git commit` (см. раздел 5)

Чтобы совместить (слить) любую ветку с текущей, вызываем команду
`git merge <имя ветки для слияния с текущей>`

В случае возникновения конфликта при слиянии (если происходит наложение информации в ветке master и созданной ветке), разрешаем конфликт, используя интерфейс VSC, или вручную удаляя и (или) оставляя изменения

После разрешения конфликта, сохраняем (коммитим) изменения командами `git add` и `git commit` (см. раздел 5)

Если слитая ветка больше не нужна, ее можно удалить, вызвав команду `git branch -d <имя удаляемой ветки>`

В случае удаления ветки с неслитой в основную ветку информацией, командой `git branch -d <имя удаляемой ветки>`ветку удалить не удастся (появится соответствующее сообщение об ошибке). Далее: либо сливаем ветки установленным выше порядком, либо удалем ветку командой `git branch -D <имя удаляемой ветки>`

# Работа с удаленными репозиториями

## Настройка совместной работы

Создать аккаунт на GitHub.com

Создать в своем аккаунте удаленный репозиторий, нажав в правом верхнем углу кнопку "+"

Создать локальный репозиторий (см. раздел 4)

“Подружить” ваш локальный и удалённый репозитории. GitHub при создании нового репозитория подскажет, как это можно сделать. А именно необходимо ввести следующие команды:
```
git remote add origin https://github.com/<nickname>/<название вашего удаленного репозитория>.git
git branch -M main 
git push -u origin main
```
При внесении изменений в локальном репозитории (добавления информации, удаления и т.д.) сохраняем (коммитим) изменения (см. раздел 5)

Отправить ваш откорретированный локальный репозиторий в удалённый (на GitHub) командой `git push`, при этом, возможно, 
вам нужно будет авторизоваться на удалённом репозитории

При возникновении необходимости выгрузить c GitHub откорректированный удаленный репозиторий в свой локальный используем команду `git pull`
```
Команда `git pull` позволяет скачать все из удаленного репозитория и автоматически сделать merge с нашей версией

Команда `git fetch` загружает коммиты, файлы и ссылки из удаленного репозитория в ваш локальный репозиторий

Из этих двух команд `git fetch` можно считать «безопасным» вариантом. Она загружает удаленное содержимое, но не обновляет рабочее состояние локального репозитория, оставляя текущую работу нетронутой
```

## Создания **pull request**

Команда ***pull request***

* команда для предложения изменений
* запрос на вливание изменений в репозиторий

*Справочно: в больших компаниях один ответственный за проект создает аккаунт. Другие пользователи дают команду pull request, предлагая свои изменения, дополнения в проект. Изменения предлагаются в новых ветках, не трогая основную*

Для создания ***pull request*** необходимо:

* На GitHub делаем копию (ответвление) репозитория в свой аккаунт нажимая на кнопку "fork"

* Командой git clone <URL-адрес репозитория на GitHub> создаем копию своей версии репозитория
```
Команда git clone составная: она не только загружает все изменения, но и пытается слить все ветки на локальном компьютере и в удаленном репозитории
```

Создаем новую ветку (см. раздел 9) и в НЕЕ вносим свои изменения

Фиксируем изменения (делаем коммиты) (см. раздел 5)

Командой `git push` отправляем свою версию в свой GitHub. GIT подскажет, как отправить новую ветку в GitHub т.к. в исходном виде команда `git push` не сработает

На сайте GitHub, выбрав нашу ветку, нажимаем кнопку "pull request" или перейдя на вкладку <pull requests> нажимаем на кнопку "Compare & pull request". Далее следуем подсказкам GitHub

# КОНЕЦ