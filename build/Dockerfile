FROM ubuntu:focal

# General platform dependencies come before any other decision
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y tzdata \
    && ln -fs /usr/share/zoneinfo/UTC /etc/localtime \
    && dpkg-reconfigure --frontend noninteractive tzdata
RUN apt-get update && apt-get install -y \
    git build-essential protobuf-compiler python \
    libprotobuf-dev libcurl4-openssl-dev libboost-all-dev \
    libncurses5-dev wget m4 clang libssl-dev \
    debhelper curl
RUN wget https://download.rethinkdb.com/repository/raw/dist/rethinkdb-2.4.1.tgz && \
    tar xf rethinkdb-2.4.1.tgz
RUN cd rethinkdb-2.4.1.tgz && \
    ./configure --allow-fetch CXX=clang++ && \
    make build-deb UBUNTU_RELEASE=focal
