# postgresql-docker-starter

**IMPORTANT:** This repository is working but documentation is work in progress.

Containerized PostgreSQL starter package that creates users with necessary permissions.

# What does it do?

Upon first initialization, a database is setup with the following configuration.

## Users

Two users are created upon initialization.

- One **admin user** named based on the env variable `DB_ADMIN_USER` and the password is based on `DB_ADMIN_PASSWORD` (see below)
- One **app user** named based on the env variable `DB_APP_USER` and the password is based on `DB_APP_PASSWORD` (see below)

## Database

A database is created. This database is owned by the admin user and named based on the env variable `DB_NAME`, with a schema named based on `DB_SCHEMA` and also owned by the admin user

## Permissions

To come.


All of the above permissions are DEFAULT PRIVILEGES, meaning that they apply per default to all future items that are created going forward.

# Setup

Follow the steps below to setup your PostgreSQL database.

### Clone repository

```bash
git clone https://github.com/stefnba/postgresql-docker-starter.git
```

### Create .env file

Create a `.env` file in your project root.

### Specify enviornment variables for configuration

Specify the following variables in your `.env` file:

```bash
DB_HOST="Host of the database"
DB_PORT="Port of the database"
DB_ROOT_PASSWORD="Root passtword of database for user postgres"
DB_NAME="Name of database that will be created"
DB_SCHEMA="Schema name within database"
DB_ADMIN_USER="Name of admin user with advanced permissions"
DB_ADMIN_PASSWORD="Password of admin user"
DB_APP_USER="Name of user that has "
DB_APP_PASSWORD="Password of app user"
```

### Spin up docker container running the database

```bash
docker compose up
```
