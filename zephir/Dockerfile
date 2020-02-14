FROM centos:7

RUN printf "\n" && \
	yum update -y && \
	yum install epel-release -y && \
	yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm -y && \
	yum-config-manager --enable remi-php74 && \
	printf "\n"

RUN printf "\n" && \
	yum install php -y && \
	yum install php-pear php-devel \
	php-opcache php-mcrypt php-dom php-mbstring php-gd php-xml php-curl -y && \
	yum install yum-utils coreutils file sudo tree wget git make gcc re2c autoconf automake vim curl composer unzip httpd mod_ssl -y && \
#	yum install ImageMagick ImageMagick-devel ImageMagick-perl -y && \
#	yum install libreoffice -y && \
#	yum install chromium -y && \
	printf "\n"

RUN printf "\n" && \
	cd /tmp && \
	rm -Rf php-zephir-parser && \
	git clone git://github.com/phalcon/php-zephir-parser.git && \
	cd php-zephir-parser/ && \
	phpize && \
	./configure && \
	make && \
	make install && \
	printf "\n"

RUN echo "extension=zephir_parser.so" >> /etc/php.d/custom-php.ini

RUN printf "\n" && \
	cd /tmp && \
	wget https://github.com/phalcon/zephir/releases/download/0.12.16/zephir.phar && \
	chmod +x zephir.phar && \
	mv zephir.phar /usr/bin/zephir && \
	printf "\n"
