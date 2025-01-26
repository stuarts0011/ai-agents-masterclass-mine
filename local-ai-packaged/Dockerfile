FROM n8nio/n8n:latest

USER root

# Install system dependencies for n8n nodes and playwright
RUN npm install -g winattr msg-parser tslib pg
RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    build-essential \
    libgtk-3-0 \
    libnotify-dev \
    libgconf-2-4 \
    libnss3 \
    libxss1 \
    libasound2 \
    libxtst6 \
    xvfb \
    fonts-liberation \
    libappindicator3-1 \
    lsb-release \
    xdg-utils \
    && rm -rf /var/lib/apt/lists/*

# Install Python requirements
RUN pip3 install --no-cache-dir \
    requests \
    beautifulsoup4 \
    python-dotenv

# Install Playwright for browser automation support
RUN npx playwright install chromium

USER node

# Health check endpoint
HEALTHCHECK --interval=30s --timeout=10s --retries=3 \
  CMD curl --fail http://localhost:5678/healthz || exit 1