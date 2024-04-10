# Айоу этот проект нужен для того, чтобы помочь тебе разобраться с git'ом, братик.

## Что такое git?
   -  Управление версиями: Git позволяет сохранять различные версии проекта, так что можно вернуться к предыдущим состояниям кода или увидеть, что было изменено и когда.
   -  Сотрудничество: Множество разработчиков могут работать над одним проектом одновременно, внося изменения в различные фрагменты кода без конфликтов.
   -  Отслеживание изменений: Git предоставляет детальную историю изменений кода, указывая автора и описание каждой правки.
   -  Рабочие процессы: Различные рабочие процессы, такие как feature branch workflow, gitflow workflow, fork workflow, поддерживаются Git и помогают командам оптимизировать процесс разработки.
   -  Отказоустойчивость: Благодаря распределённой архитектуре, каждая копия проекта на компьютере разработчика является полным репозиторием с историей изменений, что обеспечивает защиту от потери данных.
   -  Интеграция с инструментами разработки: Git хорошо интегрируется с множеством систем сборки, непрерывной интеграции и другим инструментарием, что упрощает автоматизацию процесса разработки и тестирования.

## 1. Скачай git на свой ПК

   Для этого просто на сайт, зайди и скачай.
   https://git-scm-clone.vercel.app/pages/download.html
   Ну и скачай gitbash для общения через него. Это типо консоль.

## 2. Настройка .gitconfig

   Сейчас вы работаете в одиночку, но в дальнейшем вам может понадобиться использовать Git в команде. Чтобы участникам проекта было понятно, кто и какие изменения вносил, нужно представиться и указать имя пользователя и адрес электронной почты.
   Вы можете указать любую электронную почту и любое имя. Сделать это можно с помощью команды git config (от англ. configuration — «конфигурация», «настройка») с ключом --global (англ. «глобальный»). При этом не имеет значения, в какой директории вы находитесь прямо сейчас: вызов git config --global сработает везде.
   В качестве значения user.name нужно указать своё имя или никнейм. Для настройки параметра user.email указывают электронную почту.

```bash
$ git config --global user.name "User Namovich" 
# имя или ник нужно написать латиницей и в кавычках

$ git config --global user.email username@yandex.ru
# здесь нужно указать свой настоящий email
```

   Все глобальные настройки Git хранит в файле .gitconfig в домашней директории. Команда запишет в этот файл указанные имя и почту. Чтобы убедиться в этом, можно вызвать команду для чтения файлов.

```bash
$ cat ~/.gitconfig
```

   Или можете сделать то же самое командой.

```bash
$ git config --list
```

## 3. Инициализируем репозиторий
   
   для этого нужно перейти в нужную вам папку и создать репозиторий командами.

```bash
$ cd ~/dev/first-project # перешли в нужную папку

$ git init # создали репозиторий 
```
   В вашей папке создастся подпапка с названием ".git" в которой будут будет храниться вся служебная информация
   Если же вы по ошибкке Инициализировали репозиторий не там, где хотели, то можете просто "разгитить" удалив подпапку ".git"командой.

```bash
$ cd <папка с репозиторием> # перешли в папку

$ rm -rf .git # удалили подпапку .git
```

   Команда rm происходит от аннглийского "remove" что означает "удалить". А вот с флагами -r и -f поинтереснее:
   - ключ -r (от англ. recursive — «рекурсивно») позволяет удалять папки вместе с их содержимым;
   - ключ -f (от англ. force — «заставить») избавит вас от вопросов вроде «Вы точно хотите удалить этот файл? А этот? И этот тоже?».

   Чтобы проверить состояние репозитория - используйте команду ```bash git status ```
   Команда git status выведет:
- название текущей ветки: On branch master или On branch main;
- сообщение о том, что в репозитории ещё нет коммитов: No commits yet;
- сообщение, которое говорит: «чтобы что-нибудь закоммитить (то есть зафиксировать), нужно сначала это создать» — nothing to commit (create/copy files and use "git add" to track).

## Регистрация на GitHub

###Инструкция по регистрации

1. В правом верхнем углу главной страницы GitHub нажмите на Sign up (англ. «зарегистрироваться»).

2. На экране будут последовательно появляться поля для ввода.

  2.1. Введите адрес электронной почты (англ. Enter your email).
  2.2. Придумайте пароль (англ. Create a password).
  2.3. Введите имя пользователя (англ. Enter a username).

3. Платформа спросит, хотите ли вы получать на почту рассылку с обновлениями и новостями (англ. Would you like to receive product updates and announcements via email?). Введите y, если хотите получать рассылку, или n, если не хотите.

4. Нажмите кнопку Continue (англ. «продолжить»).

5. GitHub предложит вам пройти капчу. Сделайте это.

6. После прохождения капчи нажмите <b>Create account<\b> (англ. «создать аккаунт»).

