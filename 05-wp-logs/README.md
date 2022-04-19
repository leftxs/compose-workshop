# Wordpess example

With `env` settings in compose file.

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

## Logs

```shell
docker-compose logs <name-of-service>
```

For example

```shell
docker-compose logs db
```

For all services

```
docker-compose logs
```


You can start Docker compose in detached mode and attach yourself to the logs of all container later.
If you're done watching logs you can detach yourself from the logs output without shutting down your services.

Use `docker-compose up -d` to start all services in detached mode (`-d)` (you won't see any logs in detached mode)
Use `docker-compose logs -f -t` to attach yourself to the logs of all running services, whereas -f means you follow the log output and the `-t` option gives you timestamps (See Docker reference)
Use `Ctrl + z` or `Ctrl + c` to detach yourself from the log output without shutting down your running containers
If you're interested in logs of a single container you can use the docker keyword instead:

Use `docker logs -t -f <name-of-service>`

Save the output
To save the output to a file you add the following to your logs command:

`docker-compose logs -f -t >> myDockerCompose.log`

Unfortunately we need to run docker-compose logs separately from docker-compose run.
To get this to work reliably we need to suppress the docker-compose run exit status then redirect the log and exit with the right status.

```shell
#!/bin/bash
set -euo pipefail
docker-compose run app | tee app.log || failed=yes
docker-compose logs --no-color > docker-compose.log
[[ -z "${failed:-}" ]] || exit 1
```

