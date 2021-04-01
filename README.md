# GIMPQGISProjects
This repository contains automatically generated QGIS project files that access and display Greenland Ice Mapping Project (GIMP) data archived at NSIDC.

See the notebook https://github.com/fastice/GIMPNotebooks/blob/master/NSIDCLoginNotebook.ipynb for directions on setting up the authentication for GDAL and QGIS to be able to read the remote data.

## General Notes

The data are stored as cloud optimized GeoTiffs and users can navigate an image mosaic relatively quickly. In some cases a network error may occur, in which case usually recentering the data will force a new read.

Performance is best when only one or a few active images are checked. Checking all of the images at once in a project with several hundred images can cause network errors as the program will try access all of the images simultaneously.

## QGISImageTest.qgs
This is a small project with only 4 images that is good for debugging the authentication process since it should fail more quickly if the authentication is not working properly.
