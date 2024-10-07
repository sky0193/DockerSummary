# Download base image for RHEL 9
FROM registry.access.redhat.com/ubi9/ubi

# LABEL about the custom image
LABEL maintainer="lena.bykov93@gmail.com"
LABEL version="0.1"
LABEL description="This is a custom Docker Image for RHEL 9 with compiled gRPC from source"

# Disable Prompt During Packages Installation
ARG DEBIAN_FRONTEND=noninteractive

# Update Software repository and install necessary tools
RUN yum update -y && \
    yum install -y \
        make \
        gcc \
        gcc-c++ \
        git \
        cmake \
        protobuf-devel \
        grpc-devel \
        autoconf \
        libtool \
        pkgconfig \
        && yum clean all

# Clone gRPC repository and build from source
RUN git clone -b v1.50.0-pre1 https://github.com/grpc/grpc && \
    cd grpc && \
    git submodule update --init && \
    mkdir -p cmake/build && \
    cd cmake/build && \
    cmake ../.. && \
    make && \
    make install

# Clean up the workspace
RUN rm -rf /grpc

# Set the default command (optional)
CMD ["/bin/bash"]

