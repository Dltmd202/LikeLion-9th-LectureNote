# 👨🏽‍💻10주차!

## 10.5 Model 실습

### 10.5.1 Setting

Terminal

```bash
pip install django
django -admin startproject [projectName]
python manage.py startapp blog
```

setting.py

```python
INSTALLED_APPS =[
  '~',
  '~',
  '~',
  'blog'
]
```

model.py

```python
from django.db import models

class Blog(models.Model):
  title = models.CharField(max_Length=200)
  writer = medels.CharField(max_Length=100)
  pub_data = models.DateTimeField()
  body = models.TextField()
  
  #Override
  def __str__(self):
    return self.title
```



| 필드타입      | HTML 위젯      | 필수 옵션  |
| ------------- | -------------- | ---------- |
| BooleanField  | CheckboxInput- | -          |
| CharField     | TextInput      | Max_length |
| DataField     | TextInput      | -          |
| DataTimeField | TextInput      | -          |
| FloatField    | NumberInput    | -          |
| IntegerField  | NumberInput    | -          |
| TextField     | Textarea       | -          |

Terminal

```bash
python manage.py makemigration
python manage.py migrate
```



* makemigrations

  앱 내의 migration 폴더를 만들어서 models.py 의 변경사항 저장

* migrate

  Migration 폴더를 실행시켜 데이터베이스에 적용



### 10.5.2 Admin

Terminal

```bash
python manage.py createsuperuser
Email
pw
pw
python manage.py runserver
```

* localserver:[portNum]/admin/

admin.py

```python
from .models import Blog

admin.site.register(Blog)

```



