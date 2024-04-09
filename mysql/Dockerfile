FROM mysql:8.0.33

ENV MYSQL_ROOT_PASSWORD="root123"
ENV MYSQL_DATABASE="accounts"
EXPOSE 3306

ADD ./db_backup.sql docker-entrypoint-initdb.d/db_backup.sql
