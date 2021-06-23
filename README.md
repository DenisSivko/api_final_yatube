# Финальный проект «API для Yatube»
## Описание
Проект полезен тем, что в первую очередь даёт возможность взаимодействовать с сайтом и предоставляет возможность пользоваться функционалом, не заходя на сайт.
##### Функционал:
###### POSTS
- Получить список всех публикаций
- Создать новую публикацию
- Получить публикацию по id
- Обновить публикацию по id
- Частично обновить публикацию по id
- Удалить публикацию по id
###### COMMENTS
- Получить список всех комментариев публикации
- Создать новый комментарий для публикации
- Получить комментарий для публикации по id
- Частично обновить комментарий для публикации по id
- Удалить комментарий для публикации по id
###### AUTH
- Получить JWT-токен
- Обновить JWT-токен
###### FOLLOW
- Получить список всех подписчиков
- Создать подписку
###### GROUP
- Получить список всех групп
- Создать новую группу

Документация к API доступна по адресу `http://127.0.0.1:8000/redoc/`
## Установка
Клонируем репозиторий на локальную машину:

git clone `https://github.com/DenisSivko/api_final_yatube.git`

Создаем виртуальное окружение:

`python -m venv venv`

Устанавливаем зависимости:

`pip install -r requirements.txt`

Создаем и применяем миграции:

`python manage.py makemigrations`
`python manage.py migrate`

Запуск:

`python manage.py runserver`

## Примеры
##### Получаем токен
Для формирования запросов ответов использована программа [Postman](https://www.postman.com/).

Отправляем POST-запрос на адрес `http://127.0.0.1:8000/api/v1/token/` 

- `username` - указываем имя пользователя.
- `password` - указываем пароль пользователя.

![token_image](https://i.ibb.co/nLcD2Pv/token.png)

Токен `refresh` пригодятся для обновления токена.
Токен `access` используется для аутентификации пользователя.

##### Создаем новый пост
Отправляем POST-запрос и для аутентификации передаём JWT-токен в заголовке Authorization: Bearer <токен>.
- Обязательное поле: `text`

![posts_image](https://i.ibb.co/KLLsfP6/posts.png)

##### Получаем список всех публикаций
Отправляем GET-запрос на адрес `http://127.0.0.1:8000/api/v1/posts/`.

![allposts_image](https://i.ibb.co/qpsnphB/allposts.png)

