FROM llavina/supervisord

MAINTAINER Luis R. Lavina Jr. llavina@gorocketlabs.com

RUN apt-get update && apt-get clean

RUN apt-get install -q -y default-jre openjdk-6-jre-headless && apt-get clean

ADD openfire/openfire.deb /opt/openfire.deb

RUN chmod 644 /opt/openfire.deb

RUN dpkg --install /opt/openfire.deb

# copy supervisor files
ADD ./supervisord/supervisor.conf /etc/supervisor/supervisor.conf
ADD ./supervisord/openfire.sv.conf /etc/supervisor/conf.d/openfire.sv.conf

EXPOSE 9090

CMD ["supervisord", "-c", "/etc/supervisor/supervisor.conf"]
