FROM debian:9
ENTRYPOINT ["/bin/bash"]
RUN mkdir /var/playpen
COPY ./ /var/playpen

RUN printf "\n" && \
	mkdir -p /usr/share/man/man1 && \
	apt-get update -y && \
	apt-get install aptitude -y && \
	aptitude install openjdk-8-jre-headless -y && \
    aptitude install openjdk-8-jre -y && \
    aptitude install libreoffice -y && \
    aptitude install -f -y && \
	aptitude install imagemagick -y && \
	apt-get install chromium -y && \
	printf "\n"

WORKDIR /var/playpen
