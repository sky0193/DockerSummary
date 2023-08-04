# Download base image ubuntu 22.04
FROM ubuntu:22.04

# LABEL about the custom image
LABEL maintainer="lena.bykov93@gmail.com"
LABEL version="0.1"
LABEL description="This is a custom Docker Image for Ubuntu22 with compiled grpc from source"

# Disable Prompt During Packages Installation
ARG DEBIAN_FRONTEND=noninteractive

# Update Ubuntu Software repository
RUN apt update
RUN apt-get install -y apt-utils build-essential  git cmake
RUN apt-get update && apt-get install -y lsb-release && apt-get clean all
RUN apt-get update && apt-get install -y protobuf-compiler libprotobuf-dev
RUN apt-get update && apt-get install -y libgrpc-dev
RUN apt-get install -y build-essential autoconf libtool pkg-config
RUN git clone -b v1.50.0-pre1 https://github.com/grpc/grpc && \
    cd grpc && \
    git submodule update --init && \
    mkdir -p cmake/build && \
    cd cmake/build && \
    cmake ../.. && \
    make && \
    make install
