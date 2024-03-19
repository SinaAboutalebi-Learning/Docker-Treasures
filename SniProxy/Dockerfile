# bullseye = ubuntu 20.04 focal
FROM debian:bullseye 

# Install dependencies , Download sniProxy Source , Build & Install Package , Remove Unnecessary Packages & Files
RUN apt update &&\
apt install -y autotools-dev cdbs debhelper dh-autoreconf dpkg-dev gettext libev-dev libpcre3-dev libudns-dev pkg-config fakeroot devscripts &&\ 
wget -O /tmp/sniproxy.tar.gz https://github.com/dlundquist/sniproxy/archive/refs/tags/0.6.1.tar.gz &&\
cd /tmp && tar -xzvf sniproxy.tar.gz &&\
cd /tmp/sniproxy* && ./autogen.sh && dpkg-buildpackage -us -uc -b &&\
dpkg -i /tmp/*.deb &&\
rm -rf /tmp/sniproxy* && apt purge -y debhelper dh-autoreconf dpkg-dev libev-dev libpcre3-dev libudns-dev pkg-config

# Add Config File
COPY sniproxy.conf /etc/sniproxy.conf

# Expose Ports
EXPOSE 80
EXPOSE 443

# Run sniProxy in foreground
ENTRYPOINT [ "sniproxy" ,"-f" ]