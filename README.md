<H1 align="center">Primeiro App Django</H1>
<p align="center">🚀 Projeto de criação de um primeiro app em Django para referências futuras</p>

## Recursos Utilizados

* Python 3.10.6
* Django


## Criando um Projeto

Criando um projeto chamado mysite

```
django-admin startproject mysite
```

A estrutura do projeto será criado dessa forma

```
mysite/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        asgi.py
        wsgi.py
```

## Criação de pacote

Consiste na criação de um pacote que segue uma convenção e será criado no mesmo nivel de mysite para servir como a representação de um pacote

```
python manage.py startapp polls
```

```
mysite/
polls/
```

## Criação da View

```
polls/views.py
```

```
from django.http import HttpResponse
def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")
```

Pará chamar esta view é necessário mapea-la para que seja inserida nos rotas através de um URLconf


## Mapeando rotas

### polls/urls.py

```
from django.urls import path

from . import views

urlpatterns = [
    path("", views.index, name="index"),
]
```

### mysite/urls.py

```
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path("polls/", include("polls.urls")),
    path("admin/", admin.site.urls),
]
```

## Iniciando o servidor 

Comando necessário para que o servidor seja iniciado, podendo trocar o localhost como parâmetro

```
python manage.py runserver
```
   
