FROM xdevelsistemas/debian-env:java7-env

MAINTAINER Clayton Santos da Silva "clayton@xdevel.com.br"

ENV NGINX_VERSION 1.9.7-1~jessie


RUN wget -c http://nginx.org/keys/nginx_signing.key && \
    apt-key add nginx_signing.key && \
    echo "deb http://nginx.org/packages/mainline/debian/ jessie nginx" >> /etc/apt/sources.list && \
    apt-get update && \
    apt-get install -y ca-certificates nginx=${NGINX_VERSION} && \
    rm -rf /var/lib/apt/lists/*  && \
    # forward request and error logs to docker log collector
    ln -sf /dev/stdout /var/log/nginx/access.log  && \
    ln -sf /dev/stdout /var/log/nginx/access.log 


VOLUME ["/var/cache/nginx"]

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
