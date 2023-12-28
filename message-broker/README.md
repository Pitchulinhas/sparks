# Message Broker

Message broker to comunication between services.

## Requirements

- Create a **.env** (there is an example file named _.env.example_) file or create environment variables used in **docker-compose.yml**.

## Docker Image

### Build

Execute the command below to build an image from the Dockerfile:

```bash
docker build . -t sparks/message-broker:latest
```

### Start

Execute the command below to start a container from the image created previously:

```bash
docker run -d --name sparks-message-broker \
-e RABBITMQ_DEFAULT_USER=<ADMIN_USERNAME (ex: admin)> \
-e RABBITMQ_DEFAULT_PASS=<ADMIN_PASSWORD (ex: admin)> \
-p <BROKER_EXTERNAL_PORT (ex: 4101)>:5672 \
-p <MANAGER_EXTERNAL_PORT (ex: 4102)>:15672 \
sparks/message-broker
```

### Stop

Execute the command below to stop the container:

```bash
docker stop sparks-message-broker
```

## Docker Compose

### Start

Execute the command below to start message broker:

```bash
docker-compose up -d
```

### Stop

Execute the command below to stop message broker:

```bash
docker-compose down
```
