FROM debian:buster
RUN apt-get update
RUN apt-get install -y pulseaudio pulseaudio-module-bluetooth
RUN adduser --disabled-password --gecos '' pi
RUN sed -i 's/<policy user="root">/<policy user="pi">/g' /etc/dbus-1/system.d/bluetooth.conf
RUN echo 'load-module module-esound-protocol-tcp auth-anonymous=1' >> /etc/pulse/default.pa
RUN echo 'load-module module-native-protocol-tcp auth-ip-acl=127.0.0.1;192.168.0.0/16;172.0.0.0/8' >> /etc/pulse/default.pa

#RUN echo 'load-module module-zeroconf-publish' >> /etc/pulse/default.pa

#to remove
#RUN apt-get install -y nano
#RUN apt-get install -y net-tools

EXPOSE 4713
USER pi:pi

CMD pulseaudio -vvvv
#CMD [ "pulseaudio", "-vvvv"]