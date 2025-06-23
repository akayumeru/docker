FROM php:8.4-alpine
COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/
RUN apk add --no-cache openssh-client openssl rsync
RUN install-php-extensions @composer-2 zip
RUN rm -rf /var/cache/apk/*

ENV COMPOSER_ALLOW_SUPERUSER=1
ENV PATH="${PATH}:/root/.composer/vendor/bin"

RUN composer global require deployer/deployer
