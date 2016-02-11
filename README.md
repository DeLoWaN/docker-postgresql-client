# Postgresql Client

This client is compatible with the official postgresql image, which means that it uses the environment variables provided by the image.

## Usage

### Start a postgres database

```
docker run -e POSTGRES_USER=user -e POSTGRES_PASSWORD=pwd -d --name=pg_container postgres:9.4
```

### Use psql or pg_dump command

```
docker run --rm --link pg_container:db kalumkalac/postgresql-client:9.4 psql -c 'create database foo'
docker run --rm --link pg_container:db -v /tmp/foo:/dump kalumkalac/postgresql-client:9.4 pg_dump foo -f /dump/dump_foo.sql
```

