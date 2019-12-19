FROM trnape/rpi-samba

EXPOSE 445
CMD ["-u","share:share",\
"-s","share_net:/media/1TB/share_net:rw:share",\
"-s","downloads:/media/transmission/downloads:rw:share",\
#"-s","babes:/media/500GB/babes:rw:share",\
"-s","homeassistant:/share/homeassistant:rw:share"]

ENTRYPOINT ["/run.sh"]
