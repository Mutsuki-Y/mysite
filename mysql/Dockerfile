FROM mysql:5.7
COPY ./my.cnf /etc/mysql/conf.d/my.cnf
COPY ./sql/initialize.sql /docker-entrypoint-initdb.d/
