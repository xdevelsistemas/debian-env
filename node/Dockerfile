FROM xdevelsistemas/debian-env:java7-env

MAINTAINER Clayton Santos da Silva "clayton@xdevel.com.br"

RUN apt-get update && \ 
    apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup | bash - && \
    apt-get install -y nodejs

# Setup
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv E56151BF

# Add the repository
RUN echo "deb http://repos.mesosphere.io/debian wheezy main" | \
   tee /etc/apt/sources.list.d/mesosphere.list \
   &&  apt-get -y update

RUN apt-get install -y maven \
    mesos \
    scala 


