FROM ghcr.io/forestsoftgmbh/devcontainer:latest


USER root

RUN mkdir -p /opt/template/home  && sudo rsync -arv /home/coder/ /opt/template/home/

USER coder
