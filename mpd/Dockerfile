FROM debian:buster
RUN apt-get update 
# && apt-get -y upgrade

RUN apt-get install -y mpd
#RUN apt-get install -y nano

### this section is already in attached drive
# RUN mkdir /config
# RUN touch /config/pid
# RUN touch /config/tag_cache
# RUN touch /config/state
# RUN mkdir /config/music
# RUN mkdir /config/playlists
#RUN chown -R mpd:audio /config

### this section is not needed we copy prepared mpd.conf file
#RUN sed -i 's/\/run\/mpd\/pid/\/config\/pid/g' /etc/mpd.conf
#RUN sed -i 's/\/var\/lib\/mpd\//\/config\//g' /etc/mpd.conf
#RUN sed -i 's/localhost/::/g' /etc/mpd.conf

#we failed with this web client
#apt install ruby ruby-dev openssl libssl-dev
#RUN apt-get install -y ruby-full
#RUN apt-get install -y ruby-dev
#RUN gem update --system
#RUN gem install pifi --no-document

#RUN apt-get install -y sudo
#RUN echo "mpd ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

#COPY mpd.conf /etc/mpd.conf

USER mpd:audio
EXPOSE 6600

CMD mpd --verbose --stdout --no-daemon /config/mpd.conf