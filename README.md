# Trino and Iceberg REST Catalog Demo

## Start containers

```bash
docker compose up -d
```

This will initialize `iceberg` catalog in Trino.

## Initialize `test` schema

There is a simple SQL script to initialize a test schema
in the `iceberg` catalog by copying TPCH "tiny" schema from the Trino:

```bash
docker exec -it trino trino -f /home/trino/test-schema.sql
```

This is not required. It is possible to create other schemata in the `iceberg`
catalog and create and populate tables there in any way.

## Running queries

Connect to Trino CLI and execute queries:

```bash
docker exec -it trino trino
```

Inspect warehouse bucket contents: open [Minio Admin panel](http://localhost:9001)
(user name: `admin` password: `password`).
