FROM mysql
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y tzdata && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime
COPY my.cnf /etc/mysql/conf.d/