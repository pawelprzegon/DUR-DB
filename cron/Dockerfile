FROM postgres:15.3-alpine
ENV MYDB=postgresql://docker:docker@postgres:5432/Artgeist_API
RUN mkdir /backup
RUN chmod -c 777 /backup
RUN set -x \
    && apk add --no-cache supercronic shadow \
    && useradd -m app
USER app
COPY crontab .