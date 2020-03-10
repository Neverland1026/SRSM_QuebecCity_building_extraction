# Quebec City building footprints extracted by SRSM 
Delineated building footprints in Quebec City (Canada), resulted by the SRSM method (Super-Resolution-based Snake Model). The dataset covers a total area is **656 square kilometers, with more than 200 thousand buildings**.

These building footprints are the results of our paper **Super-Resolution-based Snake Model --- An Unsupervised Method for Large-Scale Building Extraction using Airborne LiDAR Data and Optical Image**.

Authors: [Thanh Huy Nguyen](mailto:nthuy190991@gmail.com), Sylvie Daniel, Didier Guériot, Christophe Sintès, and Jean-Marc Le Caillec.

## Download links
[SRSM results](https://ulavaldti-my.sharepoint.com/:u:/g/personal/thngu52_ulaval_ca/EcsaXqiItQFAqF9HxTBc7fQB0bBIndcbUuF3oPzHFFUa0A?e=m4UCCf) (approx. 210 MB).

(in case that the link expires, please open an issue on the Issues tracker or [email me](mailto:nthuy190991@gmail.com))


## Citation
If you use these footprints, please cite our paper:
```
  {bibtex}
```


## Ground Truth (GT) building footprints
The GT footprints of Quebec City are provided by the City of Quebec and updated regularly.
They are used as a reference for evaluating the SRSM results. It is worth-nothing that we don't use them as training data  or use any training data for that matter (hence **unsupervised**).

We would like to thank the City of Quebec for providing and maintaining this dataset.
To download these GT footprints, please refer to their [website](https://www.donneesquebec.ca/recherche/fr/dataset/empreintes-des-batiments).


## Comparison with Microsoft open Canada building footprints
We compared the SRSM results with the open Canada building footprint datasets carried out by Microsoft Bing maps team (see their [blog entry](https://blogs.bing.com/maps/2019-03/microsoft-releases-12-million-canadian-building-footprints-as-open-data) and [Github](https://github.com/microsoft/CanadianBuildingFootprints)). 

### Accuracy metrics
|  | Completeness | Correctness | Quality (IoU) | Notes |
| --- | --- | --- | --- | --- |
| Microsoft | 77.42 % | 87.61 % | 69.77 % | Using ResNet34 as the DNN foundation |
| SRSM | 82.32 % | 72.02 % | 62.37 % | Unsupervised method |
    
    
## Some examples

![SRSM results overlapped on z-image (tile 4190)](https://github.com/nthuy190991/SRSM_QuebecCity_building_extraction/blob/master/examples/4190_on_zimg.png)
![SRSM results overlapped on orthoimage (tile 4190)](https://github.com/nthuy190991/SRSM_QuebecCity_building_extraction/blob/master/examples/4190_on_opt_img.png)

## What is the coordinate reference system?
[EPSG: 2949](https://epsg.io/2949) a.k.a. NAD83(CSRS) / MTM zone 7


## Notes:
- For the sake of computational cost, we carried out the SRSM separately on tile (each covers a 1km x 1km area).
- The tile-based results were then combined in QGIS.
- A version of the polygonized footprints by applying the ERSI ArcMap built-in polygonization [algorithm](https://arxiv.org/abs/1504.06584) can be found [here](). But only the raw results from SRSM are used in the publication.


## Conversion ERSI Shapefile into GeoJSON
In order to convert [ERSI Shapefile](https://www.esri.com/library/whitepapers/pdfs/shapefile.pdf) into [GeoJSON](https://geojson.org) or vice versa, please use the Python script 'geojson_to_shp.py' (credits to Dr. Eric Janssens-Coron from CRDIG, Université Laval). Prerequisite: [Geopandas](https://geopandas.org).


## Questions/Discussions
For any other questions/issues, please open an issue on the Issues tracker.
