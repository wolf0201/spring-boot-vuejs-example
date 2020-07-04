# spring-boot-vuejs-example

## 環境構築

- 開発DBの構築

```
$ cd (ユーザーディレクトリ)/spring-boot-vuejs-example/src/main/resources
$ docker-compose up -d
```

- flyway修正時のDB初期化方法
```
$ docker stop (mariadbのコンテナID)
$ docker rm (mariadbのコンテナID)
$ rm -rf (ユーザーディレクトリ)/spring-boot-vuejs-example/src/main/resources/docker/db
$ cd (ユーザーディレクトリ)/spring-boot-vuejs-example/src/main/resources
$ docker-compose up -d
$ cd (ユーザーディレクトリ)/spring-boot-vuejs-example
$ gradle bootRun
```

- PC再起動時のDB起動方法
```
// コンテナ確認
$ docker ps -a
$ docker start (↑で確認したコンテナIDを入力)
```

- アプリケーション起動時にFlywayのエラーが発生したら以下のコマンドを実行する

```
$ docker exec mariadb_demo sh -c 'exec mysql_upgrade -uroot -proot'
```

