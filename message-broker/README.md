# Message Broker

Message broker to comunication between services.

## Requirements

- Build image **sparks/message-broker-server** from Dockerfile located in _server_ folder;
- Create a **.env** (there is an example file named _.env.example_) file or create environment variables used in **docker-compose.yml**.

## Start

Execute the command below to start message broker:

```bash
docker-compose up -d
```

## Stop

Execute the command below to stop message broker:

```bash
docker-compose down
```
