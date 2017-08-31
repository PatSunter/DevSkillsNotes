

Colors:
-------

Get color code for a matplotlib named color::

  import matplotlib.colors as mcolors
  In [28]: mcolors.cnames['grey']
  Out[28]: u'#808080'

https://stackoverflow.com/questions/22408237/named-colors-in-matplotlib

Convert between hex, rgb:

Pre matplotlib 2.0::

  mcolors.hex2color()
  mcolors.rgb2hex()
