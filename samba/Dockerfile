FROM trnape/rpi-samba

EXPOSE 445
CMD ["  -v /media/transmission:/media/transmission \
  -v /media/1TB:/media/1TB \
  -v /media/500GB:/media/500GB \
  -v /home/pi/homeassistant:/share/homeassistant \
  --name samba trnape/rpi-samba \
  -u share:share \
  -s share_net:/media/1TB/share_net:rw:share \
  -s downloads:/media/transmission/downloads:rw:share \
  -s babes:/media/500GB/babes:rw:share \
  -s homeassistant:/share/homeassistant:rw:share"]
