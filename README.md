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
