FROM golang
RUN apt-get update && \
    apt-get upgrade -y && \
    go get github.com/go-sql-driver/mysql && \
    go get github.com/gorilla/mux && \
    go get github.com/auth0/go-jwt-middleware && \
    go get github.com/dgrijalva/jwt-go && \
    go get github.com/subosito/gotenv && \
    go get golang.org/x/crypto/bcrypt && \
    cd && \
    git clone https://github.com/yujialves/Memoriz-EN-Backend
COPY .env /root/Memoriz-EN-Backend/.env
RUN cd /root/Memoriz-EN-Backend && \
    go build main.go
WORKDIR /root/Memoriz-EN-Backend
CMD ["./main"]