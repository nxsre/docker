# Go cross compiler (xgo): Go 1.12.5
# Copyright (c) 2019 Soopsio. All rights reserved.
#
# Released under the MIT license.

FROM karalabe/xgo-base

MAINTAINER Soopsio <admin@soops.io>

# Configure the root Go distribution and bootstrap based on it
ENV GO_VERSION 1125

# go 1.11 darwin 至少需要 macos 10.10 ,
# 使用 MACOSX_DEPLOYMENT_TARGET 指定开发环境版本
ARG MACOSX_DEPLOYMENT_TARGET=10.10
ENV MACOSX_DEPLOYMENT_TARGET=${MACOSX_DEPLOYMENT_TARGET:-10.10}
RUN \
  export ROOT_DIST=https://dl.google.com/go/go1.12.5.linux-amd64.tar.gz      && \
  export ROOT_DIST_SHA=aea86e3c73495f205929cfebba0d63f1382c8ac59be081b6351681415f4063cf && \
  \
$BOOTSTRAP_PURE

# 解决 debconf: delaying package configuration, since apt-utils is not installed
ARG DEBIAN_FRONTEND=noninteractive

RUN sed -i 's/archive.ubuntu.com/mirrors.163.com/g' /etc/apt/sources.list && \
    apt-get update && apt-get install --assume-yes apt-utils
RUN apt-get -y install libpam-dev --assume-yes
