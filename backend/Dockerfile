FROM golang
RUN sed -i 's@archive.ubuntu.com@ftp.jaist.ac.jp/pub/Linux@g' /etc/apt/sources.list && \
    apt upgrade -y && apt update -y && \
    apt install -y unzip wget curl gnupg && \
    wget --no-check-certificate https://dl-ssl.google.com/linux/linux_signing_key.pub && \
    apt-key add linux_signing_key.pub && \
    sh -c 'echo "deb http://dl.google.com/linux/chrome/deb/ stable main " >> /etc/apt/sources.list' && \
    apt update && \
    apt install -y google-chrome-stable && \
    curl -O https://chromedriver.storage.googleapis.com/88.0.4324.96/chromedriver_linux64.zip && \
    unzip chromedriver_linux64.zip && \
    mv chromedriver /usr/local/bin/ && \
    rm chromedriver_linux64.zip && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime
ADD https://api.github.com/repos/yujialves/memoriz-en-backend/git/refs/heads/master version.json
RUN git clone https://github.com/yujialves/memoriz-en-backend.git /root/memoriz-en-backend/
COPY .env /root/memoriz-en-backend/.env
RUN cd /root/memoriz-en-backend && \
    go build main.go
WORKDIR /root/memoriz-en-backend
CMD ["./main"]