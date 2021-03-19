FROM ubuntu:20.04
WORKDIR /app
RUN apt-get update && \
    apt install -y wget dumb-init && \
    wget https://github.com/ianchen06/docker-rethinkdb/releases/download/2.4.1/rethinkdb_2.4.1.0focal_arm64.deb && \
    apt install -y ./rethinkdb_2.4.1.0focal_arm64.deb && \
    apt-get remove --purge -y wget && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /app/rethinkdb_2.4.1.0focal_arm64.deb
