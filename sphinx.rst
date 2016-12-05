Sphinx documentation for Python skills and notes
================================================

configuration:
--------------

Tips for getting Sphinx to read versioneer for versions - do
as following::

  # The short X.Y version.
  from wafari import __version__
  version = __version__
  # The full version, including alpha/beta/rc tags.
  release = __version__

