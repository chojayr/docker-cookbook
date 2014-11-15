FROM phusion/baseimage:0.9.9

ENV HOME /root
ENV    DEBIAN_FRONTEND noninteractive

RUN dpkg-divert --local --rename --add /sbin/initctl
#RUN ln -s /bin/true /sbin/initctl

#RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update 

RUN echo "mysql-server mysql-server/root_password password pass30rd" | debconf-set-selections
RUN echo "mysql-server mysql-server/root_password_again password pass30rd" | debconf-set-selections

RUN apt-get -y install mysql-client mysql-server

RUN sed -i -e"s/^bind-address\s*=\s*127.0.0.1/bind-address = 0.0.0.0/" /etc/mysql/my.cnf

ADD ./start_up.sh /opt/start_up.sh

EXPOSE 3306

CMD ["/bin/bash", "/opt/start_up.sh"]
