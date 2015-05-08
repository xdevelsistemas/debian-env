FROM xdevelsistemas/debian-env:latest

MAINTAINER Clayton Santos da Silva "clayton@xdevel.com.br"

ENV DEBIAN_FRONTEND noninteractive

# add our user and group first to make sure their IDs get assigned consistently, regardless of whatever dependencies get added
RUN groupadd -r mongodb && useradd -r -g mongodb mongodb


# Install packages
RUN apt-get update && apt-get install -y mongodb-server && \
	mkdir -p /var/opt/mongodb && \ 
	chown mongodb:mongodb /var/opt/mongodb 


# Expose MongoDB port
EXPOSE 27017

USER mongodb


VOLUME  ["/var/opt/mongodb"]



#CMD ["--dbpath", "/var/opt/mongodb", "--replSet", "rs0"]
CMD ["/usr/bin/mongod","--dbpath", "/var/opt/mongodb"]

