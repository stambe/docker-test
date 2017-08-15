FROM ubuntu:14.04

RUN apt-get update -y
RUN apt-get install -y build-essential git libpq-dev nodejs nginx curl libcurl3 libcurl3-dev php5-curl
RUN curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
ADD nginx.conf /etc/nginx/nginx.conf
ADD angularapp /etc/nginx/sites-available/default

# Create app directory
WORKDIR /var/www/html

# Bundle app source
COPY . .

EXPOSE 80
CMD [ "service", "nginx", "start" ]