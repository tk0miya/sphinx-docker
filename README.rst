docker-sphinx
=============

Docker image for Sphinx build.

Images
------

* sphinx-doc/base
* sphinx-doc/html
* sphinx-doc/epub
* sphinx-doc/pdf

.. note:: ``sphinx-doc/pdf`` contains TeXLive packages. So the image is very large (over 2GB!).

Usage
-----

Build HTML document::

  $ docker run --rm /path/to/document:/docs sphinx-doc/html

Build EPUB document::

  $ docker run --rm /path/to/document:/docs sphinx-doc/epub

Build PDF document::

  $ docker run --rm /path/to/document:/docs sphinx-doc/epub

Tips
----

If you would like to install dependencies, use ``sphinx-doc/base`` as a base image::

  # in your Dockerfile
  FROM sphinx-doc/base

  WORKDIR /docs
  ADD requirements.txt
  RUN pip install -r requirements.txt
  CMD make html
