FROM ubuntu:20.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && apt upgrade -y && apt install -y curl

RUN mkdir -p /usr/local/bin && cd /usr/local/bin && \
  curl -o azcopy.tar.gz https://azcopyvnext.azureedge.net/release20230331/azcopy_linux_amd64_10.18.0.tar.gz && \
  tar -xzvf azcopy.tar.gz --strip-components=1
