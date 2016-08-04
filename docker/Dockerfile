FROM ubuntu

RUN apt-get update --fix-missing && \
		apt-get install -y git nmap && \
		apt-get install -y vim

RUN apt-get install -y nginx

EXPOSE 80 443 22 9000

VOLUME ["/etc/nginx"]

CMD ["nginx", "-g", "daemon off;"]

