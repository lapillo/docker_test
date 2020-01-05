FROM debian:buster
RUN apt-get update 
# && apt-get -y upgrade
RUN apt-get install -y wget
RUN apt-get install -y gnupg gnupg2 gnupg1
RUN wget -q -O - https://apt.mopidy.com/mopidy.gpg | apt-key add -
RUN wget -q -O /etc/apt/sources.list.d/mopidy.list https://apt.mopidy.com/buster.list
RUN wget -q -O /etc/apt/sources.list.d/mopidy.list https://apt.mopidy.com/stretch.list
RUN apt-get update
RUN apt-get install -y mopidy gstreamer1.0-plugins* python-pip
RUN pip install Mopidy-Iris
RUN pip install Mopidy-MusicBox-Webclient
#RUN pip install Mopidy-Moped
#RUN pip install Mopidy-Mopify

RUN apt-get install -y sudo

RUN echo "mopidy ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers
#RUN mkdir /root/.config && mkdir /root/.config/mopidy
#COPY mopidy.conf /root/.config/mopidy/mopidy.conf
COPY mopidy.conf /var/lib/mopidy/.config/mopidy/mopidy.conf
USER mopidy
RUN sudo chown -R mopidy:audio /var/lib/mopidy

ENV XDG_MUSIC_DIR /var/lib/mopidy/file

EXPOSE 6680
EXPOSE 6600
CMD mopidy