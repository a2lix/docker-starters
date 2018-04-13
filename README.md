# Docker Starter - DEV1 (PHP7.2 & Xdebug2.6 / Postgres10.3 / Adminer)

A simple Docker PHP starter with the PHP built-in web server.

---

## Start:

- ```docker-compose build```
- Use the docker Composer once to init your project. By example, for:
  - a Symfony FLEX skeleton  ```docker run --rm --interactive --tty --volume $PWD:/app --user $(id -u):$(id -g) composer create-project symfony/skeleton app```
  - a Symfony FLEX website skeleton  ```docker run --rm --interactive --tty --volume $PWD:/app --user $(id -u):$(id -g) composer create-project symfony/website-skeleton app```
- Now use docker-compose as usual. By example:
  - start/restart docker-compose ```docker-compose up``` & ```docker-compose down```
  - add new Composer packages ```docker-compose exec --user $(id -u):$(id -g) app composer require maker```
  - execute commands ```docker-compose exec --user $(id -u):$(id -g) app bin/console clear:cache```, ```docker-compose exec --user $(id -u):$(id -g) app vendor/bin/php-cs-fixer fix --verbose```, ...

And enjoy ```http://localhost:8000``` in your browser.

### Postgres

In your Symfony FLEX project, update **/app/config/packages/doctrine.yaml** to:

```
doctrine:
    dbal:
        # configure these for your database server
        driver: 'pdo_pgsql'
        server_version: '10.3'
        # charset: utf8mb4
```

### XDebug

Enable it on demand with the URL parameter ?XDEBUG_SESSION_START


### Adminer

Enjoy ```http://localhost:8080``` in your browser.

---

## Resources:

- https://hub.docker.com/_/php/ (Alpine FTW)
- https://hub.docker.com/_/composer/
- https://hub.docker.com/_/postgres/  (Alpine FTW)
- https://hub.docker.com/_/adminer/
