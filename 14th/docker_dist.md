# ð¨ð½âð»14ì£¼ì°¨!

## 14.5 Docker ì´ë¯¸ì§ ìì±

### 14.5.1 Gitpot setting

* Url - hotpot.io/[remote repository url]

* Requirements ì¤ì¹

  `pip install -r requirements.txt`

* White noise ì¤ì¹

  `pip install whitenoise`

  MIDDLEWAREìì SecurityMiddleware ë°ë¡ ìë ë´ì© ì¶ê°

  ```python
  MIDDLEWARE = [
    'django.middleware.security.SecureityMiddleware',
    # ìê±° ì¶ê°
    'whitenoise.middleware.WhiteNoseiMiddleware', 
  ]
  ```

* Gunicorn ì¤ì¹

  `pip install gunicorn`

* Dockerfile ìì±

![áá³áá³ááµá«áá£áº 2021-07-12 áá©áá® 2.49.36](/Users/mac/Library/Application Support/typora-user-images/áá³áá³ááµá«áá£áº 2021-07-12 áá©áá® 2.49.36.png)

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







