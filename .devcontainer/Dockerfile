# FROM mcr.microsoft.com/devcontainers/php:0-8.1
FROM mcr.microsoft.com/devcontainers/php:0-8.1-bullseye

# Install MariaDB client
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y mariadb-client libpng-dev libicu-dev libxml2-dev libzip-dev libsodium-dev libxslt-dev zlib1g-dev libpng-dev libjpeg-dev libfreetype6-dev \ 
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*

# Install php-mysql driver
RUN docker-php-ext-configure gd --with-jpeg --with-freetype && \
    docker-php-ext-install mysqli pdo pdo_mysql gd intl bcmath soap sockets sodium zip xsl

RUN echo 'memory_limit = -1' >> /usr/local/etc/php/conf.d/memory_limit.ini

COPY ./entrypoint /usr/local/bin/entrypoint

# [Choice] Node.js version: none, lts/*, 16, 14, 12, 10
# ARG NODE_VERSION="16"
# RUN if [ "${NODE_VERSION}" != "none" ]; then su vscode -c "umask 0002 && . /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION} 2>&1"; fi

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# [Optional] Uncomment this line to install global node packages.
# RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && npm install -g <your-package-here>" 2>&1

