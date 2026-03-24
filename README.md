<div align="center">
  <a id="russian"></a>
  <h1>Добро пожаловать в Project-Euler-CSS</h1>
  <p>Данный проект - это CSS-настройки для моего блога
    <a href="(https://github.com/AlexandrAnatoliev/project-euler-blog">Project-Euler-Blog</a>.
    Выделение CSS-настроек в отдельный репозиторий, позволяет
    использовать их повторно в разных проектах и избавляет от необходимости
    вносить одни и те же изменения в каждый проект.</p>

  [![EN](https://img.shields.io/badge/English-🇬🇧-blue)](#english)
  [![RU](https://img.shields.io/badge/Русский-🇷🇺-red)](#russian)
  ![Version 0.1.6](https://img.shields.io/badge/Version-0.1.6-orange.svg)
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
* [Клонирование репозитория с Git-подмодулем](#clone-repo-ru-ru)
* [Обновление подмодуля до последней версии](#update-submodule-ru)

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
