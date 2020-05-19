# Dockerized PHP Environment

Set of Docker files to set up a development environment for PHP (Laravel in particular) with artisan and composer.

The environment uses nginx to serve files, MySQL as database, and Adminer to manage the database.

---

## Setup

> Note: Obviously, you need Docker installed. You also need docker-compose - Docker Desktop for Windows includes docker-compose.

1. Clone or download the repository
2. Place your project files in src folder. Make sure your "public" folder exists as src/public
3. Run the docker services:

    `$ docker-compose up -d`

4. That's it! Your application is hosted and your services should now be accessible on the following urls:

    - Web server: `localhost` or `localhost:80`
    - Adminer: `localhost:9090`

5. You can run composer and artisan commands like so:

    ```
    $ docker-compose run composer install
    $ docker-compose run artisan migrate
    ```

---

## Notes

- Take a look at `docker-compose.yml` and modify it to suit your configuration.
- Make sure the database particulars in your .env matches those in `docker-compose.yml`
  - In particular, the database host name should be the name of the database's service, i.e. `db`. Docker services are named after their service name in the Docker network.
- The database is persisted in the database folder
- To use a different "public" folder, modify the root location in `nginx/default.conf`

---

## License

Licensed under the MIT license.
