FROM ubuntu

RUN apt-get update --fix-missing 
RUN apt-get install -y vim
RUN apt-get install -y nginx

# PHP
RUN apt-get update \
  && apt-get install -y \
    cron \
    libfreetype6-dev \
    libicu-dev \
    libmcrypt-dev \
    libpng12-dev \
    libxslt1-dev

RUN apt-get -y install php7.0-fpm php7.0-mysql
RUN apt-get install -y libcurl3 php7.0-curl php7.0-gd php7.0-mcrypt

RUN apt-get install php7.0-bcmath
RUN apt-get install -y php7.0-intl
RUN apt-get install -y php7.0-mbstring
#RUN apt-get install -y php7.0-mhash
#RUN apt-get install -y php7.0-openssl
#RUN apt-get install -y php7.0-pdo_mysql
RUN apt-get install -y php7.0-simplexml
RUN apt-get install -y php7.0-soap
RUN apt-get install -y php7.0-xml
RUN apt-get install -y php7.0-xsl
RUN apt-get install -y php7.0-zip
RUN apt-get install -y php7.0-json
RUN apt-get install -y php7.0-iconv

RUN apt-get install -y php7.0-dom

ADD nginx/nginx.conf /etc/nginx/nginx.conf
ADD nginx/sites-enabled/magento.conf /etc/nginx/sites-enabled/magento

CMD rm -r /etc/nginx/sites-enabled/default
ADD files/start.sh /docker/start.sh

EXPOSE 80 443 22 9000

VOLUME ["/etc/nginx", "/var/www/"]

ENTRYPOINT sh /docker/start.sh

#docker run --name ng-php -p 9999:80 -itd <images>
