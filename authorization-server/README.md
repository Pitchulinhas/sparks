# Authorization Server

Server to authenticate and authorizate users across the services.

## Requirements

- Build image **sparks/authorization-server-app** from Dockerfile located in _app_ folder.
- Build image **sparks/authorization-server-db** from Dockerfile located in _db_ folder.
- Create a **.env** (there is an example file named _.env.example_) file or create environment variables used in **docker-compose.yml**

## Start

Execute the command below to start authorization server:

```bash
docker-compose up -d
```

## Stop

Execute the command below to stop authorization server:

```bash
docker-compose down
```
