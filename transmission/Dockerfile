FROM robsharp/rpi-transmission

EXPOSE 9091
EXPOSE 51413
EXPOSE 51413

COPY web /usr/share/transmission/web

#RUN sed -i 's/"rpc-whitelist-enabled": true/"rpc-whitelist-enabled": false/g' /etc/transmission-daemon/settings.json