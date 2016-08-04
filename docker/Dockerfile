FROM ubuntu

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update --fix-missing 
RUN apt-get install -y vim
RUN apt-get install -y nginx

ADD nginx/nginx.conf /etc/nginx/nginx.conf
ADD nginx/sites-enabled/magento.conf /etc/nginx/sites-enabled/magento
CMD rm -r /etc/nginx/sites-enabled/default

EXPOSE 80 443 22 9000

VOLUME ["/etc/nginx", "/var/www/"]

CMD ["nginx", "-g", "daemon off;"]

# PHP
RUN apt-get update \
  && apt-get install -y \
    cron \
    libfreetype6-dev \
    libicu-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng12-dev \
    libxslt1-dev

RUN apt-get -y install php7.0 php7.0-fpm php7.0-mysql
RUN apt-get install -y libcurl3 php7.0-curl php7.0-gd php7.0-mcrypt

RUN apt-get install php7.0-bcmath
