FROM ubuntu
MAINTAINER Anshuman Bhartiya <anshuman.bhartiya@gmail.com>

RUN apt-get update
RUN apt-get -y install curl wget
RUN curl -o caddy.tar.gz 'https://caddyserver.com/download/build?os=linux&arch=amd64&features='
RUN tar -zxvf caddy.tar.gz
RUN openssl req -days 3650 -new -x509 -newkey rsa:2048 -nodes -keyout key.pem -out cert.pem -days 9999 -subj "/C=US/ST=LAIR/L=Lairville/O=Dis/CN=www.lair.fun"
RUN printf '127.0.0.1:11013\ntls cert.pem key.pem\nproxy /api 127.0.0.1:11015\nproxy / 127.0.0.1:11014 {\n  websocket\n}\n' > Caddyfile
