# 0.0.0
FROM rdeleo/centos7-php7.3-apache-dev:latest
MAINTAINER myro.stadler+dockerhub.medium@gmail.com

RUN yum update -y && \
	yum install git make vim composer nmap gcc postgresql qpdf sox qrencode python3 xorg-x11-server-Xvfb libsass -y && \
	echo

RUN yum update -y && \
	yum install php73-php-pear php73-php-pecl-imagick php73-php-pecl-imagick-devel php73-php-pspell php73-php-pgsql -y && \
	echo "extension=/opt/remi/php73/root/usr/lib64/php/modules/imagick.so" >> /etc/php.d/imagick.ini && \
	echo

RUN yum update -y && \
	yum install libreoffice -y && \
	yum install chromium -y && \
	echo

#ffmpeg coreutils yui-compressor python3-pyparsing