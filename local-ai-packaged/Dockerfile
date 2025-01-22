FROM n8nio/n8n:latest
USER root
RUN apk update && apk add --no-cache \
    python3 \
    py3-pip \
    build-base \
    g++ \
    make
RUN npm install -g winattr msg-parser tslib pg
USER node