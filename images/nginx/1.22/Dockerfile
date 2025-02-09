# Use Nginx 1.22 Alpine base image
FROM nginx:1.22-alpine

# Maintainer information
LABEL maintainer="Focela Technologies <opensource@focela.com>"

# Define application user ID
ARG APP_ID=1000

# Create user and group for running the application
RUN addgroup -g "$APP_ID" app \
    && adduser -G app -u "$APP_ID" -h /var/www -s /bin/bash -S app

# Prepare necessary system directories
RUN mkdir -p /sock /etc/nginx/certs /etc/nginx/html /var/www \
    && touch /var/run/nginx.pid \
    && chown -R app:app /etc/nginx /var/www /var/cache/nginx /var/run/nginx.pid /sock

# Install required dependencies
RUN apk add --no-cache \
    curl \
    nss-tools \
    openssl

# Generate self-signed SSL certificate for development
RUN echo -e "\n\n\n\n\n\n\n" | openssl req -x509 -nodes -days 365 \
    -newkey rsa:2048 -keyout /etc/nginx/certs/nginx.key \
    -out /etc/nginx/certs/nginx.crt \
    && chmod 644 /etc/nginx/certs/nginx.key /etc/nginx/certs/nginx.crt \
    && chown app:app /etc/nginx/certs/nginx.key /etc/nginx/certs/nginx.crt

# Define target architecture for mkcert
ARG TARGETARCH

# Download and install mkcert for SSL certificate management
RUN curl -L "https://github.com/FiloSottile/mkcert/releases/download/v1.4.4/mkcert-v1.4.4-linux-$TARGETARCH" \
    -o /usr/local/bin/mkcert \
    && chmod +x /usr/local/bin/mkcert

# Copy configuration files into the container
COPY ../shared-configs/nginx.conf /etc/nginx/
COPY ../shared-configs/default.conf /etc/nginx/conf.d/

# Set user and working directory
USER app:app
WORKDIR /var/www
VOLUME /var/www
