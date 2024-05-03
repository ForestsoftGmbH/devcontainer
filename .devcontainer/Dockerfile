FROM mcr.microsoft.com/devcontainers/base:ubuntu

USER root
RUN usermod -l coder vscode \
    && mv /home/vscode /home/coder \
    && mv /etc/sudoers.d/vscode /etc/sudoers.d/coder \
    && sed -i s/vscode/coder/ /etc/sudoers.d/coder
USER coder
