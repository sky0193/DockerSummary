# Download base image ubuntu 22.04
FROM ubuntu:22.04

# LABEL about the custom image
LABEL maintainer="lena.bykov93@gmail.com"
LABEL version="0.1"
LABEL description="This is a custom Docker Image for Empty Ubuntu22 playground."

# Disable Prompt During Packages Installation
ARG DEBIAN_FRONTEND=noninteractive

# Update Ubuntu Software repository
RUN apt update
RUN apt-get update && apt-get install -y lsb-release && apt-get clean all
