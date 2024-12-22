FROM postgres:16-alpine

# Install build tools and dependencies
RUN apk add --no-cache --virtual .build-deps \
    build-base \
    git \
    postgresql-dev \
 && git clone --depth 1 https://github.com/pgvector/pgvector.git /usr/src/pgvector \
 && cd /usr/src/pgvector \
 && make \
 && make install \
 && apk del .build-deps \
 && rm -rf /usr/src/pgvector

# Set up the database with the extension
RUN echo "shared_preload_libraries = 'pgvector'" >> /usr/share/postgresql/postgresql.conf.sample
