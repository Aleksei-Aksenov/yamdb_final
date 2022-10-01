[![yamdb_workflow](https://github.com/Aleksei-Aksenov/yamdb_final/workflows/yamdb_workflow/badge.svg)](https://github.com/Aleksei-Aksenov/yamdb_final/actions/workflows/yamdb_workflow.yml)
# Групповой проект: [yamdb_final](http://http://51.250.90.71/)

![badge](https://user-images.githubusercontent.com/86766017/175809946-525c22c7-c999-4101-85e0-f284ee3ac198.svg)
## Групповой проект 
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
![python](https://user-images.githubusercontent.com/86766017/175810761-2a172f41-70a4-47d9-9c70-e645f018a5e4.svg)
![drf](https://user-images.githubusercontent.com/86766017/175810765-3c6dc2fd-9484-4487-beff-202db318fd56.svg)

## Как установить и запустить проект

- git clone https://github.com/Snowball558/api_yamdb.git
- cd api_final_yatube
- python -m venv venv
- source venv/Scripts/activate
- python -m pip install --upgrade pip
- pip install -r requirements.txt
- python manage.py migrate
- python manage.py runserver


## Примеры запросов
Получение списка всех произведений

__GET /api/v1/titles/__

Получить список всех отзывов к определенному произведению по его id

__GET /api/v1/titles/{title_id}/reviews/__

Получить список всех комментариев к отзыву по id

__GET /api/v1/titles/{title_id}/reviews/{review_id}/comments/__
