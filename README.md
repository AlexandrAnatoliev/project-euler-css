<div align="center">
  <a id="english"></a>
  <h1>Project-Euler-CSS</h1>

  [![EN](https://img.shields.io/badge/English-🇬🇧-blue)](#english)
  [![RU](https://img.shields.io/badge/Русский-🇷🇺-red)](#russian)
  ![Version 0.1.2](https://img.shields.io/badge/Version-0.1.2-orange.svg)
  ![Stars](https://img.shields.io/github/stars/AlexandrAnatoliev/project-euler-css.svg?style=flat)
  ![Forks](https://img.shields.io/github/forks/AlexandrAnatoliev/project-euler-css.svg?style=flat)
  [![PRs Welcome](https://img.shields.io/badge/PR:s-welcome-brightgreen.svg)](https://github.com/AlexandrAnatoliev/project-euler-css/pulls)
  [![First Contributors](https://img.shields.io/badge/first-contributors-brightgreen.svg)](https://github.com/AlexandrAnatoliev/project-euler-css/pulls)
  ![GitHub repo size](https://img.shields.io/github/repo-size/AlexandrAnatoliev/project-euler-css)
</div>

  > **Author:** Alexandr Anatoliev

  > **GitHub:** [AlexandrAnatoliev](https://github.com/AlexandrAnatoliev)

---
 

## Выделение CSS настроек в отдельный репозиторий

#### Подключить репозиторий как Git-подмодуль в основном репозитории:
```
git submodule add https://github.com/AlexandrAnatoliev/project-euler-css.git src/styles
```

```
# Структура после добавления
project-euler-website/
├── src/
│   ├── styles/          # Это связанный репозиторий
│   │   └── main.css
│   └── index.html
└── .gitmodules
```

#### Добавить в html файл
```
<!-- Относительная ссылка на файл внутри подмодуля -->
<link rel="stylesheet" href="/src/styles/main.css">
```

#### При клонировании репозитория использовать флаг --recursive
```
git clone --recursive https://github.com/AlexandrAnatoliev/project-euler-website.git
```

#### Или так
```
# Обычное клонирование — папка src/styles будет пустой!
git clone https://github.com/AlexandrAnatoliev/project-euler-website.git
cd project-euler-website
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
