# Message Broker - Server

## Build

Execute the command below to build an image from the Dockerfile:

```bash
docker build . -t sparks/message-broker-server:latest
```

## Run

Execute the command below to start a container from the image created previously:

```bash
docker run -d --name message-broker-server \
-e RABBITMQ_DEFAULT_USER=<ADMIN_USERNAME (ex: admin)> \
-e RABBITMQ_DEFAULT_PASS=<ADMIN_PASSWORD (ex: admin)> \
-p <BROKER_EXTERNAL_PORT (ex: 4101)>:5672 \
-p <MANAGER_EXTERNAL_PORT (ex: 4102)>:15672 \
sparks/message-broker-server
```

## Stop

Execute the command below to stop the container:

```bash
docker stop sparks-message-broker-server
```
