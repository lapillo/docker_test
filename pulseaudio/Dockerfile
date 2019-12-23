FROM debian:buster
RUN apt-get update && apt-get -y upgrade
RUN apt-get install -y pulseaudio pulseaudio-module-bluetooth
RUN adduser --disabled-password --gecos '' pi
RUN sed -i 's/<policy user="root">/<policy user="pi">/g' /etc/dbus-1/system.d/bluetooth.conf
RUN echo 'load-module module-esound-protocol-tcp auth-anonymous=1' >> /etc/pulse/default.pa
RUN echo 'load-module module-native-protocol-tcp auth-ip-acl=127.0.0.1;192.168.0.0/16;172.0.0.0/8' >> /etc/pulse/default.pa
RUN sed -i 's/load-module module-suspend-on-idle/#load-module module-suspend-on-idle/g' /etc/pulse/default.pa

RUN echo 'exit-idle-time = -1' >> /etc/pulse/daemon.conf

EXPOSE 4713
USER pi:pi

CMD pulseaudio -vvvv