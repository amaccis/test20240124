FROM php:8.3.2-fpm-alpine3.19

LABEL maintainer="Andrea Maccis <andrea.maccis@gmail.com>"

ARG docker_php_extension_installer=2.1.77

ENV DOCKER_PHP_EXTENSION_INSTALLER=${docker_php_extension_installer}

RUN set -eux ; \
    # install https://github.com/mlocati/docker-php-extension-installer \
    curl \
        --silent \
        --fail \
        --location \
        --retry 3 \
        --output /usr/local/bin/install-php-extensions \
        --url https://github.com/mlocati/docker-php-extension-installer/releases/download/$DOCKER_PHP_EXTENSION_INSTALLER/install-php-extensions ; \
    echo "677e067f9dd53064e8cd4492647cb666d0d989c082250c56a4f9209fdf459302a8c9ad686db035ffff20c5459933263b57700e0570218b0fb29bcd7d4fea95b8  /usr/local/bin/install-php-extensions" | sha512sum -c ; \
    chmod +x /usr/local/bin/install-php-extensions ; \
    # install pdo_mysql \
    install-php-extensions pdo_mysql
