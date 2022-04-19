# Wordpess example

With `env` settings in a standalone `.env` file.

Now, run `docker-compose --env-file .env-example up-d` from your project directory.

This runs `docker-compose` up in detached mode, pulls the needed Docker images,
and starts the wordpress and database containers, as shown in the example below.

Stop containers and remove volumes:

```shell
➜ docker-compose stop
Stopping wp          ... done
Stopping wp-mysql-db ... done

➜ docker-compose rm
Going to remove wp, wp-mysql-db
Are you sure? [yN] y
Removing wp          ... done
Removing wp-mysql-db ... done
```

Open your browser and go to http://http://localhost:8000/