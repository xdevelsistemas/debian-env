FROM debian:jessie
MAINTAINER xdevel <clayton@xdevel.com.br>

# Install some deps, lessc and less-plugin-clean-css, and wkhtmltopdf
RUN set -x; \
        apt-get update \
        && apt-get install -y --no-install-recommends \
            ca-certificates \
            curl \
            node-less \
            node-clean-css \
            python-pyinotify \
            python-renderpm \
            python-support \
            python-pip \ 
            postgresql-client-9.4 \
            postgresql-9.4 \
            postgresql-server-dev-9.4  \ 
            libxml2-dev \ 
            libxslt-dev \
            python-dev \ 
            libsasl2-dev \  
	    python-dev \ 
	    libldap2-dev \ 
	    libssl-dev \
	    file \  
	    g++ \    
        && curl -o wkhtmltox.deb -SL http://nightly.odoo.com/extra/wkhtmltox-0.12.1.2_linux-jessie-amd64.deb \
        && echo '40e8b906de658a2221b15e4e8cd82565a47d7ee8 wkhtmltox.deb' | sha1sum -c - \
        && dpkg --force-depends -i wkhtmltox.deb \
        && apt-get -y install -f --no-install-recommends \
        && apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false -o APT::AutoRemove::SuggestsImportant=false npm \
        && rm -rf /var/lib/apt/lists/* wkhtmltox.deb  

