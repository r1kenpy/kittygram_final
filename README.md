![Статус workflow](https://github.com/r1kenpy/kittygram_final/actions/workflows/main.yml/badge.svg)

Проект позволяет делиться фотографиями котиков. Доступно: удаление добавление, удаление, редактирование своих публикаций.
Сервис доступен только зарегистрированным пользователям.

## 1. Как развернуть проект
Скачайте [pdocker-compose.production.yml](https://github.com/r1kenpy/kittygram_final/blob/main/docker-compose.production.yml)

Создайте файл .env c переменными окружения:
```
POSTGRES_DB=`База Данных`
POSTGRES_USER=`имя пользователя`
POSTGRES_PASSWORD=`пароль`
DB_NAME=`имя Базы Данных`
DB_HOST=db
DB_PORT=5432
SECRET_KEY=`ключ Django`
DEBUG=`True/False`
ALLOWED_HOSTS=`хосты`
```

# 2. Запуск Docker compose
```
sudo docker compose -f docker-compose.production.yml pull
sudo docker compose -f docker-compose.production.yml down
sudo docker compose -f docker-compose.production.yml up -d
```

# 3. Mиграции и собор статики
```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /static/static/
  
```

## Cтек
- Django 
- React
- Nginx
- Docker compose

# Автор [r1kenpy](https://github.com/r1kenpy/)
