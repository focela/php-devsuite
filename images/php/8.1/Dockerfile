# Use PHP 8.1 FPM base image
FROM php:8.1-fpm-bookworm

# Maintainer information
LABEL maintainer="Focela Technologies <opensource@focela.com>"

# Set application user ID
ARG APP_ID=1000

# Create a new user and group for the application
RUN groupadd -g "$APP_ID" app \
  && useradd -g "$APP_ID" -u "$APP_ID" -d /var/www -s /bin/bash app

# Create required directories and set permissions
RUN mkdir -p /etc/nginx/html /var/www /sock \
  && chown -R app:app /etc/nginx /var/www /usr/local/etc/php/conf.d /sock

# Install system dependencies
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - \
  && apt-get update && apt-get install -y --no-install-recommends \
    cron \
    default-mysql-client \
    git \
    gnupg \
    gzip \
    libbz2-dev \
    libfreetype6-dev \
    libicu-dev \
    libjpeg62-turbo-dev \
    libmagickwand-dev \
    libmcrypt-dev \
    libonig-dev \
    libpng-dev \
    libpq-dev \
    libsodium-dev \
    libssh2-1-dev \
    libwebp-dev \
    libxslt1-dev \
    libzip-dev \
    lsof \
    mailutils \
    msmtp \
    nodejs \
    procps \
    rsync \
    strace \
    vim \
    zip \
    zlib1g-dev \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

# Install PHP extensions using PECL
RUN pecl channel-update pecl.php.net && pecl install \
    redis-6.1.0 \
    ssh2-1.4.1 \
    swoole-6.0.0 \
    xdebug-3.4.1 \
  && pecl clear-cache \
  && rm -rf /tmp/pear

# Install and configure Imagick extension
RUN imagick_branch="28f27044e435a2b203e32675e942eb8de620ee58" \
  && apt-get update && apt-get install -y --no-install-recommends unzip \
  && curl -L https://github.com/Imagick/imagick/archive/$imagick_branch.zip -o imagick.zip \
  && unzip imagick.zip \
  && rm imagick.zip \
  && cd imagick-$imagick_branch \
  && phpize \
  && ./configure --with-php-config=/usr/local/bin/php-config \
  && make \
  && make install \
  && echo "extension=imagick.so" > $PHP_INI_DIR/conf.d/imagick.ini \
  && cd .. \
  && rm -rf imagick-$imagick_branch

# Configure and install PHP extensions
RUN docker-php-ext-configure gd --with-freetype --with-jpeg --with-webp \
  && docker-php-ext-install \
    bcmath \
    bz2 \
    calendar \
    exif \
    ftp \
    gd \
    gettext \
    intl \
    mbstring \
    mysqli \
    opcache \
    pcntl \
    pdo_mysql \
    soap \
    sockets \
    sodium \
    sysvmsg \
    sysvsem \
    sysvshm \
    xsl \
    zip \
  && docker-php-ext-enable \
    imagick \
    redis \
    ssh2 \
    xdebug

# Install Blackfire Profiler
RUN version=$(php -r "echo PHP_MAJOR_VERSION.PHP_MINOR_VERSION;") \
  && architecture=$(uname -m) \
  && curl -A "Docker" -o /tmp/blackfire-probe.tar.gz -D - -L -s \
       https://blackfire.io/api/v1/releases/probe/php/linux/$architecture/$version \
  && mkdir -p /tmp/blackfire \
  && tar zxpf /tmp/blackfire-probe.tar.gz -C /tmp/blackfire \
  && mv /tmp/blackfire/blackfire-*.so $(php -r "echo ini_get('extension_dir');")/blackfire.so \
  && rm -rf /tmp/blackfire /tmp/blackfire-probe.tar.gz

# Install PHP-SPX profiler
RUN git clone --branch v0.4.17 --depth=1 https://github.com/NoiseByNorthwest/php-spx.git /usr/lib/php-spx \
  && cd /usr/lib/php-spx \
  && phpize \
  && ./configure \
  && make \
  && make install

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --version=2.7.9 \
  --install-dir=/usr/local/bin --filename=composer

# Copy configuration files
COPY ../shared-configs/blackfire.ini $PHP_INI_DIR/conf.d/blackfire.ini
COPY ../shared-configs/spx.ini $PHP_INI_DIR/conf.d/spx.ini
COPY ../shared-configs/msmtprc /etc/msmtprc
COPY ../shared-configs/php.ini $PHP_INI_DIR
COPY ../shared-configs/php-fpm.conf /usr/local/etc/
COPY ../shared-configs/www.conf /usr/local/etc/php-fpm.d/

# Set user and working directory
USER app:app
VOLUME /var/www
WORKDIR /var/www
