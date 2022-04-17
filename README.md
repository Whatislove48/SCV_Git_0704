# Working in Git 
## 1. Проверка наличия установленного Git
В терминале выполнить команду: 
`"git version"`

Если git установлен появится информация о программе. Иначе ошибка 

## 2. Установка Git
Загружаем последнюю версию **Git** с сайта https://git-scm.com/download/win
Устанавливаем с настройками по умолчанию

## 3. Настройка Git 
При первом использовании **Git** необходимо представиться 
для этого нужно ввести в терминале 2 команды:
```
 <git config --global user.name "Ваше имя">
 <git config --global user.email "Ваша почта ">
 ВНИМАНИЕ! скобочки по бокам не входят в команду
 ```

 если ошибок нет то все хорошо 

## 4. Инициализация 
В терминале переходим к папке, в которой хотим создать репозиторий.
```
Делается это путем выбора папки в верхнем левом углу программы в "проводнике"
```

 Выполняем команду `git init `.
В исходной папке появится скрытая папка *.git*

## 5. Запись изменений в репозиторий    

Для начала необходимо сохранить сам текстовый файл в котором идет работа при помощи клавиш `Ctrl+S` ну или же курсором.
Но лучше в окне `файл(file)` поставить галочку на `автосохранение`.

Затем введем в терминал команду 
```
<git status>
```
После этого в окне терминала появится информация о файле, с рекоммендацией к дальнейшему сохранению.
После этого необходимо добавить данный файл (в котором работаем), в отслеживание программой при помощи команды _**`git add`**_:
```
<git add "file-name">
file-name - название нашего файла 
Например: 
git add "Homework"
```
После, если ввести комнаду _**`git status`**_ мы увидим, что теперь файл отслеживается и готов к фиксации при помощи команды _`git commit`_
```
<git commit -m "Notes">
-m = (massege)обозначение что далее комментарий
Notes = собственно сама заметка о внесении изменений
<git commit -am "Notes"> комбинация add + commit + massege но только если команда <git add> использоваласб хотя бы один раз
Например: 
git commit -am "исправлен раздел 5 - запись в репозиторий"

```

## 6. Просмотр истории коммитов 

Для просмотра истории Commit используем команду 
```
<git log> 
<git log --oneline>
Расшиненная и сокращенная версия
```

 ВНИМАНИЕ! При использовании первой команды отобразится много информации о сохранениях и чтобы выйти из этого режима нажмем клавищу - `q`

Последние коммиты находятся вверху 

## 7. Перемещение между сохранениями 

При использовании команд из раздела 6, в терминале отобразятся hash-коды коммитов, Например:
```
commit 0e46cc85ebced4400dafe1457c281cdc059728d6
```
Используя данный код или же первые 6 символов можно переместиться на нужное нам сохранение при помощи команды:
```
<git checkout 'number'> пример - git checkout 0e46cc8
'number' - hash-код
кавычки для наглядности
```

ВНИМАНИЕ! После всех манипуляций не забудьте обратно перейти к главной ветке `master`, введя команду 
```
git checkout master
```
Если высветится `Switched to branch 'master'`, то вы перешли обратно к главной ветке


## 8. Игнорирование файлов 

Иногда некоторые файлы которые находятся в нашем рабочем репозитории не нужно отслеживать (например фото). Для этого используют игнорирование файла. 
Инструкция к данной процедуре следующая:
```
Для начала создадим файл -
 <.gitignore> - именно так (без скобочек)!
 
 И добавить в этот файл строку с названием игнорируемого файла, например:

 Фото Андрюхи.jpg

```

## 9. Работа с рисунками 
Чтобы вставить изображение, необходимо перенести файл в рабочую папку (репозиторий), слева сверху. И ввести в файле следующую строку

```
![Текст прикрепляемы к картинке](Название файла с изображением)
Например:
![привет Андрей](фото Андрюхи.jpg)

```
![Андрюха](maxresdefault.jpg)


## 10. Создание веток 

