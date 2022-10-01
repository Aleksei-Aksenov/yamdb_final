[![yamdb_workflow](https://github.com/Aleksei-Aksenov/yamdb_final/workflows/yamdb_workflow/badge.svg)](https://github.com/Aleksei-Aksenov/yamdb_final/actions/workflows/yamdb_workflow.yml)
# Групповой проект: [yamdb_final](http://http://51.250.90.71/)

![badge](https://user-images.githubusercontent.com/86766017/175809946-525c22c7-c999-4101-85e0-f284ee3ac198.svg)

__YAMDB__ собирает отзывы на произведения от пользователей. 

Категории произведений: 
- Книги
- Фильмы
- Музыка

Список категорий может быть расширен.
В каждой категории есть произведения: музыкальные, книги или фильмы. Произведению может быть присвоен жанр. Новые жанры может создавать только администратор.
У читателей есть возможность оставлять к произведениям отзывы и выставлять произведению рейтинг. Высчитывается средняя оценка произведения.


### Над проектом работали:
- Алексей Аксенов __(Review/Comments)__
https://github.com/Aleksei-Aksenov
- Александр Доведин __(Auth/Users)__
https://github.com/Snowball558
- Ян Шадрин __(Categories/Genres/Titles)__
https://github.com/Iankel86

### Стек технологий:

    Python 3.7.0
    Django 2.2.16
    DRF 3.12.4
    Nginx
    Postgres
    Docker


## Как установить и запустить проект

- Клонировать репозиторий:
```
    git clone https://github.com/Aleksei-Aksenov/yamdb_final.git
```
- Создать .env файл в директории infra/ (либо воспользоваться подсказкой из файла .env.example, переименовав его в .env), в котором должны содержаться следующие переменные:

    DB_ENGINE=django.db.backends.postgresql
    
    DB_NAME= # название БД
    
    POSTGRES_USER= # ваше имя пользователя
    
    POSTGRES_PASSWORD= # пароль для доступа к БД
    
    DB_HOST=db
    
    DB_PORT=5432
    

- Перейти в папку infra, запустить docker-compose.yaml и собрать контейнеры (при установленном и запущенном Docker)
```
    cd infra_sp2/infra
    sudo docker compose up -d --build
```
- В контейнере web выполнить миграции:
```
    sudo docker compose exec web python manage.py migrate
```
- Создать суперпользователя:
```
    sudo docker compose exec web python manage.py createsuperuser
```
- Собрать статику:
```
    sudo docker compose exec web python manage.py collectstatic --no-input
```
- Проверить работоспособность приложения, для этого перейти на страницу:

    http://localhost/admin/
    
- Убедиться, что страница отображается полностью: статика подгрузилась;
- Авторизоваться под аккаунтом суперпользователя и убедиться, что миграции прошли успешно;
- Протестировать приложение, например, через Postman


## Примеры запросов

- ### Регистрация нового пользователя:

__POST /api/v1/auth/signup/__

![изображение](https://user-images.githubusercontent.com/99750013/190842608-65abc990-7330-4474-b73b-12cef552d5cd.png)

    
- ### Получение списка всех произведений

__GET /api/v1/titles/__

![изображение](https://user-images.githubusercontent.com/99750013/190842799-ef9fde79-3044-47eb-be61-13723954dd9f.png)


- ### Получить список всех отзывов к определенному произведению по его id

__GET /api/v1/titles/{title_id}/reviews/__

![изображение](https://user-images.githubusercontent.com/99750013/190842878-abaefc2a-3081-4d48-b3c0-792519f0023f.png)

- ### Получить список всех комментариев к отзыву по id

__GET /api/v1/titles/{title_id}/reviews/{review_id}/comments/__

![изображение](https://user-images.githubusercontent.com/99750013/190843000-d3a2143a-3f69-4c5f-8c4b-4a0b9cd495b1.png)

