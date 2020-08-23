FROM nginx:latest

RUN apt-get update && apt-get install -y openssl && mkdir /etc/nginx/ssl \
&& openssl req -x509 -sha256 -newkey rsa:2048 -nodes -days 365 -subj "/CN=localhost" \
-out /etc/nginx/ssl/localhost.crt -keyout /etc/nginx/ssl/localhost.key
