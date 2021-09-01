FROM ubuntu:latest

WORKDIR /usr/vpype


RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* \
    && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8

# this is the minimum to run vpype
RUN export DEBIAN_FRONTEND=noninteractive && apt update && apt install -y python3.9 python3-pip python3-shapely git

RUN  pip install vpype

# uncomment to install plugins

# Flow Imager
# pip install git+https://github.com/serycjon/vpype-flow-imager.git\#egg=vpype-flow-imager 

    
ENV LANG en_US.utf8