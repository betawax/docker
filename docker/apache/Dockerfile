FROM httpd:2.4-alpine

# Include custom configuration files in the main httpd.conf
RUN echo "Include conf.d/*.conf" >> /usr/local/apache2/conf/httpd.conf

# Create a self-signed SSL certificate
RUN apk update && apk add openssl && \
openssl req -x509 -sha256 -newkey rsa:2048 -nodes -days 365 -subj "/CN=localhost" \
-out /usr/local/apache2/conf/server.crt -keyout /usr/local/apache2/conf/server.key
