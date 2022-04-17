FROM debian:latest

ARG WIREGUARD_RELEASE
LABEL maintainer="Aleksandr Trohhatsov"
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update -y && DEBIAN_FRONTEND=noninteractive TZ=Asia/Singapore && \
    apt install -y software-properties-common iptables curl iproute2 nano ifupdown iputils-ping wireguard qrencode wireguard-tools
RUN echo resolvconf resolvconf/linkify-resolvconf boolean false | debconf-set-selections && \
    echo "REPORT_ABSENT_SYMLINK=no" >> /etc/default/resolvconf && \
    apt-get install resolvconf --fix-missing
VOLUME /etc/wireguard
EXPOSE 443/tcp
EXPOSE 80/tcp
EXPOSE 51820

