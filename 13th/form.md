# ๐จ๐ฝโ๐ป13์ฃผ์ฐจ!

## 13.4 Form

### 13.4.1 Setting

Blog/forms.py

```python
from django import form
from .models import Blog

class BlogForm(forms.ModelForm):
  class Meta:
    model = Blog
    fields = ['title', 'writer', 'body', 'image']
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
	form = BlogForm(request.POST, request.FILES)
  if from.is_valid():
    #pub_date 
    new_blog = form.save(commit=False)
    new_blog.pub_date = timezone.now()
    new_blog.save()
    return redirect('detail', new_blog.id)
  # ๊ธฐ์กด html๋ก ๋ณต๊ท
  return redirect('home')

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




