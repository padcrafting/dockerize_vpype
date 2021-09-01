FROM alpine:latest

WORKDIR /usr/vpype

# this is the minimum to run vpype
RUN apk update && \
    apk add --no-cache \
        gcc bash python3 python3-dev py3-pip py3-scipy blas lapack libc-dev geos-dev 

RUN  pip install vpype

# uncomment to install plugins

# Flow Imager
# pip install git+https://github.com/serycjon/vpype-flow-imager.git\#egg=vpype-flow-imager 

    
ENV LANG en_US.utf8