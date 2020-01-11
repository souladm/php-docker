FROM ubuntu:18.04
LABEL maintainer="Bogdan Kosarevskyi <kosar@freedom.valor.ua>"
LABEL vendor="1node"
LABEL lastUpdate="11-01-2020"
LABEL description="php-fpm7.4 container based on UBUNTU 18.04"
ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt upgrade -y
# set timezone
RUN echo 'Europe/Kiev' > /etc/timezone
RUN apt install -y tzdata
# install php 7.1
RUN apt install -y software-properties-common
RUN add-apt-repository -y ppa:ondrej/php && apt update
# Deleted: php7.4-recode. Reference: https://wiki.php.net/rfc/unbundle_recode
RUN apt install -y php7.4 php7.4-bcmath php7.4-bz2 php7.4-cgi \
    php7.4-cli php7.4-common php7.4-curl php7.4-dba php7.4-fpm \
    php7.4-gd php7.4-gmp php7.4-json php7.4-intl php7.4-mbstring \
    php7.4-mysql php7.4-opcache php7.4-readline php7.4-soap \
    php7.4-xml php7.4-xmlrpc php7.4-xsl php7.4-zip php-geoip php-memcache \
    php-memcached php-redis php-uuid php-yaml php-net-ftp
RUN mkdir /run/php
RUN sed -i 's/listen\ =\ \/run\/php\/php7.4-fpm.sock/listen\ =\ 0.0.0.0:9000/' /etc/php/7.4/fpm/pool.d/www.conf
EXPOSE 9000
CMD ["php-fpm7.4", "-F"]
