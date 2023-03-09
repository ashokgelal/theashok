---
title: "Postgres Password Secrets in Docker"
date: 2023-03-08T18:19:04-05:00
draft: false
tags: ['docker', 'postgres']
---

I needed a way to spin up a [postgres container](https://hub.docker.com/_/postgres) without hardcoding any credentials. But it turns out postgres wants at least `POSTGRES_PASSWORD` being set.
<!--more-->

After some digging, I found out that there is a very non-trivial way to accomplish what I wanted to achieve. It needed the password to be provided in a file and set `secrets` in the `docker-compose.yml`. Here is how:


```.yml
version: '3'
services:
  database:
    container_name: database
    environment:
      POSTGRES_PASSWORD_FILE: /run/secrets/postgres_password
    image: postgis/postgis:13-master
    volumes:
      - /data/database:/var/lib/postgresql/data
    secrets:
      - postgres_password
secrets:
  postgres_password:
    file: ./docker_postgres_password
```

Notice `POSTGRES_PASSWORD_FILE` instead of just `POSTGRES_PASSWORD`. Also notice at the very bottom how I've mentioned that `postgres_password` will be in a file named `docker_postgres_password`. The contents of this file is simply just the password itself and nothing else.

