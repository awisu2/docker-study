FROM ubuntu:18.04

# apt update
RUN apt-get update
RUN apt-get install -y sudo

# add sudo user
RUN groupadd -g 1000 user && \
    useradd  -g      user -G sudo -m -s /bin/bash user && \
    echo 'user:password' | chpasswd

RUN echo 'Defaults visiblepw'             >> /etc/sudoers
RUN echo 'iganari ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

USER user
