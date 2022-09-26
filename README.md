## Проект «API для Yatube»

Yatube - проект социально сети, созданной в учебных целях. Проект «API для Yatube» даёт возможность работать с проектом Yatube через API. Он реализует возможность создавать посты, комментарии к ним и группы, а также упрявлять подписками.

### Технологии использованные в проекте:

- [Python](https://www.python.org/) - язык программирования тспользуемого в проекте.
- [Django](https://www.djangoproject.com/) - Фреймворк Django.
- [Django REST Framework](https://www.django-rest-framework.org/) - API Фреймворк.

### Запуск проекта.

Клонирование и запуск проекта на локальном компьютере:

Ссылка на репозиторий:
`https://github.com/psevdoslon-ya/api_final_yatube.git`

Клонирование проекта:
`git clone https://github.com/psevdoslon-ya/api_final_yatube.git`

Создание виртуального окружения:

`Перейти в папку с проектом: cd ../api_final_yatube`
`python3 -m venv venv`
`. venv/bin/activate`

Установка зависимостей:
`pip install -r requirements.txt`

Выполнение миграций:
`python3 manage.py migrate`

Запуск локального сервера:
`python3 manage.py runserver`

### Ссылка на документацию проекта:

`http://localhost:port/redoc/`

#### Примеры запросов:

POST-запрос с токеном, добавление новой публикации в коллекцию публикаций.

`POST http://localhost:port/api/v1/posts/`

```
{
  "text": "Однажды в студеную зимнюю пору, я из лесу вышел, был сильный мороз!",
  "group": 1
}
```

Ответ:

```
{
    "id": 9,
    "author": "root",
    "text": "Однажды в студеную зимнююю пору, я из лесу вышел, был сильный мороз!",
    "pub_date": "2021-09-22T02:37:44.494905Z",
    "image": null,
    "group": 1
}
```


GET-запрос, получение информации о сообществе по id=2.

`GET http://localhost:port/api/v1/groups/2/`

Ответ:

```
{
    "id": 2,
    "title": "group2",
    "slug": "group2",
    "description": "group2"
}
```

POST-запрос, подписка авторизованного пользователя `user=root` от имени которого сделан запрос на автора интересующей публикации `following=admin`.

`POST http://localhost:port/api/v1/follow/`

```
{
  "following": "admin"
}
```

Ответ:

```
{
    "id": 6,
    "user": "root",
    "following": "admin"
}
```
