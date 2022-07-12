> ### [Moleculer](http://moleculer.services/) codebase containing real world examples (CRUD, auth, advanced patterns, etc) that adheres to the [RealWorld](https://github.com/gothinkster/realworld) spec and API.

_For more information on how to this works with other frontends /backends, head over to the [RealWorld](https://github.com/gothinkster/realworld) repo._

## Getting started

### To get the Node server running locally:

- Clone this repo
- `npm install` to install all required dependencies
- `npm run dev` to start the local server
- the API is available at http://localhost:3000/api

#### MongoDB persistent store

Basically the services stores data in an NeDB persistent file storage in the `./data` folder. If you have to use MongoDB, set the `MONGO_URI` environment variable.

```
MONGO_URI=mongodb://localhost/conduit
```

### To get the Node server running locally with Docker

1. Checkout the repo
2. Start with docker-compose: `docker-compose up -d`

   It starts all services in separated containers, a NATS server for communication, a MongoDB server for database and a [Traefik](https://traefik.io/) reverse proxy

3. Open the http://docker-ip:3000
4. Scale up services

   `docker-compose scale api=3 articles=2 users=2 comments=2 follows=2 favorites=2`

### Dependencies

- [moleculer](https://github.com/ice-services/moleculer) - Microservices framework for NodeJS
- [moleculer-web](https://github.com/ice-services/moleculer-web) - Official API Gateway service for Moleculer
- [moleculer-db](https://github.com/ice-services/moleculer-db/tree/master/packages/moleculer-db#readme) - Database store service for Moleculer
- [moleculer-db-adapter-mongo](https://github.com/ice-services/moleculer-db/tree/master/packages/moleculer-db-adapter-mongo#readme) - Database store service for MongoDB _(optional)_
- [jsonwebtoken](https://github.com/auth0/node-jsonwebtoken) - For generating JWTs used by authentication
- [bcrypt](https://github.com/kelektiv/node.bcrypt.js) - Hashing user password
- [lodash](https://github.com/lodash/lodash) - Utility library
- [slug](https://github.com/dodo/node-slug) - For encoding titles into a URL-friendly format
- [nats](https://github.com/dodo/node-slug) - [NATS](https://nats.io) transport driver for Moleculer
