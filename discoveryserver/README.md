# Discovery Server

Sparks discovery server.

## Configuration

### Requirements

- JDK 17
- Maven

### Environment variables

You will need to set the environment variables below:

- PORT: Port to run the server (ex: 8081);
- CONFIG_SERVER_BASIC_AUTH_URL: URL of Config Server using Basic authorization (ex: http://username:password@localhost:8888).

### Dependencies

Execute the command below to install project dependencies:

```shell
mvn clean install -DskipTests
```

## Run

### Tests

Execute the command below to test the project:

```shell
mvn clean test
```

### Development

Execute the command below to run the project in development mode:

```shell
mvn clean spring-boot:run
```

### Production

Execute the command below to build the project:

```shell
mvn clean package -DskipTests
```

To run locally, navigate into _target_ folder and execute the command below:

```shell
java -Dspring.profiles.active=production -jar configserver-0.0.1-SNAPSHOT.jar
```

To run via Docker container, execute the command below in project root:

```shell
docker compose up -d
```

**PS:** You will need to create a **.env** (there is an example file named _.env.example_) file or define environment variables used in **docker-compose.yml**.