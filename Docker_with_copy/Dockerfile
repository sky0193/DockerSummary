# Download base image debian 12
FROM debian:bookworm

# LABEL about the custom image
LABEL maintainer="kristian.schmidt@aristech.de"
LABEL version="1.0"
LABEL description="custom docker image for building apps on deb 12"

# Disable Prompt During Packages Installation
ARG DEBIAN_FRONTEND=noninteractive

# Update Ubuntu Software repository
RUN apt update
RUN apt upgrade
RUN apt-get install -y apt-utils build-essential git cmake 
RUN apt-get install -y lsb-release


COPY ../application-server /app

