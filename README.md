<div align="center">
  <a id="russian"></a>
  <h1>Добро пожаловать на Project-Euler-CSS</h1>
  <p>Данный проект - это CSS настройки для моего блога
    <a href="(https://github.com/AlexandrAnatoliev/project-euler-blog">Project-Euler-Blog</a>.
    Выделение CSS настроек в отдельный репозиторий, позволяет
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

* [Выделение CSS настроек в отдельный репозиторий](#extracting-css-settings-ru)
* [Задачи](#problems-ru)
* [Отправка Ваших Изменений](#submitting-your-changes-ru)
* [Похожие Проекты](#influences-ru)
* [Контакты](#contact-ru)
* [Требования](#requirements-ru)
* [Список Контрибьютеров](#list-of-contributors-ru)

---

<div align="center">
  <a id="extracting-css-settings-ru"></a>
  <h2>Выделение CSS настроек в отдельный репозиторий</h2>
</div>

<div align="center">
  <h3>Подключение Git-подмодуля репозитория</h3>
</div>
      
Чтобы подключить репозиторий **project-euler-css**, как Git-подмодуль 
репозитория **project-euler-blog** нужно зайти в проект:
```
  project-euler-blog/
  └── index.html
```

И ввести команду:
```
git submodule add https://github.com/AlexandrAnatoliev/project-euler-css.git src/styles
```

Структура после добавления связанного репозитория:
```
  project-euler-blog/
  ├── src/
  │   └── styles/          # Это связанный репозиторий
  │       └── main.css
  ├── index.html
  └── .gitmodules
```

В HTML файл проекта (**index.html**) необходимо добавить ссылку 
на файл внутри подмодуля (**main.css**):
```
<link rel="stylesheet" href="src/styles/main.css">;
```

#### При клонировании репозитория использовать флаг --recursive
```
git clone --recursive https://github.com/AlexandrAnatoliev/project-euler-blog.git
```

#### Или так
```
# Обычное клонирование — папка src/styles будет пустой!
git clone https://github.com/AlexandrAnatoliev/project-euler-blog.git
cd project-euler-blog
ls src/styles/  # пусто или не существует

# Нужно инициализировать и обновить подмодули
git submodule init    # инициализирует подмодули из .gitmodules
git submodule update  # загружает актуальные файлы
```

#### Обновление подмодуля до последней версии
```
# Перейти в папку подмодуля
cd src/styles

# Обновиться до последнего коммита в ветке main
git checkout main
git pull

# Вернуться в основной репозиторий
cd ../..

# Зафиксировать изменение (новую ссылку на коммит)
git add src/styles
git commit -m "Update project-euler-css to latest version"
```

#### Изменение файлов внутри подмодуля
```
# 1. Вносите изменения внутри src/styles
cd src/styles
echo "/* new styles */" >> main.css
git add main.css
git commit -m "Add new styles"
git push  # пушим в репозиторий project-euler-css

# 2. Возвращаетесь в основной репозиторий
cd ../..
git add src/styles  # фиксируем новую ссылку на обновленный коммит
git commit -m "Update submodule reference"
git push  # пушим в основной репозиторий
```
