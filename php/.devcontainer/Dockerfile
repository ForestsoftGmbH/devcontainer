FROM ghcr.io/forestsoftgmbh/devcontainer:latest

USER root

RUN curl -SLs https://raw.githubusercontent.com/shyim/devcontainers-features/main/src/php/install.sh | EXTENSIONSEXTRA="xdebug redis yaml mbstring" sudo bash -s --

RUN a2dissite 000-default \
    && a2enmod proxy proxy_fcgi \
    && usermod -a -G www-data coder \
    && update-rc.d apache2 defaults \
    && update-rc.d php8.2-fpm defaults \
    && mkdir -p /home/coder/apache2/

COPY 000-default.conf /home/coder/apache2    

RUN echo "IncludeOptional /home/coder/apache2/*.conf" >> /etc/apache2/apache2.conf

RUN mkdir -p /opt/template/ && sudo rsync -arv /home/coder/ /opt/template/home/
UsER coder



