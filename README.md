





# Webapp

Webapp is a Django application designed as a starting point for user-based projects.

## Prerequisites

Before getting started, make sure you have a superuser profile created for your Django project.

## Installation

1. Download the `webapp` project and install its requirements using pip:</br>

`pip install -r requirements.txt`</br>


2. Place the `webapp` folder in your project directory, alongside your SQL file.</br>

```
.
├── PROJECT
│   ├── PROJECT 
│   ├── db.sqlite3
│   ├── app
│   ├── manage.py
│   ├── templates
│   │   ├── base_external.html
│   │   ├── base_internal.html
│   │   └── webapp
│   │       ├── business.html
│   │       ├── home.html
│   │       ├── login.html
│   │       ├── profile.html
│   │       ├── register.html
│   │       ├── search_results.html
│   │       ├── settings.html
│   │       └── snippets
│   │           ├── footer.html
│   │           ├── navbar.html
│   │           ├── search.html
│   │           └── sidebar.html
│   └── webapp
│       ├── admin.py
│       ├── apps.py
│       ├── forms.py
│       ├── migrations
│       ├── models.py
│       ├── tests.py
│       ├── urls.py
│       └── views.py
└── README.md
```

3. Include the `webapp` app in your project's `settings.py` by adding it to the `INSTALLED_APPS` list:</br>

```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    
    # Packages
    'djmoney',
    'django_countries',

    # Custom Apps
    'webapp',
]

LOGIN_REDIRECT_URL = 'webapp:login'
```



Include the webapp app in your project's urls.py:
```
from django.contrib import admin
from django.urls import path, include
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('webapp.urls'))
] + static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)
```

Run migrations to create the database tables:</br>
`django-admin makemigrations && django-admin migrate`</br>

You're all set! Now, start the server by running the following command:</br>
`python manage.py runserver`</br>


### Usage

Visit the Django admin panel at http://localhost:8000/admin/ and start building your user-based project with Webapp.

### Author
Built by KS Tsoaela