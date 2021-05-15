FROM nginx:1.19-alpine

RUN apk update && apk add openssl && \
openssl req -x509 -sha256 -newkey rsa:2048 -nodes -days 365 -subj "/CN=localhost" \
-out /etc/nginx/server.crt -keyout /etc/nginx/server.key
