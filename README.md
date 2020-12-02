# About the project:
This repo contains the backend for the Barbr App

## Running using Docker:

`docker-compose build`

`docker-compose up`

## Setting up dev:

### Installing Postgres with Postgis
Mac: 
https://postgresapp.com/  
This comes with Postgis by default

Linux:  
Postgres: https://computingforgeeks.com/how-to-install-postgresql-13-on-ubuntu/  
Postgis: https://postgis.net/install/

### Installing Python and dependencies:

Installing Pyenv to manage python versions  
This is the best tool so far to manage multiple python versions

[Pyenv](https://github.com/pyenv/pyenv#installation)  
[Linux installation](https://www.liquidweb.com/kb/how-to-install-pyenv-virtualenv-on-ubuntu-18-04/)

Installing Python:

`pyenv install 3.9.0`

Installing Poetry to manage dependencies:

[Poetry](https://python-poetry.org/docs/#installation)

Creating virtualenv:

`pyenv virtualenv 3.9.0 barbr`

Activating virtualenv:

`pyenv activate barbr`

Clone the repository then:

`cd barbr_backend/`

Once the virtualenv is activated run  
`poetry install`

The command above will install all the required dependencies

In order to override settings or add your environment specific settings you can create a `settings_local.py`
file along with your `settings.py` file.
Anything added to the `settings_local.py` will override the default settings.

Running the services:

`python manage.py runserver`

#### Pre-commit hooks for code quality check
Setting up pre-commit hooks, run:  
`pre-commit install`

This will add git pre-commit hooks to format your code, imports, style.  
This is required to auto format your code before commit.  
Without these checks no PR should be merged. 
