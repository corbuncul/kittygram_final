# КИТТИГРАМ

Проектом «Киттиграм» — сайт, на котором пользователи могут публиковать информацию о своих питомцах-котиках.
## Для запуска api проекта необходимо:
- Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/corbuncul/kittygram.git
cd kittygram/backend
```
- Cоздать и активировать виртуальное окружение:
```
python3 -m venv env
```
* Если у вас Linux/macOS

    ```
    source env/bin/activate
    ```

* Если у вас windows

    ```
    source env/scripts/activate
    ```
- Установить зависимости из файла requirements.txt:
```
python3 -m pip install --upgrade pip
pip install -r requirements.txt
```
- Выполнить миграции:
```
python3 manage.py migrate
```
- Запустить проект:
```
python3 manage.py runserver
```
## Для запуска фронтенда проекта необходимо:
- перейти в папку фронтенда
```
cd kittygramm/frontend
```
- Установить зависимости:

```
npm i
```

- Запустить проект:

```
npm run start
```
## Для запуска проекта вместе фронтендом необходимо:
- создать файл .env и внести в него следующие настройки:
```
POSTGRES_DB=<имя базы данных>
POSTGRES_USER=<пользователь базы данных>
POSTGRES_PASSWORD=<пароль пользователя базы данных>
DB_NAME=<имя базы данных>
DB_HOST=<имя контейнера с базой данных>
DB_PORT=<порт, на котором работает база данных>
SECRET_KEY=<секретный ключ джанго-проекта>
SERVER_IP=<IP-адрес сайта>
SERVER_DOMAIN=<Доменное имя сайта>
```
- запустить проект командой:
```
docker compose up -d
```
- произвести миграции и скопировать статику:
```
docker compose exec backend python manage.py migrate
docker compose exec backend python manage.py collectstatic
docker compose exec backend cp -r /app/collected_static/. /backend_static/static/
```
- создать суперпользователя:
```
docker compose exec backend python manage.py createsuperuser
```
- Можно пользоваться. Проект будет доступен по адресу http://localhost:9000/
