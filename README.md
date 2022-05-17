# Проект API для социальной сети "YATUBE"

### Описание

Проект "YATUBE" - это социальная сеть для ведения личного дневника.
Проект "YATUBE" дает пользователям возможность создавать учетную запись, публиковать заметки в личный дневник, подписываться на других авторов, отмечать и комментировать понравившиеся записи, отправлять в сообщества, где можно прочитать заметки разных авторов.
API для "YATUBE" дает возможность взаимодействоть с функциональной частью "YATUBE" через API-сервис.

### Технологии

Python 3.7

Django 2.2.19


### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/Beloborodova-Anastasiia/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source env/bin/activate
```

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```


### Примеры запросов к API

Получить список всех публикаций:

```
GET: /api/v1/posts/
```
```
Ответ:
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}
```

Создать комментарий к посту:

```
POST: /api/v1/posts/{post_id}/comments/
```
```
Тело запроса:
{
"text": "string"
}
```
```
Ответ:
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```
