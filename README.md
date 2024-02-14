# trackmate
### steps to create a django project

commands to be followed:

 django-admin startproject <project_name> -----> this command creates a django folder with the project name.
 cd <project-name> ------> redirects to project folder
 python manage.py startapp <app-name> ---------> this command creates the working django project inside the project folder
 python manage.py makemigrations
 python manage.py migrate ---------> these two commands are used to detect changes and update the website on server
 python manage.py runserver --------> runs the project and shows the default output 

changes to be made:

1. create a urls.py file in <app-name> and add create the urls for the views created

eg:
from django import views
from django.urls import path
from .views import expense_list

urlpatterns = [
    path('', expense_list, name='expense_list'),
    # Add more URL patterns as needed for other views
]


2. then add <app-name> urls file to the <project-name>/urls.py file
   
eg:
path('',include('finance_app.urls')),

3. Dont forget to add ur <app-name> to installed apps in settings.py file
   
eg:
   INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'finance_app', #this the app included
    
]

Now you are all set create template folder to add all ur static files i.e html,css etc. then create views for the html pages and add them in urls.py of <app-name> folder.
apply migrations and run server to see the output of yout code.
