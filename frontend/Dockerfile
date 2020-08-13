FROM node:14.5
RUN cd && \
    apt-get update && \
    apt-get upgrade -y && \
    npm install -g http-server && \
    yarn global add expo-cli && \
    git clone https://github.com/yujialves/Memoriz-EN-Frontend && \
    cd Memoriz-EN-Frontend && \
    npm install
COPY secrets /root/Memoriz-EN-Frontend/secrets/
RUN cd /root/Memoriz-EN-Frontend && \
    ls && \
    ls secrets && \
    expo build:web && \
    cd web-build && \
    sed -e 's/\/?utm_source=web_app_manifest/\/memoriz\/en\/?utm_source=web_app_manifest/g' manifest.json > manifest_temp.json && \
    mv manifest_temp.json manifest.json && \
    cd ../ && \
    mv web-build frontend
WORKDIR /root/Memoriz-EN-Frontend
CMD http-server ./frontend -p 8000