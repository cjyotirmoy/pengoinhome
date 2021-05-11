FROM ubuntu:bionic
RUN apt-get update
RUN DEBIAN_FRONTEND="noninteractive" apt-get install -y apt-utils curl gnupg software-properties-common
RUN curl -fsSL https://gerbera.jfrog.io/artifactory/api/gpg/key/public | apt-key add -
RUN apt-add-repository https://gerbera.jfrog.io/artifactory/debian
RUN apt-get update
RUN DEBIAN_FRONTEND="noninteractive" apt-get install -y gerbera sqlite3
COPY config.xml /root/.config/gerbera/config.xml
EXPOSE 1900 1900/udp 49152 49152/udp 49153 49153/udp
VOLUME /content
CMD ["gerbera"]
