### api_yamdb

![example workflow](https://github.com/korsss/yamdb_final/actions/workflows/main.yml/badge.svg)

# Описание проекта

Проект **YaMDb** собирает отзывы пользователей на произведения. Произведения делятся на категории: «Книги», «Фильмы», «Музыка».
Автор: Мелкомуков Кирилл

# Параметры .env файла (заполнить своими параметрами)

```
DB_ENGINE=django.db.backends.postgresql
DB_NAME={имя базы данных}
POSTGRES_USER={имя пользователя}
POSTGRES_PASSWORD={пароль пользователя}
DB_HOST={адрес хоста с БД, для compose - db}
DB_PORT=5432
```

# Запуск проекта

```
docker-compose up -d --build
```

# Настройка при первом запуске

Выполнить миграцию -> Создать суперпользователя -> Собрать статику

```
docker-compose exec web python manage.py migrate --noinput
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input 
```

# Тестовые данные

Собраны в файлике fixtures.json

# Проект доступен по ссылке http://just-hi.tk/redoc/