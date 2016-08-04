FROM ubuntu

RUN apt-get update --fix-missing 
RUN apt-get install -y vim
RUN apt-get install -y nginx

ADD nginx/nginx.conf /etc/nginx/nginx.conf
ADD nginx/sites-enabled/magento.conf /etc/nginx/sites-enabled/magento
CMD rm -r /etc/nginx/sites-enabled/default

EXPOSE 80 443 22 9000

VOLUME ["/etc/nginx", "/var/www/"]

CMD ["nginx", "-g", "daemon off;"]

RUN apt-get -y install php7.0-fpm
