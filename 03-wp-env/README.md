# Wordpess example

With `env` settings in compose file and showcasing `depends_on`.

> Note:
>The docker volumes db_data and wordpress_data persists updates made by WordPress to the database, as well as the installed themes and plugins.

WordPress Multisite works only on ports 80 and 443.

Now, run `docker-compose up -d` from your project directory.

This runs docker-compose up in detached mode, pulls the needed Docker images, and starts the wordpress and database containers, as shown in the example below.

Stop containers and remove volumes

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