FROM centos:7
ENTRYPOINT ["/bin/bash"]
RUN mkdir /var/playpen
COPY ./ /var/playpen
RUN printf "\n" && \
	yum update -y && \
	yum install epel-release -y && \
	yum install vim -y && \
	yum install php-pear php-devel gcc -y && \
	yum install ImageMagick ImageMagick-devel ImageMagick-perl -y && \
	yum install libreoffice -y && \
	yum install chromium -y && \
	printf "\n"

WORKDIR /var/playpen
