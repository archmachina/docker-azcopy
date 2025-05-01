FROM ubuntu:24.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && apt upgrade -y && apt install -y curl

RUN mkdir -p /usr/local/bin && cd /usr/local/bin && \
  curl -o azcopy.tar.gz https://azcopyvnext.azureedge.net/release20230331/azcopy_linux_amd64_10.18.0.tar.gz && \
  tar -xzvf azcopy.tar.gz --strip-components=1 --wildcards \*/azcopy && \
  chmod 755 /usr/local/bin/azcopy && \
  chown root:root /usr/local/bin/azcopy && \
  rm -f /usr/local/bin/azcopy.tar.gz

WORKDIR /work
ENV HOME=/work
RUN chmod 777 /work

ENTRYPOINT [ "/usr/local/bin/azcopy" ]
