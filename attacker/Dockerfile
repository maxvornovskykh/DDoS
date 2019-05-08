FROM node

MAINTAINER Max Vornovskykh <max.vornovskykh@gmail.com>

RUN npm install commander && npm install keypress

COPY slowloris/* /home/node/app/

WORKDIR /home/node/app
USER node
CMD ["node", "slowloris", "http://victim:80"]