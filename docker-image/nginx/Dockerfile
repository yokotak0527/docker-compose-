FROM nginx:1-alpine

ARG USER_NAME
ARG USER_UID

# 一時ファイル追加
COPY tmp/* /tmp/

# リモートリポジトリのアップデート
RUN apk update --no-cache

# ユーザー追加
RUN adduser ${USER_NAME} -u ${USER_UID} -D

# サーバータイムゾーン変更
RUN apk add --no-cache tzdata && \
    ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

# nginx設定テンプレートを出力して追加
RUN envsubst < /tmp/nginx.conf > /etc/nginx/nginx.conf
# CMD sh -c "envsubst < /usr/template/nginx.conf > /etc/nginx/nginx.conf && nginx -g 'daemon off;'"