7. Введите короткий код, который будет отправлен на указанный вами почтовый адрес.

   Поздравляем! Вы успешно зарегистрировались на крупнейшем веб-хостинге проектов GitHub. Теперь у вас есть возможность работать бок о бок с миллионами профессионалов по всему миру, обмениваться идеями и развиваться.

## Создаём удалённый репозиторий

### Инструкция по созданию репозитория на GitHub

1. Зайдите в свой профиль по ссылке https://github.com/username, где username — имя, которое вы указали при регистрации.

   Эта страница — презентация вас и ваших проектов. Её видят другие пользователи. Надпись You don't have any public repositories yet (англ. «у вас пока нет публичных репозиториев») сообщает, что пока у вас нет проектов.

2. Создайте репозиторий. Для этого перейдите на вкладку Repositories (англ. «репозитории»), а затем нажмите на зелёную кнопку New (англ. «новый») справа.

3. Открылось окно создания нового репозитория. Назовите его first-project. Название удалённого репозитория необязательно должно совпадать с именем папки проекта у вас на компьютере. Но чтобы не путаться, будем называть их одинаково.

   Другие поля вам пока не понадобятся. Смело нажимайте на зелёную кнопку Create repository (англ. «создать репозиторий») внизу.
-------------------------
   Готово! Удалённый репозиторий создан. Страница с ним открывается автоматически.
-------------------------
   Осталось связать удалённый репозиторий с локальным, который уже есть на вашем компьютере. GitHub предоставляет для этого инструкцию (пункт …or push an existing repository from the command line).
   Но прежде, чтобы упростить работу с GitHub и сделать её более безопасной, вы научитесь генерировать SSH-ключи (от англ. Secure Shell — «безопасная оболочка»). Об этом в следующем уроке.

## Что такое SSH. Генерируем SSH-ключ

### Что такое SSH

   Когда компьютеры обмениваются данными в сети, они следуют сетевым протоколам (англ. network protocols) — правилам обмена данными между компьютерами.
   Один из наиболее распространённых сетевых протоколов — SSH (от англ. Secure Shell Protocol). Он обеспечивает безопасный обмен данными в сети. С помощью этого протокола можно получать данные с удалённого компьютера или отправлять их на него. Трафик шифруется, поэтому протокол безопасен.
   SSH использует пару ключей для обеспечения безопасности — публичный и приватный: 

- Приватный ключ (англ. private key) хранится только на вашем компьютере и не должен передаваться кому-либо ещё. Он используется для расшифровки данных.
- Публичный ключ (англ. public key) доступен всем и используется для шифрования данных. Они могут быть расшифрованы парным приватным ключом.

   Только вы можете расшифровать данные с помощью приватного ключа, но любой владелец публичного ключа может их для вас зашифровать. Эти два ключа связаны и образуют SSH-пару. В будущем вы наверняка будете использовать их для взаимодействия с GitHub и другими удалёнными серверами.

### Проверка наличия SSH-ключа

   Прежде чем генерировать SSH-ключи, убедитесь, что у вас их ещё нет. По умолчанию директория с SSH-ключами находится в домашней директории пользователя. Перейдите в неё.
   Обычно SSH-ключи находятся в директории .ssh/. Проверить наличие этой директории и файлов в ней можно с помощью следующей команды.

```bash
$ cd ~ && ls -la .ssh/ # зашли в домашнюю директорию и вывели список созданных ключей 
```
   Если папка пуста - все хорошо. Если нет - удалите все файлы.

###Инструкция по генерации SSH-ключа

1. Для генерации SSH-пары можно использовать программу ssh-keygen. Откройте терминал и введите следующую команду.

```bash $ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub" ```

   Используйте электронную почту, к которой привязан ваш GitHub-аккаунт.
   Если вы видите сообщение об ошибке, то, скорее всего, ваша система не поддерживает алгоритм шифрования ed25519. Ничего страшного: используйте другой алгоритм.

```bash $ ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан ваш аккаунт на GitHub" ```

2. Укажите место хранения ключей. Простой вариант — сделать домашний каталог пользователя путём по умолчанию. Для этого нажмите Enter.

```bash > Enter a file in which to save the key (C:\Users\<имя_пользователя>\.ssh\):[Press enter] ```

   Теперь в указанной директории появится пара ключей.

3. Программа запросит кодовую фразу (англ. passphrase) для доступа к SSH-ключу. Вы можете оставить поле пустым. Для этого нажмите Enter, а затем ещё раз Enter для подтверждения.

```bash > Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again] ```

4. Готово! Теперь осталось проверить, что ключи действительно сгенерировались. Для этого вызовите эту команду.

```bash ls -a ~/.ssh ```

