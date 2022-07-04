# docker-study

- [Home \- Docker](https://www.docker.com/)
- [Docker Compose — Docker\-docs\-ja 19\.03 ドキュメント](https://docs.docker.jp/compose/toc.html)

## samples

- [ubuntu](./ubuntu/README.md)
- [redis](./samples/redis/README.md)

## virtualbox

docker ではないが、virtualboxの動かし方

- [virtualbox](./virtualBox/README.md)

## commands

- build: `docker build . -f Dockerfile`
  - [docker build \| Docker Documentation](https://docs.docker.com/engine/reference/commandline/build/)
- image一覧: `docker images`
- docker run: `docker run -it ubuntu bin/bash`
  - 終了時 削除: `--rm`
  - カレントディレクトリをシェアする: `-v "$(pwd)":/tmp/work`
    - pwd はスペースが入るとエラーになるので `"` で囲っておく
  - エントリポイント指定: `docker run -i -t --entrypoint /bin/bash ubuntu`
    - [Docker run リファレンス — Docker\-docs\-ja 20\.10 ドキュメント](https://docs.docker.jp/engine/reference/run.html#entrypoint)

## notes

- windowsで異様にメモリを消費する: vmmemというプロセスがwsl＋dockerで悪さをするとのこと
  - [programing\-study/README\.md at main · awisu2/programing\-study](https://github.com/awisu2/programing-study/blob/main/os/windows/windwos11/README.md)