# HabitQuest

**HabitQuest** — веб-сервис — трекер привычек с элементами геймификации.
Индивидуальная выпускная работа: ИТ-проект (Лицей НИУ ВШЭ).

## Возможности

- Аккаунт: регистрация, вход, восстановление пароля, редактирование профиля
- Привычки: создание с расписанием (ежедневно / по будням / выбранные дни / N раз в неделю), отметка выполнения, редактирование, архивация
- Готовые шаблоны привычек
- Серии (streaks) и статистика с графиками
- Геймификация: XP, уровни, достижения
- Друзья: заявки, рейтинг, сравнение прогресса
- Напоминания и уведомления
- Экспорт статистики в CSV
- Тёмная/светлая тема

## Стек технологий

| Слой | Технология |
|---|---|
| Backend | Python 3, Flask 3, Flask-SQLAlchemy, Flask-Login, Flask-WTF |
| База данных | SQLite (локально) / PostgreSQL (на хостинге) |
| Frontend | HTML5, CSS3, JavaScript, Bootstrap 5, Chart.js |
| Инструменты | Git/GitHub, VS Code |

## Запуск локально

```bash
# 1. Создать и активировать виртуальное окружение
python3 -m venv venv
source venv/bin/activate        # macOS / Linux
venv\Scripts\activate           # Windows

# 2. Установить зависимости
pip install -r requirements.txt

# 3. Запустить приложение (база данных создастся автоматически)
python run.py

# 4. Открыть в браузере
# http://127.0.0.1:5000
```

## Структура проекта

```
project/
├── application.md          # заявка на проект (ИВР)
├── userscripts.md          # пользовательские сценарии
├── run.py                  # точка входа
├── config.py               # конфигурация
├── requirements.txt
└── app/
    ├── __init__.py         # фабрика приложения
    ├── models.py           # модели БД
    ├── forms.py            # формы
    ├── utils.py            # уровни, достижения, напоминания
    ├── routes_auth.py      # аутентификация
    ├── routes_habits.py    # привычки
    ├── routes_main.py      # статистика, друзья, экспорт
    ├── routes_api.py       # JSON API для уведомлений
    ├── templates/          # шаблоны Jinja2
    └── static/             # CSS и JavaScript
```

## Развёртывание на хостинге

1. Создайте проект на [Render](https://render.com) или [Railway](https://railway.app).
2. Укажите команду запуска: `gunicorn run:app`.
3. Задайте переменные окружения:
   - `SECRET_KEY` — секретный ключ приложения;
   - `DATABASE_URL` — строка подключения к PostgreSQL;
   - `SMTP_HOST`, `SMTP_PORT`, `SMTP_LOGIN`, `SMTP_PASSWORD` — для отправки писем восстановления пароля (необязательно).# Petrov-repo
