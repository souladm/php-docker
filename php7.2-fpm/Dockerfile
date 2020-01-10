FROM ubuntu:18.04
LABEL maintainer="kosar@freedom.valor.ua"
LABEL vendor="1node"
LABEL created="10-02-2019"
LABEL lastUpdate="21-03-2019"
LABEL description="php-fpm7.2 container based on UBUNTU 18.04"
ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt upgrade -y
# set timezone
RUN echo 'Europe/Kiev' > /etc/timezone
RUN apt install -y tzdata
# install php 7.1
RUN apt install -y software-properties-common
RUN add-apt-repository -y ppa:ondrej/php && apt update
RUN apt install -y php7.2 php7.2-bcmath php7.2-bz2 php7.2-cgi \
    php7.2-cli php7.2-common php7.2-curl php7.2-dba php7.2-fpm \
    php7.2-gd php7.2-gmp php7.2-json php7.2-intl php7.2-mbstring \
    php7.2-mysql php7.2-opcache php7.2-readline php7.2-recode php7.2-soap \
    php7.2-xml php7.2-xmlrpc php7.2-xsl php7.2-zip php-geoip php-memcache \
    php-memcached php-redis php-uuid php-yaml php-net-ftp
RUN mkdir /run/php
RUN sed -i 's/listen\ =\ \/run\/php\/php7.2-fpm.sock/listen\ =\ 0.0.0.0:9000/' /etc/php/7.2/fpm/pool.d/www.conf
EXPOSE 9000
CMD ["php-fpm7.2", "-F"]
