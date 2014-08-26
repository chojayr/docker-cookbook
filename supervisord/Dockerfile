FROM ubuntu:14.04

MAINTAINER Luis Lavina "https://github.com/chojayr"

ENV DEBIAN_FRONTEND noninteractive

#update repo
RUN apt-get update && locale-gen en_US.UTF-8 && apt-get install -y curl htop \
man git software-properties-common unzip wget vim

ENV LANG en_US.UTF-8
ENV LANGUAGE en_US.UTF-8
ENV LC_ALL en_US.UTF-8
ENV HOME /root

#to install the supervisor 
RUN apt-get -y install supervisor && mkdir -p /var/log/supervisor && \
mkdir -p /etc/supervisor/conf.d


ADD supervisord.conf /etc/supervisord.conf

CMD ["supervisord", "-c", "/etc/supervisor/supervisord.conf"]
