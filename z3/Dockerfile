FROM ubuntu:xenial

RUN apt-get update && \
    apt-get install --no-install-recommends -q -y python3 python3-pip libgomp1 wget unzip && \
    pip3 install setuptools && \
    rm -rf /var/lib/apt/lists/*

ENV Z3_VERSION 4.6.0

RUN cd /tmp && \
    wget https://github.com/Z3Prover/z3/releases/download/z3-$Z3_VERSION/z3-$Z3_VERSION-x64-ubuntu-16.04.zip && \
    unzip z3-$Z3_VERSION-x64-ubuntu-16.04.zip && \
    cd z3-$Z3_VERSION-x64-ubuntu-16.04 && \
    cp bin/libz3.so /usr/lib/libz3.so && \
    cp -r bin/python/z3 /usr/lib/python3/dist-packages/z3 && \
    cd /tmp && \
    rm -rf z3-$Z3_VERSION-x64-ubuntu-16.04.zip z3-$Z3_VERSION-x64-ubuntu-16.04

CMD ["/bin/bash"]
