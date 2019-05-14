FROM ubuntu:xenial

MAINTAINER Soopsio <admin@soops.io>
RUN apt-get update \
    && apt-get install -y iputils-ping iproute2 traceroute \
    curl dnsutils netcat-openbsd jq nmap net-tools \
    && rm -rf /var/lib/apt/lists/*

LABEL org.label-schema.vcs-type="Git" \
      org.label-schema.vcs-url="https://github.com/soopsio/docker/tree/master/net-tools"
     
