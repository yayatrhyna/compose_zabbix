FROM mysql:5.7

COPY schema.sql /docker-entrypoint-initdb.d/
COPY images.sql /docker-entrypoint-initdb.d/
COPY data.sql /docker-entrypoint-initdb.d/

RUN cat /docker-entrypoint-initdb.d/schema.sql | mysql -u users -p root_password zabbix && \
    cat /docker-entrypoint-initdb.d/images.sql | mysql -u users -p root_password zabbix && \
    cat /docker-entrypoint-initdb.d/data.sql | mysql -u root -p root_password zabbix
