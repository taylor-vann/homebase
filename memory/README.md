# memory

Build and deploy`redis` and `postgres` containers.

### Dot env

Create a dot env file with the following schema:

example `.env`

```
HOMEBASE_POSTGRES_DIR=./postgres_data
HOMEBASE_POSTGRES_PORT=4005
HOMEBASE_POSTGRES_PASSWORD=magicbeans
HOMEBASE_REDIS_DIR=./redis_data
HOMEBASE_REDIS_PORT=4010
HOMEBASE_REDIS_CONFIG=./redis.conf
```

