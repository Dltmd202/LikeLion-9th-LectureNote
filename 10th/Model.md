# π¨π½βπ»10μ£Όμ°¨!

## 10.5 Model μ€μ΅

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



| νλνμ      | HTML μμ ―      | νμ μ΅μ  |
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

  μ± λ΄μ migration ν΄λλ₯Ό λ§λ€μ΄μ models.py μ λ³κ²½μ¬ν­ μ μ₯

* migrate

  Migration ν΄λλ₯Ό μ€νμμΌ λ°μ΄ν°λ² μ΄μ€μ μ μ©



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



