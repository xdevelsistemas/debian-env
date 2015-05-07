FROM xdevelsistemas/debian-env:latest

MAINTAINER Clayton Santos da Silva "clayton@xdevel.com.br"

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update -qq

RUN apt-get install wget -qq

RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ wheezy-pgdg main" > /etc/apt/sources.list.d/pgdg.list

RUN gpg --keyserver keys.gnupg.net --recv-keys ACCC4CF8

RUN gpg --export --armor ACCC4CF8|apt-key add -

RUN apt-get update 

# If you need use a specific locale, you can change commands below. e.g. pt_BR.UTF-8
RUN echo "locales locales/locales_to_be_generated multiselect en_US.UTF-8 UTF-8" | debconf-set-selections &&\
    echo "locales locales/default_environment_locale select en_US.UTF-8" | debconf-set-selections

RUN apt-get install locales -qq

ENV LC_ALL en_US.UTF-8

RUN         apt-get update && apt-get install -y redis-server
EXPOSE      6379
CMD	    ["/usr/bin/redis-server"]


