![CI/CD](https://github.com/ignat-alt/habit-tracker/actions/workflows/ci-cd.yml/badge.svg)

# Habit Tracker

Приложение для отслеживания привычек: заводишь привычку, отмечаешь выполнение каждый день, видишь серию (streak).

## Структура

- `backend/` — REST API на FastAPI (привычки, отметки, streak) + тесты
- `web/` — статическая страница (деплой на Cloudflare Pages)
- `.github/workflows/ci-cd.yml` — CI/CD: lint, тесты на Python 3.10–3.12, покрытие, деплой

## Запуск backend локально

```bash
cd backend
python -m venv venv
source venv/bin/activate        # Windows (Git Bash): source venv/Scripts/activate
pip install -r requirements-dev.txt
uvicorn app.main:app --reload --port 8000
```

Документация API: http://127.0.0.1:8000/docs

## Тесты

```bash
cd backend
pytest -v --cov=app --cov-report=term-missing
ruff check .
```
