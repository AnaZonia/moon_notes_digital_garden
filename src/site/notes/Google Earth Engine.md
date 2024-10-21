---
{"dg-publish":true,"permalink":"/google-earth-engine/"}
---

- Needed to use earthengine authenticate --auth_mode=notebook to install. Thanks [SpatialThoughts!](https://courses.spatialthoughts.com/install-gee-python-api.html)
- [community datasets](https://github.com/samapriya/awesome-gee-community-datasets)

To install GEE:
```
conda install -c conda-forge earthengine-api
conda install -c conda-forge geemap

sudo apt-get install apt-transport-https ca-certificates gnupg curl sudo
y
```

The information of the saved credentials are in
~/.config/earthengine/credentials
^this is what ee.Authenticate() reaches out to

These credentials can be changed with gcloud init (check SpatialThoughts tutorial above)

### Pros
- **Easy handling and exporting** of very large data
- **Easy immediate visualization** of your data on a map
### Cons
- **Cannot export large files as CSV** - much better at exporting and importing geotiff files
- **Learning curve is reasonably steep** - ImageCollections and Features are not as intuitive as rasters and sf files in R for example.
- **Hard to examine FeatureCollections** - It may be impossible to even print out summaries on the information of very large FeatureCollections.
- **Hard to tell what changes are being done to the files** - getInfo() will return the original value of the file, before processing. So if you clip an image, sometimes the initial size will be returned rather than the clipped size. This can make it hard to monitor progress.
- There is a difference between **client-side and server-side** functions, and these can sometimes run into issues. Trying to pass a client-side function into a server-side function will not work!

### Computational Power
- [EECU - Earth Engine Compute Unit](https://developers.google.com/earth-engine/cloud/api_monitoring#:~:text=An%20EECU%20is%20an%20Earth,online%20%2C%20batch%20%2C%20highvolume%20%5D.) is the measure of power. Workload tags can be set to monitor the performance of a task as it's performed.
- The [high volume endpoint](https://developers.google.com/earth-engine/cloud/highvolume) should be used if making many small requests, like exporting many little tiles from a very large image as done [here](https://gorelick.medium.com/fast-er-downloads-a2abd512aa26).

### File types

Image <- one Scene
- ImageCollection
- the usage of imagecollections is different from that of Image objects, unlike raster vs rasterstack which we operate on pretty much the same way.
- What is the difference between an image collection and an image with multiple bands?
Feature <- polygons, points, lines
- FeatureCollection
Every image is a feature, but not every feature is an image.

## Javascript
### Cons
- It is not recommended to run for loops in the GEE interface
- cannot run deep learning
- an API allows to overlay GEE data with my own other datasets
### Pros
- A lot of resources come in javascript
- The js in the code editor is easy to learn
- Visualization works better and faster


[Coding Best Practices  |  Google Earth Engine  |  Google for Developers](https://developers.google.com/earth-engine/guides/best_practices)

[Cloud-Based Remote Sensing with Google Earth Engine: Fundamentals and Applications](https://www.eefabook.org/go-to-the-book.html) Chapters 1-5
	- [​Chapter Summary Videos (eefabook.org)](https://www.eefabook.org/videos.html)

[Land use and Land cover classification using Random forest machine learning in Google Earth Engine - YouTube](https://www.youtube.com/watch?v=Z-DPRCWWaqg)

[Analyzing the Amazon Deforestation with ML and Google Earth – Part 1 | AI FOR GOOD DISCOVERY - YouTube](https://www.youtube.com/watch?v=C4IU21rjO3k)

## Python API
[mod4\_1\_time\_series\_charts.ipynb - Colaboratory](https://colab.research.google.com/github/worldbank/OpenNightLights/blob/master/onl/tutorials/mod4_1_time_series_charts.ipynb#scrollTo=dBUTbuWMH7I6)
### geemap
- [geemap](https://geemap.org/)
- [GitHub - google/earthengine-community at 6801dd2d05d1cd6a44d8c86131accda657c253ce](https://github.com/google/earthengine-community/tree/6801dd2d05d1cd6a44d8c86131accda657c253ce)
- [Earth Engine Python API](https://developers.google.com/earth-engine/tutorials/community/intro-to-python-api)
- [GitHub - giswqs/earthengine-py-examples: A collection of 300+ examples for using Earth Engine and the geemap Python package](https://github.com/giswqs/earthengine-py-examples/tree/master)
- [04 using basemaps - GEE Courses](https://courses.geemap.org/geemap_intro/04_using_basemaps/#introduction)
## rgee
- [Using Google Earth Engine with R](https://www.css.cornell.edu/faculty/dgr2/_static/files/R_html/ex_rgee.html)
- [Introduction to Google Earth Engine with R language - YouTube](https://www.youtube.com/watch?v=SHXuIpjU3YE)
[rgee examples](https://csaybar.github.io/rgee-examples/)
- [rgee documentation](https://r-spatial.github.io/rgee/)
[Best Practices](https://r-spatial.github.io/rgee/articles/rgee03.html)
[Earth Engine with R book](https://r-earthengine.com/rgeebook/)
[Installing RGEE to use Google Earth Engine inside R - YouTube](https://www.youtube.com/watch?v=1-k6wNL2hlo)



## Resources
[GIS Stack Exchange](https://gis.stackexchange.com/questions/tagged/google-earth-engine)
[Google Earth Engine Developers Forum](https://groups.google.com/g/google-earth-engine-developers)
[JavaScript and Python Guides](https://developers.google.com/earth-engine/guides)