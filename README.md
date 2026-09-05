# Django React Blog

Fullstack-платформа для блога: REST API на Django и клиент на React.

Пользователи могут регистрироваться, входить в аккаунт, читать посты, создавать записи, редактировать свой профиль и просматривать авторов.

## Возможности

- регистрация и авторизация через JWT
- CRUD для постов
- редактировать и удалять пост может только автор
- кастомная модель пользователя и страница профиля
- категории, пагинация и фильтрация постов
- загрузка изображений для постов и профиля
- список авторов
- защищённые маршруты на frontend

## Стек

Backend: Python, Django 5, Django REST Framework, Simple JWT, SQLite, Pillow

Frontend: React, Vite, React Router, React Query, Axios, Tailwind CSS

## Структура проекта

- Backend — Django REST API
- Frontend — React-приложение

## Запуск проекта локально

Нужны Python 3, Node.js и npm.

Backend:

cd Backend
python -m venv .venv
source .venv/Scripts/activate
pip install -r requirements.txt
cp .env.example .env
python manage.py migrate
python manage.py runserver

API будет доступен по адресу: http://127.0.0.1:8000

Frontend:

cd Frontend
npm install
echo "VITE_BASE_URL=http://127.0.0.1:8000" > .env
npm run dev

Клиент будет доступен по адресу: http://localhost:5173

## Переменные окружения

Backend/.env

DJANGO_SECRET_KEY=replace-with-strong-secret
DJANGO_DEBUG=True
DJANGO_ALLOWED_HOSTS=localhost,127.0.0.1
DJANGO_CORS_ALLOWED_ORIGINS=http://localhost:5173

Frontend/.env

VITE_BASE_URL=http://127.0.0.1:8000

Файл .env не хранится в Git. Для примера используй Backend/.env.example.

## Основные API endpoints

- POST /register_user/ — регистрация
- POST /token/ — получение JWT
- POST /token_refresh/ — обновление токена
- GET /blog_list — список постов
- GET /blogs/<slug> — один пост
- POST /create_blog/ — создать пост
- PUT /update_blog/<id>/ — обновить пост
- POST /delete_blog/<id>/ — удалить пост
- GET /authors/ — список авторов
- PUT /update_user/ — обновить профиль

## Автор

Андрей Литовко
GitHub: https://github.com/AndreiLitovko