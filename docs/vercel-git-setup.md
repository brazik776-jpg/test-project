# Vercel: авто-деплой при push в main

Чтобы сайт из этого репозитория автоматически выкатывался на Vercel при каждом `git push` в ветку **main**, сделай один раз настройку по шагам ниже.

## 1. Подключи репозиторий к Vercel

1. Зайди на [vercel.com](https://vercel.com) и войди через **GitHub** (логин brazik776-jpg).
2. Нажми **Add New… → Project**.
3. В списке репозиториев выбери **test-project** (или импортируй по ссылке `https://github.com/brazik776-jpg/test-project`).
4. Нажми **Import**.

## 2. Настройки проекта (один раз)

- **Framework Preset:** Other (или None).
- **Root Directory:** оставь пустым (корень репо = корень сайта).
- **Build Command:** оставь пустым (статический сайт, сборка не нужна).
- **Output Directory:** оставь пустым или `.`.
- **Install Command:** можно оставить пустым.

Проверь, что в блоке **Git** указано:

- **Production Branch:** `main` — тогда каждый `git push origin main` будет запускать деплой.

Нажми **Deploy**.

## 3. Что будет дальше

- После первого деплоя Vercel выдаст постоянный URL вида `https://test-project-xxx.vercel.app`.
- Каждый раз, когда ты делаешь `git push origin main`, Vercel сам соберёт и выложит новую версию сайта.
- В проекте уже есть `vercel.json` — по нему Vercel понимает, что это статический сайт без сборки.

## 4. Проверка

Локально:

```bash
git add .
git commit -m "Add Vercel config and docs"
git push origin main
```

Затем открой в браузере дашборд Vercel → свой проект → вкладка **Deployments**: должен появиться новый деплой по последнему коммиту.
