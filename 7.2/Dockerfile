FROM vanio/php-postgres:7.2

RUN apt-get update && apt-get install -y --no-install-recommends \
    xvfb wkhtmltopdf libmagickwand-dev && \
    pecl install imagick-3.4.3 && docker-php-ext-enable imagick && \
    docker-php-ext-install exif && \
    docker-php-ext-configure exif --enable-exif
