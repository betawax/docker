FROM httpd:2.4-alpine

RUN echo "Include conf.d/*.conf" >> /usr/local/apache2/conf/httpd.conf

RUN apk update && apk add openssl && \
openssl req -x509 -sha256 -newkey rsa:2048 -nodes -days 365 -subj "/CN=localhost" \
-out /usr/local/apache2/conf/server.crt -keyout /usr/local/apache2/conf/server.key
