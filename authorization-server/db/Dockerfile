FROM postgres:alpine

RUN mkdir /docker-entrypoint-initdb.d || true

COPY init-authorization-db.sh /docker-entrypoint-initdb.d