# 0.0.0
FROM rdeleo/centos7-php7.3-apache-dev:latest
MAINTAINER Nobody

RUN yum update -y && \
	yum install git make vim nmap -y && \
	echo

RUN yum update -y && \
	yum install php73-php-pear php73-php-pecl-imagick php73-php-pecl-imagick-devel php73-php-pspell php73-php-pgsql -y && \
	echo "extension=/opt/remi/php73/root/usr/lib64/php/modules/imagick.so" >> /etc/php.d/imagick.ini && \
	echo

RUN yum update -y && \
	yum install libreoffice -y && \
	yum install chromium -y && \
	echo

RUN yum update -y && \
	yum install unoconv postgresql qpdf sox qrencode python3 xorg-x11-server-Xvfb -y && \
	yum install ruby -y && \
	gem install sass && \
	echo
#ffmpeg coreutils ruby-sass  yui-compressor python3-pyparsing
