FROM ubuntu:18.04
LABEL maintainer="kosar@freedom.valor.ua"
LABEL vendor="1node"
LABEL lastUpdate="05-12-2019"
LABEL description="php-fpm-5.6 container based on UBUNTU 18.04"
ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt upgrade -y
# set timezone
RUN echo 'Europe/Kiev' > /etc/timezone
RUN apt install -y tzdata
# install php 5.6
RUN apt install -y software-properties-common
RUN add-apt-repository -y ppa:ondrej/php && apt update
RUN apt install -y php5.6 php5.6-bcmath php5.6-bz2 php5.6-cgi php5.6-cli \
    php5.6-common php5.6-curl php5.6-dba php5.6-fpm php5.6-gd php5.6-gmp \
    php5.6-json php5.6-intl php5.6-mbstring php5.6-mcrypt php5.6-mysql \
    php5.6-opcache php5.6-readline php5.6-recode php5.6-soap php5.6-xml \
    php5.6-xmlrpc php5.6-xsl php5.6-zip 
RUN mkdir /run/php
RUN sed -i 's/listen\ =\ \/run\/php\/php5.6-fpm.sock/listen\ =\ 0.0.0.0:9000/' /etc/php/5.6/fpm/pool.d/www.conf
EXPOSE 9000
CMD ["php-fpm5.6", "-F"]
