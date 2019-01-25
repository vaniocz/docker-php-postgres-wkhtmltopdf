FROM vanio/php-postgres:7.2

RUN apt-get update && apt-get install -y --no-install-recommends \
    wget \
    zlib1g \
    fontconfig \
    libfreetype6 \
    libx11-6 \
    libxext6 \
    libxrender1 \
    libssl1.0-dev \
    libmagickwand-dev \
    ghostscript && \
    wget https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.4/wkhtmltox-0.12.4_linux-generic-amd64.tar.xz && \
    tar vxf wkhtmltox-0.12.4_linux-generic-amd64.tar.xz && \
    cp wkhtmltox/bin/wk* /usr/local/bin/ && \
    rm -rf wkhtmltox && \
    rm -rf /var/lib/apt/lists/* && \
    pecl install imagick-3.4.3 && docker-php-ext-enable imagick && \
    docker-php-ext-install exif && \
    docker-php-ext-configure exif --enable-exif && \
