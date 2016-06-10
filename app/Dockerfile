FROM centos:centos6
MAINTAINER Anshuman bhartiya <anshuman.bhartiya@gmail.com>

# Enable Extra Packages for Enterprise Linux (EPEL) for CentOS
RUN yum install -y epel-release

# Install Node.js and npm
RUN yum install -y npm wget

RUN wget https://github.com/lair-framework/lair/releases/download/v2.1.0/lair-v2.1.0-linux-amd64.tar.gz
RUN tar -zxvf lair-v2.1.0-linux-amd64.tar.gz
RUN cd bundle

RUN curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.26.1/install.sh | bash
RUN source ~/.bash_profile; nvm install v0.10.40; nvm use v0.10.40

RUN cd bundle/programs/server; npm i; cd ../../

WORKDIR /bundle
