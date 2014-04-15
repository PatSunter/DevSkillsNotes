QGIS Skills and notes
=====================

Note/warning :- As of writing (Apr 2014), most of these are oriented to QGIS "1.8.0-trunk" on the Mac, using the packaged version provided by KyngChaos - which is distributed as a "System Framework" and provides other tools like GDAL etc.

However from a few places I've looked at, this doesn't seem to correspond exactly with the 1.8 release.

Some time soon I should update to 2.0

Ways to get a particular selected line, e.g. a tram route, to show above other lines in the same layer.
-------------------------------------------------------------------------------------------------------

In QGIS 1.8 on Mac its quite hard to clearly select a particular symbol and show it clearly, just with the select tool.

General References:
 * http://gis.stackexchange.com/questions/86859/how-to-edit-overlapping-lines/86974#86974
 * http://anitagraser.com/2012/06/03/sld-support-and-other-qgis1-8-style-features/

The first of these has a couple of suggestions I tried.

1) - add a new 'layer' to QGIS, using the same shapefile, then run Queries/Filters on it
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

This worked quite well. E.g. here is what you do:
 # Use the "new vector layer" button, and add a new version of exactly the same layer.
 # Drag it to just above the old layer in the rendering tab, and rename it appropriately (e.g. an '(Editing)' suffix)
 # Right click the newly added layer, and choose style so it appears appropriately (e.g. a different color to other one.)
 # Then, right-click on new layer again, and choose 'Query ...'
 # Now you just have to query by appropriate property e.g. "name = '8'" for tram route 8.
 # Voila! QGIS will now show just the feature you're interested in.

2) Use categorised or rule-based symbols, then use "symbol layers" to force rendering order
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

This comes from the last answer on the StackExchange site above.

In this approach, you change the Style from 'simple' to either 'categorised' or 'rule-based'.
Then, use the "Symbol Layers" advanced option to change rendering order so the desired line always shows on top.

The 'rule-based' approach would be better for this purpose, but I found that the Symbol Layers box doesn't seem to work in the 1.8-Mac version of QGIS I have sadly. So one can 'hack' with the Categorised option, but its pretty awkward.
From the second link above, it looks like both stability and user-interface of this rule-based stuff improves quite a bit in the final 1.8 release, and 2.0 of QGIS.



 
symbol to clearly 
