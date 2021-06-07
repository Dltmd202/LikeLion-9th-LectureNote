# 👨🏽‍💻10주차!

## 10.9 CRUD - DELETE

### 10.9.1 Setting

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

def edit(request, id):
  edit_blog = Blog.objects.get(id = id)
  return render(request, 'edit.html',{
    'blog': edit_blog
  })

def update(request, id):
  update_blog = Blog.objects.get(id=id)
  update_blog.title = request.POST['title']
  update_blog.writer = request.POST['writer']
  update_blog.body = request.POST['body']
  update_blog.upb_date = timezone.now()
  update_blog.save()
  return redirect('detail', update_blog.id)
  
def delete(request, id):
  delete_blog = Blog.objects.get(id=id)
  delete_blog.delete()
  return redirect('home')

```



urls.py

```python
from blog.views import *

urlpatterns = [
  path('admin/', name='home'),
  path('<str:id>', detail, name='detail'),
  path('new/', new, name='new'),
  path('create/', create. name='create'),
	path('edit/<str:id>', edit, name='edit'),
  path('update/<str:id>', update, name='update'),
  path('delete/<str:id>', delete, name='delete')
]

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
    <a href="{%  url 'edit' blog.id%}">수정하기</a>
        <a href="{%  url 'delete' blog.id %}">삭제하기</a>
  </body>
</html>
```



edit.html

```html
<h1>
  Update your Blog
</h1>
<form action="{% url 'update' blog.id %}" method="post">
  <!--- csrf 공격이 아님을 서버에 알림 --->
  {% csrf_token %}
  <p>
    제목: <input type="text" name="title" value ="{{ blog.title }}">
  </p>
  <p>
    작성자: <input type="text" name="writer" value="{{ blog.writer }}">
  </p>
  <p>
    본문: <textarea name="body" id="" cols="30" rows="10">{{ blog.body }}</textarea>
  </p>
  <button type="submit">
    submit
  </button>
</form>
```

