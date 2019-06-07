FROM ubuntu:16.04
MAINTAINER UbuntuDockerfile
EXPOSE 5432
RUN apt-get update
RUN apt install -y postgresql postgresql-contrib
RUN apt-get -y install nano
ADD postgresql.conf /etc/postgresql/9.5/main/
ADD pg_hba.conf /etc/postgresql/9.5/main/
RUN service postgresql start && su -c "psql -c \"ALTER USER postgres WITH PASSWORD '123456'; \" " postgres
 #"create database mydb; create user myuser with encrypted password 'mypass'; grant all privileges on database mydb to myuser;"
CMD ["postgresql"]
ENTRYPOINT /bin/bash