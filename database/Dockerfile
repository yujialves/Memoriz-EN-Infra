FROM mariadb:latest
RUN sed -i 's@archive.ubuntu.com@ftp.jaist.ac.jp/pub/Linux@g' /etc/apt/sources.list && \
    apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y tzdata && \
    apt-get install -y apparmor-profiles && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime
COPY my.cnf /etc/mysql/conf.d/