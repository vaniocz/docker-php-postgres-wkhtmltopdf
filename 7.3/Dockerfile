FROM vanio/php-postgres:7.3

RUN apt-get update && apt-get install -y --no-install-recommends \
    wget \
    fontconfig \
    libxrender1 \
    xfonts-75dpi \
    xfonts-base \
    libmagickwand-dev && \
    wget https://downloads.wkhtmltopdf.org/0.12/0.12.5/wkhtmltox_0.12.5-1.buster_amd64.deb && \
    dpkg -i wkhtmltox_0.12.5-1.buster_amd64.deb && \
    apt-get install -f && \
    pecl install imagick-3.4.3 && docker-php-ext-enable imagick && \
    docker-php-ext-install exif && \
    docker-php-ext-configure exif --enable-exif
