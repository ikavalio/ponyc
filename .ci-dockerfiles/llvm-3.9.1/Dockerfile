FROM ubuntu:14.04

ENV LLVM_VERSION 3.9.1

RUN apt-get update \
 && apt-get install -y software-properties-common \
 && add-apt-repository -y ppa:ubuntu-toolchain-r/test \
 && apt-get update \
 && apt-get install -y \
  apt-transport-https \
  build-essential \
  g++-6 \
  git \
  libncurses5-dev \
  libssl-dev \
  make \
  wget \
  xz-utils \
  zlib1g-dev \
 && wget -O - http://llvm.org/releases/${LLVM_VERSION}/clang+llvm-${LLVM_VERSION}-x86_64-linux-gnu-debian8.tar.xz \
 | tar xJf - --strip-components 1 -C /usr/local/ clang+llvm-${LLVM_VERSION}-x86_64-linux-gnu-debian8

# install pcre2
RUN wget ftp://ftp.csx.cam.ac.uk/pub/software/programming/pcre/pcre2-10.21.tar.bz2 \
 && tar xvf pcre2-10.21.tar.bz2 \
 && cd pcre2-10.21 \
 && ./configure --prefix=/usr \
 && make install \
 && cd .. \
 && rm -rf pcre2-10.21*
