#
# Nginx Dockerfile
#
# https://github.com/dockerfile/nginx
#

# Pull base image.
FROM ubuntu:16.04

# Install Nginx.

RUN echo "deb http://archive.ubuntu.com/ubuntu/ xenial main universe" >> /etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y wget dialog net-tools
RUN apt-get install -y nginx

RUN rm -v /etc/nginx/nginx.conf
RUN mkdir /var/www/pdandqueenie.com/
ADD nginx.conf /etc/nginx/
ADD htdocs /var/www/pdandqueenie.com/htdocs


RUN echo "daemon off;" >> /etc/nginx/nginx.conf


# Expose ports.
EXPOSE 80
EXPOSE 443
RUN nginx -t
CMD service nginx start
