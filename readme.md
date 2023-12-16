**Система контроля версий (Version Control System)** - это программа, которая помогает сохранять разные версии файлов и документов. Она нужна, чтобы не потерять изменения, которые вы сделали в своей работе. С помощью системы контроля версий можно вернуться к более ранней версии файла или сравнить изменения, которые были сделаны в разное время. Это очень полезно, когда вы работаете над большим проектом, состоящим из множества файлов.
Системы контроля версий используются для сохранения изменений в программах, текстах, документах, веб-сайтах и других типах файлов. Они помогают отслеживать, кто и когда внес какие изменения, что может быть полезно при совместной работе над проектом.
Например, если вы работаете над сайтом и вносите изменения в его код, система контроля версий поможет вам сохранить разные версии кода и вернуться к предыдущей версии, если что-то пойдет не так. Это также позволит вам сравнить разные версии кода и увидеть, какие изменения были внесены.
Таким образом, система контроля версий - это инструмент, который помогает организовать работу над проектами и избежать потери важных изменений. Она является неотъемлемой частью процесса разработки программного обеспечения и других сложных проектов.  

**Git** является одним из таких инструментов контроля версий.  

## Работа с командной строкой  

Для удобной и продуктивной работы с Git полезно уметь работать с командной строкой.  

У программ есть привычный графический интерфейс (англ. Graphical User Interface, или GUI). Это окна, значки, кнопки, выпадающее меню с настройками и прочие элементы.
**Командная строка (англ. Command-line Interface, или CLI)** — тоже интерфейс, только текстовый. Пользователь вводит в неё команды. Она принимает их от пользователя и выполняет. Эта строка — обычная программа на вашем компьютере. Такая же, как, например, браузер, в котором вы читаете этот урок.  
Командную строку часто называют *терминалом* или *консолью*. Эти термины пришли из тех времён, когда компьютеры выглядели совсем не так, как сейчас. У них не было привычного интерфейса. Вводить данные или вызывать программы можно было только через специальные устройства: терминалы и консоли. С их помощью происходило взаимодействие человека с компьютером.  

* **pwd** (print working directory) - команда, выводящая путь к текущей директории, т.е. к той папке в которой вы сейчас находитесь;    
* **cd** (change directory) - команда, с помощью которой можно сменить директорию, т.е. перейти в другую папку;  
* **cd ..** - переход на уровень выше в родительскую директорию;    
* **cd ~** - cd в сочетании с тильдой используется для перехода в домашнюю директорию (в Windows это корневая директория юзера);  
* **ls** (list directory contents) - команда, отображающая содержимое директории, т.е. список файлов и папок хранящихся в директории;  
* **ls -a** - отображается список всех файлов и папок, включая скрытые;  
* **touch** - команда для создания файлов;  
* **mkdir** - команда для создания директорий;  
* **mkdir -p** - используя флаг *p* можно создать целую структуру директорий  
    ```mkdir -p dir1/dir_inside/dir_deeper_inside```
* **cp** - команда для копирования файлов. Принимает два параметра: *что_копируем* и *куда_копируем*;  
    ```cp file.txt to fol/``` - копируем файл file.txt в папку fol  
    ```cp index.html style.css script.js src/``` - копируем несколько файлов в папку src  
* **mv** - команда для перемещения файлов и папок. Синтаксис аналогичен синтаксису *cp*;     
* **cat** - команда для чтения содержимого файла в консоль;  
* **rm** - команда для удаления файла;  
* **rmdir** - команда для удаления директории (если в папке, которую вы собираетесь удалить содержатся какие-нибудь файлы, то папка не удалится и выведется сообщение: *"Directory not empty"*);  
* **rm -r** - с помощью флага *r* можно удалить всю директорию с её содержимым  
    ```rm -r images``` - удалит папку *images* со всем её содержимым  
