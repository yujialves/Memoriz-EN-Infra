FROM golang
RUN apt-get upgrade -y && apt-get update -y && \
    apt install -y unzip && \
    curl -O https://chromedriver.storage.googleapis.com/88.0.4324.96/chromedriver_linux64.zip && \
    unzip chromedriver_linux64.zip && \
    mv chromedriver /usr/local/bin/ && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    cd && \
    git clone https://github.com/yujialves/memoriz-en-backend
COPY .env /root/memoriz-en-backend/.env
RUN cd /root/memoriz-en-backend && \
    go build main.go
WORKDIR /root/memoriz-en-backend
CMD ["./main"]