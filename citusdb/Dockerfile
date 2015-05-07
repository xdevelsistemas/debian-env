FROM xdevelsistemas/debian-env:latest

MAINTAINER Clayton Santos da Silva "clayton@xdevel.com.br"

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get -y install wget && cd /root \
  && wget http://packages.citusdata.com/readline-6.0/citusdb-4.0.0-1.amd64.deb \
  && dpkg --install citusdb-4.0.0-1.amd64.deb &&  rm citusdb-4.0.0-1.amd64.deb \
  && apt-get -y remove wget && apt-get autoclean -y && apt-get clean
#ADD run.sh /opt/citusdb/run.sh
#RUN chmod +x /opt/citusdb/run.sh
EXPOSE 5432/tcp
#USER postgres
