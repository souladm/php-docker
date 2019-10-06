FROM ubuntu:18.04
LABEL maintainer="kosar@freedom.valor.ua"
LABEL vendor="1node"
LABEL lastUpdate="06-10-2019"
LABEL description="php-fpm7.0 container based on UBUNTU 18.04"
ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt upgrade -y
# set timezone
RUN echo 'Europe/Kiev' > /etc/timezone
RUN apt install -y tzdata
# install php 7.0
RUN apt install -y software-properties-common
RUN add-apt-repository -y ppa:ondrej/php && apt update
RUN apt install -y php7.0 php7.0-bcmath php7.0-bz2 php7.0-cgi \
    php7.0-cli php7.0-common php7.0-curl php7.0-dba php7.0-fpm \
    php7.0-gd php7.0-gmp php7.0-json php7.0-intl php7.0-mbstring \
    php7.0-mcrypt php7.0-mysql php7.0-opcache php7.0-readline \
    php7.0-recode php7.0-soap php7.0-xml php7.0-xmlrpc php7.0-xsl \
    php7.0-zip php-geoip php-memcache php-memcached php-redis \
    php-uuid php-yaml php-net-ftp
RUN mkdir /run/php
EXPOSE 9000
CMD ["php-fpm7.0", "-F"]
