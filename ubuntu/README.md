# ubuntu

[Ubuntu \- Official Image \| Docker Hub](https://hub.docker.com/_/ubuntu)

## docker-compose

run with tty. it can access with bash because ther process does not break

```yml
version: "3.3"
services:
  ubuntu:
    image: ubuntu:18.04
    working_dir: /usr/src
    volumes:
      - ./src/:/usr/src
    ports:
      - 80:80
    restart: "no"
    tty: true
```

```bash
docker compose up -d
docker compose exec ubuntu bash
```
