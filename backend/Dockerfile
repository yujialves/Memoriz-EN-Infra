FROM golang
RUN apt upgrade -y && apt update -y && \
    apk add --no-cache udev ttf-freefont chromium chromium-chromedriver && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    cd && \
    git clone https://github.com/yujialves/memoriz-en-backend
COPY .env /root/memoriz-en-backend/.env
RUN cd /root/memoriz-en-backend && \
    go build main.go
WORKDIR /root/memoriz-en-backend
CMD ["./main"]