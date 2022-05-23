# redis

- [Redis \- Official Image \| Docker Hub](https://hub.docker.com/_/redis)

## docker-compose

- Where /myredis/conf/ is a local directory containing your redis.conf file
- /data is a redis parmanently data directory

```yml
version: "3.3"
services:
  redis-server:
    image: redis:7
    restart: "no"
    command: redis-server --save 60 1 --loglevel warning
    volumes:
      - ./data:/data
    ports:
      - 6379:6379
networks:
  default:
    external:
      name: some-network
```

```bash
# create network (only first time)
docker network create some-network

# run
docker compose up -d

# access
docker run -it --network some-network --rm redis:7 redis-cli -h redis-server

# stop
docker compose stop
```