FROM vanio/php-postgres:7.2

COPY wkhtmltox_0.12.6-0.20190712.20.dev.e3fa5a9.buster_amd64.deb /

RUN apt-get update && apt-get install -y --no-install-recommends \
    xfonts-75dpi \
    xfonts-base \
    libmagickwand-dev && \
    dpkg -i /wkhtmltox_0.12.6-0.20190712.20.dev.e3fa5a9.buster_amd64.deb && \
    apt-get install -f && \
    rm /wkhtmltox_0.12.6-0.20190712.20.dev.e3fa5a9.buster_amd64.deb && \
    pecl install imagick-3.4.3 && docker-php-ext-enable imagick && \
    docker-php-ext-install exif && \
    docker-php-ext-configure exif --enable-exif
