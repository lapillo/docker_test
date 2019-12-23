FROM nodered/node-red
#RUN apk update

RUN npm update && npm upgrade
RUN npm install node-red-contrib-home-assistant-websocket \
                node-red-contrib-mytimeout \
                node-red-contrib-stoptimer \
                node-red-node-rbe \
                node-red-node-tail

EXPOSE 1880