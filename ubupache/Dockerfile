# Ubuntu 18.04 + Apache 2.4 + PHP 7.4
# A base image for running PHP web apps in development

FROM ubuntu:18.04
MAINTAINER myro.stadler+dockerhub@gmail.com

ENV DEBIAN_FRONTEND=noninteractive

RUN printf "\n" && \
	apt-get update -y && \
	apt-get install git make vim composer unzip coreutils software-properties-common ruby-sass python3 -y && \
	printf "\n"

RUN printf "\n" && \
	apt-get install ssl-cert apache2 libapache2-mod-php -y && \
	printf "\n"

RUN printf "\n" && \
	add-apt-repository ppa:ondrej/php -y && \
	apt-get update -y && \
	apt-get install php7.4 -y && \
	printf "\n"

RUN printf "\n" && \
	apt-get install \
		php7.4-pgsql php7.4-mysql php7.4-json php7.4-mbstring php7.4-curl php7.4-xdebug \
		php7.4-opcache php7.4-dom php7.4-gd php7.4-xml \
		-y && \
	printf "\n"

RUN printf "\n" && \
	a2enmod rewrite && \
	a2dismod php7.2 && \
	a2enmod php7.4 && \
	printf "\n"

RUN echo 'ServerName localhost.docker' >> /etc/apache2/apache2.conf
EXPOSE 80
CMD ["apachectl", "-D", "FOREGROUND"]