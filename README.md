# Heroku Django Starter Template

Project starter template for Django 1.11

Requirements

    Python 3.5+
    Postgres 9.4+

## Creating Your Project

Using this template to create a new Django app is easy::

    $ pip install django
    $ django-admin.py startproject --template=https://github.com/bahattincinic/heroku-django-template/archive/master.zip --name=Procfile helloworld --extension=py,md


## Deployment to Heroku

    $ git init
    $ git add -A
    $ git commit -m "Initial commit"

    $ heroku create
    $ git push heroku master

    $ heroku run python manage.py migrate

## Existing Heroku Project

    $ heroku login
    $ heroku git:remote -a project_name
    $ git push heroku master
    $ heroku run python manage.py migrate