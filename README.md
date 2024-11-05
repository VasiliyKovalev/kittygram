## Kittygram
Kittygram — социальная сеть для обмена фотографиями любимых котиков.
### Описание
*  Проект Kittygram позволяет выкладывать фотографии котиков на сайт.
*  При добавлении фотографии необходимо указать имя питомца, его дату рождения и цвет. По желанию можно заполнить графу 'Достижения'.
*  Добавлять фотографии могут только аутентифицированные пользователи.
### Как запустить проект:
1. Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:VasiliyKovalev/kittygram_final.git
```

```
cd kittygram_final
```

2. Создать файл .env:

```
touch .env
```

3. Указать переменные окружения в файле .env по примеру файла .env.example:

```
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
POSTGRES_DB=kittygram
DB_HOST=kittygram
DB_PORT=5432
SECRET_KEY=
```

4. Запустить Docker Compose:

```
docker compose up
```

5. Выполнить миграции:

```
docker compose exec backend python manage.py migrate
```

6. Собрать статику:

```
docker compose exec backend python manage.py collectstatic
```

```
docker compose exec backend cp -r /app/collected_static/. /backend_static/static/
```

### После запуска проект будет доступен по адресу:
http://127.0.0.1:9000/