На экране должны появиться два файла — один с расширением .pub, другой — без. Файл в .pub — публичный, им можно делиться с веб-сайтами или коллегами. Файл без расширения .pub — приватный. Ни в коем случае не передавайте его никому! 

## Привязываем SSH-ключ к GitHub

### Инструкция по связыванию SSH-ключа и GitHub-аккаунта

1. После выполнения команды ssh-keygen из предыдущего урока в директории ~/.ssh будет создано два файла — id_ed25519 и id_ed25519.pub (или id_rsa и id_rsa.pub — в зависимости от того, какой алгоритм вы использовали):
- id_ed25519/id_rsa — приватный ключ (файл без .pub в конце). Ни в коем случае не копируйте его и не делитесь им.
- id_ed25519.pub/id_rsa.pub — публичный ключ (на это указывает расширение .pub).
   Скопируйте содержимое файла с публичным ключом в буфер обмена.
   Для этого выведите содержимое файла с помощью cat ~/.ssh/id_rsa.pub или cat ~/.ssh/id_ed25519.pub и скопируйте вывод в буфер обмена из консоли.

2. Перейдите на GitHub и выберите пункт Settings (англ. «настройки») в меню аккаунта.

3. В меню слева нажмите на пункт SSH and GPG keys.

4. В открывшейся вкладке выберите New SSH key (англ. «новый SSH-ключ»).

5. В поле Title (англ. «заголовок») напишите название ключа. Например, Personal key (англ. «личный ключ»).

6. В поле Key type (англ. «тип ключа») должно быть Authentication Key (англ. «ключ аутентификации»).

7. В поле Key скопируйте ваш ключ из буфера обмена.

8. Нажмите на кнопку Add SSH key (англ. «добавить SSH-ключ»).

9. Проверьте правильность ключа с помощью следующей команды.

```bash $ ssh -T git@github.com ```

   Если это первый раз, когда вы используете Git, чтобы поделиться проектом на GitHub, появится похожее предупреждение.

```bash The authenticity of host 'github.com (140.82.121.4)' can't be established. ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU. This key is not known by any other names. Are you sure you want to continue connecting (yes/no/[fingerprint])? ```

   Это предупреждение сообщает, что вы никогда не соединялись с сервером GitHub. Поэтому Git не может гарантировать, что сервер является тем, за кого он себя выдаёт.
Для подтверждения подлинности сервер генерирует и публикует ключи SHA256. Вы можете проверить ключи GitHub по этой ссылке. Если ключ в предупреждении совпадает с тем, что вы видите на сайте, значит, сервер является действительным. Введите yes, чтобы продолжить. Вы увидите приветствие на экране.

```bash Hi %ВАШ_АККАУНТ%! You've successfully authenticated, but GitHub does not provide shell access. ```

<b>Ура: теперь ваш ключ привязан к GitHub! Если вы установили кодовую фразу для SSH-ключа, её нужно будет вводить для работы с репозиторием.<\b>

## Связываем локальный и удалённый репозитории

### Привязать удалённый репозиторий к локальному — git remote add

   Перейдите на страницу удалённого репозитория, выберите тип SSH и скопируйте URL. Кнопка справа позволит сделать это мгновенно.

   Откройте консоль, перейдите в каталог локального репозитория и введите команду git remote add (от англ. remote — «удалённый» и add — «добавить»).

```bash $ cd ~/dev/first-project
$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git ```

### Убедиться, что репозитории связаны, — git remote -v

   Отлично: вы связали локальный репозиторий с удалённым. Осталось убедиться, что всё работает, с помощью следующей команды.

```bash $ git remote -v
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (fetch)
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (push) ```

## Синхронизируем локальный и удалённый репозитории

### Отправить изменения на удалённый репозиторий — git push

   Вы уже прошли весь «цикл коммита»: подготовили файлы с помощью git add, закоммитили их с комментарием командой git commit -m. Осталось загрузить содержимое локального репозитория на GitHub. За это отвечает команда git push (от англ. push — «толкать»).
   В первый раз эту команду нужно вызвать с флагом -u и параметрами origin (имя удалённого репозитория) и main или master (название текущей ветки). Флаг -u свяжет локальную ветку с одноимённой удалённой. Как вы связывали локальный и удалённый репозитории в предыдущем уроке, так же и здесь нужно дополнительно связать ветки.

```bash $ git push -u origin main # Если команда приведёт к ошибке, попробуйте 
                          # заменить main на master. ```


   При взаимодействии с удалёнными репозиториями Git выводит в консоль отладочную информацию: количество объектов (файлов), которые отправляются на сервер, информацию о прогрессе сжатия и записи и так далее.
   Если вы указывали кодовую фразу при настройке SSH-ключей, её нужно будет ввести.
   Зайдите в репозиторий first-project на GitHub. Вы увидите, что в репозитории появились файлы с изменениями





















