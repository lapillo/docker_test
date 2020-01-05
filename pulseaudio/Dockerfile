FROM debian:buster
RUN apt-get update && apt-get -y upgrade
RUN apt-get install -y pulseaudio pulseaudio-module-bluetooth
#RUN adduser --disabled-password --gecos '' pi
#RUN sed -i 's/<policy user="root">/<policy user="pi">/g' /etc/dbus-1/system.d/bluetooth.conf

#enable remote connectoion
RUN echo 'load-module module-esound-protocol-tcp auth-anonymous=1' >> /etc/pulse/default.pa
RUN echo 'load-module module-native-protocol-tcp auth-ip-acl=127.0.0.1;192.168.0.0/16;172.0.0.0/8' >> /etc/pulse/default.pa

#wait while remote connection is idle
RUN sed -i 's/load-module module-suspend-on-idle/#load-module module-suspend-on-idle/g' /etc/pulse/default.pa
RUN echo 'exit-idle-time = -1' >> /etc/pulse/daemon.conf

#for debug
#RUN apt-get install -y sudo
#RUN echo "pi ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

RUN apt-get install -y alsa-utils
#RUN usermod -a -G audio pi
RUN usermod -a -G audio root

EXPOSE 4713
#USER pi:pi
CMD pulseaudio -vvvv -L 'module-alsa-sink device=hw:0,0' -L 'module-switch-on-connect'