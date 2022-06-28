# ubuntu

[Ubuntu \- Official Image \| Docker Hub](https://hub.docker.com/_/ubuntu)

## easy run

```bash
docker run --rm -it -v "$(pwd)":/tmp/work ubuntu:18.04 /bin/bash
```

## docker-compose

- [just run](./composes/justrun/docker-compose.yml)
  - run with tty. it can access with bash because ther process does not break
- [with sudo](./composes/withSudo/docker-compose.yml)

### basic command

```bash
docker compose up -d
docker compose exec ubuntu bash
docker down
```
