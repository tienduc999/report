FROM ubuntu:16.04

MAINTAINER UbuntuDockerfile
EXPOSE 80

RUN apt-get update
RUN apt-get -y install nano
RUN export DEBIAN_FRONTEND="noninteractive"
RUN echo "mysql-server-5.7 mysql-server/root_password password 150799" | debconf-set-selections

RUN echo "mysql-server-5.7 mysql-server/root_password_again password 150799" | debconf-set-selections

RUN apt-get install -y mysql-server-5.7
ADD mysqld.cnf /etc/mysql/mysql.conf.d/
RUN service mysql start && mysql -uroot -p150799 -e"GRANT ALL PRIVILEGES ON *.* TO root@'%' IDENTIFIED BY '150799' WITH GRANT OPTION;"
