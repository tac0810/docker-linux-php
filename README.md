# docker-linux-php

## 導入
要求環境
- Dockerクライアント
  - [Mac](https://matsuand.github.io/docs.docker.jp.onthefly/desktop/mac/install/)
  - [Win](https://matsuand.github.io/docs.docker.jp.onthefly/desktop/windows/)

## ディレクトリ構造
```
/
├── php/
│   ├── Dockerfile
│   └── php.ini
├── public/
│   └── index.php
└── docker-compose.yml
```

## バージョンの変更方法

```Dockerfile
#FROM php:5.6-apache
FROM php:7.4-apache
```
使うバージョンだけコメントアウトを解除してください。


## 起動方法
`$ docker compose up --build`  

`--build` オプションをつけると起動のたびにビルドするのでバージョンを変えた時はつけて起動してください


## メール送信
メールキャッチャーとして [mailhog](https://github.com/mailhog/MailHog)を入れています。  
phpのmail関数とかを普通に実行するだけなら http://localhost:8025 にアクセスして確認できます。

```
host: mailhog
post: 1025
```
- 必要に応じて上記の情報を入れるか環境変数にいれて実行してください。