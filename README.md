[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1227836.svg)](https://doi.org/10.5281/zenodo.1227836)
![GitHub](https://img.shields.io/github/license/felixriese/hyperspectral-soilmoisture-dataset)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/felixriese/hyperspectral-soilmoisture-dataset/master?filepath=example.ipynb)

# Hyperspectral benchmark dataset on soil moisture

Hyperspectral and soil-moisture data from a lysimeter field campaign based on a soil sample. Karlsruhe (Germany), 2017.

**Abbreviation:** KarLy (Karlsruhe Lysimeter)

**License:** [CC BY 4.0](LICENSE)

**Authors:**

- [Felix M. Riese, M.Sc.](mailto:github@felixriese.de)
- [Dr. rer.nat. Sina Keller](mailto:sina.keller@kit.edu)

**Affiliation:** Karlsruhe Institute of Technology, Institute of Photogrammetry and Remote Sensing ([Link](https://ipf.kit.edu))

**Citation:** see [Citation](#citation) and [bibliography.bib](bibliography.bib).

**Example script:** [example.ipynb](example.ipynb)


## Description

This dataset was measured in a five-day field campaign in May 2017 in Karlsruhe, Germany. An undisturbed soil sample is the centerpiece of the measurement setup. The soil sample consists of bare soil without any vegetation and was taken in the area near Waldbronn, Germany.

The following sensors were deployed:

- Cubert UHD 285 **hyperspectral** snapshot camera recording 50 by 50 images with 125 spectral bands ranging from 450 nm to 950 nm and a spectral resolution of 4 nm.
- TRIME-PICO time-domain reflectometry (TDR) sensor in a depth of 2 cm measuring the **soil moisture** in percent.

The raw sensor data was processed with the [Hyperspectral Processing Scripts for the HydReSGeo Dataset](https://github.com/felixriese/hyperspectral-processing) beforehand.

## Variables

- **datetime:** date and time (CEST) of the measurement
- **soil_moisture:** soil moisture in %
- **soil_temperature:** soil temperature in °C
- **454, 458, … 946, 950:** hyperspectral bands in nm


## Citation

The bibtex file including both references is available in [bibliography.bib](bibliography.bib).

**Paper**

Felix M. Riese and Sina Keller, “Introducing a Framework of Self-Organizing Maps for Regression of Soil Moisture with Hyperspectral Data,” in *IGARSS 2018 - 2018 IEEE International Geoscience and Remote Sensing Symposium*, Valencia, Spain, 2018, pp. 6151-6154. ([Link](https://doi.org/10.1109/IGARSS.2018.8517812))

```
@inproceedings{riese2018introducing,
    author = {Riese, Felix~M. and Keller, Sina},
    title = {{Introducing a Framework of Self-Organizing Maps for Regression of Soil Moisture with Hyperspectral Data}},
    booktitle = {IGARSS 2018 - 2018 IEEE International Geoscience and Remote Sensing Symposium},
    year = {2018},
    month = {July},
    address = {Valencia, Spain},
    doi = {10.1109/IGARSS.2018.8517812},
    ISSN = {2153-7003},
    pages = {6151--6154},
}
```

**Code**

Felix M. Riese and Sina Keller, "Hyperspectral benchmark dataset on soil moisture", Dataset, Zenodo, 2018. ([Link](http://doi.org/10.5281/zenodo.1227836))

```
@misc{riesekeller2018,
    author = {Riese, Felix~M. and Keller, Sina},
    title = {Hyperspectral benchmark dataset on soil moisture},
    year = {2018},
    DOI = {10.5281/zenodo.1227837},
    publisher = {Zenodo},
    howpublished = {\href{https://doi.org/10.5281/zenodo.1227837}{doi.org/10.5281/zenodo.1227837}}
}
```

