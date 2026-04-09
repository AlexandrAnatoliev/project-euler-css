<div align="center">
  <a id="english"></a>
  <h1>Welcome to Project-Euler-CSS</h1>
  <p>This project contains CSS settings for my 
    <a href="https://github.com/AlexandrAnatoliev/project-euler-blog">Project-Euler-Blog</a>.
    Separating the CSS settings into a separate repository allows them to be reused 
    across different projects and eliminates the need to make the same changes in each project.</p>

  [![EN](https://img.shields.io/badge/English-🇬🇧-blue)](#english)
  [![RU](https://img.shields.io/badge/Русский-🇷🇺-red)](#russian)
  ![Version 0.1.14](https://img.shields.io/badge/Version-0.1.14-orange.svg)
  ![Stars](https://img.shields.io/github/stars/AlexandrAnatoliev/project-euler-css.svg?style=flat)
  ![Forks](https://img.shields.io/github/forks/AlexandrAnatoliev/project-euler-css.svg?style=flat)
  [![PRs Welcome](https://img.shields.io/badge/PR:s-welcome-brightgreen.svg)](https://github.com/AlexandrAnatoliev/project-euler-css/pulls)
  [![First Contributors](https://img.shields.io/badge/first-contributors-brightgreen.svg)](https://github.com/AlexandrAnatoliev/project-euler-css/pulls)
  ![GitHub repo size](https://img.shields.io/github/repo-size/AlexandrAnatoliev/project-euler-css)
</div>

  > **Author:** Alexandr Anatoliev

  > **GitHub:** [AlexandrAnatoliev](https://github.com/AlexandrAnatoliev)

---

<div align="center">
  <h2>Navigation</h2>
</div>

* [Adding a Git submodule](#connecting-git-submodule)
* [Cloning a repository with a Git submodule](#clone-repo)
* [Updating a submodule to the latest version](#update-submodule)
* [Contributing](#contributing)
* [Influences](#influences)
* [Contact](#contact)
* [List of Contributors](#list-of-contributors)

---

<div align="center">
  <h1>Separating CSS settings into a separate repository</h1>
</div>

<div align="center">
  <a id="connecting-git-submodule"></a>
  <h2>Adding a Git submodule</h2>
</div>
      
To add the **project-euler-css** repository as a Git submodule to the 
**project-euler-blog** repository, navigate to the project:
```bash
  project-euler-blog/
  └── index.html
```

And run the command:
```bash
git submodule add https://github.com/AlexandrAnatoliev/project-euler-css.git src/styles
```

Structure after adding the linked repository:
```bash
  project-euler-blog/
  ├── src/
  │   └── styles/          
  │       └── main.css
  ├── index.html
  └── .gitmodules
```

In the project's HTML file (**index.html**), 
add a link to the file inside the submodule (**main.css**):
```html
<link rel="stylesheet" href="src/styles/main.css">;
```

---

<div align="center">
  <a id="clone-repo"></a>
  <h2>Cloning a repository with a Git submodule</h2>
</div>

When cloning a repository, you must use the **--recursive flag**:
```bash
git clone --recursive https://github.com/AlexandrAnatoliev/project-euler-blog.git
```

Otherwise, with a regular clone, the src/styles folder will be empty:
```bash
git clone https://github.com/AlexandrAnatoliev/project-euler-blog.git
cd project-euler-blog
ls src/styles/  # пусто или не существует
```

In this case, you need to initialize and update the submodules:
```bash
git submodule init    
git submodule update 
```

---

<div align="center">
  <a id="update-submodule"></a>
  <h2>Updating a submodule to the latest version</h2>
</div>

Navigate to the submodule folder:
```bash
cd src/styles
```

Update to the latest commit in the main branch:
```bash
git checkout main
git pull
```

Return to the main repository:
```bash
cd ../..
```

Commit the change (the new commit reference):
```bash
git add src/styles
git commit -m "Update css to latest version"
```

---

<div align="center">
  <a id="contributing"></a>
  <h2>Contributing</h2>
</div>

<div align="center">
  <h3>Setup Instructions</h3>
</div>

1. Fork this repository by clicking on the "Fork" 
  button at the top-right corner of this page. 
  This creates a copy of the repository in your 
  GitHub account.

2. Clone your forked repository by clicking the 
  "Code" button:

That will open this small window:

After that you can copy and paste the URL to 
  your local machine with the command:

```bash
git clone https://github.com/<your-username>/project-euler-css.git
```

3. Navigate to your project folder:

```bash
cd project-euler-css
```

4. Add a reference to the original repository for 
  future updates:

```bash
git remote add upstream https://github.com/AlexandrAnatoliev/project-euler-css.git
```

(Remember to keep here the original repository URL, 
  not your forked one, so the username in this 
  needs to be `AlexandrAnatoliev`, not your 
  own username.)

5. Check the remotes for your local repository:

```bash
git remote -v
```

You should now see the origin (added automatically
when cloning) and upstream remotes listed.

``` 
origin  https://github.com/<your-username>/project-euler-css.git (fetch)
origin  https://github.com/<your-username>/project-euler-css.git (push)
upstream        https://github.com/AlexandrAnatoliev/project-euler-css.git (fetch)
upstream        https://github.com/AlexandrAnatoliev/project-euler-css.git (push)
```

6. Pull from the upstream repository 
to your master branch to keep it in sync with 
the main project:

```bash
git pull upstream master
```

7. Create a new branch with the command:

```bash
git switch -c fix-issue
```

Now you are ready to start working on the issues!
Remember every once in a while to pull from the 
upstream repository to keep your local repository 
up to date with the main project.

_Note: I recommend to always create a new branch 
with each Issue you solve! Otherwise the pull 
requests will get too large and there could be 
possible merge conflicts._

---

<div align="center">
  <h3>Submitting Your Changes</h3>
</div>

Once you've made the necessary changes requested 
in the issue, you're ready to submit your changes!

1. Stage your changes with the command:

```bash
git add files-that-you-changed
```

2. Commit your changes with the command:

```bash
git commit -m "Fixed issue"
```

3. Push your changes to your forked repository 
with the command:

```bash
git push origin fix-issue
```

Once you've pushed your changes to GitHub, 
you're ready to create a pull request. 
Go to your forked repository on GitHub.

- You should see message "fix-issue had recent pushes" 
(or whatever your branch name is) and button 
"Compare & pull request" next to it.

- Click the "Compare & pull request" button 
to proceed to the pull request page of the original 
project-euler-css repository.

- Fill in the title and description boxes 
with details about the problem and 
how you got it to work. You can also add some 
additional information such as screenshots, 
if you want.

- Finally, click "Create pull request" to finish 
creating the pull request.

Congratulations on making your open source 
contribution on GitHub!

Sit back and wait for feedback 
on the pull request. If everything is 
fine, you should get the pull request merged. 
If not, you will be requested to make changes 
to your code.

Remember to wait for me to review your pull 
request, do not close it yourself.
If you are asked to make changes, you can do 
so by committing them to the same branch, 
there is no need to close the current Pull 
Request and open a new one.

---

<div align="center">
  <a id="influences"></a>
  <h2>Influences</h2>
</div>

This project was inspired by a number of 
fantastic resources designed to help newcomers 
make their first contributions to open source. 
In particular, I would like to acknowledge:

- [Fork, Commit, Merge](https://github.com/fork-commit-merge/fork-commit-merge): 
A project designed to help you familiarize 
yourself with the open source contribution 
workflow on GitHub, as well as to help you learn 
the basics of programming with different languages, 
libraries and frameworks.

- [Polyglot-Calculators](https://github.com/B3rou/Polyglot-Calculators): 
Polyglot-Calculators is a community-driven, modern hybrid project that 
showcases how mathematical calculators and algorithms are implemented across 
different programming languages.

I highly recommend checking out these projects 
if you want to learn more about contributing 
to open source!

---

<div align="center">
  <a id="contact"></a>
  <h2>Contact</h2>
</div>

For any queries, feel free to open an issue,
write to [Discussions](https://github.com/AlexandrAnatoliev/project-euler-css/discussions/10)
or reach out to me at per-1986@list.ru.

---

<div align="center">
  <a id="list-of-contributors"></a>
  <h2>List of Contributors</h2>
</div>

Massive thanks to all the fine individuals 
who contributed to this project!

<a href="https://github.com/AlexandrAnatoliev"><img src="https://images.weserv.nl/?url=https://avatars.githubusercontent.com/u/116306656?v=4&h=300&w=300&fit=cover&mask=circle&maxage=7d" width="80px"/></a>

---

<div align="center">
  <a id="russian"></a>
  <h1>Добро пожаловать в Project-Euler-CSS</h1>
  <p>Данный проект - это CSS-настройки для моего блога
    <a href="https://github.com/AlexandrAnatoliev/project-euler-blog">Project-Euler-Blog</a>.
    Выделение CSS-настроек в отдельный репозиторий позволяет
    использовать их повторно в разных проектах и избавляет от необходимости
    вносить одни и те же изменения в каждый проект.</p>

  [![EN](https://img.shields.io/badge/English-🇬🇧-blue)](#english)
  [![RU](https://img.shields.io/badge/Русский-🇷🇺-red)](#russian)
  ![Version 0.1.14](https://img.shields.io/badge/Version-0.1.14-orange.svg)
  ![Stars](https://img.shields.io/github/stars/AlexandrAnatoliev/project-euler-css.svg?style=flat)
  ![Forks](https://img.shields.io/github/forks/AlexandrAnatoliev/project-euler-css.svg?style=flat)
  [![PRs Welcome](https://img.shields.io/badge/PR:s-welcome-brightgreen.svg)](https://github.com/AlexandrAnatoliev/project-euler-css/pulls)
  [![First Contributors](https://img.shields.io/badge/first-contributors-brightgreen.svg)](https://github.com/AlexandrAnatoliev/project-euler-css/pulls)
  ![GitHub repo size](https://img.shields.io/github/repo-size/AlexandrAnatoliev/project-euler-css)
</div>

  > **Author:** Alexandr Anatoliev

  > **GitHub:** [AlexandrAnatoliev](https://github.com/AlexandrAnatoliev)

---

<div align="center">
  <h2>Навигация</h2>
</div>

* [Подключение Git-подмодуля репозитория](#connecting-git-submodule-ru)
* [Клонирование репозитория с Git-подмодулем](#clone-repo-ru)
* [Обновление подмодуля до последней версии](#update-submodule-ru)
* [Для контрибьютеров](#contributing-ru)
* [Похожие проекты](#influences-ru)
* [Контакты](#contact-ru)
* [Список контрибьютеров](#list-of-contributors-ru)

---

<div align="center">
  <h1>Выделение CSS настроек в отдельный репозиторий</h1>
</div>

<div align="center">
  <a id="connecting-git-submodule-ru"></a>
  <h2>Подключение Git-подмодуля репозитория</h2>
</div>
      
Чтобы подключить репозиторий **project-euler-css**, как Git-подмодуль 
репозитория **project-euler-blog**, нужно зайти в проект:
```bash
  project-euler-blog/
  └── index.html
```

И ввести команду:
```bash
git submodule add https://github.com/AlexandrAnatoliev/project-euler-css.git src/styles
```

Структура после добавления связанного репозитория:
```bash
  project-euler-blog/
  ├── src/
  │   └── styles/          # Это связанный репозиторий
  │       └── main.css
  ├── index.html
  └── .gitmodules
```

В HTML-файл проекта (**index.html**) необходимо добавить ссылку 
на файл внутри подмодуля (**main.css**):
```html
<link rel="stylesheet" href="src/styles/main.css">;
```

---

<div align="center">
  <a id="clone-repo-ru"></a>
  <h2>Клонирование репозитория с Git-подмодулем</h2>
</div>

При клонировании репозитория необходимо использовать флаг **--recursive**:
```bash
git clone --recursive https://github.com/AlexandrAnatoliev/project-euler-blog.git
```

Иначе, при обычном клонировании - папка src/styles будет пустой:
```bash
git clone https://github.com/AlexandrAnatoliev/project-euler-blog.git
cd project-euler-blog
ls src/styles/  # пусто или не существует
```

В этом случае нужно инициализировать и обновить подмодули:
```bash
git submodule init    
git submodule update 
```

---

<div align="center">
  <a id="update-submodule-ru"></a>
  <h2>Обновление подмодуля до последней версии</h2>
</div>

Перейти в папку подмодуля:
```bash
cd src/styles
```

Обновиться до последнего коммита в ветке main:
```bash
git checkout main
git pull
```

Вернуться в основной репозиторий:
```bash
cd ../..
```

Зафиксировать изменение (новую ссылку на коммит):
```bash
git add src/styles
git commit -m "Update css to latest version"
```

---

<div align="center">
  <a id="contributing-ru"></a>
  <h2>Для контрибьютеров</h2>
</div>

<div align="center">
  <h3>Инструкции по Установке</h3>
</div>

1. Сделайте "форк" этого репозитория нажатием 
  кнопки "Fork" в правом верхнем углу страницы.
  Это создаст копию репозитория на Вашем GitHub 
  аккаунте.

2. Клонируйте Ваш "форкнутый" репозиторий нажатием
  кнопки "Code":

Откроется маленькое окно: 

Скопируйте из него URL и выполните на своем 
компьютере команду:

```bash
git clone https://github.com/<your-username>/project-euler-css.git
```

3. Перейдите в папку с проектом:

```bash
cd project-euler-css
```

4. Добавьте ссылку на оригинальный репозиторий
  для будущих обновлений:

```bash
git remote add upstream https://github.com/AlexandrAnatoliev/project-euler-css.git
```

(Напомню, здесь должен быть URL оригинального
репозитория, а не "форкнутого" Вами, так что
username в нем должно быть `AlexandrAnatoliev`,
а не Ваш собственный username.)

5. Проверьте ремоуты для своего репозитория:

```bash
git remote -v
```

Вы должны увидеть origin (создается автоматически
при клонировании) и upstream ремоуты: 

``` 
origin  https://github.com/<your-username>/project-euler-css.git (fetch)
origin  https://github.com/<your-username>/project-euler-css.git (push)
upstream        https://github.com/AlexandrAnatoliev/project-euler-css.git (fetch)
upstream        https://github.com/AlexandrAnatoliev/project-euler-css.git (push)
```

6. Выполните pull из upstream репозитория в Вашу
  master ветку, чтобы синхронизировать ее с основным
  проектом:

```bash
git pull upstream master
```

7. Создайте новую ветку командой:

```bash
git switch -c fix-issue
```

Сейчас вы готовы начать работать с issue!
Помните, каждый раз сначала делать pull
из upstream репозитория, чтобы держать содержимое
Вашего локального репозитория в соответствии
с главным проектом.

_Примечание: Рекомендую всегда создавать новую
ветвь для каждого issue, который вы выполняете!
Иначе pull request будут слишком большими и 
возможно возникнут конфликты слияния._

---

<div align="center">
  <a id="submitting-your-changes-ru"></a>
  <h2>Отправка Ваших изменений</h2>
</div>

После того как вы решили проблему, вы готовы отправить 
изменения! 

1. Добавьте Ваши изменения в отслеживание:

```bash
git add файлы-которые-вы-изменили
```

2. Сделайте коммит:

```bash
git commit -m "Fixed issue"
```

3. Отправить изменения в Ваш "форкнутый" репозиторий:

```bash
git push origin fix-issue
```

После того как вы отправили Ваши изменения на 
GitHub, вы готовы создать pull request.
Перейдите на Ваш "форк" репозитория на GitHub.

- Вы увидите надпись "fix-issue had recent pushes" 
(или как Ваша ветка называется) и кнопку 
"Compare & pull request" на ней.

- Нажмите кнопку "Compare & pull request" и перейдете
на страницу pull request оригинального репозитория
проекта project-euler.

- Заполните поля title и description подробностями
о задаче и Вашем ее решении. Вы можете также добавить
иную информацию, такую как скриншоты, если хотите.

- В конце нажмите кнопку "Create pull request" 
чтобы закончить создание pull request.

Поздравляю, вы сделали свой вклад в open 
source на GitHub!

Можете расслабиться и подождать пока не сделают
ревью Вашего кода. Если все хорошо, Ваш pull request
вольют в основную ветку. Если нет, Вам будет 
предложено внести изменения в Ваш код.

Помните, что нужно подождать ревью Вашего pull 
request, не закрывайте его сами.
Если Вас просят сделать изменения, вы можете
коммитить их в ту же самую ветвь, не нужно
закрывать текущий pull request и открывать новый.

---

<div align="center">
  <a id="influences-ru"></a>
  <h2>Похожие проекты</h2>
</div>

Этот проект вдохновлялся несколькими хорошими
проектами, созданными с целью помочь новичкам
сделать свой первый вклад в open source.

- [Fork, Commit, Merge](https://github.com/fork-commit-merge/fork-commit-merge): 
Проект созданный чтобы помочь Вам познакомиться
с процессом вклада в open source на GitHub,
а также помочь освоить базы программирования на
различных языках, библиотеках и фреймворках.

- [Polyglot-Calculators](https://github.com/B3rou/Polyglot-Calculators): 
Polyglot-Calculators управляемый сообществом современный гибридный проект, 
который демонстрирует, как математические калькуляторы  и алгоритмы реализуются
на разных языках программирования.

Я очень рекомендую посмотреть эти проекты!

---

<div align="center">
  <a id="contact-ru"></a>
  <h2>Контакты</h2>
</div>

Столкнувшись с затруднениями, не стесняйтесь
открыть issue, написать в
[Discussions](https://github.com/AlexandrAnatoliev/project-euler-css/discussions/10)
или мне на почту per-1986@list.ru.

---

<div align="center">
  <a id="list-of-contributors-ru"></a>
  <h2>Список Контрибьютеров</h2>
</div>

Огромное спасибо всем, кто контрибьютил
в этот проект!

<a href="https://github.com/AlexandrAnatoliev"><img src="https://images.weserv.nl/?url=https://avatars.githubusercontent.com/u/116306656?v=4&h=300&w=300&fit=cover&mask=circle&maxage=7d" width="80px"/></a>

