FROM archlinux:latest

RUN pacman -Syu --noconfirm base-devel git sudo

RUN useradd -m builder && \
    echo "builder ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

USER builder
WORKDIR /home/builder/pkg
