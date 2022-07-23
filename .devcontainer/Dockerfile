FROM ubuntu:latest

COPY .bashrc tmp
RUN cp /tmp/.bashrc /etc/skel/.bashrc
RUN mv /tmp/.bashrc ~/.bashrc

COPY .profile tmp
RUN cp /tmp/.profile /etc/skel/.profile
RUN mv /tmp/.profile ~/.profile

# Replace shell with bash so we can source files
RUN rm /usr/bin/sh && \
    ln -s /usr/bin/bash /bin/sh && \
    chsh -s /bin/bash

RUN apt-get update && \
    apt-get -y install curl

RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash && \
    source ~/.nvm/nvm.sh

RUN bash -c "nvm install --lts"
