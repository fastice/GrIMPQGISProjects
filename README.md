# GIMPQGISProjects
This repository contains automatically generated QGIS project files that access and display Greenland Ice Mapping Project (GIMP) data archived at NSIDC.

See the notebook https://github.com/fastice/GIMPNotebooks/blob/master/NSIDCLoginNotebook.ipynb for directions on setting up the authentication for GDAL and QGIS to be able to read the remote data. _**If the authentication procedures in the this notebook are not followed, the data will not be loaded**_

## General Notes
### Performance Issues

The data are stored as cloud optimized GeoTiffs and users can navigate an image mosaic relatively quickly. In some cases a network error may occur, in which case usually recentering the data will force a new read.

Performance is best when only one or a few active images are checked. Checking all of the images at once in a project with several hundred images can cause network errors as the program will try access all of the images simultaneously.

### Updates
The projects contain links to specific product versions. As products are updated, the links may no longer work or point to old data. Check back here for updated project files. Alternatively, in April 2021, Jupyter Notebooks will be distributed (https://github.com/fastice/GIMPNotebooks) that can regenerate or customize the QGIS projects.

### QGIS Version
These projects have been tested successfully with QGIS V3.16 and 3.18. It is know to have failed on QGIS 3.10.

## QGISImageTest.qgs
This is a small project with only 4 images that is good for debugging the authentication process since it should fail more quickly if the authentication is not working properly. It should load in under a minute even on a slow connection. 

## QGISImageMosaics.qgs
This project contains all (309) of Sentinel1 GIMP image mosaics at 25-m resolution (https://nsidc.org/data/nsidc-0723) through January 2015 through mid-December 2020. Depending on network speed, it may take anywhere from under a minute to as many as 10 minutes to load. Once loaded, it provides reasonably fast image browsing (see General Notes). It loads in under a minute on an Ubuntu machine on a university network and about 6 minutes on Mac with a 75Mbs home network connection.
