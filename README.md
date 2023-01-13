# API-servise for social network "YATUBE"

### Description

Social network Yatube is for keeping a diary. Users can create an account, publish notes, subscribe on another author, tag and comment on fovourite notes, add notice to the special groups.

Interraction with functional part of Yatube occurs through API-servise.


### Technologies

Python 3.7

Django 2.2.19

Django REST framework 3.12.4


### Local project run:

Clone a repository and navigate to it on the command line:

```
git clone https://github.com/Beloborodova-Anastasiia/api_yatube.git
```

```
cd api_yatube/
```

Create and activate virtual environment:

```
for Mac or Linux:
python3 -m venv venv
source venv/bin/activate
```
```
for Windows:
python -m venv venv
source venv/Scripts/activate 
```

Install dependencies from requirements.txt file:

```
for Mac or Linux:
python3 -m pip install --upgrade pip
```
```
for Windows:
python -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Make migrations:

```
for Mac or Linux:
cd yatube_api/
python3 manage.py migrate
```
```
for Windows:
cd yatube_api/
python manage.py migrate
```

Create superuser if necessary:

```
for Mac or Linux:
python3 manage.py createsuperuser
```
```
for Windows:
python manage.py createsuperuser
```

Run project:

```
for Mac or Linux:
python3 manage.py runserver
```
```
for Windows:
python manage.py runserver
```

The project administrator's website is available at:

```
http://localhost/admin
```

Project's documentation is available at:

```
http://localhost/redoc
```


### API request examples

Get JWT-token:
```
POST: /api/v1/jwt/create/
```
```
Request body:
{
  "username": "string",
  "password": "string"
}
```
```
Response:
{
  "refresh": "string",
  "access": "string"
}
```

All publication recieving:

```
GET: /api/v1/posts/
```
```
Response:
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

Create a commentary to the post:

```
POST: /api/v1/posts/{post_id}/comments/
```
```
Request body:
{
"text": "string"
}
```
```
Response:
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```


### Author

Anastasiia Beloborodova 

anastasiia.beloborodova@gmail.com
