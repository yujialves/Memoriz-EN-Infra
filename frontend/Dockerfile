FROM node:14.5
RUN cd && \
    apt-get update && \
    apt-get upgrade -y && \
    npm install -g http-server && \
    yarn global add expo-cli && \
    git clone https://github.com/yujialves/memoriz-en-frontend && \
    cd memoriz-en-frontend && \
    npm install
COPY secrets /root/memoriz-en-frontend/secrets/
RUN cd /root/memoriz-en-frontend && \
    ls && \
    ls secrets && \
    expo build:web && \
    cd web-build && \
    sed -e 's/\/?utm_source=web_app_manifest/\/memoriz\/en\/?utm_source=web_app_manifest/g' manifest.json > manifest_temp.json && \
    mv manifest_temp.json manifest.json && \
    cd ../ && \
    mv web-build frontend
WORKDIR /root/memoriz-en-frontend
CMD http-server ./frontend -p 8000