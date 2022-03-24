# Bind mount

The new volumes key mounts the project directory (current directory) on the host to /code inside the container,
allowing you to modify the code on the fly, without having to rebuild the image.

The environment key sets the FLASK_ENV environment variable, which tells flask run to run in development mode and reload the code on change. This mode should only be used in development.

```shell
docker-compose up
```

Point your web browser to [https://localhost:8000](http://localhost:8000).