* **&&** - оператор для одновременной передачи сразу нескольких команд:  
    ```mkdir fol && cd fol && touch file.txt``` - создаём папку, переходим в неё и создаём там файл  

## Настройка Git  
* **git version** - команда, отображающая текущую версию Git, установленную на компьютере;  
* **git config --global user.name "first_name last_name"** - команда для указания имени или никнейма пользователя в файле *.gitcinfig*;  
* **git config --global user.email example@gmail.com** - команда для указания имейла пользователя в файле *.gitconfig*;  
* **cat ~/.gitconfig** - читаем данные их файла *.gitconfig*;  
* **git config --list** - вывод полного содержимого конфигураций *Git*;

# Работа с Git  

## Базовые команды  
* **git init** - команда, для преобразования текущей директории в репозиторий;  
* **rm -rf .git** - команда, для "разгичивания" директории. Т.е. если нужно чтобы папка перестала быть репозиторием;  
    * *-r* (recursive) - флаг, позволяющий удалять папки вместе с их содержимым;  
    * *-f* (force) - избавляет от вопросов типа "Вы точно хотите удалить этот файл?"
> Будьте осторожны: в подпапке .git хранится история изменений. Если удалить .git, то вся история проекта будет стёрта без возможности восстановления — останется только последняя версия файлов.  

* **git status** - показывает текущее состояние репозитория;  
* **git add** - команда, для подготовки файлов к сохранению в репозитории  
    ```git add file.txt``` - подготовка файла к добавлению в репозиторий;  
    ```git add --all``` - подготовка к сохранению всех файлов в репозитории;  
    ```git add .``` - добавление всей текущей папки  
> **Чем отличается запоминание от сохранения?**  
> Команда git add не сохраняет содержимое файлов в репозитории. Само сохранение, или фиксацию состояния файлов, называют коммитом (от англ. commit — «совершать», «фиксировать»). «Сделать коммит» значит сохранить текущую версию файла. 
> Если провести аналогию, команду git add можно сравнить с добавлением товаров в корзину в интернет-магазине, а коммит — с оформлением и оплатой заказа.  

* **git commit -m** - делаем коммит с сопроводительным комментарием  
    ```git commit -m 'my first commit'```  
> Коммит — это одна из основных сущностей в Git (и в других системах контроля версий). Коммит гарантирует, что изменения будут сохранены в истории и при необходимости к ним можно будет «откатиться».  

> **Ещё раз о разнице между git add и git commit**  
> Сначала команда git add сообщает Git, какие именно файлы нужно сохранить и какую их версию. Затем с помощью команды git commit происходит само сохранение. 

* **git log** - выводит историю коммитов  

## Работа с Github  

**GitHub** — платформа для хранения IT-проектов и совместной работы над ними с использованием Git. По сути, это сайт, куда можно загрузить файлы своего проекта для обмена с другими людьми.  

### Что такое SSH  
Когда компьютеры обмениваются данными в сети, они следуют сетевым протоколам (англ. network protocols) — правилам обмена данными между компьютерами.
Один из наиболее распространённых сетевых протоколов — SSH (от англ. Secure Shell Protocol). Он обеспечивает безопасный обмен данными в сети. С помощью этого протокола можно получать данные с удалённого компьютера или отправлять их на него. Трафик шифруется, поэтому протокол безопасен.
SSH использует пару ключей для обеспечения безопасности — публичный и приватный: 
Приватный ключ (англ. private key) хранится только на вашем компьютере и не должен передаваться кому-либо ещё. Он используется для расшифровки данных.
Публичный ключ (англ. public key) доступен всем и используется для шифрования данных. Они могут быть расшифрованы парным приватным ключом.
Только вы можете расшифровать данные с помощью приватного ключа, но любой владелец публичного ключа может их для вас зашифровать. Эти два ключа связаны и образуют SSH-пару. В будущем вы наверняка будете использовать их для взаимодействия с GitHub и другими удалёнными серверами.

