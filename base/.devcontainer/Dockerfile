FROM mcr.microsoft.com/devcontainers/base:ubuntu

ENV GITHUB_USER="Forestsoft-de"

USER root
RUN usermod -d /home/coder -l coder vscode \
    && mv /home/vscode /home/coder \
    && mv /etc/sudoers.d/vscode /etc/sudoers.d/coder \
    && sed -i s/vscode/coder/ /etc/sudoers.d/coder \
    && echo "fs.inotify.max_user_watches = 1048576" >> /etc/sysctl.d/idea.conf
    && groupmod -n coder vscode \
    && echo "alias kickstart='curl -fLs https://raw.githubusercontent.com/Forestsoft-de/dotfiles/master/install.sh > install.sh && chmod +x install.sh && ./install.sh'" >> /etc/profile.d/kickstart-alias.sh
USER coder
