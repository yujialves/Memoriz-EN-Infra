FROM mysql
RUN apt-get install -y tzdata && \
    apt-get install -y apparmor-profiles && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime
COPY my.cnf /etc/mysql/conf.d/