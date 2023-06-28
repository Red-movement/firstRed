FROM alpine:3.18

RUN apk update \
    && apk add --no-cache python3-dev \
    && apk add --no-cache py3-pip \
    && pip3 install --upgrade pip \
    && apk add --no-cache postgresql postgresql-client \
    && mkdir -p /run/postgresql \
    && chown -R postgres:postgres /run/postgresql \
    && apk add --no-cache su-exec \
    && su-exec postgres initdb -D /var/lib/postgresql/data

USER postgres

RUN pg_ctl -D /var/lib/postgresql/data start \
    && sleep 5 \
    && psql -U postgres -c "CREATE DATABASE gasty;"

EXPOSE 5432

WORKDIR /app

COPY . /app

RUN pip3 --no-cache install -r requirements.txt

CMD ["python3", "src/app.py"]
