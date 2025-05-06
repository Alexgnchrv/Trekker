# Trekker

## О проекте
Trekker — приложение для управления задачами. Приложение состоит из фронтенда на React и бэкенда на Django, упакованных в Docker-контейнеры для удобства локальной разработки и развёртывания.

## Функциональность
- Добавление, редактирование и удаление задач  
- Перевод задач между статусами «Незавершённые» и «Завершённые»  
- Фильтрация списка задач по статусу  
- Аутентификация через JWT, хранение сессий в Redis  
- Централизованное логирование и мониторинг ошибок  

## Стек технологий
- **Backend**: Python, Django, Django REST Framework  
- **Frontend**: React, Redux  
- **База данных**: PostgreSQL  
- **Кэш и сессии**: Redis  
- **Контейнеризация**: Docker, Docker Compose  
- **CI/CD**: GitHub Actions  
- **Веб-сервер**: Nginx, Gunicorn  

## Быстрый старт
```bash
# 1. Клонировать репозиторий
git clone https://github.com/your-username/taski-docker.git
cd taski-docker

# 2. Скопировать шаблон окружения и настроить переменные
cp .env.example .env
# отредактировать .env (DB_HOST, DB_NAME, DB_USER, DB_PASSWORD, SECRET_KEY и т.п.)

# 3. Собрать и запустить контейнеры
docker-compose up --build

# 4. Выполнить миграции и создать суперпользователя
docker-compose exec backend python manage.py migrate
docker-compose exec backend python manage.py createsuperuser

# 5. Открыть в браузере:
#    Фронтенд: http://localhost:3000
#    API:       http://localhost:8000/api/
