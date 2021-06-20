# 👨🏽‍💻13주차!

## 13.1 Templete 상속

### 13.1.1  Setting

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
        <a class="navbar-brand" href="#">Navbar</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="#">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Link</a>
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
{% endblock %}
```



setting.py

```python
TEMPLATES = [
  'DIRS' : ['[PrName]/templates'],
]
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
      <p>{{ blog.body}}</p>
    <a href="{%  url 'edit' %}">수정하기</a>
	{% block content %}
```



blog/urls.py

```python
from .views import *

urlpatterns = [
  path('<str:id>', detail, name='detail'),
  path('new/', new, name="new"),
  path('create/', create, name="create"),
	path('edit/<str:id>', edit, name="edit"),
  path('update/<str:id>', update, name="update"),
  path('delete/<str:id>', delete, name="delete"),
]
```



[PrName]/urls.py

```python
from blog.views import home

urlpatterns = [
  path('admin/', admin.site.urls),
  path('', home, name='home'),
  path('blog/', include('blog.urls'))
]
```

