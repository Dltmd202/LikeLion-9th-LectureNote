# 👨🏽‍💻14주차!

## 14.5 Docker 이미지 생성

### 14.5.1 Gitpot setting

* Url - hotpot.io/[remote repository url]

* Requirements 설치

  `pip install -r requirements.txt`

* White noise 설치

  `pip install whitenoise`

  MIDDLEWARE에서 SecurityMiddleware 바로 아래 내용 추가

  ```python
  MIDDLEWARE = [
    'django.middleware.security.SecureityMiddleware',
    # 요거 추가
    'whitenoise.middleware.WhiteNoseiMiddleware', 
  ]
  ```

* Gunicorn 설치

  `pip install gunicorn`

* Dockerfile 생성

![스크린샷 2021-07-12 오후 2.49.36](/Users/mac/Library/Application Support/typora-user-images/스크린샷 2021-07-12 오후 2.49.36.png)

run.sh

```sh
#!/bin/bash
python manage.py migrate
python mange.py collecstatic
gunicorn [ProjName].wsgi -b 0.0.0.0:8000
```

* `pip freeze > requirements.txt`
* `sudo docker -up`
* `cmd` + `shift` + `'`
* `docker build -t [id]/[AppName]`
* `docker run -it -p 8000:8000 [id]/[AppName]`
* `docker login`
* `docker push [id]/[AppName]`







