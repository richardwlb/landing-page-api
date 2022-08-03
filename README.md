# React Avançado - Landing Page API

This is the API to create the [React Avançado Landing Page](https://reactavancado.com.br/).

## Requirements

This project uses [PostgreSQL](https://www.postgresql.org/), so, in order to make it working, install in your local machine or use Docker.

The configuration to the Database can be found on [config/database.js](config/database.js)

## Development

After cloning this project, install the dependencies:

```
yarn install
```

And run using:

```
yarn develop
```

The urls to access are:

- `http://localhost:1337/admin` - The Dashboard to create and populate data
- `http://localhost:1337/graphql` - GraphQL Playground to test your queries

The first time to access the Admin you'll need to create an user.

## Dump data

This project uses `Postgres` and if you want all the data previously, unzip the [data.zip](data.zip), copy the `uploads` folder to [public/uploads](public/uploads) and restore the data from the `local.dump` file inside the zip.

# My notes strapi (Backend)

### Install postgresql
```
sudo apt install postgresql postgresql-contrib
service postgresql status
service postgresql start
```

### create user/database
```
sudo -u postgres createuser strapi
sudo -u postgres createdb strapi
```

### Change password/grant
```
sudo -u postgres psql
postgres=# alter user strapi with encrypted password 'strapi123';
postgres=# grant all privileges on database strapi to strapi;
```

### Install strapi/create schema
```
npx create-strapi-app@3.4.3 example
npx create-strapi-app@latest  reactavancado-api // do not works for this dump.
```

yarn dev, and create user. Stop
change folder to the downloaded project landing-page-api

### Import database
```
psql -h localhost -U strapi -d strapi -W < strapi.sql
```

### Config. Copy the key from example strapi, to landing-page-api
config/server.js
secret: env("ADMIN_JWT_SECRET", '189189189128398293829'),
