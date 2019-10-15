# RAVIMOSHARK - APIS - CLIENT - NodeJS APP

> The **main repository** is hosted in [gitlab.com/ravimosharksas](https://gitlab.com/ravimosharksas/apis/client/app-nodejs.git) but it is automatically mirrored to [github.com/RavimoShark](https://github.com/RavimoShark/apis-client-app-nodejs.git), [gitlab.com/singletonsd](https://gitlab.com/singletonsd/ravimosharksas/apis/client/app-nodejs.git), [github.com/singletonsd](https://github.com/singletonsd/ravimoshark-apis-client-app-nodejs.git), [github.com/patoperpetua](https://github.com/patoperpetua/ravimoshark-apis-client-app-nodejs.git) and to [gitlab.com/patoperpetua](https://gitlab.com/patoperpetua/ravimoshark-apis-client-app-nodejs.git). If you are in the Github page it may occur that is not updated to the last version.

## Overview

This server was generated by the [swagger-codegen](https://github.com/swagger-api/swagger-codegen) project.  By using the [OpenAPI-Spec](https://github.com/OAI/OpenAPI-Specification) from a remote server, you can easily generate a server stub.

## RUNNING SERVER

Be aware to setup the configuration of the database. It can be set by database user and password as [ENVIRONMENT VARIABLES](#environment-variables) or to provide your own [ormconfig.json file](#database-connections).

After setup database configuration and running the server using either way, you can access the api under:

```bash
http://localhost:8000/
```

To view the Swagger UI interface:

```bash
open http://localhost:8000/docs
```

### USING DOCKER

To use this container with docker, just type `docker-compose -f docker-compose/main.yaml up` or execute the following script:

```bash
docker run -it --rm -e DB_PASSWORD= -e DB_USER=Ravimo2015 \
    -p 8000:8000 \
    registry.gitlab.com/ravimosharksas/apis/client/app-nodejs/alpine:8-alpine-latest
```

#### DIFFERENT IMAGE FLAVORS

Docker images run using [Docker Node Official Images](https://hub.docker.com/_/node/) and [Docker Keymetrics PM2 Official Images](https://hub.docker.com/r/keymetrics/pm2/).

You can choose to execute the server in two different operative systems:

- **alpine:** it uses base image node:-alpine. Available versions:
  - *8-alpine*
  - *10-alpine*
- **stretch:** it uses base image node:-stretch. Available versions:
  - *8-stretch*
  - *6-stretch*

### USING NPM

To run the server, type:

```bash
npm install
npm start
```

### DEFAULT API TOKEN

<!-- TODO: -->

## ENVIRONMENT VARIABLES

- `API_VERSION`: api version image. Default: latest.
- `API_BASE`: api base image (alpine or stretch). Default: alpine.
- `SWAGGER_URL`: url of api.
- `APP_PORT`: port to connect to the api. Default: 8000.
- `HOST_PORT`: port to map to host. Default: 80.
- `DB_USER`: user for database connection.
- `DB_PASSWORD`: password for database connection.

## API TOKENS

<!-- TODO: tell how to connect with KeyClock. -->

## DATABASE CONNECTIONS

You can provide your own *ormconfig.json* file to connect with a database. Use the following example configuration to create that file and put it in the root folder.

```json
{
   "name": "default",
   "type": "mssql",
   "host": "",
   "port": 1433,
   "username": "",
   "password": "",
   "database": "",
   "options": {
      "encrypt": true
   },
   "schema": "dbo",
   "synchronize": false,
   "logging": "WARN"
}
```

## DEPLOYMENT

- **MASTER BRANCH:**
  - It creates a docker image using the following tags:
    - ravimosharksas/apis/client/app-nodejs:latest.
- **DEVELOP BRANCH:**
  - It creates a docker image using the following tags:
    - ravimosharksas/apis/client/app-nodejs:develop.

## BRANCHING MODEL

- Default branch when pull is DEVELOP.
- Master branch is protected and it is not possible to push. Create a merge request instead.

## TODO

- [X] Setup docker image.
- [ ] Setup test environment.
- [X] Connect Database with an ORM.
- [X] Add lint rules.
- [X] Config TS.
- [ ] Config Keyclock to authenticate.

----------------------
© [Singleton SD](http://singletonsd.com), France, 2019.
