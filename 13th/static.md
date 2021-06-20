# 👨🏽‍💻13주차!

## 13.2 Static

### 13.2.1  웹에서의 파일

* 정적 파일

  미리 서버에 저장되어 있는 파일

  서버에 저장된 그대로를 서비스해주는 파일

* 동적 파일

  서버의 데이터들이 어느정도 가공된다음 보여지는 파일

  (상황에 따라 달라질 수 있음)



### 13.2.2 정적 파일

* Static

  개발자가 서버를 개발할 때 미리 넣어놓은 정적파일(Img, js, css)

* Media

  사용자가 업로드 할 수 있는 파일

 

### 13.2.3 Setting

* static 폴더 생성

setting.py

```python
import os
STATIC_URL = '/static/'

# 현재 static 파일들이 어디에 있는지
STATICFILED_DIRS = [
  os.path.join(BASE_DIR, 'blog', 'static')
]
# satic 파일을 어디에 모을건지
STATIC_ROOT = os.path.join(BASE_DIR, 'satic')
```



terminal

```bash
python manage.py collectstatic
```

* Static 파일을 수집함



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



