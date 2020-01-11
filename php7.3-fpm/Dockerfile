FROM ubuntu:18.04
LABEL maintainer="Bogdan Kosarevskyi <kosar@freedom.valor.ua>"
LABEL vendor="1node"
LABEL lastUpdate="11-01-2020"
LABEL description="php-fpm7.3 container based on UBUNTU 18.04"
ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt upgrade -y
# set timezone
RUN echo 'Europe/Kiev' > /etc/timezone
RUN apt install -y tzdata
# install php 7.1
RUN apt install -y software-properties-common
RUN add-apt-repository -y ppa:ondrej/php && apt update
RUN apt install -y php7.3 php7.3-bcmath php7.3-bz2 php7.3-cgi \
    php7.3-cli php7.3-common php7.3-curl php7.3-dba php7.3-fpm \
    php7.3-gd php7.3-gmp php7.3-json php7.3-intl php7.3-mbstring \
    php7.3-mysql php7.3-opcache php7.3-readline php7.3-recode php7.3-soap \
    php7.3-xml php7.3-xmlrpc php7.3-xsl php7.3-zip php-geoip php-memcache \
    php-memcached php-redis php-uuid php-yaml php-net-ftp
RUN mkdir /run/php
RUN sed -i 's/listen\ =\ \/run\/php\/php7.3-fpm.sock/listen\ =\ 0.0.0.0:9000/' /etc/php/7.3/fpm/pool.d/www.conf
EXPOSE 9000
CMD ["php-fpm7.3", "-F"]
