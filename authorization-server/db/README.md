# Authorization Server - Database

## Build

Execute the command below to build an image from the Dockerfile:

```bash
docker build . -t sparks/authorization-server-db:latest
```

## Start

Execute the command below to start a container from the image created previously:

```bash
docker run -d --rm --name sparks-authorization-server-db \
-e POSTGRES_PASSWORD=<DB_PASSWORD (ex: postgres)> \
-e APP_DB_NAME=<APP_DB_NAME (ex: authorization)> \
-p <EXTERNAL_PORT (ex: 4002)>:5432 \
sparks/authorization-server-db
```

## Stop

Execute the command below to stop the container:

```bash
docker stop sparks-authorization-server-db
```
