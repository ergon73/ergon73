# 🔧 Альтернативные варианты GitHub Stats

Если GitHub Stats не отображаются, вот запасные варианты:

## Вариант 1: Только Streak + Badges (самый надёжный)

```markdown
### 📊 GitHub Активность

<div align="center">

![Profile Views](https://komarev.com/ghpvc/?username=ergon73&color=brightgreen&style=flat-square)
![GitHub Followers](https://img.shields.io/github/followers/ergon73?style=flat-square&color=blue)
![Total Stars](https://img.shields.io/github/stars/ergon73?style=flat-square&color=yellow)
![Repos](https://img.shields.io/badge/repos-64-orange?style=flat-square)

![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=ergon73&theme=tokyonight)

</div>
```

## Вариант 2: Простая таблица со статистикой

```markdown
### 📊 Статистика

| Метрика | Значение |
|---------|----------|
| 📦 Публичные репозитории | 64 |
| ⭐ Звёзды | [Проверить](https://github.com/ergon73?tab=repositories) |
| 👥 Подписчики | [Подписаться](https://github.com/ergon73) |
| 🎯 Основные языки | Python, Jupyter Notebook, Shell |
| 📅 На GitHub с | 2024 |
```

## Вариант 3: Activity Graph (GitHub Contribution Snake)

```markdown
### 📊 Активность

![GitHub Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=ergon73&theme=tokyo-night)

![Snake animation](https://raw.githubusercontent.com/ergon73/ergon73/output/github-contribution-grid-snake-dark.svg)
```

**Примечание:** Для snake animation нужно настроить GitHub Action (см. ниже)

## Вариант 4: Комбинированный (рекомендуется)

```markdown
### 📊 GitHub Статистика

<div align="center">

<!-- Простые badges всегда работают -->
![Views](https://komarev.com/ghpvc/?username=ergon73&color=blueviolet)
![Followers](https://img.shields.io/github/followers/ergon73?label=Followers&style=social)
![Stars](https://img.shields.io/github/stars/ergon73?label=Stars&style=social)

<br><br>

<!-- Streak обычно стабилен -->
![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=ergon73&theme=dark)

</div>

**Топ проекты:**
- 🚀 [vps-autodeploy-fastapi](https://github.com/ergon73/vps-autodeploy-fastapi) - Production FastAPI + Docker
- 📊 [grafana-loki-stack](https://github.com/ergon73/grafana-loki-stack) - Monitoring stack
- 🤖 [multi-llm-data-analyzer](https://github.com/ergon73/multi-llm-data-analyzer) - AI data analysis
```

---

## 🛠 Настройка GitHub Contribution Snake (опционально)

Если хотите красивую анимацию змейки поедающей ваши коммиты:

### Шаг 1: Создать файл `.github/workflows/snake.yml`

```yaml
name: Generate Snake

on:
  schedule:
    - cron: "0 0 * * *" # каждый день в полночь
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ergon73
          outputs: |
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
            
      - uses: crazy-max/ghaction-github-pages@v3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

### Шаг 2: Запустить вручную

1. Зайдите в Actions на GitHub
2. Найдите "Generate Snake"
3. Нажмите "Run workflow"

### Шаг 3: Добавить в README

```markdown
![Snake animation](https://raw.githubusercontent.com/ergon73/ergon73/output/github-contribution-grid-snake-dark.svg)
```

---

## 🔍 Почему не работают GitHub Stats?

Основные причины:
1. **Перегрузка Vercel API** - слишком много запросов
2. **Rate limit** - превышен лимит запросов
3. **Кеширование** - нужно подождать несколько минут
4. **Приватные репозитории** - статистика не видна без токена

## ✅ Текущее решение

Я использовал комбинированный подход:
- ✅ Profile Views badge (всегда работает)
- ✅ Followers/Stars badges (всегда работают)
- ✅ GitHub Streak (стабильный сервис)
- ⚠️ GitHub Stats (может глючить, но выглядит красиво)

**Если Stats не загружаются:**
- Подождите 2-3 минуты
- Обновите страницу (Ctrl+F5)
- Попробуйте через incognito режим
- В крайнем случае - используйте Вариант 1 или 4 выше

---

**Важно:** Все эти варианты выглядят профессионально для портфолио! 🎯
