FROM postgres:17.3

RUN apt update \
    && apt install -y --no-install-recommends \
    patroni=4.0.4-2.pgdg120+1 \
    python3-psycopg2 \
    && apt clean \
    && rm -rf \
    /var/lib/apt/lists/* \
    /var/cache/* \
    && mkdir /var/lib/postgresql -p \
    && chown postgres:postgres /var/lib/postgresql \
    && chmod 700 /var/lib/postgresql

USER postgres

ENTRYPOINT ["/usr/bin/patroni"]
CMD [ "/etc/patroni/config.yml" ]
