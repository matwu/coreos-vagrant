FROM ubuntu:wily

MAINTAINER matwu matwusk8@gmail.com

# open port for nginx
EXPOSE 80

# install modules by apt-get
RUN apt-get update && apt-get install -y \
  nginx \
  && rm -rf /var/lib/apt/lists/*

# start nginx
ENTRYPOINT nginx -g 'daemon off;' -c /etc/nginx/nginx.conf
