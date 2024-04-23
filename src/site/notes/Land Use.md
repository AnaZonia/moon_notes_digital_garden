---
{"dg-publish":true,"permalink":"/land-use/"}
---

Brian and Morgane's previous efforts using atmospherically corrected Landsat data did not work out. Training data was not useful across footprints - training worked well for one footprint at a time only. I believe these are the reasons:
- Only Landsat's 9 bands were input into random forest. Mapbiomas seems to improve on this issue by ==using 90 features, and training the data for the whole country all at once, for each year==.
- Data for annual plants was implemented regardless of stage in growing cycle, but that should be considered for classification as MapBiomas [[Land Use#Time Series\|does]]
- Rice and Citrus classes were classified using U-Net by MapBiomas

## Ongoing Plan of Action
- [ ] Get landsat for Panama in the correct time window
- [ ] Collect some sample points for the main crop types of the country (perennial such as banana, annual such as maize, coffee)
- [ ] Can U-Net help us do better land use classification in Panama?
- [ ] Can Samgeo help us augment the datapoints for training?
- [ ] How to define the feature space for classification in Panama?
- [ ] Besides multispectral, could it be an advantage to add SAR data?
- [ ] How does time series help us classify, and how would we implement that?
## How does MapBiomas do it?
Here I write a short summary of:
- [ATBD Collection 8 MapBiomas](https://brasil.mapbiomas.org/wp-content/uploads/sites/4/2023/09/ATBD-Collection-8-v1.1.docx.pdf)
	- [Agriculture and Forest Plantation - Appendix C8](https://brasil.mapbiomas.org/wp-content/uploads/sites/4/2023/09/Agriculture-and-Forest-Plantation-Appendix-C8-reviewed.pdf)
	- [Amazon - Appendix C8](https://brasil.mapbiomas.org/wp-content/uploads/sites/4/2023/08/Amazon-Appendix-ATBD-Collection-8.pdf)
- [ATBD MapBiomas Amazonia 4.0](https://s3.amazonaws.com/amazonia.mapbiomas.org/atbd/atbd%20general/ATBD_General_MapBiomas_Amazonia_4.0.pdf) (including all amazonian countries)
	- [Agricultura - Apéndice 4.0](https://s3.amazonaws.com/amazonia.mapbiomas.org/atbd/atbd%20transversales/Ap%C3%A9ndice_12_Agricultura_Colecci%C3%B3n_4.0.pdf)
	- 
[MapBiomas Brasil Github](https://github.com/mapbiomas-brazil) has the source code:
- JS - image classification and post-classification
- Python API - Map integration, post-classification, statistical analysis
- R - improve processing of large datasets, machine learning, data analysis and visualization.
[github](https://github.com/joaosiqueira/mapbiomas-chile-training)for training of mapbiomas chile data (js)

### MapBiomas Brasil
Using Surface Reflectance (SR) from Landsat Collection 2 (Tier 1) 

1. **Got landsat data in specific temporal windows** to optimize spectral contrast and better discriminate the LULC classes.
2. **Define feature spaces** for each year
	- Shadow masking + cloud cover less than or equal to 50%
		- Temporal Dark Outlier Mask (TDOM) algorithm(identifies cloud shadows as pixels that are both dark in the infrared bands and that are dark statistical outliers across the time series.)
		- [GEE median reducer](https://developers.google.com/earth-engine/guides/ic_reducing)- picks the median pixel value in each band over time
		- Band Quality Assessment (BQA)
		- Visually removed scenes that could affect results like haze, cloud, no data through a preview on earth engine
	- Defined a feature space with approx 90 features:
		- Median: median of the pixel values within the defined stack of images
		- Median_dry: median of the quartile of the lowest pixel NDVI values
		- Median_wet: median of the quartile of the highest pixel NDVI values
		- Amplitude: amplitude of variation of the index considering all the year's images
		- stdDev: stdDev of the pixel values within the defined stack of images
		- Min: the lower annual value of the pixels of each band

![](https://imgur.com/fW0m717.png)

 3. **Selected training samples** with LAPIG/UFG [Chave de Interpretação](https://chave.lapig.iesa.ufg.br/pt/) and then ran [data augmentation](https://www.datacamp.com/tutorial/complete-guide-data-augmentation)
	- *Amazon biome* -> Statistical analysis to define minimum number of samples for accuracy assessment:
		- 10k points for training (phase 1)
		- 10k points for accuracy assessment (phase 2)
		- 15k points for accuracy assessment (phase 3)
		Did feature selection in R using Landsat bands, spectral indices, and fractions from [Spectral Mixture Analysis (SMA)](https://www.cambridge.org/core/books/abs/hyperspectral-imaging-remote-sensing/spectral-mixture-analysis/AA9C2AF0CC6DDCF485E170DD4E70712C)
		Final variables were Green Vegetation (GV), Non-Photosynthetic Vegetation (NPV), Soil, Cloud, Green Vegetation Shade (GVS), Normalized Difference Fraction Index (NDFI), Shade and Canopy Shade Fraction (CSFI) using [Mean Decrease in Accuracy](https://stats.stackexchange.com/questions/197827/how-to-interpret-mean-decrease-in-accuracy-and-mean-decrease-gini-in-random-fore)in R randomForest. Additional samples obtained with segmentation technique SNIC. (Check out Samgeo)
	- *Other biomes* -> Randomly sampled from areas with LCLU classes that did not change across all years of Collection 7 (stable classes). When necessary, additional samples were collected.

4. **Yearly classification** done for each biome. Aquaculture, Mining, Irrigation, Rice, and Citrus had their areas of occurrence identified using the U-Net convolutional neural network classifier (CNN).
5. **Post-classification filters**
	- *Time-wise gap fill* -> fills out no-cloud pixels/gaps. Either replaces it with the last valid class, or the first valid class after the gap.
	- *Spatial filter* -> removes isolated pixels (connectedPixelCount function). A pixel that does not share connections to at least four identical neighbors is considered isolated and its value is replaced with the mode value of the surrounding. ==That means the minimum mapping unit is 5 pixels,== or about half a hectare.
	- *Temporal filter* -> Backward windows of 3, 4 or 5 years that show unrealistic transitions between land use classes. If the two years at the extremities of the time window are identical, but the central positions are not, then the central pixels are reclassified to match the class of the extremities. Also, given any 3 consecutive years, if the classifications of the first and last years are different from their neighbors, these values are replaced by the classification of its matching neighbors.
	- *Frequency filter* -> all natural class occurrences with less than a given percentage of temporal persistence (e.g. three or fewer years out of 38) are filtered out.
	- *Incidence filter* -> all pixels that changed more than eight times and are connected to less than six pixels are replaced by the mode value of that given pixel posiiton in the stack of years.
6. **Maps were integrated** following prevalence rules.
	- A temporal filter was applied on classes with less than three occurrences in the whole 38 year period
	- A spatial filter was applied to remove isolated classes with less than half a hectare
[TVI - Temporal Visual Inspection](https://github.com/lapig-ufg/tvi)
Global Accuracy
Allocation disagreement
Area disagreement

![](https://i.imgur.com/Y9v8VDD.png)


![](https://imgur.com/RU2OTOP.png)


![](https://imgur.com/tUX4UZg.png)


### Mapbiomas Amazonia 4.0

![](https://imgur.com/PmkHtb5.png)

![](https://imgur.com/bn3Iym5.png)

![](https://imgur.com/O6bdGWO.png)

![](https://i.imgur.com/S5doCrT.png)


### U-Net
[Working with U-net in R (github)](https://github.com/JonathanVSV/U-netR)
[Using the U‐net convolutional network to map forest types and disturbance in the Atlantic rainforest with very high resolution images (Wagner et al 2019)](https://zslpublications.onlinelibrary.wiley.com/doi/epdf/10.1002/rse2.111)

[Mapping tropical forest degradation with deep learning and Planet NICFI data - ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0034425723003498#bb0030)

There's a possibility that combining with SAR for the classification will be even better - but does that mean that using SAR as response will become redundant as far as the stats goes?
[Land Use Land Cover Classification with U-Net: Advantages of Combining Sentinel-1 and Sentinel-2 Imagery](https://www.mdpi.com/2072-4292/13/18/3600#)

![](https://www.mdpi.com/remotesensing/remotesensing-13-03600/article_deploy/html/images/remotesensing-13-03600-g002.png)



### Time Series
For mapping annual crops, the Landsat mosaics require images that cover the period from October to March

[F4 - Earth Engine Fundamentals and Applications - EEFA - Live Document - Google Docs](https://docs.google.com/document/d/11oo1TuvXyEvReoYLDeTcoh16rEN90I8Bf5qp0KxVu7U/edit) (page 109)

![](https://i.imgur.com/MBkDPwW.png)

[Comparing Two Methods of Leaf Area Index Estimation for Rice (Oryza sativa L.) Using In-Field Spectroradiometric Measurements and Multispectral Satellite Images](https://www.mdpi.com/2624-7402/5/2/60)

[Remote Sensing | Free Full-Text | Trend Change Detection in NDVI Time Series: Effects of Inter-Annual Variability and Methodology](https://www.mdpi.com/2072-4292/5/5/2113)

### Desmatamento/Vegetação Secundária

[Benchmark maps of 33 years of secondary forest age for Brazil (Silva Junior 2020)](https://www-nature-com.proxy3.library.mcgill.ca/articles/s41597-020-00600-4)
[github](https://github.com/celsohlsj/gee_brazil_sv)
This is the dataset used in [Heinrich et al 2021](https://www-nature-com.proxy3.library.mcgill.ca/articles/s41467-021-22050-1), and it seems to work better than Mapbiomas' land use transitions straight out of the box. I have seen isolated pixels in the dataset, which could be fixed with MapBiomas' spatial filter.
## Samgeo
*A Python package for segmenting geospatial data with the Segment Anything Model (SAM)* - Automatically generates masks
May help with the collection of training data?
[documentation](https://samgeo.gishub.org/)
[github](https://github.com/opengeos/segment-geospatial)
[paper](https://joss.theoj.org/papers/10.21105/joss.05663)

![](https://camo.githubusercontent.com/32f6f9e30c7f773b42e7c7d6c47a251b88e88723af456afd8016c26063966204/68747470733a2f2f692e696d6775722e636f6d2f4931496844677a2e676966)

Segmentation done in Amazon biome to get more samples:
![](https://i.imgur.com/dfpGWSa.png)

### Bayesian Updating of Land-cover Classifications
[Jeffrey Cardille - Bayesian Updating of Land-cover Classifications - YouTube](https://www.youtube.com/watch?v=KNeoSpIDVBk)

## Other efforts
[The Global 2000-2020 Land Cover and Land Use Change Dataset Derived From the Landsat Archive: First Results (Potapov 2022)](https://www.frontiersin.org/articles/10.3389/frsen.2022.856903/full) did a global analysis of multiple types of land use change, but did not go further than "cropland" class.

[CERES: IGBP Land Classification | Climate Data Guide (ucar.edu)](https://climatedataguide.ucar.edu/climate-data/ceres-igbp-land-classification)
There are issues with shrubland classification in Panama, they are often misclassified as secondary forests.

Another algorithm that flags deforestation events 
AVOCADO [Continuous monitoring of forest change dynamics with satellite time series (Decuyper 2022)](https://www.sciencedirect.com/science/article/pii/S0034425721005496?via%3Dihub)
- captures gradual change (unlike rgrowth, for example) 
- would be possible to incorporate logging for example 
- is less effective on dry tropical forest because NDMI of crops is quite similar to NDMI of the forest itself... so be careful with that. Regrowth was flagged accidentally. 
Some sociological factor studies only show the probability of permanence of forests depending on different sociological factors; forests may be allowed to regrow for 5-20 years before being cleared up again. This could just be a predictor for fallow period, but that’s gathered from remote sensing anyways, so it’s kind of useless for my study. 
The algorithm is calibrated with nearby mature forests.

[rgrowth - Tracking disturbance-regrowth dynamics (bendevries.ca)](http://bendevries.ca/rgrowth/)