# 👨🏽‍💻14주차!

## 14.3 배포 사전준비

### 14.3.1 EC2

* __지역__ 확인

* instance

* launch instatnce

* Ubuntu Server __64bit__

* t2.micro

* 8 - 30G

* security-group

  Rule

  | Type                | Protocol | Port Range |
  | ------------------- | -------- | ---------- |
  | HTTP                | TCP      | 80         |
  | HTTPS               | TCP      | 443        |
  | Custom TCP Protocol | TCP      | 8000       |

* Launch
* Elestic IP

Terminal

```bash
ssh ubuntu@[ip] -i [키]
yes
sudo apt update && sudo apt -y upgrade
sudo apt install -y python3 python3-pip python3-dev python3-venv build-essential libpq-dev vim git
```

settings.py

```python
SECRET_KEY = os.environ.get('SECRET_KEY', 'key')
DEBUG = (os.environ.get('DEBUG', 'True') != 'False')

ALLOWED_HOSTS = ['*']

AWS_ACCESS_KEY_ID = '아이디'
AWS_SECRET_ACCESS_KEY = '접근 코드'
AWS_STORAGE_BUCKET_NAME = '버킷이름'
AWS_S3_SIGNATURE_VERSION = "s3v4"
AWS_S3_REGION_NAME = "ap-northeast-2"
AWS_S3_CUSTOM_DOMAIN = ""
```

terminal

```bash
python3 -m venv venv
source venv/bin/activate
pip freeze > requirements.txt
git add *
git commit -m "~~"
git push
```

terminal

```bash
sudo reboot
git clone github/repo django-app
source ../venv/bin/activate

cd django-app
pip install -r requirements.txt
python manage.py runserver 0.0.0.0:8000
decativate
```

* PostgreSQL 설치

```bash
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt update
sudo apt -y install postgresql
sudo systemctl enable --now postgresql@13-main
sudo -u postgres createdb [dbName]
sudo -u postgres psql [dbName]
```

SQL

```sql
create userdjango with password '[password]';
alter role [dbName] set client_encodingto 'utf-8';
alter role [dbName] set timezone to 'Asia/Seoul';
grant all privileges on database [dbName] to [dbName]
```



settings.py

```python
DATABASES = {
  'default':{
    'ENGINE': 'django.db.backends.postgresql_psycopg2',
    'NAME': os.environ.get('DB_NAME'),
    'USER': os.environ.get('DB_USER'),
    'PASSWORD': os.environ.get('DB_PASSWORD'),
    'HOST': os.environ.get('DB_HOST'),
    'PORT': '',
  }
}
```

terminal

```bash
git add *
git commit -m "~~"
git push
```

terminal

```bash
git pull
source ../venv/bin/activate
pip install psycopg2
export DB_NAME=[dbName]
export DB_USER=[name]
export DB_PASSWORD = ''
export DB_HOST = localhost

python mange.py makemigrations
python manage.py migrate
python manage.py runserver 0.0.0.0:8000
```

* gunicorn으로 Django 실행

```bash
pip install gunicorn
deactivate
../venv/bin/gunicorn [PJNAME].wsgi -b 0.0.0.0

```



* Systems 에  gunicorn  등록

```bash
sudo vi /etc/systemd/systemd/gunicorn.service
```

```
[Unit]
Description=gunicorn daemon
Requires=gunicorn.socket
After=network.target

[Service]
Type=notify
RuntimeDirectory=gunicorn
WorkingDirectory=/home/ubuntu/projects/mysite
EnvironmentFile=/home/ubuntu/venvs/mysite.env
ExecStart=/home/ubuntu/venvs/mysite/bin/gunicorn [pjName]
killMode=mixed
TimeouStopSec=5
PrivateTmp=true
EnviromentFile=/etc/qunicorn/env.conf

[Install]
WantedBy=multi-user.target
```



```bash
sudo vi /etc/systemd/systemd/gunicorn.socket
```

```
[Unit]
Description=gunicorn socket

[Service]
ListenStream=/run/qunicorn.sock
SocketUser=www-data

[Install]
WantedBy=sockets.target
```





```bash
sudo mkdir /etc/gunicorn

sudo vi /etc/gunicorn/env.conf
```

```
DB_NAME=[dbName]
DB_USER=[user]
DB_PASSWORD = ''
DB_HOST=localhost
```



```bash
sudo systemctl daemon-reload
sudo systemctl enable --now gunicorn.socket
sudo systemctl enable --now gunicorn

curl --unix-socket /run/gunicorn.sock http
sudo apt -y install nginx
sudo vi /etc/nginx/sites-available/django-app
```

```
server {
        listen 80;
        server_name [주소];

        location = /favicon.ico { access_log off; log_not_found off; }

        location /static/ {
                root /home/foo/django_test/repo;
        }

        location / {
                include proxy_params;
                proxy_pass http://unix:/home/foo/django_test/run/gunicorn.sock;
        }
}
```



```bash
sudo in -s /etc/gninx/sites-availale/django_app /etc/nginx/sites_enabled
sudo nginex -t
sudo systemctl restart nginx
source ../venv/bin/activate
python manage.py collectstatic
```

