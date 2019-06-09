# Docker LEMP環境

`./docker-compose.yml` は `./docker-image/` でビルドしたイメージを利用することを想定しています。
事前に `./docker-image/` 以下でイメージの作成を行ってください。
詳細は `./docker-image/README.md` を参照

# 実行ユーザー

PHPとNginxはユーザー `www-user(1000)` で実行されます。

# イメージ情報

## PHP

- `php.ini` は `./docker-image/php/php.ini` 参照
- `Compoesr` インストール済み

## Nginx

初期設定は `./docker-image/nginx/tmp/nginx.conf` 参照
