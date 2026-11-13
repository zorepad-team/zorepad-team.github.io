# Зорепад

Сайт команди Зорепад: переклади ретро ігор українською. Jekyll + GitHub Pages, без JS.

## Локальний запуск

```bash
bundle install
bundle exec jekyll serve
```

## Структура

- `_translations/<платформа>/<slug>.md` — переклад (front matter + опис у тілі)
- `assets/translations/<платформа>/<slug>/` — `main.png` (титульний екран) і скріншоти `1.png`, `2.png`...
- `_data/platforms.yml` — платформи для фільтра
- `_data/navigation.yml` — пункти меню (новини, ромхаки додаються тут)
- `assets/css/main.css` — усі стилі, `assets/fonts/` — шрифт назви

## Додати переклад

1. Покладіть зображення в `assets/translations/<платформа>/<slug>/`.
2. Створіть `_translations/<платформа>/<slug>.md`:

```yaml
---
title: Назва - український переклад   # заголовок сторінки
name: Назва                           # коротка назва для списку
platform: famicom                     # slug з _data/platforms.yml
date: 2026-11-03                      # дата релізу, за нею сортується список
download: https://...
screenshots: [1.png, 2.png, 3.png]
---

Опис у Markdown.
```

Список сортується за `date`, нові зверху.

## Додати платформу

1. Додайте запис у `_data/platforms.yml`.
2. Скопіюйте `translations/famicom/index.html` у `translations/<slug>/index.html` і змініть `title` та `platform`.
