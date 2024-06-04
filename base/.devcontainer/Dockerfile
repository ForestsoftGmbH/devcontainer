FROM mcr.microsoft.com/devcontainers/base:ubuntu

ENV GITHUB_USER="Forestsoft-de"

USER root
RUN usermod -d /home/coder -l coder vscode \
    && mv /home/vscode /home/coder \
    && mv /etc/sudoers.d/vscode /etc/sudoers.d/coder \
    && sed -i s/vscode/coder/ /etc/sudoers.d/coder \
    && echo "fs.inotify.max_user_watches = 1048576" >> /etc/sysctl.d/idea.conf \
    && groupmod -n coder vscode \
    && sudo curl https://raw.githubusercontent.com/docker/docker-ce/master/components/cli/contrib/completion/bash/docker -o /etc/bash_completion.d/docker.sh \
    && apt update \
    && apt install -y pass \
    && rm -rf /var/lib/apt/lists/* \
    && echo "alias kickstart='curl -fLs https://raw.githubusercontent.com/Forestsoft-de/dotfiles/master/install.sh > install.sh && chmod +x install.sh && ./install.sh'" >> /etc/profile.d/kickstart-alias.sh
USER coder
