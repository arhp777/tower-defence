# Оборона Від Зомбі — Локальний Flask-проєкт

Лаконічний локальний Flask-проєкт з екраном входу та ігровою панеллю (dashboard).

## Швидкий огляд
- Сервер: [app.py](app.py) — головний Flask-додаток, маршрути: [`app.index`](app.py), [`app.login`](app.py), [`app.dashboard`](app.py).
- UI: шаблони — [templates/login.html](templates/login.html) та [templates/dashboard.html](templates/dashboard.html).
- Стилі: [static/style_login.css](static/style_login.css).

## Файлова структура
- [app.py](app.py)
- templates/
  - [login.html](templates/login.html)
  - [dashboard.html](templates/dashboard.html)
- static/
  - [style_login.css](static/style_login.css)

## Вимоги
- Python 3.8+
- Flask

Установка (приклад):
```bash
python -m venv venv
venv\Scripts\activate   # Windows
# або: source venv/bin/activate  # macOS / Linux
pip install Flask
```

## Запуск
Запустіть локальний сервер:
```bash
python app.py
```
Потім відкрийте у браузері: http://127.0.0.1:5000/ (буде перенаправлення на сторінку входу).

> Примітка: секретний ключ знаходиться в [app.py](app.py) у змінній `app.secret_key` — замініть на безпечне значення для продакшену.

## Тестові облікові дані
- Логін: `testuser` / Пароль: `password123`  
- Логін: `admin` / Пароль: `adminpass`

(Дані зберігаються в пам'яті у змінній `USERS` в [app.py](app.py).)

## Коротка інструкція по використанню
1. Відкрийте стартову сторінку → введіть логін/пароль.
2. Успішний вхід перенаправляє до [dashboard.html](templates/dashboard.html), де запускається фронтенд-гра на канвасі.

## Нотатки для розробника
- UI/логіка гри — у [templates/dashboard.html](templates/dashboard.html) вбудований JS-код; для великих змін варто винести скрипти в окремий файл у `static/`.
- Для збереження користувачів/сесій у продакшені використовуйте СУБД та безпечну конфігурацію секретного ключа.
- Щоб змінити стартові ресурси/налаштування гри — редагуйте константи в [templates/dashboard.html](templates/dashboard.html).

## Виправлення проблем
- Якщо шаблони не завантажуються — перевірте потоки логів у терміналі, де запущено `python app.py`.
- Якщо зміни в шаблонах не відображаються — перезапустіть сервер (debug=True інколи кешує шаблони).

## Ліцензія
Проєкт для локального використання/демонстрації. При використанні чи публікації оновіть ліцензію відповідно до ваших потреб.
