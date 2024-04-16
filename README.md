<H1 align="center">First Django App</H1>
<p align="center">🚀 Project to create a first app in Django for future references</p>

## Resources Used

* Python 3.10.6
* Django


## Creating a Project

<details>
 <summary>Click to show content</summary>

Creating a project called mysite

```
django-admin startproject mysite
```

The project structure will be created this way

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


</details>


## Package creation

<details>
 <summary>Click to show content</summary>

It consists of creating a package that follows a convention and will be created at the same mysite level to serve as the representation of a package

```
python manage.py startapp polls
```

```
mysite/
polls/
```


</details>




## View Creation

<details>
 <summary>Click to show content</summary>

```
polls/views.py
```

```
from django.http import HttpResponse
def index(request):
 return HttpResponse("Hello, world. You're at the polls index.")
```

To call this view, it is necessary to map it so that it can be inserted into the routes through a URLconf

</details>




## Mapping routes

<details>
 <summary>Click to show content</summary>


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

</details>



## Starting the server

Command necessary for the server to start, being able to change localhost as a parameter

```
python manage.py runserver
```
