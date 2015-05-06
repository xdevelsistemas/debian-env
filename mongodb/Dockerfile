FROM xdevelsistemas/debian-env:latest

MAINTAINER Clayton Santos da Silva "clayton@xdevel.com.br"

ENV DEBIAN_FRONTEND noninteractive


# Install packages
RUN apt-get update && apt-get install -y mongodb-server

# Create database directory
RUN mkdir -p /var/opt/mongodb && chown mongodb.mongodb /var/opt/mongodb

# Expose MongoDB port
EXPOSE 27017

USER mongodb


VOLUME  ["//var/opt/mongodb"]

#CMD ["--dbpath", "/var/opt/mongodb", "--replSet", "rs0"]
CMD ["/usr/bin/mongod","--dbpath", "/var/opt/mongodb"]

