# 👨🏽‍💻10주차!

## 10.7 CRUD - CREATE

### 10.7.1 Setting

views.py

```python
from django.shortcuts import render,get_object_or_404, redirect
from .models import Blog
from django.utils import timezone

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

def new(request):
  return render(request,
               'new.html')


def create(request):
  new_blog = Blog()
  new_blog.title = request.POST['title']
  new_blog.writer = request.POST['writer']
  new_blog.body = request.POST['body']
  new_blog.pub_date = timezone.now()
  new_blog.save()
  # 기존 html로 복귀
  return redirect('detail', new_blog.id)
```



urls.py

```python
from blog.views import *

urlpatterns = [
  path('admin/', name='home'),
  path('<str:id>', detail, name='detail'),
  path('new/', new, name='new'),
  path('create/', create. name='create')
]

```



new.html

```html
<h1>
  Write your Blog
</h1>
<form action="{% url 'create' %}" method="post">
  <!--- csrf 공격이 아님을 서버에 알림 --->
  {% csrf_token %}
  <p>
    제목: <input type="text" name="title">
  </p>
  <p>
    작성자: <input type="text" name="writer">
  </p>
  <p>
    본문: <textarea name="body" id="" cols="30" rows="10"></textarea>
  </p>
  <button type="submit">
    submit
  </button>
</form>
```



### 10.7.2 GET / POST

* GET

  데이터를 얻기 위한 요청

  데이터가 url에 보임

* POST

  데이터를 생성하기 위한 요청

  데이터 Url 안보임

  csrf 공격 방지

  * 웹사이트 취약점 공격