* **ls -la ~/.ssh/** - проверка наличия SSH ключей;  
* **ssh-keygen -t ed25519 -C "the email to which your Github is linked"** - команда для генерации SSH-ключа;  

> Быть или не быть кодовой фразе — вот в чём вопрос
Как бы странно ни звучало, кодовая фраза — это «пароль от ключа». Представьте, что SSH-ключ лежит в шкатулке. А на самой шкатулке — кодовый замок, который открывается кодовой фразой.
Многие пользователи Git не используют кодовую фразу для защиты своего SSH-ключа. Если такой фразы нет, то её не нужно вводить всякий раз при взаимодействии с удалённым репозиторием.
С другой стороны, применение кодовой фразы усиливает безопасность ключей. Если вы используете эту фразу, ключ будет надёжно защищён в случае несанкционированного доступа к вашему компьютеру.  

### Привязываем SSH-ключ к Github  
```clip < ~/.ssh/id_ed25519.pub``` - копируем содержимое ключа в буфер обмена  
В Github переходим в *Settings/SSH and GPG keys/New SSH key*. В поле *Title* пишем название ключа, в поле *Key type* выбираем *Authentication key*, и в поле *Key* вставляем содержимое буфера обмена. Нажимаем *Add SSH key*.  

```ssh -T git@github.com``` - проверяем правильность ключа.  

### Связываем локальный и удалённый репозиторий  

1. Перейдите на страницу удалённого репозитория, выберите тип SSH и скопируйте URL. Кнопка справа позволит сделать это мгновенно.  
2. Откройте консоль, перейдите в каталог локального репозитория и введите команду git remote add (от англ. remote — «удалённый» и add — «добавить»). Команде необходимо передать два параметра: имя удалённого репозитория и его URL. В качестве имени используйте слово origin. А URL вы скопировали со страницы удалённого репозитория.  
    ```  
    cd my_project  
    git remote add origin git@github.com:%ИМЯ_АККАУНТА%/my_project.git 
    ```
> для вставки значения из буфера обмена в командную строку используйте сочетание клавиш `Ctrl+Shift+V`  

```git remote -v``` - проверяем что репозитории связались  

### Отправление изменений на удалённый репозиторий  
**git push** - команда загружающая содержимое локального репозитория на Github   
В первый раз эту команду нужно вызвать с флагом -u и параметрами origin (имя удалённого репозитория) и main или master (название текущей ветки). Флаг -u свяжет локальную ветку с одноимённой удалённой. Как вы связывали локальный и удалённый репозитории в предыдущем уроке, так же и здесь нужно дополнительно связать ветки.  
    ```git push -u origin main #если команда приведёт к ошибке попробуйте заменить main на master```  

### Файл README.md  
Чтобы другие пользователи, а также потенциальные клиенты или работодатели могли понять, что представляет собой проект, его нужно описать. Такое описание принято указывать в файле README.md (от англ. read — «прочитай» и me — «меня»).  

Как правило, в README.md проекта можно найти следующую информацию:  
1. Название проекта и его краткое описание: кем создан, для чего, какие решает задачи и какие закрывает проблемы.  
2. Технологии, которые применяются в проекте. В чём его отличие от аналогичных.  
3. Документация проекта — подробная инструкция о том, что представляет собой проект.  
4. Планы проекта, если они есть.  

Для оформления содержимого файла README.md используется язык разметки `markdown`.  

####Заголовки, абзацы и перенос  
Заголовки разных уровней создают решётками.  
> # H1 — заголовок первого уровня, самый большой  
> ## H2 — заголовок второго уровня, поменьше  
> ### H3  
> #### H4  
> ##### H5  
> ###### H6 — заголовок шестого уровня, самый маленький   
Можно добавить черту под заголовком или абзацем.  
#### Заголовок 4  

Текст над чертой  

---  

Текст под чертой  


Чтобы сделать разрыв строки, нужно поставить два пробела (в примере ниже они обозначены точками ⋅⋅) или сочетание символов <br>.  

Текст до переноса⋅⋅  
Текст после переноса <br>
Текст после второго переноса    
Чтобы начать новый параграф, в конце предыдущей строки должно стоять два символа переноса. Для этого нужно нажать Enter два раза.  

line  

another line  

Если сделать один перенос строки, как в примере ниже, и не поставить два пробела, текст сольётся в одну строку.  
line
another line  

#### Выделение текста  
Чтобы выделить текст курсивом (*текст*), его заключают в звёздочки (астериски) или нижние подчёркивания.  
Курсив — это *звёздочки* или _подчёркивания_.   
Чтобы выделить текст полужирным шрифтом (**текст**), его окружают двойными звёздочками или двойными нижними подчёркиваниями.  
Полужирный шрифт — двойные **звёздочки** или двойные __подчёркивания__.  
Можно совместить выделение **звёздочки и _подчёркивания_**.   
Чтобы зачеркнуть текст (~~текст~~), его окружают двойными волнистыми линиями — тильдами.  
~~Зачёркнутый текст.~~ 

#### Списки  
Для оформления нумерованного списка достаточно поставить в начало строки цифры с точкой.  
1. Первый пункт нумерованного списка.  
2. Второй пункт.   
Ненумерованный список создаётся звёздочкой с пробелом в начале строки либо дефисом с пробелом.  
* первый пункт ненумерованного списка;  
* второй пункт ненумерованного списка  

- первый пункт ненумерованного списка;  
- второй пункт ненумерованного списка   

#### Ссылки  
Чтобы сделать ссылкой часть текста, его заключают в квадратные скобки, а затем указывают нужный адрес в круглых скобках.  
[Яндекс](https://www.yandex.ru)   
Также можно добавить ссылке тайтл (от англ title — «название», «заголовок»). Тайтл — это всплывающая подсказка, которая появляется при наведении мыши на ссылку. Тайтл нужно заключить в кавычки и указать внутри скобок после адреса.  
[Яндекс](https://www.yandex.ru "Я Yandex!")   

#### Код    
Чтобы оформить текст как код, нужно окружить его тройками косых кавычек — грависов. После первой тройки грависов указывают язык программирования, на котором написан код. В маркдауне есть поддержка синтаксиса почти всех популярных языков и инструментов.  
```bash  
ls - la  
```  
```html  
<h1>А я просто текст</h1>  
```   
Обратите внимание: вторая тройка тройных кавычек стоит на отдельной строке.  

## Навигация по коммитам. Статусы файлов  

### Хеширование  
`Хеширование` (от английского *hash* - "рубить", "крошить", "мешанина") - это способ преобразовать набор данных и получить их *отпечаток*.  

Git хеширует информацию о коммите с помощью алгоритма **SHA-1** (Secure Hash Algorithm) (40 cимволов). Хеш обладает следующими важными свойствами:  
* если хеш получить дважды для одного и того же набора входных данных, то результат будет гарантированно одинаковый;  
* если хоть что-то в исходных данных поменяется (хотя бы один символ), то хеш тоже изменится.  

Хеш является основным идентификатором для коммита. Git хранит таблицу соответствий `хеш -> информация о коммите` в служебных файлах, которые находятся в скрытой папке *.git*.  

### Исследуем лог  
После вызова комманды `git log` появляется список коммитов, который состоит из следующих элементов:  
* строка из цифр и латинских букв после слова commit - это хеш коммита;  
* Author - имя автора и его электронная почта;  
* Date - дата и время создания коммита;  
* в конце находится сообщение коммита.  

Например, описание первого коммита кода самого Git:  
```
commit e83c5163316f89bfbde7d9ab23ca2e25604af290
Author: Linus Torvalds <torvalds@linux-foundation.org>
Date:   Thu Apr 7 15:13:13 2005 -0700

    Initial revision of "git", the information manager from hell
```  

С помощью команды `git log --oneline` можно получить сокращённый лог. Тогда в терминале появятся только первые несколько символов хеша каждого коммита и их комментарии.   
Сокращённый лог полезен, если в репозитории уже много коммитов - например сотни или тысячи. В этом случае можно быстро найти нужный по описанию.  
> Обратите внимание: если выход из просмотра логов не произошёл автоматически, нажмите клавишу `Q` (quit). 

### Файл HEAD  
Файл HEAD - один из служебных файлов папки *.git*. Он указывает на коммит, который был сделан последним (т.е. на самый новый).  
Внутри HEAD ссылка на служебный файл: `refs/heads/main`. Если заглянуть в этот файл, можно увидеть хеш последнего коммита. Когда вы делаете коммит, Git обновляет `refs/heads/main` и записывает в него хеш последнего коммита. Так что, если какой-либо команде нужно передать хеш последнего коммита, то можно вместо него просто написать `HEAD` - Git поймёт, что вы имели в виду последний коммит.  

### Статусы файлов в Git  
Одна из ключевых задач Git - отслеживать изменения файлов в репозитории. Для этого каждый файл помечается каким-либо статусом. Рассмотрим основные:  
* `untracked` - неотслеживаемый. Новые файлы в Git-репозитории помечаются как `untracked`. Git видит что такой файл существует, но не следит за изменениями в нём. У untracked-файла нет предыдущих версий, зафиксированных в коммитах или через команду git add;  
* `staged` - подготовленный. После выполнения команда `git add` файл попадает в ***staging area***, т.е. в список файлов, которые войдут в коммит. В этот момент файл находится в состоянии `staged`.     
> ***Staging area*** также называют *index* или *cache*, а состояние файла `staged` иногда называют *indexed* или *cached*.   
* `tracked` - отслеживаемый. Это противоположность состояния *tracked*. В него попадают файлы, которые уже были зафиксированы с помощью `git commit`, а также файлы которые были добавлены в *staging area* командой `git add`. Т.е. это файлы, в которых Git так или иначе отслеживает изменения;  
* `modified` - означает что Git сравнил содержимое файла с последней сохранённой версией и нашёл отличия. Например, файл был закоммичен и после этого изменён.  
> Для файлов в состоянии `staged` и `modified` обычно не указывают, что они также `tracked`, потому что это состояние подразумевается.  

### Оформление сообщений к коммитам  
#### Инфинитив и императив  
Для сообщений на русском языке часто рекомендуют использовать инфинитивы. Например: `добавить текст для сервиса`, `исправить ошибку #123` и так далее.  
Для сообщений на английском языке рекомендуется использовать повелительное наклонение. Например: `use library mega_lig_300`, `fix edit button` и так далее.  

#### Корпоративный  
Во многих компаниях применяеься Jira - система для организации проектов и задач. У каждой задачи в Jira есть идентификатор, например *LGS-239*. В корпоративном стиле, в начале сообщения обычно указывают Jira-ID, а после - текст сообщения.  

### Conventional Commits  
Стандарт `Conventional Commits` отличается качественной документацией и подробной проработкой. Он подходит для репозиториев с исходным кодом программ. 
Conventional Commits предлагает такой формат коммита: `<type>: <message>`.  
Первая часть `type` - это тип изменений. Таких типов достаточно много. Вот два примера:  
* `feat`(feature) - для новой функциональности;  
* `fix` - для исправленных ошибок.  

#### GitHub стиль  
GitHub можно использовать не только для хранения файлов проекта, но и для ведения списка задач (issue) этого проекта. Если коммит "закрывает" или "решает" какую-то задачу, то в его сообщении удобно указывать ссылку на неё. Для этого в любом месте задачи нужно указать `#<номер задачи>`

```
> new_file = untracked  
> modified | git add = staged  
> git commit | staged = tracked  
```  
