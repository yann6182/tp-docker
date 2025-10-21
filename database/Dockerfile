FROM postgres:17.2-alpine

ENV POSTGRES_DB=db \
    POSTGRES_USER=postgres \
    POSTGRES_PASSWORD=postgres

COPY ./initdb /docker-entrypoint-initdb.d
