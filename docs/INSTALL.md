# Installation Guide

### Requirements

* Python 3.5+
* Postgres 9.4+

### Installation

#### OSX

Install Homebrew

    $ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

Install Required Packages:

    $ brew install python3
    $ brew install postgresql


#### Ubuntu/Debian

Install Required Packages:
(python3 is already installed as default on 16.04)

    $ sudo apt-get install python3-dev libpq-dev postgresql
  
Set postgres password:

    $ sudo -u postgres psql -c "ALTER USER postgres PASSWORD 'postgres';"

Add postgres as default user: (write this in your .bashrc or .zshrc to make it persistent)

    $ export PGUSER=postgres
    $ export PGPASSWORD=postgres

### Building the Project

Create Virtual Environment (3.5+)

    $ virtualenv --python=$(which python3) env
    $ sourve env/bin/activate

Setup PostgreSQL Database

    $ initdb /usr/local/var/postgres
    $ postgres -D /usr/local/var/postgres/ #in another terminal
    $ createuser --superuser postgres
    $ createdb -U postgres db_name

Clone the repository

install requirements

    $ pip install -r requirements/dev.txt

copy settings file

    $ cp {{ project_name }}/settings/dev.py-dist {{ project_name }}/settings/dev.py
    $ export DJANGO_SETTINGS_MODULE="{{ project_name }}.settings.dev"

To run the project, Follow the following commands:

    $ python manage.py migrate
    $ python manage.py runserver