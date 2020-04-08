FROM trnape/rpi-samba

EXPOSE 445
CMD ["-u","share:share",\
"-s","share_net:/media/1TB/share_net:rw:share",\
"-s","downloads:/media/transmission/downloads:rw:share",\
"-s","scrapy:/share/scrapy:rw:share",\
"-s","homeassistant:/share/homeassistant:rw:share"]

ENTRYPOINT ["/run.sh"]
