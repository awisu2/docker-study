# mongo

- [Redis \- Official Image \| Docker Hub](https://hub.docker.com/_/redis)

## docker-compose

- /data is a redis parmanently data directory
- networks is for access from docker component, you don't to write that if don't need it.
- デフォルトポートは 27017

```yml
version: "3.3"
services:
  mongo:
    image: mongo
    restart: always
    ports:
      - 27017:27017
    environment:
      MONGO_INITDB_ROOT_USERNAME: root
      MONGO_INITDB_ROOT_PASSWORD: example
  mongo-express:
    image: mongo-express
    restart: always
    ports:
      - 8081:8081
    environment:
      ME_CONFIG_MONGODB_ADMINUSERNAME: root
      ME_CONFIG_MONGODB_ADMINPASSWORD: example
      ME_CONFIG_MONGODB_URL: mongodb://root:example@mongo:27017/
```

- [access express](http://localhost:8081)

## access

- mongoshっていうコマンドをインストール
  - [Install mongosh — MongoDB Shell](https://www.mongodb.com/docs/mongodb-shell/install/#std-label-mdb-shell-install)
- login方法 [Connect to a Deployment — MongoDB Shell](https://www.mongodb.com/docs/mongodb-shell/connect/)

```bash
mongosh "mongodb://localhost:27017" --username root --password
```

