FROM debian:buster
RUN apt-get update 
# && apt-get -y upgrade

RUN apt-get install -y nano

RUN apt-get install -y wget tar bzip2 libmpdclient-dev
RUN wget -q -O /home/ympd-1.2.3-armhf.tar.bz2 https://ympd.org/downloads/ympd-1.2.3-armhf.tar.bz2
WORKDIR "/home"
RUN tar -xvf ympd-1.2.3-armhf.tar.bz2
WORKDIR "/"

EXPOSE 80

CMD /home/ympd --webport 80
#CMD tail -f /etc/passwd