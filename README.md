# Docker Starter 1 (PHP7.2 / Postgres10.3)

A simple Docker starter for Symfony with its PHP built-in webserver use.

---

### Start:

- ```docker-compose build```
- ```docker run --rm --interactive --tty --volume $PWD:/app --user $(id -u):$(id -g) composer create-project symfony/website-skeleton app```
- ```docker run --rm --interactive --tty --volume $PWD/app:/app --user $(id -u):$(id -g) composer require __ADDITIONAL_REQUIRE__```
- Update **/app/config/packages/doctrine.yaml** for Postgres use:
    ```
    doctrine:
        dbal:
            # configure these for your database server
            driver: 'pdo_pgsql'
            server_version: '10.3'
            # charset: utf8mb4
    ```
- ```docker-compose up```
- Enjoy ```http://localhost:8000``` and commands ```docker-compose exec app bin/console __CMD__```, ...

---

### Resources:

- https://hub.docker.com/_/php/ (Alpine FTW)
- https://hub.docker.com/_/composer/
- https://hub.docker.com/_/postgres/  (Alpine FTW)
- https://hub.docker.com/_/adminer/
