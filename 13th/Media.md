# ๐จ๐ฝโ๐ป13์ฃผ์ฐจ!

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
  #staitc์ ๋ณ๋ ฌ์  ํ์์ผ๋ก ๋ํด์ค
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
  #MEDIA_URL์ blog ํด๋์ ์๋ก๋ ํจ์ ์ง์ ํจ
  image = models.ImageField(upload_to = 'blog', blank=True, null=True) 
  '''๋ชจ๋ธ ๋ณ๊ฒฝ์ผ๋ก migration ์ญ์ 
  	 migrate ํ์ผ ์ญ์ 
  	 db.sqlite ์ญ์ 
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

* ์ด๋ฏธ์ง ํ๋ ์ฌ์ฉ์ ์ํ ๋ชจ๋



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
  <!--- csrf ๊ณต๊ฒฉ์ด ์๋์ ์๋ฒ์ ์๋ฆผ --->
  {% csrf_token %}
  <p>
    ์ ๋ชฉ: <input type="text" name="title">
  </p>
  <p>
    ์์ฑ์: <input type="text" name="writer">
  </p>
  <p>
    ์ฌ์ง: <input type="file" name="image">
  </p>
  <p>
    ๋ณธ๋ฌธ: <textarea name="body" id="" cols="30" rows="10"></textarea>
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
  #image ์๋ก๋
  new_blog.image = request.FILES('image')
  new_blog.save()
  # ๊ธฐ์กด html๋ก ๋ณต๊ท
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
        <!----- image์ ๊ฒฝ๋ก๋ฅผ ํธ์ถํด์ผ ํจ ----->
      	<img src="{% blog.image.url %}" alt="">  
			</p>
      <p>{{ blog.body}}</p>
    <a href="{%  url 'edit' %}">์์ ํ๊ธฐ</a>
	{% block content %}
```

