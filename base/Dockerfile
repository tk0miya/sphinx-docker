FROM ubuntu:xenial
MAINTAINER Sphinx Team <https://github.com/sphinx-doc/sphinx>

RUN mkdir /docs
RUN apt-get update \
 && apt-get install -y \
      graphviz \
      make \
      python3 \
      python3-dev \
      python3-pip \
      python3-pil \
 && apt-get autoremove \
 && apt-get clean

RUN pip3 install Sphinx
