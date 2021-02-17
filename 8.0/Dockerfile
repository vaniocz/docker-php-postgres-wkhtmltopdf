FROM vanio/php-postgres:8.0

ARG IMAGICK_COMMIT='448c1cd0d58ba2838b9b6dff71c9b7e70a401b90'

RUN apt-get update && apt-get install -y --no-install-recommends \
    wget \
    fontconfig \
    libxrender1 \
    xfonts-75dpi \
    xfonts-base \
    libmagickwand-dev && \
    wget https://github.com/wkhtmltopdf/packaging/releases/download/0.12.6-1/wkhtmltox_0.12.6-1.buster_amd64.deb && \
    dpkg -i wkhtmltox_0.12.6-1.buster_amd64.deb && \
    apt-get install -f && \

    # build imagick
    cd /tmp && \
    git clone https://github.com/Imagick/imagick && \
    cd imagick && \
    git checkout $IMAGICK_COMMIT && \
    phpize && \
    ./configure && \
    make && \
    make install && \
    echo "extension=imagick.so" > /usr/local/etc/php/conf.d/ext-imagick.ini && \
    rm -rf /tmp/* && \

    docker-php-ext-install exif && \
    docker-php-ext-configure exif --enable-exif
