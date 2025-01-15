# Use Nginx 1.25 as the base image
FROM nginx:1.25-alpine
LABEL maintainer="Focela Technologies <contact@focela.com>"

# Define application user and group
ARG APP_ID=1000
RUN addgroup -g "$APP_ID" app && \
    adduser -G app -u "$APP_ID" -h /var/www -s /bin/bash -S app

# Create necessary directories and set permissions
RUN mkdir -p /var/run /sock /etc/nginx/certs /etc/nginx/html /var/www && \
    touch /var/run/nginx.pid && \
    chown -R app:app /etc/nginx /var/www /var/cache/nginx /var/run/nginx.pid /sock

# Install required packages
RUN apk add --no-cache \
    curl \
    nss-tools \
    openssl

# Generate self-signed SSL certificates
RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
    -keyout /etc/nginx/certs/nginx.key \
    -out /etc/nginx/certs/nginx.crt \
    -subj "/CN=localhost"

# Install mkcert for managing additional certificates
ARG TARGETARCH
RUN curl -L https://github.com/FiloSottile/mkcert/releases/download/v1.4.4/mkcert-v1.4.4-linux-$TARGETARCH -o /usr/local/bin/mkcert && \
    chmod +x /usr/local/bin/mkcert

# Copy Nginx configuration files
COPY ./conf/nginx.conf /etc/nginx/
COPY ./conf/default.conf /etc/nginx/conf.d/

# Set application user and working directory
USER app:app
WORKDIR /var/www

# Define application volume
VOLUME /var/www
