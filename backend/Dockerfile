FROM golang
RUN apt-get update && \
    apt-get upgrade -y && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    go get github.com/go-sql-driver/mysql && \
    go get github.com/gorilla/mux && \
    go get github.com/auth0/go-jwt-middleware && \
    go get github.com/dgrijalva/jwt-go && \
    go get github.com/subosito/gotenv && \
    go get golang.org/x/crypto/bcrypt && \
    cd && \
    git clone https://github.com/yujialves/memoriz-en-backend
COPY .env /root/memoriz-en-backend/.env
RUN cd /root/memoriz-en-backend && \
    go build main.go
WORKDIR /root/memoriz-en-backend
CMD ["./main"]