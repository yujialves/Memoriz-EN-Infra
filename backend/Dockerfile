FROM golang
RUN echo 'deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main' >> /etc/apt/sources.list && \
    apt upgrade -y && apt update -y && \
    apt install -y unzip wget curl gnupg && \
    wget https://dl.google.com/linux/linux_signing_key.pub && \
    apt-key add linux_signing_key.pub && \
    sudo apt update && \
    apt install -y google-chrome-stable && \
    curl -O https://chromedriver.storage.googleapis.com/88.0.4324.96/chromedriver_linux64.zip && \
    unzip chromedriver_linux64.zip && \
    mv chromedriver /usr/local/bin/ && \
    rm chromedriver_linux64.zip && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    cd && \
    git clone https://github.com/yujialves/memoriz-en-backend
COPY .env /root/memoriz-en-backend/.env
RUN cd /root/memoriz-en-backend && \
    go build main.go
WORKDIR /root/memoriz-en-backend
CMD ["./main"]