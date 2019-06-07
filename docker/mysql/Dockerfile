FROM mysql:8

# conf.d/以下の設定ファイルを全て追加
COPY conf.d/* /etc/mysql/conf.d/

RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

CMD ["mysqld"]
