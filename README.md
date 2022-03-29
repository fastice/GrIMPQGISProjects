# GrIMPQGISProjects [![Binder](https://gesis.mybinder.org/badge_logo.svg)](https://gesis.mybinder.org/v2/gh/fastice/GrIMPQGISProjects/HEAD?urlpath=lab)
This repository contains automatically generated QGIS project files that access and display Greenland Ice Mapping Project (GrIMP) data archived at NSIDC.

See the notebook https://github.com/fastice/GrIMPNotebooks/blob/master/NSIDCLoginNotebook.ipynb for directions on setting up the authentication for GDAL and QGIS to be able to read the remote data. _**If the authentication procedures in the this notebook are not followed, the data will not be loaded**_

## What's Included

### GrIMP-Products.qgs and Related Layer Definition Files

This repository contains *QGIS* project, `GrIMP-Products.qgs`, with many of the GrIMP velocity and image products. 

Due to the large number of products, this file may take several minutes to load. 

If only a limited set of products is needed, it is better to open a new *QGIS* project and use **Layer->Add from Layer Definition File...** with one or more of the following [Layer definition](https://getspatial.com/gisblog/tip-of-the-day-create-layer-definition-files-for-reuse-and-consistency/) files:
* GrIMP-Products.Annual.qlr: All of the Sentinel-era annual velocity products ([NSIDC-0725](https://nsidc.org/data/nsidc-0725));
* GrIMP-Products.Quarterly.qlr: All of the Sentinel-era quarterly velocity products ([NSIDC-0727](https://nsidc.org/data/nsidc-0727));
* GrIMP-Products.Monthly.qlr: All of the Sentinel-era monthly velocity products ([NSIDC-0731](https://nsidc.org/data/nsidc-0731));
* GrIMP-Products.s1cyle.qlr: All of the Sentinel-era 6/12-day (1 Sentinel 1 cycle) velocity products ([NSIDC-0766](https://nsidc.org/data/nsidc-0766));
* GrIMP-Products.Imagery.qlr: All of the Sentinel-era 6/12 SAR image, sigma0, and gamma0 products ([NSIDC-0723](https://nsidc.org/data/nsidc-0723));
* GrIMP-Products.Termini.qlr: All of the terminus position shape file products ([NSIDC-0642](https://nsidc.org/data/nsidc-0642));

##$ QGISImageTest.qgs
This is a small project with only 4 images that is good for debugging the authentication process since it should fail more quickly if the authentication is not working properly. It should load in under a minute even on a slow connection. 

### Performance Issues

The data are stored as cloud optimized GeoTiffs and users can navigate an image mosaic relatively quickly. In some cases a network error may occur, in which case usually recentering the data will force a new read.

Due to network limitations, problems can occur when too many images are selected as visible (checked) at once so that QGIS tries to render them all simultaneously. This situation can cause network errors, especially if the number of NDIDC connections (15) is exceeded. To avoid such problems, the automatically generated *QGIS* projects have most of the layers unchecked at first. As best practice, avoid **Check All and Its Children** in *QGIS* unless there only a handful of products. Since generally only one or a few products can be viewed at once, navigate to the product of interest, check it to view it, then uncheck when moving to a different product (a few images can viewed simulaneously - for example to flicker pairs of images).

**When network errors occur, an image may not render properly. If this occurs, uncheck excess images, then zoom in and out, which will trigger a reload that usually will re-render the image correctly (the error flag next to the product may persist even after the image loads correctly).**

Assuming there are no authentication errors, then network errors usually are caused by the number of network accesses exceeding the number that NSIDC allows.  
**In QGIS this problem can largely be eliminated by setting** `Preferences->Rendering->Max Cores to Use` **to <=2.**

### Updates
The projects contain links to specific product versions. As products are updated, the links may no longer work or point to old data. Check back here for updated project files. 

Alternatively, the [*buildGrIMPQGIS.ipynb*](https://github.com/fastice/GrIMPQGISProjects/blob/master/buildGrIMPQGIS.ipynb) notebook included in this repository can update all of the *QGIS* files.

### QGIS Version
These projects have been tested successfully with QGIS V3.16 and 3.18. It is know to have failed on QGIS 3.10.




