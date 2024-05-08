FROM ghcr.io/forestsoftgmbh/devcontainer:latest

USER root

RUN a2dissite 000-default \
    && a2enmod proxy proxy_fcgi \
    && usermod -a -G www-data coder \
    && mkdir -p /home/coder/apache2/ \
    && cp -R /etc/apache2/sites-available/* /home/coder/apache2/
    
RUN echo "IncludeOptional /home/coder/apache2/*.conf" >> /etc/apache2/apache2.conf

RUN mkdir -p /opt/template/ && sudo rsync -arv /home/coder/ /opt/template/home/
UsER coder



