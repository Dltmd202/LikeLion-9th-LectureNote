# π¨π½βπ»13μ£Όμ°¨!

## 13.2 Static

### 13.2.1  μΉμμμ νμΌ

* μ μ  νμΌ

  λ―Έλ¦¬ μλ²μ μ μ₯λμ΄ μλ νμΌ

  μλ²μ μ μ₯λ κ·Έλλ‘λ₯Ό μλΉμ€ν΄μ£Όλ νμΌ

* λμ  νμΌ

  μλ²μ λ°μ΄ν°λ€μ΄ μ΄λμ λ κ°κ³΅λλ€μ λ³΄μ¬μ§λ νμΌ

  (μν©μ λ°λΌ λ¬λΌμ§ μ μμ)



### 13.2.2 μ μ  νμΌ

* Static

  κ°λ°μκ° μλ²λ₯Ό κ°λ°ν  λ λ―Έλ¦¬ λ£μ΄λμ μ μ νμΌ(Img, js, css)

* Media

  μ¬μ©μκ° μλ‘λ ν  μ μλ νμΌ

 

### 13.2.3 Setting

* static ν΄λ μμ±

setting.py

```python
import os
STATIC_URL = '/static/'

# νμ¬ static νμΌλ€μ΄ μ΄λμ μλμ§
STATICFILED_DIRS = [
  os.path.join(BASE_DIR, 'blog', 'static')
]
# satic νμΌμ μ΄λμ λͺ¨μκ±΄μ§
STATIC_ROOT = os.path.join(BASE_DIR, 'satic')
```



terminal

```bash
python manage.py collectstatic
```

* Static νμΌμ μμ§ν¨



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



