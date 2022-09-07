FROM alpine:3.16

LABEL maintainer="docker@stefan-van-essen.nl"

RUN apk -U upgrade && apk add --no-cache \
    curl \
    nginx \
    php81-fpm \
    tzdata \
    && ln -s /usr/sbin/php-fpm81 /usr/sbin/php-fpm \
    && addgroup -S php \
    && adduser -S -G php php \
    && rm -rf /var/cache/apk/* /etc/nginx/http.d/* /etc/php81/conf.d/* /etc/php81/php-fpm.d/*

COPY etc/  /etc/
COPY www /www

WORKDIR /www

CMD ["/usr/sbin/nginx"]

EXPOSE 80
