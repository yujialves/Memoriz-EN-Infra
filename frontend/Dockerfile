FROM ghcr.io/yujialves/expo-server-image/expo-server:latest
RUN cd /root && \
    git clone https://github.com/yujialves/memoriz-en-frontend && \
    cd memoriz-en-frontend && \
    yarn install
COPY secrets /root/memoriz-en-frontend/secrets/
RUN cd /root/memoriz-en-frontend && \
    expo build:web && \
    cd web-build && \
    sed -e 's/\/?utm_source=web_app_manifest/\/memoriz\/en\/?utm_source=web_app_manifest/g' manifest.json > manifest_temp.json && \
    mv manifest_temp.json manifest.json && \
    cd ../ && \
    mv web-build frontend
WORKDIR /root/memoriz-en-frontend
CMD http-server ./frontend -p 8000