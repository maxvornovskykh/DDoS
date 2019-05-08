FROM nginx

MAINTAINER Max Vornovskykh <max.vornovskykh@gmail.com>

COPY config/nginx.conf /etc/nginx/
COPY config/victim.conf /etc/nginx/conf.d
RUN rm -rf /etc/nginx/conf.d/default.conf
EXPOSE 80 8080

CMD ["nginx", "-g", "daemon off;"]