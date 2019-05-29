FROM ubuntu:18.04
LABEL maintainer="kosar@freedom.valor.ua"
LABEL vendor="1node"
LABEL created="10-02-2019"
LABEL lastUpdate="21-03-2019"
LABEL description="php-fpm7.1 container based on UBUNTU 18.04"
ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt upgrade -y
# set timezone
RUN echo 'Europe/Kiev' > /etc/timezone
RUN apt install -y tzdata
# install php 7.1
RUN apt install -y software-properties-common
RUN add-apt-repository -y ppa:ondrej/php && apt update
RUN apt install -y php7.1 php7.1-bcmath php7.1-bz2 php7.1-cgi \
    php7.1-cli php7.1-common php7.1-curl php7.1-dba php7.1-fpm \
    php7.1-gd php7.1-gmp php7.1-json php7.1-intl php7.1-mbstring \
    php7.1-mcrypt php7.1-mysql php7.1-opcache php7.1-readline \
    php7.1-recode php7.1-soap php7.1-xml php7.1-xmlrpc php7.1-xsl \
    php7.1-zip php-geoip php-memcache php-memcached php-redis \
    php-uuid php-yaml php-net-ftp
RUN mkdir /run/php
EXPOSE 9000
CMD ["php-fpm7.1", "-F"]
