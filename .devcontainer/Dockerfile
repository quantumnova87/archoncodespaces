FROM archlinux:latest

RUN pacman -Sy --noconfirm \
    bash \
    sudo \
    curl \
    vim \
    dbus \
    systemd \
    && pacman -Scc --noconfirm

RUN rm -f /usr/local/bin/systemctl 

RUN useradd -m -s /bin/bash user && echo "user ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers && echo "user:root" | chpasswd

STOPSIGNAL SIGRTMIN+3
CMD ["/sbin/init"]
