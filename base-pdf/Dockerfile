FROM tk0miya/sphinx-base:latest
MAINTAINER Sphinx Team <https://github.com/sphinx-doc/sphinx>

RUN apt-get install -y \
      lmodern \
      texlive-latex-recommended \
      texlive-latex-extra \
      texlive-fonts-recommended \
      texlive-fonts-extra \
      texlive-luatex \
      texlive-xetex \
 && apt-get autoremove \
 && apt-get clean
