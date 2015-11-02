FROM ubuntu:14.04

COPY conf /etc/opkg.conf

MAINTAINER Noam Y. Tenne <noam@10ne.org>
RUN apt-get update && apt-get install -y gcc pkg-config libarchive13 libarchive-dev libcurl3 libcurl3-dev libgpgme11 libgpgme11-dev autogen autoconf make wget libtool vim curl
RUN wget http://git.yoctoproject.org/cgit/cgit.cgi/opkg/snapshot/opkg-0.3.0.tar.gz
RUN tar -xvf opkg-0.3.0.tar.gz
RUN cd opkg-0.3.0 && ./autogen.sh && ./configure --with-static-libopkg --disable-shared --disable-gpg --disable-curl --prefix=/usr && make && make install
