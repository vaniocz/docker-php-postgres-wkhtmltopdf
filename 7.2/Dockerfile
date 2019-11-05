FROM vanio/php-postgres:7.2

RUN apt-get update && apt-get install -y --no-install-recommends \
    wget \
    fontconfig \
    libxrender1 \
    xfonts-75dpi \
    xfonts-base \
    libmagickwand-dev && \
    wget https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.5/wkhtmltox_0.12.5-1.stretch_amd64.deb && \
    dpkg -i wkhtmltox_0.12.5-1.stretch_amd64.deb && \
    apt-get install -f && \
    pecl install imagick-3.4.3 && docker-php-ext-enable imagick && \
    docker-php-ext-install exif && \
    docker-php-ext-configure exif --enable-exif
