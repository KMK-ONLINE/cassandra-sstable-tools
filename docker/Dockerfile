# Dockerfile used to build the deb package

FROM ubuntu:xenial

RUN  apt -qq update && \
     apt install -qy ant debhelper dpkg-dev software-properties-common && \
     add-apt-repository -y ppa:webupd8team/java && \
     apt -qq update && \
     echo debconf shared/accepted-oracle-license-v1-1 select true | \
       debconf-set-selections && \
     echo debconf shared/accepted-oracle-license-v1-1 seen true | \
       debconf-set-selections && \
     apt install -qy oracle-java8-installer oracle-java8-set-default && \
     sed -i 's:# en_US.UTF-8:en_US.UTF-8:g' /etc/locale.gen && \
     locale-gen
