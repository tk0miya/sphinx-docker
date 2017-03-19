docker-sphinx
=============

Docker image for Sphinx build.

Images
------

* tk0miya/sphinx-docker:base
* tk0miya/sphinx-docker:html
* tk0miya/sphinx-docker:epub
* tk0miya/sphinx-docker:pdf

.. note:: ``tk0miya/sphinx-docker:pdf`` contains TeXLive packages. So the image is very large (over 2GB!).

Usage
-----

Build HTML document::

  $ docker run --rm -v /path/to/document:/docs tk0miya/sphinx-docker:html

Build EPUB document::

  $ docker run --rm -v /path/to/document:/docs tk0miya/sphinx-docker:epub

Build PDF document::

  $ docker run --rm -v /path/to/document:/docs tk0miya/sphinx-docker:epub

Tips
----

If you would like to install dependencies, use ``tk0miya/sphinx-docker:base`` as a base image::

  # in your Dockerfile
  FROM tk0miya/sphinx-docker:base

  WORKDIR /docs
  ADD requirements.txt
  RUN pip install -r requirements.txt
  CMD make html
