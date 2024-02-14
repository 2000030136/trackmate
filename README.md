# Trackmate
## Steps to create a django project

### Commands to be followed:

 1. ```django-admin startproject <project_name>``` ---> this command creates a django folder with the project name.
 2. ```cd <project_name>``` ------> redirects to project folder
 3. ```python manage.py startapp <app_name>``` ---------> this command creates the working django project inside the project folder
 4. ```python manage.py makemigrations```
 5. ```python manage.py migrate``` ---------> these two commands are used to detect changes and update the website on server
 6. ```python manage.py runserver``` --------> runs the project and shows the default output 

### Changes to be made:

1. Create a urls.py file in <app_name> and add create the urls for the views created

eg:
``` 
from django import views
from django.urls import path
from .views import expense_list

urlpatterns = [
    path('', expense_list, name='expense_list'),
    # Add more URL patterns as needed for other views
]
```

2. Then add <app-name> urls file to the <project_name>/urls.py file
   
eg:
```
path('',include('finance_app.urls')),
```
3. Dont forget to add ur <app_name> to installed apps in settings.py file
   
eg:
```
   INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'finance_app', #this the app included
    
]
```
Now you are all set create template folder to add all ur static files i.e html,css etc. then create views for the html pages and add them in urls.py of <app_name> folder.
apply migrations and run server to see the output of yout code.
