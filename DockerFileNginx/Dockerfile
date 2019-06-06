FROM ubuntu:16.04
MAINTAINER UbuntuDockerfile
EXPOSE 80
RUN apt-get update
RUN apt-get install -y nano
RUN apt-get install -y nginx
RUN apt-get install -y software-properties-common
RUN LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php
RUN apt-get update
RUN apt-get install -y php7.2 php7.2-fpm php7.2-mysql
ADD test.conf /etc/nginx/sites-enabled/
ADD adminer.conf /etc/nginx/sites-enabled/