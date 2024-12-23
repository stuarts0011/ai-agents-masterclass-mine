FROM n8nio/n8n:latest

WORKDIR /home/node

# Install additional dependencies
RUN npm install tslib msg-parser fs --save

# No need to define Tini explicitly, as it's already part of the base image
CMD ["n8n"]