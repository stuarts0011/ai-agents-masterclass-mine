FROM n8nio/n8n:latest

WORKDIR /home/node

# Install additional dependencies
RUN npm install tslib msg-parser fs --save

# Use the default entrypoint and CMD provided by n8n
CMD ["n8n"]
