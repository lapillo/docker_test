FROM debian:buster
RUN apt-get update && apt-get install -y wget
RUN apt-get install -y gnupg gnupg2 gnupg1
RUN wget -q -O - https://apt.mopidy.com/mopidy.gpg | apt-key add -
RUN wget -q -O /etc/apt/sources.list.d/mopidy.list https://apt.mopidy.com/buster.list
RUN wget -q -O /etc/apt/sources.list.d/mopidy.list https://apt.mopidy.com/stretch.list
RUN apt-get update
RUN apt-get install -y mopidy
RUN apt-get install -y python-pip
RUN pip install Mopidy-Iris
RUN mkdir /root/.config && mkdir /root/.config/mopidy
COPY mopidy.conf /root/.config/mopidy/mopidy.conf

EXPOSE 6680
CMD ["mopidy"]