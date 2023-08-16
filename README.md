## 手順

#### 1.git clone https://github.com/tsubasahirakida/docker_react_rails.git

#### 2.Docker Desktopの立ち上げ

#### 3.cd docker_react_rails

#### 4.docker-compose build

#### 5.docker-compose up -d --build
※ `-dオプション` バックグラウンドでコンテナが起動

#### 7.localhost:3000にRails、localhost:8000にReactで各サーバーにアクセスできるか確認

#### 8.mysqlのコンテナにtypingというdb作られたか確認

```
$ docker exec -it typing_db /bin/bash
※ docker execでコンテナ内に入れる。入るためにbashを使用。
$ mysql -u root -p
Enter password: password
$ SHOW DATABASES;
```

#### 9.docker-compose down
※コンテナはメモリ容量大きいので、作業が終われば、コンテナを削除

#### 10.再度コンテナを起動する際は、`docker-compose up -d`
※Dockerイメージは5の手順で作成されているため、再度コンテナ起動する際は、--buildオプション不要

#### 11.このアプリのDockerイメージも不要になれば、Dockerイメージ削除

```
$ docker images
$ docker rmi <IMAGE ID>
```
