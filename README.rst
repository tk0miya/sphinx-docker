docker-sphinx
=============

Docker image for Sphinx build.

Images
------

* tk0miya/sphinx-base
* tk0miya/sphinx-base-pdf

.. note:: ``tk0miya/sphinx-base-pdf`` contains TeXLive packages. So the image is very large (over 2GB!).

Usage
-----

Build HTML document::

  $ docker run --rm -v /path/to/document:/docs tk0miya/sphinx-base html

Build EPUB document::

  $ docker run --rm -v /path/to/document:/docs tk0miya/sphinx-base epub

Build PDF document::

  $ docker run --rm -v /path/to/document:/docs tk0miya/sphinx-base-pdf

Tips
----

If you would like to install dependencies, use ``tk0miya/sphinx-base`` as a base image::

  # in your Dockerfile
  FROM tk0miya/sphinx-base

  ADD requirements.txt /docs
  RUN pip3 install -r requirements.txt
  CMD html
