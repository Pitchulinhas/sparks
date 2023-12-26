# Authorization Server - Application

## Build

Execute the command below to build an image from the Dockerfile:

```bash
docker build . -t sparks/authorization-server-app:latest
```

## Run

Execute the command below to start a container from the image created previously:

```bash
docker run -d --name sparks-authorization-server-app \
-e KEYCLOAK_ADMIN=<ADMIN_USERNAME (ex: admin)> \
-e KEYCLOAK_ADMIN_PASSWORD=<ADMIN_PASSWORD (ex: admin)> \
-e KC_DB=<DB_TYPE (ex: postgres, ...)> \
-e KC_DB_URL=<JDBC_URL (ex: jdbc:postgresql://localhost:5432/authorization)> \
-e KC_DB_USERNAME=<DB_USERNAME (ex: postgres)> \
-e KC_DB_PASSWORD=<DB_PASSWORD (ex: postgres)> \
-e KC_HOSTNAME=<HOSTNAME (ex: localhost)> \
-e KC_HOSTNAME_PORT=<EXTERNAL_PORT (ex: 4001)> \
-p <EXTERNAL_PORT (ex: 4001)>:8443 \
sparks/authorization-server-app start --optmized
```

## Stop

Execute the command below to stop the container:

```bash
docker stop sparks-authorization-server-app
```
