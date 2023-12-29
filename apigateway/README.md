# API Gateway

Sparks API Gateway.

## Standalone application

### Requirements

You will need the following requirements:

- JDK 17
- Maven

### Environment variables

You will need to set the environment variables below:

- **PORT:** Port to run the server;
- **CONFIG_SERVER_BASIC_AUTH_URL:** URL of Config Server using Basic authorization.

**Example**

```text
PORT=8080

CONFIG_SERVER_BASIC_AUTH_URL=http://admin:admin@localhost:8888
```

### Dependencies

Execute the command below to install project dependencies:

```shell
mvn clean install -DskipTests
```

### Run

**Tests**

Execute the command below to test the project:

```shell
mvn clean test
```

**Development**

Execute the command below to run the project in development mode:

```shell
mvn clean spring-boot:run
```

**Production**

Execute the command below to build the project:

```shell
mvn clean package -DskipTests
```

To run the generated JAR navigate into _target_ folder and execute the command below:

```shell
java -Dspring.profiles.active=production -jar configserver-0.0.1-SNAPSHOT.jar
```

## Docker Image

### Requirements

You will need the following requirements to build a Docker image of the application:

- Application built

### Build

To build the image execute the command below in project root:

```shell
docker build . -t sparks/api-gateway:latest
```

## Docker Container

### Requirements

You will need the following requirements to execute a docker container of the application:

- Docker image built

### Create container

To create a container execute the command bellow:

```shell
docker run -d --name sparks-api-gateway \
-e PORT=<Application port (ex: 8080)> \
-e CONFIG_SERVER_BASIC_AUTH_URL=<Config Server Basic Authentication URL (ex: http://admin:admin@localhost:8888)> \
-e DISCOVERY_SERVER_DEFAULT_ZONE_URL=<Discovery Server service registration URL (ex: http://localhost:8081/eureka)> \
-p <External application port (ex: 4000)>:<Application port (ex: 8080)> \
sparks/api-gateway
```

### Stop container

To stop the container in execution execute the command below:

```shell
docker stop sparks-api-gateway
```

## Docker Compose

### Requirements

You will need the following requirements to execute the docker compose of the application:

- Application built / Image built

### Environment variables

You will need to set the environment variables below or create a **.env** file with them:

- **API_GATEWAY_PORT:** Port to run the server;
- **API_GATEWAY_EXTERNAL_PORT:** Port accessible to the host;
- **API_GATEWAY_CONFIG_SERVER_BASIC_AUTH_URL:** URL to connect to Config Server with Basic Authentication;
- **API_GATEWAY_DISCOVERY_SERVER_DEFAULT_ZONE_URL:** URL to register services in Discovery Server; 

**Example**

```text
# Server

API_GATEWAY_PORT=8080
API_GATEWAY_EXTERNAL_PORT=4401

# Config Server

API_GATEWAY_CONFIG_SERVER_BASIC_AUTH_URL=http://admin:admin@config-server:8888

# Discovery Server

API_GATEWAY_DISCOVERY_SERVER_DEFAULT_ZONE_URL=http://discovery-server:8081/eureka
```

### Start Docker Compose

To start docker compose execute the command below in project root:

```shell
docker compose up -d
```

### Stop Docker Compose

To stop docker compose execute the command below in project root:

```shell
docker compose down
```