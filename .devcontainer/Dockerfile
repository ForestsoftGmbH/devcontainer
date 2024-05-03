FROM mcr.microsoft.com/devcontainers/base:ubuntu

USER root
RUN usermod -l coder vscode \
    && mv /home/vscode /home/coder
USER coder
