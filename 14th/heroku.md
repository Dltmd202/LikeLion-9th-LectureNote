# 👨🏽‍💻14주차!

## 14.2 배포 사전준비

### 14.2.1 Setting

settings.py

```python
SECRET_KET = os.environ.get('비밀키')
DEFAULT_FILE_STORAGE = 'storages.backends.s3boto3.S3Boto3Storage'

AWS_ACCESS_KEY_ID = '아이디'
AWS_SECRET_ACCESS_KEY = '접근 코드'
AWS_STORAGE_BUCKET_NAME = '버킷이름'
AWS_S3_SIGNATURE_VERSION = "s3v4"
AWS_S3_REGION_NAME = "ap-northeast-2"
AWS_S3_CUSTOM_DOMAIN = ""
```

Procfile

```bash
web: gunicorn [projNmae].wsgi
```

runtime.txt

```bash
python-3.9.1
```

```bash
pip install gunicorn whienoise dj-database-url psycopg2-binary
```

settings.py

```python
MIDDLEWARE = [
  'whitenoise.middleware.WhiteNoiseMiddleware',
]

ALLOWED_HOSTS = [
  '*'
]

import dj_database_url
db_from_env = dj_database_url.config(conn_max_age=500)
DATABASE['default'].update(db_from_env)
```

terminal

```bash
pip freeze > requirements.txt
git add *
git commit -m "~~"

heroku login
heroku create
git push heroku main
heroku run python manage.py migrate
heroku run python manage.py createsuperuser
heroku open
```

