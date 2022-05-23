# redis

- [Redis \- Official Image \| Docker Hub](https://hub.docker.com/_/redis)

## docker-compose

- /data is a redis parmanently data directory
- networks is for access from docker component, you don't to write that if don't need it.

```yml
version: "3.3"
services:
  redis-server:
    image: redis:7
    restart: "no"
    command: redis-server
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
redis-cli

# stop
docker compose stop
```

### access by docker command

- we can access by docker command but there host is in the docker container. then we need specific the network and host
  - preceding note's mean is can't access to localhost or 127.0.0.1 from in the docker container

```bash
# access
docker run -it --network some-network --rm redis:7 redis-cli -h redis-server
```