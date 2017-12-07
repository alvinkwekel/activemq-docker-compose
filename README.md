ActiveMQ network of brokers in Docker Compose.

Broker A is a single instance with file (KahaDB) store on version 5.11.0 (Fuse).
Broker B is a master/slave pair with Postgres store on version 5.15.2.

## Avoid already exists DB warnings
    <jdbcPersistenceAdapter createTablesOnStartup="false">

## Add volume for Postgres
```
  db-b:
    image: ci/postgres-amq:9.6-1
    ports:
     - "5434:5432"
    volumes:
     - "dbdata:/var/lib/postgresql/data"
...
volumes:
  dbdata:
```
