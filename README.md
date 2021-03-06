# Dockerized PostgreSQL

Work in Progress

Basically Alpine PostgreSQL with official Postgres entrypoint.

Takes the same parameters as: [Official Postgres](https://hub.docker.com/_/postgres/)

Added the specification of database encoding and collate for Atlassian applications:

Example:

~~~~
$ docker run --name postgres -d \
    -e 'POSTGRES_USER=jira' \
    -e 'POSTGRES_PASSWORD=jellyfish' \
    -e 'POSTGRES_DB=jiradb' \
    -e 'POSTGRES_ENCODING=UNICODE' \
    -e 'POSTGRES_COLLATE=C' \
    -e 'POSTGRES_COLLATE_TYPE=C' \
    blacklabelops/postgres
~~~~

> Starts a database for Atlassian Jira.

# Database Create Statement

You can specify an initial database create statement.

~~~~
$ docker run --name postgres -d \
    -e 'POSTGRES_USER=jira' \
    -e 'POSTGRES_PASSWORD=jellyfish' \
    -e 'POSTGRES_DB=jiradb' \
    -e 'POSTGRES_DB_CREATE=CREATE DATABASE userdatabase ' \
    blacklabelops/postgres
~~~~

> Starts a database for Atlassian Jira.
