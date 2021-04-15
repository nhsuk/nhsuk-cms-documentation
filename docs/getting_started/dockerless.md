# Dockerless

If you don't want to use docker, the app can be run in a unix-based Python 3 environment.

## Build the frontend

See [frontend-build getting started](../development/frontend-build.md#getting-started)

## Install postgres server and create a database

The app connects to a postgres database, so you need to have one available.

1. [Install the postgres server](https://www.postgresql.org/download/).
2. [Create a database](https://www.postgresql.org/docs/9.1/manage-ag-createdb.html) with the `createdb wagtail` command.
3. Your postgres username and password will depend on how you've installed it. You will need these details when you set environment variables in the next step.

## Set environment variables

Recommended environment variables are in the `example.env` file. These variables can be imported into your pipenv environment by copying the file to `.env`. The `.env` file will be used by pipenv automatically. (See https://pipenv-fork.readthedocs.io/en/latest/advanced.html#automatic-loading-of-env)

You may need to change some of the variables in `.env` to suit your environment such as the `DB_USER` and `DB_PASS` variables.

A full list of environment variables and what they do can be found in our [configuration](/deployment/configuration.md) docs.

## Install python dependencies

```sh
pip install pipenv==2020.11.15
pipenv install --ignore-pipfile
```

## Run the django development server

- Run database migrations: `python manage.py migrate`
- Build index for wagtail postgres search `python manage.py update_index` (Only needs to be run one time for any given database)
- Create a superuser: `python manage.py createsuperuser`
- Start the server: `python manage.py runserver`

## Install test data (if required)

`python manage.py create_test_data`

This command will only create pages if there are none in the database already.
If you want to clear the database to install fresh test data, run `python manage.py flush`.

Running the flush command will clear all data out of the database so you will need to
create your superuser again with `python manage.py createsuperuser`.
