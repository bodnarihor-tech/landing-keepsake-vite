# Keepsake — Digital & Branding Agency

Лендінг агентства **Keepsake**, реалізований на базі **Vite**, **Pug** та модульного **SCSS**.

- **Демо (GitHub Pages):** [https://bodnarihor-tech.github.io/landing-keepsake-vite/]
- **Репозиторій:** [https://github.com/bodnarihor-tech/landing-keepsake-vite]

---

## 🔧 Вимоги до середовища

Для роботи з проєктом потрібен **Node.js** (рекомендовано версії 20+) та **npm**.

```bash
node -v
npm -v
```

---

## 🚀 Команди проєкту

```bash
# Встановлення залежностей
npm install

# Запуск сервера розробки
npm run dev

# Збірка продакшн-версії у dist/
npm run build

# Локальний перегляд зібраної версії з dist/
npm run preview

# Перевірка стилів (Stylelint) та форматування (Prettier)
npm run lint

# Окремі перевірки лінтерів
npm run lint:styles
npm run lint:format

# Автоформатування коду через Prettier
npm run format
```

---

## 🧩 Архітектура проєкту

```text
src/
 ├─ assets/              # вихідні зображення та медіаресурси
 ├─ components/          # Pug-компоненти (header, navigation, content, footer, logo)
 ├─ data/                # дані для шаблонів (data.pug)
 ├─ includes/            # head, meta, fonts
 ├─ layouts/             # базовий layout сторінки
 ├─ pages/               # сторінки (index.pug)
 ├─ styles/              # модульний SCSS
 │   ├─ base/            # _reset.scss, _typography.scss, index.scss
 │   ├─ components/      # _button.scss, _header.scss, _footer.scss, index.scss
 │   ├─ layout/          # _grid.scss, _sections.scss, index.scss
 │   ├─ utils/           # _variables.scss, _mixins.scss, index.scss
 │   └─ main.scss        # точка входу стилів
 └─ vite.config.js       # конфігурація Vite та плагінів
```

### Особливості Pug та SCSS

- **Pug:** компонентна декомпозиція (`include`), винесення даних у `src/data/data.pug`, доступність форм (зокрема `autocomplete` для поля email у формі підписки).
- **Модульний SCSS:** підключення через `@use` / `@forward` та індексні файли `index.scss` замість застарілого `@import`.
- **Токени та міксини:** використання `sass:map` для карт брейкпоінтів, `sass:math` для обчислень, генерація CSS custom properties у `:root` через `@each` та адаптивний міксин `mq($bp)` у `_mixins.scss`.

---

## 🛠 Інструменти, якість коду та Browserslist

- **Збірка та деплой:** Vite, PostCSS, `sharp`, GitHub Actions (автоматичний білд і публікація на GitHub Pages).
- **Якість коду та хуки:** Stylelint, Prettier, Husky та `lint-staged` для перевірки перед комітом.
- **Browserslist:** цільова підтримка актуальних браузерів згідно з конфігурацією проєкту (`package.json` / `.browserslistrc`).

---

## 📊 Оптимізація розмірів

| Ресурс / файл               | До оптимізації | Після оптимізації (`dist/`)  | Примітка                  |
| :-------------------------- | :------------: | :--------------------------: | :------------------------ |
| `work-02` (`.webp`)         |       —        |          `7.57 kB`           | Збірка Vite + `sharp`     |
| `work-04` (`.webp`)         |       —        |          `4.17 kB`           | Збірка Vite + `sharp`     |
| `work-05` (`.webp`)         |       —        |          `4.48 kB`           | Збірка Vite + `sharp`     |
| `work-07` (`.webp`)         |       —        |          `4.83 kB`           | Збірка Vite + `sharp`     |
| `work-08` (`.webp`)         |       —        |          `8.02 kB`           | Збірка Vite + `sharp`     |
| `work-09` (`.webp`)         |       —        |          `7.50 kB`           | Збірка Vite + `sharp`     |
| Основний CSS (`main-*.css`) |       —        | `16.61 kB` (`3.36 kB` gzip)  | Компіляція SCSS + PostCSS |
| Сторінка (`index.pug.html`) |       —        | `33.83 kB` (`14.60 kB` gzip) | Рендер Pug через Vite     |
