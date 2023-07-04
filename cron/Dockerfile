FROM postgres:15.3-alpine
ENV RAPORTS=postgresql://docker:docker@postgres:5432/raports
ENV LOGS=postgresql://docker:docker@postgres:5432/logs
RUN bash -c 'mkdir -p /backup/{logs,raports}'
RUN chmod -c 777 /backup/logs
RUN chmod -c 777 /backup/raports
RUN set -x \
    && apk add --no-cache supercronic shadow \
    && useradd -m app
USER app
COPY crontab .