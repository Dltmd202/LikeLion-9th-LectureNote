# 👨🏽‍💻13주차!

## 13.6 User 확장과 인증(실습)

### 13.6.1 Setting



Terminal

```bash
python manage.py startapp accout
```



settings.py

```python
INSTALLED_APPS =[
  'blog',
  'account'
]
```



account/ views.py

```python
from django.shortcuts import render, redirect
from django.contrib.auth.forms  import AuthenticationForm, UserCreationForm
from django.contrib.auth import authenticate, login, logout

def login_view(request):
  if request.METHOD == 'POST':
  	form = AuthenticationForm(request=request, data = request.POST)
    if form.is_valid():
      # is_valid -> cleaned_data
      username = form.cleaned_data.get("username")
      password = form.cleaned_data.get("password")
      # authenticate process
      user = authenticate(request=request, username= username, password= password)
      if user is not None:
        login(request, user)
      return redirect('home')
        
  form = AuthenticationForm()
  return render(request, 'login.html', {'form': form})

def logout_view(request):
  logout(request)
  return redirect('home')
```





account/urls.py

```python
from django.urls import path
from .views import *

urlpatterns = [
  path('login/', login_view, name='login'),
  path('logout/', logout_view, name='logout')
]
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
  path('account/', include('account.urls'))
  #staitc을 병렬적 형식으로 더해줌
] + satic(setting.MEDIA_URL, document_root=setting.MEDIA_ROOT)
```



templates/login.html

```html
{% extends 'base.html' %}

{% block content %}

<h1>Login</h1>

<form action="{% url 'login' %}"  method="post">
  {% csrf_token %}
  {{ form.as_p }}
  <button type="submit"> submit</button>
</form>
{% endblock %}
```



base.html

```html
<html>
  <head>
    <!-- JavaScript Bundle with Popper -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/js/bootstrap.bundle.min.js" integrity="sha384-gtEjrD/SeCtmISkJkNUaaKMoLD0//ElJ19smozuHV6z3Iehds+3Ulb9Bn9Plx0x4" crossorigin="anonymous"></script>
  </head>
  <body>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="{% url 'home' %}">
          <!----- Navbar -> img ----->
            <img stc="{% static 'likelion.png'}" alt="" width="25" height="25">
        </a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <!----- url new ----->
              <a class="nav-link active" aria-current="page" href="{% url 'new' %}">Writer</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="{% url 'login' %}">Login</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="{% url 'logout' %}">Logout</a>
            </li>
            <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                Dropdown
              </a>
              <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
                <li><a class="dropdown-item" href="#">Action</a></li>
                <li><a class="dropdown-item" href="#">Another action</a></li>
                <li><hr class="dropdown-divider"></li>
                <li><a class="dropdown-item" href="#">Something else here</a></li>
              </ul>
            </li>
            <li class="nav-item">
              <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
            </li>
          </ul>
          <form class="d-flex">
            <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
            <button class="btn btn-outline-success" type="submit">Search</button>
          </form>
        </div>
      </div>
    </nav>
    

    {% block content %}
    {% endblock %}
  </body>
</html>
```



home.html

```html
{% extends 'base.html' %}
{% block content %}
{% if user.is_authenticated %}
	{{ user.user_name }}
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
{% endblock %}
```




