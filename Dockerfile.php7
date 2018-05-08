FROM grrrnl/garp3-httpd:php7
MAINTAINER David Spreekmeester <david@grrr.nl>

RUN \
    # --- Install Fish shell for Debian 8.x
    apt-key adv --keyserver keyserver.ubuntu.com --recv-key D880C8E4 && \
    echo 'deb http://download.opensuse.org/repositories/shells:/fish:/release:/2/Debian_8.0/ ./' \
        > /etc/apt/sources.list.d/fish-shell.list && \
    apt -y update && \
    apt -y install fish && \
    # --- Basics
    apt -y install git vim && \
    # --- Install general MySQL client for easy access to db container
    apt -y install mysql-client && \
    # --- Install Node 6.x & NPM
    wget -qO- https://deb.nodesource.com/setup_6.x | bash - && \
    apt -y install nodejs && \
    # --- Install zlib and zip php extension
    apt -y install zlib1g-dev && \
    docker-php-ext-install zip && \
    # --- Install ruby gems
    apt -y install ruby rubygems-integration && \
    gem install scss-lint && \
    gem install semver && \
    # --- Install node modules
    npm i -g gulp && \
    npm i -g bower && \
    npm i -g jshint && \
    npm i -g yarn && \
    # --- Deploy tools
    gem install net-ssh -v 2.9.2 && \
    gem install capistrano && \
    # --- Install python package manager
    apt -y install python python-pip && \
    # --- Install aws cli tool
    pip install awscli
EXPOSE 80
