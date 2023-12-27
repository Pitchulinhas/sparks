# Config Server

Sparks configuration server.

## Configuration

### Requirements

- JDK 17
- Maven

### Environment variables

You will need to set the environment variables below:

- PORT: Port to run the server (ex: 8888);
- REPOSITORY_URL: URL of GIT repository that contains the configuration files;
- DEFAULT_USER: Username of default user to access config server resources;
- DEFAULT_PASS: Password of default user to access config server resources.

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

Navigate into _target_ folder and execute the command below to run the generated jar:

```shell
java -jar configserver-0.0.1-SNAPSHOT.jar
```