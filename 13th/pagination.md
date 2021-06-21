# 👨🏽‍💻13주차!

## 13.8 Paginator

### 13.8.1 A 태그를 이용한 Paginator

views.py

```python
from django.shortcuts import render,get_object_or_404, redirect
from django.core.paginator import Paginator
from .models import Blog
from django.utils import timezone

def home(request):
  # 최신순으로 정렬된 객체 
  blogs = models.objects.order_by('-pub_date')
  search = request.GET.get('search')
  # 필터링 기능. 
  if search = 'true':
    author = request.GET.get('writer')
    blogs = Blog.objects.filter(writer = authro)
    return render(request, 'home.html', {'blogs': blogs})
    
  paginator = Paginator(blogs, 3)
  page = request.GET.get('page')
  blogs = paginato.get_page(page)
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
  #image 업로드
  new_blog.image = request.FILES('image')
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



home.html

```html
{% extends 'base.html' %}
{% block content %}
{% if user.is_authenticated %}
	{{ user.location }}
	{{ user.nickname }}
	{{ user.nickname }}
	{{ user.user_name }}
	<a href="?search=true&writer={{user.nickname}}">내가 쓴 글</a>
{% endif %}
<h1>Blog Project</h1>
    {% for blog in blogs %}
    <div>
      <h3>
        {{ blog.title }}
      </h3>
    	{{ blog.writer }}
    	{{ blog.summury }}
    </div>
    {% endfor %}
<!----- paginator 객체가 필요 없을 때 ---->
	{% if blogs.has_previous %}
		<a href="?page=1">처음</a>
		<a href="?page={{ blogs.previous_page_number }}">이전</a>
	{% endif %}
	<span>{{ blogs.number }}</span>
	<span>of</span>
	<span>{{ blogs.paginator.num_pages }}</span>
	{% if blogs.has_next %}
		<a href="?page={{ blogs.next_page_number}}">다음</a>
		<a href="?page={{ blogs.paginator.num_pages }}">마지막</a>
	{% endif %}
{% endblock %}
```



