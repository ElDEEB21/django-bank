FROM docker.io/postgres:16-bullseye

COPY ./docker/local/postgres/maintenance /usr/local/bin/maintenance

RUN find /usr/local/bin/maintenance -mindepth 1 -maxdepth 1 -type f \
        -exec chmod +x {} \; \
        -exec mv {} /usr/local/bin/ \; \
    && rmdir /usr/local/bin/maintenance

RUN mkdir -p /backups && chown -R postgres:postgres /backups && chmod 777 /backups