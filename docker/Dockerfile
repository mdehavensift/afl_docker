FROM ubuntu:14.04

COPY afl-2.51b /root/afl

RUN apt-get update && \
    apt-get install -y patch bison automake make python libtool gcc make wget libglib2.0-dev && \
    cd /root/afl && \
    make all && \
    cd /root/afl/qemu_mode && \
    sh build_qemu_support.sh && \
    apt-get purge -y patch bison automake make python libtool gcc make wget && \
    rm -rf /var/lib/apt/lists/*