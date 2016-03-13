FROM ubuntu:wily

MAINTAINER matwu matwumatwu@gmail.com

# Install Nginx.
RUN apt-get update && apt-get install -y \
  build-essential \
  software-properties-common \
  byobu curl git htop man unzip vim wget \
  nginx &&\
  echo "\ndaemon off;" >> /etc/nginx/nginx.conf && \
  chown -R www-data:www-data /var/lib/nginx

# Define mountable directories.
VOLUME ["/etc/nginx/sites-enabled", "/etc/nginx/certs", "/etc/nginx/conf.d", "/var/log/nginx", "/var/www/html"]

# Define working directory.
WORKDIR /etc/nginx

# Define default command.
CMD ["nginx"]

# Expose ports.
EXPOSE 80
EXPOSE 443
