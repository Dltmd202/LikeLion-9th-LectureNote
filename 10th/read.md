# 👨🏽‍💻10주차!

## 10.6 CRUD - READ

### 10.6.1 CRUD

* CREATE
* READ
* UPDATE
* DELETE



### 10.6.2 Setting

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
  
  def summary(self):
    return self.body[:100]
```



views.py

```python
def home(request):
  blogs = models.objects.all()
  return render(request,
               'home.html',{
                 'blogs': blogs
               })
```

urls.py

```python
from blog.views import *

urlpatterns = [
  path('admin/', name='home')
]
```

Home.html

```html
<html>
  <head>
    <style>
    	
    </style>
  </head>
  <body>
    <h1>
      Blog Project
    </h1>
    {% for blog in blogs %}
    <div>
      <h3>
        {{ blog.title }}
      </h3>
    	{{ blog.writer }}
    	{{ blog.summury }}
    </div>
    {% endfor %}
  </body>
</html>
```



### 10.6.2 Path-converter

* url을 통해 pk에 해당하는 객체 호출
* 코드 중복 방지

views.py

```python
from django.shortcuts import render,get_object_or_404
from .models import Blog

def home(request):
  blogs = models.objects.all()
  return render(request,
               'home.html',{
                 'blogs': blogs
               })


def detail(request, id):
  blog = get_object_or_404(Blog, pk = id)
  return render(request,
               'detail.html',{
                 'blog':blog
               })
```

urls.py

```python
from blog.views import *

urlpatterns = [
  path('admin/', name='home'),
  path('<str:id>', detail, name='detail'),
  
]
```

Home.html

```html
<html>
  <head>
    <style>
    	
    </style>
  </head>
  <body>
    <h1>
      Blog Project
    </h1>
    {% for blog in blogs %}
    <div>
      <h3>
        {{ blog.title }}
      </h3>
      {{ blog.id }}
    	{{ blog.writer }}
    	{{ blog.summury }}
     	<a href="{% url 'detail' blog.id %}">...more</a>
    </div>
    {% endfor %}
  </body>
</html>
```

detail.html

```html
<html>
  <head>
  </head>
  <body>
    <h1>{{ blog.title }}</h1>
    <div>
      {{ blog.writer }}
      {{ blog.pub_date }}
    </div>
      <hr>
      <p>{{ blog.body}}</p>
  </body>
</html>
```

