# 👨🏽‍💻13주차!

## 13.3 Media

### 13.3.1 Setting



settings.py

```python
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')

MEDIA_URL = '/media/'

```



[PrName]/urls.py

```python
from blog.views import home
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
  path('admin/', admin.site.urls),
  path('', home, name='home'),
  path('blog/', include('blog.urls')),
  #staitc을 병렬적 형식으로 더해줌
] + satic(setting.MEDIA_URL, document_root=setting.MEDIA_ROOT)
```



model.py

```python
from django.db import models

class Blog(models.Model):
  title = models.CharField(max_Length=200)
  writer = medels.CharField(max_Length=100)
  pub_data = models.DateTimeField()
  body = models.TextField()
  #MEDIA_URL에 blog 폴더에 업로드 함을 지정함
  image = models.ImageField(upload_to = 'blog', blank=True, null=True) 
  '''모델 변경으로 migration 삭제
  	 migrate 파일 삭제
  	 db.sqlite 삭제
  '''
  
  #Override
  def __str__(self):
    return self.title
  
  def summary(self):
    return self.body[:100]
```



terminal

```bash
pip install pillow
```

* 이미지 필드 사용을 위한 모듈



```bash
python manage.py makemigrations
python manage.py migrate
```





new.html

```html
{% extends 'base.html' %}

{% block content %}
<h1>
  Write your Blog
</h1>
<form action="{% url 'create' %}" method="post" enctype="multipart/from-data">
  <!--- csrf 공격이 아님을 서버에 알림 --->
  {% csrf_token %}
  <p>
    제목: <input type="text" name="title">
  </p>
  <p>
    작성자: <input type="text" name="writer">
  </p>
  <p>
    사진: <input type="file" name="image">
  </p>
  <p>
    본문: <textarea name="body" id="" cols="30" rows="10"></textarea>
  </p>
  <button type="submit">
    submit
  </button>
</form>
{% endblock %}
```



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





detail.html

```html
{% extends 'base.html' %}
	{% block content %}
    <h1>{{ blog.title }}</h1>
    <div>
      {{ blog.writer }}
      {{ blog.pub_date }}
    </div>
      <hr>
			<p>
        <!----- image의 경로를 호출해야 함 ----->
      	<img src="{% blog.image.url %}" alt="">  
			</p>
      <p>{{ blog.body}}</p>
    <a href="{%  url 'edit' %}">수정하기</a>
	{% block content %}
```