Ветки служат так называемыми черновиками, поэтому следует работать в них чтобы не сломать основной код.
Создание веток имеет следующий вид:
```
Введем в терминал команду:
git branch NameBranch

NameBranch - название создаваемой ветки
``` 

## 11. Слияние веток 

После всех доработок и сохранений в ветках, возникнет момент когда необходимо вставить всю информация в главную ветвь (master)
Для этого сделаем следующее:

```
Закоммитим ветку которую хотим влить в основную. После используя команду <git merge> соеденим ветви. Например:

git merge CaseMerge

CaseMerge - название ветки которую сливаем.
```



## 12. Конфликты


Если в доп. ветке имеется какая-нибудь информация из раздела и в этом же разделе в основной ветке уже есть данные, при слиянии этих веток у нас возникнет конфликт, в зависимости от среды разработки у нас будут разные решения но в Visual Studio Code все наглядно просто. В случае конфликта мы увидим следующее:

![Скрин конфликта](Conflict.png)   

После этого мы увидим обе версии и среда предложит нам несколько вариантов решения (оставить из основной,оставить из доп.ветки, оставить оба варианта,сравнить версии) 

## 13. Удаление веток  

После слияния желательно удалить слитую ветку так как все уже находится в основной.
Делается это следующим образом

```
Перейдем на ветку master и введем команду 

git branch -d CaseMerge

CaseMerge - название ветки которую удаляем.
```

## 14. Работа с удаленными репозиториями
Рано или поздно работу проделанную в Git необходмо отправить на проверку.
Для этого зарегистрируемся на любой площадке для размещения своих проектов. Мы будем использовать GitHub. Чтобы начать работу с удаленными репозиториями выполним следующие обязательные условия:

1. Создадим аккаунт на площадке GitHub.com
2. Создадим локальный репозиторий (в программе на компьютере)
3. Открыв репозиторий на GitHub мы увидим инструкцию исходя из того что мы хотим в дальнейшем делать. Допустим мы выбрали добавить данные в удаленный репозиторий из локального. Команды в терминале будут выглядеть следующим образом: 
```
git remote add origin https://github.com/Whatislove48/Test_of_Hub.git
git push -u origin master
```
На этом этапе Git может потребовать логин и пароль пользователя для дальнейшей работы.

4. Далее с помощью команды **git push** отправляем локальные данные в GitHub, обновив страницу ммы увидим доплненные данные.

Готово! первая часть выполнена.

Работа с репозиториями может быть и в обратную сторону. Мы можем изменять данные на GitHub (удаленный репозиторий) и выкачивать (pull) их в локальный репозиторий.  
Для этого просто вносим изменения на удаленном реп. и применяем их.Далее в терминале локального реп. введем следующее: 
```
git pull
```

## 15. Продолжаем работать с удаленными репозиториями - Pull request

На сайте GitHub находим репозиторий пренадлежащий другому человеку и Форкаем ее (Fork) - используем функцию Fork на сайте.
После чего используя команду 
**clone** 
```
clone https://github.com/Whatislove48/SCV_Git_0704.git
```
Репозиторий успешно скопирован в нашу раборчую папку.
Чтобы предложить свои изменения создадим дополнителльную ветку, вносим изменения там.
Чтобы предложить нашу версию, используем команду **git рush**
Git предложит нам следующее
```

``` 




## Репозиторий для **pull request**
* В своём аккаунте на GitHub создать копию репозитория **"AndreyBulgakov19
/SCV_Git_0704"** с помощью кнопки **"Fork"**.
---
* Клонировать копию репозитория на локальный компьютер.
---
* Создать новую ветку.
---
* Добавить файл с инструкцией в новую ветку.
---
* Дополнить инструкцию разделами по работе с удалёнными репозиториями, pull request.
---
* Зафиксировать изменения (коммиты).
---
* Отправить изменения на GitHub.
---
* На сайте GitHub выполнить **Pull request**.
---
# Инструкция 
